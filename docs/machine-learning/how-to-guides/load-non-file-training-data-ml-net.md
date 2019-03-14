---
title: 'Trainieren eines Machine Learning-Modells mithilfe von Daten, die nicht in einer Textdatei enthalten sind: ML.NET'
description: Erfahren Sie, wie Sie ML.NET verwenden, um als Teil der Vorhersagepipeline Trainingsdaten, die nicht in einer Datei gespeichert sind, für Machine Learning-Modelle zu laden.
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 27b327a63cb55b7fce0f4ff7facd3ee7c4a1c85c
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678614"
---
# <a name="train-a-machine-learning-model-with-data-thats-not-in-a-text-file---mlnet"></a>Trainieren eines Machine Learning-Modells mithilfe von Daten, die nicht in einer Textdatei enthalten sind: ML.NET

> [!NOTE]
> Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden. Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Diese Anleitung und das dazugehörte Beispiel verwenden derzeit **ML.NET Version 0.10**. Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

Häufig wird das `TextLoader`-Element verwendet, um die Trainingsdaten aus einer Datei zu lesen. Dabei handelt es sich um den Anwendungsfall, der in der Regel für ML.NET veranschaulicht wird.
In Trainingsszenarios in Echtzeit können sich die Daten allerdings auch an anderen Orten befinden. Z. B.:

* Sie können in SQL Tabellen gespeichert sein.
* Sie können aus Protokolldateien extrahiert worden sein.
* Sie können spontan erstellt worden sein.

Verwenden Sie [Schemaverständnis](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md), um ein bereits vorhandenes `IEnumerable`-Objekt für C# als `DataView` in ML.NET zu übertragen.

Anhand dieses Beispiels erfahren Sie, wie Sie ein Vorhersagemodell für Änderungen durch die Kunden erstellen und die folgenden Features aus Ihrem Produktionssystem extrahieren:

* Kunden-ID (wird vom Modell ignoriert)
* Angabe, ob der Kunde eine Änderung vorgenommen hat (die Zielbezeichnung)
* Die demografische Kategorie (eine Zeichenfolge wie „junge Erwachsene“)
* Die Anzahl der Besuche in den letzten 5 Tagen.

```csharp
private class CustomerChurnInfo
{
    public string CustomerID { get; set; }
    public bool HasChurned { get; set; }
    public string DemographicCategory { get; set; }
    // Visits during last 5 days, latest to newest.
    [VectorType(5)]
    public float[] LastVisits { get; set; }
}
```

Laden Sie diese Daten in das `DataView`, und trainieren Sie das Modell mithilfe des folgenden Codes:

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging,
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// Let's assume that 'GetChurnData()' fetches and returns the training data from somewhere.
IEnumerable<CustomerChurnInfo> churnData = GetChurnInfo();

// Turn the data into the ML.NET data view.
// We can use CreateDataView or CreateStreamingDataView, depending on whether 'churnData' is an IList,
// or merely an IEnumerable.
var trainData = mlContext.Data.ReadFromEnumerable(churnData);

// Build the learning pipeline.
// In our case, we will one-hot encode the demographic category, and concatenate that with the number of visits.
// We apply our FastTree binary classifier to predict the 'HasChurned' label.

var pipeline = mlContext.Transforms.Categorical.OneHotEncoding("DemographicCategory")
    .Append(mlContext.Transforms.Concatenate("Features", "DemographicCategory", "LastVisits"))
    .Append(mlContext.BinaryClassification.Trainers.FastTree("HasChurned", "Features", numTrees: 20));

var model = pipeline.Fit(trainData);
```
