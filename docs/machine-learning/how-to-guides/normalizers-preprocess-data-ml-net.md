---
title: 'Vorverarbeiten von Trainingsdaten mit Normalisierungsfunktionen zur Nutzung in der Datenverarbeitung: ML.NET'
description: Erfahren Sie, wie Sie Normalisierungsfunktionen verwenden, um Trainingsdaten für die Modellerstellung für maschinelles Lernen vorzuverarbeiten.
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 2d18f7c19a51fd929ac6efb7f600cb1ac2733de8
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57676602"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a>Vorverarbeiten von Trainingsdaten mit Normalisierungsfunktionen zur Nutzung in der Datenverarbeitung: ML.NET

> [!NOTE]
> Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden. Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Diese Anleitung und das dazugehörte Beispiel verwenden derzeit **ML.NET Version 0.10**. Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

ML.NET bietet eine Reihe von [parametrischen und nicht parametrischen Algorithmen](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).

Es ist **nicht** so entscheidend, welche Normalisierungsfunktion Sie wählen. Entscheidender ist, dass Sie überhaupt eine Normalisierungsfunktion **verwenden**, wenn Sie lineare oder andere parametrische Modelle trainieren.

Beziehen Sie die Normalisierungsfunktion immer direkt in die ML.NET-Lernpipeline mit ein, um Folgendes zu erreichen:

- Die Lernpipeline wird nur auf Basis der Trainingsdaten trainiert und nicht auf Basis Ihrer Testdaten.
- Sie wird korrekt auf alle eingehenden Daten angewendet, ohne dass eine zusätzliche Vorverarbeitung bei der Vorhersage nötig ist.

Hier finden Sie einen Codeausschnitt, in dem die Normalisierung in Lernpipelines dargestellt ist. Hierfür wird vom Iris-Dataset ausgegangen:

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
        // The four features of the Iris dataset will be grouped together as one Features column.
        new TextLoader.Column("Features",DataKind.R4,0,3),
        // Label: kind of iris.
        new TextLoader.Column("Label",DataKind.TX,4)
    },
    // Default separator is tab, but the dataset has comma.
    separatorChar: ',',
    // First line of the file is a header, not a data row.
    hasHeader: true
);

// Read the training data.
var trainData = reader.Read(dataPath);

// Apply all kinds of standard ML.NET normalization to the raw features.
var pipeline =
    mlContext.Transforms.Normalize(
            new NormalizingEstimator.MinMaxColumn(inputColumnName:"Features", outputColumnName:"MinMaxNormalized", fixZero: true),
            new NormalizingEstimator.MeanVarColumn(inputColumnName: "Features", outputColumnName: "MeanVarNormalized", fixZero: true),
            new NormalizingEstimator.BinningColumn(inputColumnName: "Features", outputColumnName: "BinNormalized", numBins: 256));

// Let's train our pipeline of normalizers, and then apply it to the same data.
var normalizedData = pipeline.Fit(trainData).Transform(trainData);

// Inspect one column of the resulting dataset.
var meanVarValues = normalizedData.GetColumn<float[]>(mlContext, "MeanVarNormalized").ToArray();
```
