---
title: Verwenden von ML.NET in einem Standpunktanalyse-Szenario mit binärer Klassifizierung
description: Erfahren Sie, wie Sie ML.NET in einem Szenario mit binärer Klassifizierung verwenden, um zu erfahren, wie Sie die Standpunktvorhersage verwenden, um die geeignete Aktion auszuführen.
ms.date: 02/15/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 9afdf1d8369e71f9614ebc2bf327e98d31b988ff
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2019
ms.locfileid: "56748387"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="fbeed-103">Tutorial: Verwenden von ML.NET in einem Standpunktanalyse-Szenario mit binärer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="fbeed-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

> [!NOTE]
> <span data-ttu-id="fbeed-104">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="fbeed-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="fbeed-105">Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="fbeed-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="fbeed-106">Dieses Beispieltutorial veranschaulicht das Verwenden von ML.NET zum Erstellen eines Standpunktklassifizierers über eine .NET Core-Konsolenanwendung mithilfe von C# in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="fbeed-106">This sample tutorial illustrates using ML.NET to create a sentiment classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="fbeed-107">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="fbeed-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="fbeed-108">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="fbeed-108">Understand the problem</span></span>
> * <span data-ttu-id="fbeed-109">Auswählen des entsprechenden Machine Learning-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="fbeed-109">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="fbeed-110">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="fbeed-110">Prepare your data</span></span>
> * <span data-ttu-id="fbeed-111">Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="fbeed-111">Transform the data</span></span>
> * <span data-ttu-id="fbeed-112">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="fbeed-112">Train the model</span></span>
> * <span data-ttu-id="fbeed-113">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="fbeed-113">Evaluate the model</span></span>
> * <span data-ttu-id="fbeed-114">Vorhersagen treffen mit dem trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="fbeed-114">Predict with the trained model</span></span>
> * <span data-ttu-id="fbeed-115">Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen</span><span class="sxs-lookup"><span data-stu-id="fbeed-115">Deploy and Predict with a loaded model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="fbeed-116">Übersicht über das Standpunktanalyse-Beispiel</span><span class="sxs-lookup"><span data-stu-id="fbeed-116">Sentiment analysis sample overview</span></span>

<span data-ttu-id="fbeed-117">Das Beispiel ist eine Konsolen-App, die ML.NET verwendet, um ein Modell zu trainieren, das den Standpunkt als positiv oder negativ klassifiziert und vorhersagt.</span><span class="sxs-lookup"><span data-stu-id="fbeed-117">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="fbeed-118">Sie wertet das Modell auch mit einem zweiten Dataset für die Qualitätsanalyse aus.</span><span class="sxs-lookup"><span data-stu-id="fbeed-118">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="fbeed-119">Die Standpunktdatasets stammen aus dem Projekt WikiDetox.</span><span class="sxs-lookup"><span data-stu-id="fbeed-119">The sentiment datasets are from the WikiDetox project.</span></span>

<span data-ttu-id="fbeed-120">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="fbeed-120">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fbeed-121">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="fbeed-121">Prerequisites</span></span>

* <span data-ttu-id="fbeed-122">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="fbeed-122">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="fbeed-123">Die [tabstoppgetrennte Wikipedia-Detox-Zeilendatendatei (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span><span class="sxs-lookup"><span data-stu-id="fbeed-123">The [Wikipedia detox line data tab separated file (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span>
* <span data-ttu-id="fbeed-124">Die [tabstoppgetrennte Wikipedia-Detox-Zeilentestdatei (wikiPedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span><span class="sxs-lookup"><span data-stu-id="fbeed-124">The [Wikipedia detox line test tab separated file (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="fbeed-125">Machine Learning-Workflow</span><span class="sxs-lookup"><span data-stu-id="fbeed-125">Machine learning workflow</span></span>

<span data-ttu-id="fbeed-126">Dieses Tutorial folgt einem Machine Learning-Workflow, der den geordneten Ablauf des Prozesses ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="fbeed-126">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="fbeed-127">Die Workflowphasen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fbeed-127">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="fbeed-128">**Verstehen des Problems**</span><span class="sxs-lookup"><span data-stu-id="fbeed-128">**Understand the problem**</span></span>
2. <span data-ttu-id="fbeed-129">**Vorbereiten Ihrer Daten**</span><span class="sxs-lookup"><span data-stu-id="fbeed-129">**Prepare your data**</span></span>
   * <span data-ttu-id="fbeed-130">**Laden der Daten**</span><span class="sxs-lookup"><span data-stu-id="fbeed-130">**Load the data**</span></span>
   * <span data-ttu-id="fbeed-131">**Extrahieren von Funktionen (Transformieren von Daten)**</span><span class="sxs-lookup"><span data-stu-id="fbeed-131">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="fbeed-132">**Erstellen und trainieren**</span><span class="sxs-lookup"><span data-stu-id="fbeed-132">**Build and train**</span></span> 
   * <span data-ttu-id="fbeed-133">**Trainieren des Modells**</span><span class="sxs-lookup"><span data-stu-id="fbeed-133">**Train the model**</span></span>
   * <span data-ttu-id="fbeed-134">**Evaluieren des Modells**</span><span class="sxs-lookup"><span data-stu-id="fbeed-134">**Evaluate the model**</span></span>
4. <span data-ttu-id="fbeed-135">**Bereitstellen des Modells**</span><span class="sxs-lookup"><span data-stu-id="fbeed-135">**Deploy Model**</span></span>
   * <span data-ttu-id="fbeed-136">**Vorhersagen treffen mit dem Modell**</span><span class="sxs-lookup"><span data-stu-id="fbeed-136">**Use the Model to predict**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="fbeed-137">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="fbeed-137">Understand the problem</span></span>

<span data-ttu-id="fbeed-138">Sie müssen das Problem zuerst verstehen, damit Sie es in Teile aufschlüsseln können, die das Erstellen und Trainieren des Modells erleichtern.</span><span class="sxs-lookup"><span data-stu-id="fbeed-138">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="fbeed-139">Das Aufschlüsseln des Problems ermöglicht es Ihnen, die Ergebnisse vorherzusagen und auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="fbeed-139">Breaking the problem down allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="fbeed-140">Das Problem besteht bei diesem Tutorial darin, aus den auf der Website eingehenden Kommentaren den Standpunkt zu ermitteln, um die geeignete Aktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fbeed-140">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="fbeed-141">Sie können das Problem nach dem Standpunkttext und dem Standpunktwert für die Daten aufschlüsseln, mit denen Sie das Modell trainieren möchten, und einem vorhergesagten Standpunktwert, den Sie auswerten und dann praktisch verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fbeed-141">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="fbeed-142">Sie müssen dann den Standpunkt **bestimmen**, was Ihnen die Auswahl der Machine Learning-Aufgabe erleichtert.</span><span class="sxs-lookup"><span data-stu-id="fbeed-142">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="fbeed-143">Auswählen des entsprechenden Machine Learning-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="fbeed-143">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="fbeed-144">Von diesem Problem kennen Sie die folgenden Fakten:</span><span class="sxs-lookup"><span data-stu-id="fbeed-144">With this problem, you know the following facts:</span></span>

<span data-ttu-id="fbeed-145">Trainingsdaten: Websitekommentare können schädlich (1) oder unschädlich (0) sein (**Standpunkt**).</span><span class="sxs-lookup"><span data-stu-id="fbeed-145">Training data: website comments can be toxic (1) or not toxic (0) (**sentiment**).</span></span>
<span data-ttu-id="fbeed-146">Sagen Sie den **Standpunkt** eines neuen Websitekommentars voraus, schädlich oder unschädlich, wie in den folgenden Beispielen:</span><span class="sxs-lookup"><span data-stu-id="fbeed-146">Predict the **sentiment** of a new website comment, either toxic or not toxic, such as in the following examples:</span></span>

* <span data-ttu-id="fbeed-147">Bitte schreiben Sie keinen Unsinn in Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="fbeed-147">Please refrain from adding nonsense to Wikipedia.</span></span>
* <span data-ttu-id="fbeed-148">Er ist der beste, und das müsste der Artikel hervorheben.</span><span class="sxs-lookup"><span data-stu-id="fbeed-148">He is the best, and the article should say that.</span></span>

<span data-ttu-id="fbeed-149">Der Machine Learning-Algorithmus für die Klassifizierung ist für dieses Szenario am besten geeignet.</span><span class="sxs-lookup"><span data-stu-id="fbeed-149">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-task"></a><span data-ttu-id="fbeed-150">Informationen zur Klassifizierungsaufgabe</span><span class="sxs-lookup"><span data-stu-id="fbeed-150">About the classification task</span></span>

<span data-ttu-id="fbeed-151">Die Klassifizierung ist ein Machine Learning-Algorithmus, der Daten zum **Bestimmen** von Kategorie, Typ oder Klasse eines Elements oder einer Datenzeile verwendet.</span><span class="sxs-lookup"><span data-stu-id="fbeed-151">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="fbeed-152">Beispielsweise können Sie mit der Klassifizierung:</span><span class="sxs-lookup"><span data-stu-id="fbeed-152">For example, you can use classification to:</span></span>

* <span data-ttu-id="fbeed-153">Einen Standpunkt als positiv oder negativ identifizieren.</span><span class="sxs-lookup"><span data-stu-id="fbeed-153">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="fbeed-154">E-Mails als Spam, Junk oder gut klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="fbeed-154">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="fbeed-155">Bestimmen, ob die Gewebeprobe eines Patienten Krebszellen enthält.</span><span class="sxs-lookup"><span data-stu-id="fbeed-155">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="fbeed-156">Kunden nach ihrer Neigung kategorisieren, auf eine Werbekampagne zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="fbeed-156">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="fbeed-157">Klassifizierungsalgorithmen zählen häufig zu einem der folgenden Typen:</span><span class="sxs-lookup"><span data-stu-id="fbeed-157">Classification algorithms are frequently one of the following types:</span></span>

* <span data-ttu-id="fbeed-158">Binär: entweder A oder B.</span><span class="sxs-lookup"><span data-stu-id="fbeed-158">Binary: either A or B.</span></span>
* <span data-ttu-id="fbeed-159">Multiklasse: mehrere Kategorien, die mit einem einzelnen Modell vorhergesagt werden können.</span><span class="sxs-lookup"><span data-stu-id="fbeed-159">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="fbeed-160">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="fbeed-160">Create a console application</span></span>

1. <span data-ttu-id="fbeed-161">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="fbeed-161">Open Visual Studio 2017.</span></span> <span data-ttu-id="fbeed-162">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="fbeed-162">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="fbeed-163">Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus.</span><span class="sxs-lookup"><span data-stu-id="fbeed-163">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="fbeed-164">Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="fbeed-164">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="fbeed-165">Geben Sie „SentimentAnalysis“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="fbeed-165">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="fbeed-166">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern:</span><span class="sxs-lookup"><span data-stu-id="fbeed-166">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="fbeed-167">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="fbeed-167">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="fbeed-168">Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="fbeed-168">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="fbeed-169">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="fbeed-169">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="fbeed-170">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="fbeed-170">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="fbeed-171">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste sowie anschließend die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="fbeed-171">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="fbeed-172">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="fbeed-172">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="fbeed-173">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="fbeed-173">Prepare your data</span></span>

1. <span data-ttu-id="fbeed-174">Laden Sie die Datasets [Wikipedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) und [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) herunter, und speichern Sie sie im zuvor erstellten Ordner *Data*.</span><span class="sxs-lookup"><span data-stu-id="fbeed-174">Download the [Wikipedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) and the [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="fbeed-175">Das erste Dataset trainiert das Machine Learning-Modell, und das zweite kann verwendet werden, um zu evaluieren, wie genau das Modell ist.</span><span class="sxs-lookup"><span data-stu-id="fbeed-175">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="fbeed-176">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*.tsv-Dateien, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="fbeed-176">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="fbeed-177">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="fbeed-177">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="fbeed-178">Erstellen von Klassen und Definieren von Pfaden</span><span class="sxs-lookup"><span data-stu-id="fbeed-178">Create classes and define paths</span></span>

<span data-ttu-id="fbeed-179">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-179">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="fbeed-180">Sie müssen drei globale Felder erstellen, die die Pfade zu den zuletzt heruntergeladenen Dateien enthalten, und eine globale Variable für den `TextLoader`:</span><span class="sxs-lookup"><span data-stu-id="fbeed-180">You need to create three global fields to hold the paths to the recently downloaded files, and a global variable for the `TextLoader`:</span></span>

* <span data-ttu-id="fbeed-181">`_trainDataPath` enthält den Pfad zu dem Dataset, das zum Trainieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fbeed-181">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="fbeed-182">`_testDataPath` enthält den Pfad zu dem Dataset, das zum Evaluieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fbeed-182">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="fbeed-183">`_modelPath` enthält den Pfad zu dem Speicherort, in dem das trainierte Modell gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="fbeed-183">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="fbeed-184">`_textLoader` ist der zum Laden und Transformieren der Datasets verwendete <xref:Microsoft.ML.Data.TextLoader>.</span><span class="sxs-lookup"><span data-stu-id="fbeed-184">`_textLoader` is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="fbeed-185">Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um diese Pfade und die `_textLoader`-Variable anzugeben:</span><span class="sxs-lookup"><span data-stu-id="fbeed-185">Add the following code to the line right above the `Main` method to specify those paths and the `_textLoader` variable:</span></span>

[!code-csharp[Declare global variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare global variables")]

<span data-ttu-id="fbeed-186">Sie müssen einige Klassen für die Eingabedaten und Vorhersagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="fbeed-186">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="fbeed-187">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-187">Add a new class to your project:</span></span>

1. <span data-ttu-id="fbeed-188">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="fbeed-188">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="fbeed-189">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="fbeed-189">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="fbeed-190">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="fbeed-190">Then, select the **Add** button.</span></span>

    <span data-ttu-id="fbeed-191">Die Datei *SentimentData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="fbeed-191">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="fbeed-192">Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende `using`-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-192">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

<span data-ttu-id="fbeed-193">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `SentimentData` und `SentimentPrediction` der Datei *SentimentData.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-193">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

<span data-ttu-id="fbeed-194">`SentimentData` ist die Klasse des Eingabedatasets und verfügt über eine `float`-Variable (`Sentiment`), die einen entweder positiven oder negativen Wert für den Standpunkt enthält, und eine String-Variable für den Kommentar (`SentimentText`).</span><span class="sxs-lookup"><span data-stu-id="fbeed-194">`SentimentData` is the input dataset class and has a `float` (`Sentiment`) that has a value for sentiment of either positive or negative, and a string for the comment (`SentimentText`).</span></span> <span data-ttu-id="fbeed-195">Beiden Feldern sind `Column`-Attribute angefügt.</span><span class="sxs-lookup"><span data-stu-id="fbeed-195">Both fields have `Column` attributes attached to them.</span></span> <span data-ttu-id="fbeed-196">Dieses Attribut beschreibt die Reihenfolge der Felder in der Datendatei, und welches das `Label`-Feld ist.</span><span class="sxs-lookup"><span data-stu-id="fbeed-196">This attribute describes the order of each field in the data file, and which is the `Label` field.</span></span> <span data-ttu-id="fbeed-197">Die `SentimentPrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fbeed-197">`SentimentPrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="fbeed-198">Er verfügt über einen einzelnen booleschen Wert (`Sentiment`) und ein `PredictedLabel` `ColumnName`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="fbeed-198">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="fbeed-199">Das `Label` dient zum Erstellen und Trainieren des Modells, und es wird auch mit einem zweiten Dataset verwendet, um das Modell zu evaluieren.</span><span class="sxs-lookup"><span data-stu-id="fbeed-199">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="fbeed-200">Das `PredictedLabel` wird während der Vorhersage und Evaluierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="fbeed-200">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="fbeed-201">Für die Evaluierung werden eine Eingabe mit Trainingsdaten, die vorhergesagten Werte und das Modell verwendet.</span><span class="sxs-lookup"><span data-stu-id="fbeed-201">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="fbeed-202">Beim Erstellen eines Modells mit ML.NET erstellen Sie zunächst einen `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="fbeed-202">When building a model with ML.NET you start by creating an `MLContext`.</span></span> <span data-ttu-id="fbeed-203">Dies ist im Prinzip vergleichbar mit der Verwendung von `DbContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="fbeed-203">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="fbeed-204">Die Umgebung bietet einen Kontext für Ihren ML-Job, der für die Verfolgung und Protokollierung von Ausnahmen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fbeed-204">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="fbeed-205">Initialisieren von Variablen in Main</span><span class="sxs-lookup"><span data-stu-id="fbeed-205">Initialize variables in Main</span></span>

<span data-ttu-id="fbeed-206">Erstellen Sie eine Variable namens `mlContext`, und initialisieren Sie sie mit einer neuen `MLContext`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="fbeed-206">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="fbeed-207">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` mit dem folgenden Code in der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="fbeed-207">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="fbeed-208">Als nächstes initialisieren Sie zum Laden der Daten die globale Variable `_textLoader`, um sie wiederzuverwenden.</span><span class="sxs-lookup"><span data-stu-id="fbeed-208">Next, to setup for data loading initialize the `_textLoader` global variable in order to reuse it.</span></span>  <span data-ttu-id="fbeed-209">Wenn Sie einen `TextLoader` mithilfe eines `MLContext.Data.CreateTextLoader` erstellen, übergeben Sie den erforderlichen Kontext und die <xref:Microsoft.ML.Data.TextLoader.Arguments>-Klasse, um eine Anpassung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="fbeed-209">When you create a `TextLoader` using  `MLContext.Data.CreateTextLoader`, you pass in the context needed and the <xref:Microsoft.ML.Data.TextLoader.Arguments> class which enables customization.</span></span>

 <span data-ttu-id="fbeed-210">Geben Sie das Datenschema an, indem Sie ein Array von <xref:Microsoft.ML.Data.TextLoader.Column>-Objekten an das Ladeprogramm übergeben, das alle Spaltennamen und deren Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="fbeed-210">Specify the data schema by passing an array of <xref:Microsoft.ML.Data.TextLoader.Column> objects to the loader containing all the column names and their types.</span></span> <span data-ttu-id="fbeed-211">Das Datenschema wurde bereits beim Erstellen der `SentimentData`-Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="fbeed-211">You defined the data schema previously when you created our `SentimentData` class.</span></span> <span data-ttu-id="fbeed-212">Für unser Schema ist die erste Spalte (Bezeichnung) ein <xref:System.Boolean> (die Vorhersage) und die zweite Spalte (SentimentText) ist die Eigenschaft des Typs „Text/Zeichenfolge“, der für die Vorhersage des Standpunkts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fbeed-212">For our schema, the first column (Label) is a <xref:System.Boolean> (the prediction) and the second column (SentimentText) is the feature of type text/string used for predicting the sentiment.</span></span>
<span data-ttu-id="fbeed-213">Die `TextLoader`-Klasse gibt einen vollständig initialisierten <xref:Microsoft.ML.Data.TextLoader> zurück.</span><span class="sxs-lookup"><span data-stu-id="fbeed-213">The `TextLoader` class returns a fully initialized <xref:Microsoft.ML.Data.TextLoader></span></span>  

<span data-ttu-id="fbeed-214">Um die globale Variable `_textLoader` zu initialisieren, um sie für die benötigten Datasets wiederzuverwenden, fügen Sie nach der Initialisierung von `mlContext` den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-214">To initialize the `_textLoader` global variable in order to reuse it for the needed datasets, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[initTextLoader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#4 "Initialize the TextLoader")]

<span data-ttu-id="fbeed-215">Fügen Sie den folgenden Text als nächste Codezeile in die `Main`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="fbeed-215">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Train your model")]

<span data-ttu-id="fbeed-216">Die `Train`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="fbeed-216">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="fbeed-217">Laden der Daten.</span><span class="sxs-lookup"><span data-stu-id="fbeed-217">Loads the data.</span></span>
* <span data-ttu-id="fbeed-218">Extrahieren und Transformieren der Daten.</span><span class="sxs-lookup"><span data-stu-id="fbeed-218">Extracts and transforms the data.</span></span>
* <span data-ttu-id="fbeed-219">Trainieren des Modells.</span><span class="sxs-lookup"><span data-stu-id="fbeed-219">Trains the model.</span></span>
* <span data-ttu-id="fbeed-220">Vorhersagen des Standpunkts anhand der Testdaten.</span><span class="sxs-lookup"><span data-stu-id="fbeed-220">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="fbeed-221">Zurückgeben des Modells.</span><span class="sxs-lookup"><span data-stu-id="fbeed-221">Returns the model.</span></span>

<span data-ttu-id="fbeed-222">Erstellen Sie die `Train`-Methode mit dem folgenden Code direkt nach der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="fbeed-222">Create the `Train` method, just after the `Main` method, using the following code:</span></span>

```csharp
 public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

<span data-ttu-id="fbeed-223">Beachten Sie, dass zwei Parameter an die Train-Methode übergeben werden; ein `MLContext` für den Kontext (`mlContext`) und eine <xref:System.String> für den Datensetpfad (`dataPath`).</span><span class="sxs-lookup"><span data-stu-id="fbeed-223">Notice that two parameters are passed into the Train method; a `MLContext` for the context (`mlContext`), and a <xref:System.String> for the dataset path (`dataPath`).</span></span> <span data-ttu-id="fbeed-224">Sie werden diese Methode mehr als einmal zum Trainieren und Testen verwenden.</span><span class="sxs-lookup"><span data-stu-id="fbeed-224">You're going to use this method more than once for training and testing.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="fbeed-225">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="fbeed-225">Load the data</span></span>

<span data-ttu-id="fbeed-226">Sie laden die Daten mithilfe der globalen Variablen `_textLoader` mit dem `dataPath`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="fbeed-226">You'll load the data using the `_textLoader` global variable with the `dataPath` parameter.</span></span> <span data-ttu-id="fbeed-227">Zurückgegeben wird ein <xref:Microsoft.Data.DataView.IDataView>.</span><span class="sxs-lookup"><span data-stu-id="fbeed-227">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span> <span data-ttu-id="fbeed-228">Als Ein- und Ausgabe von `Transforms` ist ein `DataView` der grundlegende Datenpipelinetyp, vergleichbar mit `IEnumerable` für `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="fbeed-228">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="fbeed-229">In ML.NET ähneln die Daten einer SQL-Ansicht.</span><span class="sxs-lookup"><span data-stu-id="fbeed-229">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="fbeed-230">Sie werden verzögert ausgewertet, sind schematisiert und heterogen.</span><span class="sxs-lookup"><span data-stu-id="fbeed-230">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="fbeed-231">Das Objekt ist der erste Teil der Pipeline und lädt die Daten.</span><span class="sxs-lookup"><span data-stu-id="fbeed-231">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="fbeed-232">Für dieses Tutorial lädt es ein Dataset mit Kommentaren und entsprechend schädlichen oder unschädlichen Standpunkten.</span><span class="sxs-lookup"><span data-stu-id="fbeed-232">For this tutorial, it loads a dataset with comments and corresponding toxic or non toxic sentiment.</span></span> <span data-ttu-id="fbeed-233">Damit wird das Modell erstellt und trainiert.</span><span class="sxs-lookup"><span data-stu-id="fbeed-233">This is used to create the model, and train it.</span></span>

 <span data-ttu-id="fbeed-234">Fügen Sie den folgenden Code am Ende der ersten Zeile der `Train`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="fbeed-234">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "loading training dataset")]

## <a name="extract-and-transform-the-data"></a><span data-ttu-id="fbeed-235">Extrahieren und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="fbeed-235">Extract and transform the data</span></span>

<span data-ttu-id="fbeed-236">Vorverarbeitung und Bereinigung von Daten sind wichtige Aufgaben, die durchgeführt werden, bevor ein Dataset effektiv für Machine Learning verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fbeed-236">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="fbeed-237">Rohdaten sind häufig verunreinigt und unzuverlässig, und es können darin Werte fehlen.</span><span class="sxs-lookup"><span data-stu-id="fbeed-237">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="fbeed-238">Die Verwendung von Daten ohne diese Modellierungsaufgaben kann irreführende Ergebnisse erzeugen.</span><span class="sxs-lookup"><span data-stu-id="fbeed-238">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="fbeed-239">Mit den Transformationspipelines von ML.NET können Sie einen benutzerdefinierten Satz von Transformationen erstellen, die vor dem Trainieren oder Testen auf Ihre Daten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="fbeed-239">ML.NET's transform pipelines compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="fbeed-240">Die Transformationen dienen in erster Linie der [Datenfeaturebereitstellung](../resources/glossary.md#feature-engineering).</span><span class="sxs-lookup"><span data-stu-id="fbeed-240">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="fbeed-241">Machine Learning-Algorithmen verstehen die mit [Features ausgestatteten](../resources/glossary.md#feature) Daten, sodass der nächste Schritt darin besteht, unsere Textdaten in ein Format zu transformieren, das unsere ML-Algorithmen erkennen.</span><span class="sxs-lookup"><span data-stu-id="fbeed-241">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="fbeed-242">Dieses Format ist ein [numerischer Vektor](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="fbeed-242">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="fbeed-243">Rufen Sie anschließend `mlContext.Transforms.Text.FeaturizeText` auf, wodurch die Textspalte (`SentimentText`) in einen numerischen Vektor namens `Features` konvertiert wird, den der Machine Learning-Algorithmus verwendet.</span><span class="sxs-lookup"><span data-stu-id="fbeed-243">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text column (`SentimentText`) column into a numeric vector called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="fbeed-244">Dies ist ein Wrapperaufruf, der <xref:Microsoft.ML.Data.EstimatorChain%601> zurückgibt, das effektiv eine Pipeline ist.</span><span class="sxs-lookup"><span data-stu-id="fbeed-244">This is a wrapper call that returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="fbeed-245">Geben Sie den Namen `pipeline` ein, da Sie den Trainer an die `EstimatorChain` anfügen.</span><span class="sxs-lookup"><span data-stu-id="fbeed-245">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="fbeed-246">Fügen Sie das zur nächsten Codezeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-246">Add this as the next line of code:</span></span>

[!code-csharp[TextFeaturizingEstimator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizingEstimator")]

>[!WARNING]
> <span data-ttu-id="fbeed-247">Die ML.NET-Version 0.10 hat die Reihenfolge der Transformationsparameter geändert.</span><span class="sxs-lookup"><span data-stu-id="fbeed-247">ML.NET Version 0.10 has changed the order of the Transform parameters.</span></span> <span data-ttu-id="fbeed-248">Dies führt erst dann zu einem Fehler, wenn Sie die Anwendung ausführen und das Modell erstellen.</span><span class="sxs-lookup"><span data-stu-id="fbeed-248">This will not error out until you run the application and build the model.</span></span> <span data-ttu-id="fbeed-249">Verwenden Sie für Transformationen die Parameternamen, wie Sie im vorherigen Codeausschnitt dargestellt sind.</span><span class="sxs-lookup"><span data-stu-id="fbeed-249">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="fbeed-250">Dies ist der Vorverarbeitungs-/Featurebereitstellungsschritt.</span><span class="sxs-lookup"><span data-stu-id="fbeed-250">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="fbeed-251">Die Verwendung zusätzlicher in ML.NET verfügbarer Komponenten kann bessere Ergebnisse mit dem Modell ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="fbeed-251">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="fbeed-252">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="fbeed-252">Choose a learning algorithm</span></span>

<span data-ttu-id="fbeed-253">Um die Trainer hinzuzufügen, rufen Sie die `mlContext.Transforms.Text.FeaturizeText`-Wrappermethode auf, die ein <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer>-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fbeed-253">To add the trainer, call the `mlContext.Transforms.Text.FeaturizeText` wrapper method which returns a <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> object.</span></span> <span data-ttu-id="fbeed-254">Das ist ein Entscheidungsstruktur-Lernmodul, das Sie in dieser Pipeline verwenden.</span><span class="sxs-lookup"><span data-stu-id="fbeed-254">This is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="fbeed-255">Der `FastTreeBinaryClassificationTrainer` wird an die `pipeline` angefügt, und akzeptiert den mit Features ausgestatteten `SentimentText` (`Features`) und die `Label`-Eingabeparameter, um aus den historischen Daten zu lernen.</span><span class="sxs-lookup"><span data-stu-id="fbeed-255">The `FastTreeBinaryClassificationTrainer` is appended to the `pipeline` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

<span data-ttu-id="fbeed-256">Fügen Sie der `Train`-Methode folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-256">Add the following code to the `Train` method:</span></span>

[!code-csharp[FastTreeBinaryClassificationTrainer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="fbeed-257">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="fbeed-257">Train the model</span></span>

<span data-ttu-id="fbeed-258">Sie trainieren das Modell <xref:Microsoft.ML.Data.TransformerChain%601> basierend auf dem Dataset, das geladen und transformiert worden ist.</span><span class="sxs-lookup"><span data-stu-id="fbeed-258">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="fbeed-259">Sobald die Schätzung definiert ist, trainieren Sie Ihr Modell mit <xref:Microsoft.ML.Data.EstimatorChain%601.Fit*> und stellen die bereits geladenen Trainingsdaten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="fbeed-259">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit*> while providing the already loaded training data.</span></span> <span data-ttu-id="fbeed-260">Damit wird ein Modell zurückgegeben, das für Vorhersagen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fbeed-260">This returns a model to use for predictions.</span></span> <span data-ttu-id="fbeed-261">`pipeline.Fit()` trainiert die Pipeline und gibt einen `Transformer` basierend auf der eingegebenen `DataView` zurück.</span><span class="sxs-lookup"><span data-stu-id="fbeed-261">`pipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="fbeed-262">Das Experiment wird erst ausgeführt, wenn dies geschieht.</span><span class="sxs-lookup"><span data-stu-id="fbeed-262">The experiment is not executed until this happens.</span></span>

<span data-ttu-id="fbeed-263">Fügen Sie der `Train`-Methode folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-263">Add the following code to the `Train` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="fbeed-264">Speichern und Zurückgeben des trainierten Modells zur Verwendung für die Evaluierung</span><span class="sxs-lookup"><span data-stu-id="fbeed-264">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="fbeed-265">An diesem Punkt haben Sie ein Modell vom Typ <xref:Microsoft.ML.Data.TransformerChain%601>, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="fbeed-265">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="fbeed-266">Geben Sie das Modell am Ende der `Train`-Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="fbeed-266">Return the model at the end of the `Train` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="fbeed-267">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="fbeed-267">Evaluate the model</span></span>

<span data-ttu-id="fbeed-268">Da Sie nun das Modell erstellt und trainiert haben, müssen Sie es zur Qualitätssicherung und Validierung mit einem anderen Dataset evaluieren.</span><span class="sxs-lookup"><span data-stu-id="fbeed-268">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="fbeed-269">In der `Evaluate`-Methode wird das in `Train` erstellte Modell zur Evaluierung übergeben.</span><span class="sxs-lookup"><span data-stu-id="fbeed-269">In the `Evaluate` method, the model created in `Train` is passed in to be evaluated.</span></span> <span data-ttu-id="fbeed-270">Erstellen Sie die `Evaluate`-Methode direkt nach `Train` wie im folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="fbeed-270">Create the `Evaluate` method, just after `Train`, as in the following code:</span></span>

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="fbeed-271">Die `Evaluate`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="fbeed-271">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="fbeed-272">Laden des Testdatasets.</span><span class="sxs-lookup"><span data-stu-id="fbeed-272">Loads the test dataset.</span></span>
* <span data-ttu-id="fbeed-273">Erstellen des binären Auswerters.</span><span class="sxs-lookup"><span data-stu-id="fbeed-273">Creates the binary evaluator.</span></span>
* <span data-ttu-id="fbeed-274">Evaluieren des Modells und Erstellen von Metriken.</span><span class="sxs-lookup"><span data-stu-id="fbeed-274">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="fbeed-275">Anzeigen der Metriken.</span><span class="sxs-lookup"><span data-stu-id="fbeed-275">Displays the metrics.</span></span>

<span data-ttu-id="fbeed-276">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Train`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-276">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Call the Evaluate method")]

<span data-ttu-id="fbeed-277">Sie laden das Testdatenset mit der zuvor initialisierten globalen Variablen `_textLoader` und dem globalen Feld `_testDataPath`.</span><span class="sxs-lookup"><span data-stu-id="fbeed-277">You'll load the test dataset using the previously initialized  `_textLoader` global variable with the `_testDataPath` global field.</span></span> <span data-ttu-id="fbeed-278">Sie können das Modell unter Verwendung dieses Datasets in Form einer Qualitätsüberprüfung evaluieren.</span><span class="sxs-lookup"><span data-stu-id="fbeed-278">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="fbeed-279">Fügen Sie der `Evaluate`-Methode folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-279">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Load the test dataset")]

<span data-ttu-id="fbeed-280">Als nächstes verwenden Sie den Machine Learning-Parameter `model` (einen Transformator), um die Features einzugeben und die Vorhersagen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="fbeed-280">Next, you'll use the machine learning `model` parameter (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="fbeed-281">Fügen Sie der `Evaluate`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-281">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Predict using the Transformer")]

<span data-ttu-id="fbeed-282">Die `BinaryClassificationContext.Evaluate`-Methode berechnet die Qualitätsmetriken für das `PredictionModel` mit dem angegebenen Dataset.</span><span class="sxs-lookup"><span data-stu-id="fbeed-282">The `BinaryClassificationContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="fbeed-283">Das zurückgegebene `BinaryClassificationEvaluator.CalibratedResult`-Objekt enthält alle von Auswertern der binären Klassifizierung berechneten Metriken.</span><span class="sxs-lookup"><span data-stu-id="fbeed-283">It returns a `BinaryClassificationEvaluator.CalibratedResult` object contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="fbeed-284">Um diese zur Bestimmung der Qualität des Modells anzuzeigen, müssen Sie die Metriken zuerst abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fbeed-284">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="fbeed-285">Fügen Sie der `Evaluate`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-285">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="fbeed-286">Anzeigen der Metriken zur Modellvalidierung</span><span class="sxs-lookup"><span data-stu-id="fbeed-286">Displaying the metrics for model validation</span></span>

<span data-ttu-id="fbeed-287">Verwenden Sie den folgenden Code, um die Metriken anzuzeigen, die Ergebnisse freizugeben und dann mit ihnen zu arbeiten:</span><span class="sxs-lookup"><span data-stu-id="fbeed-287">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Display selected metrics")]

<span data-ttu-id="fbeed-288">Um das Modell vor der Rückgabe in einer ZIP-Datei zu speichern, fügen Sie den folgenden Code als nächste Zeile in `Evaluate` hinzu, um die `SaveModelAsFile`-Methode aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="fbeed-288">To save your model to a .zip file before returning, add the following code to call the `SaveModelAsFile` method as the next line in `Evaluate`:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#23 "Save the model")]

## <a name="save-the-model-as-azip-file"></a><span data-ttu-id="fbeed-289">Speichern des Modells als ZIP-Datei</span><span class="sxs-lookup"><span data-stu-id="fbeed-289">Save the model as a.zip file</span></span>

<span data-ttu-id="fbeed-290">Erstellen Sie die `SaveModelAsFile`-Methode mit dem folgenden Code direkt nach der `Evaluate`-Methode:</span><span class="sxs-lookup"><span data-stu-id="fbeed-290">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="fbeed-291">Die `SaveModelAsFile`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="fbeed-291">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="fbeed-292">Speichern Sie das Modells als ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="fbeed-292">Saves the model as a .zip file.</span></span>

<span data-ttu-id="fbeed-293">Erstellen Sie anschließend eine Methode zum Speichern des Modells, damit es wiederverwendet und in anderen Anwendungen integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="fbeed-293">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="fbeed-294">Der `ITransformer` enthält eine <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)>-Methode mit dem globalen Feld `_modelPath` und einem <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="fbeed-294">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="fbeed-295">Um die als ZIP-Datei zu speichern, erstellen Sie den `FileStream` unmittelbar vor dem Aufruf der `SaveTo`-Methode.</span><span class="sxs-lookup"><span data-stu-id="fbeed-295">To save this as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="fbeed-296">Fügen Sie der `SaveModelAsFile`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-296">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#24 "Add the SaveTo Method")]
<span data-ttu-id="fbeed-297">Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen
Sie können auch anzeigen, wo die Datei geschrieben wurde, indem Sie mit dem folgenden Code eine Konsolenmeldung mit dem `_modelPath` schreiben:</span><span class="sxs-lookup"><span data-stu-id="fbeed-297">Deploy and Predict with a loaded model You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a><span data-ttu-id="fbeed-298">Vorhersagen des Testdatenergebnisses mit dem gespeicherten Modell</span><span class="sxs-lookup"><span data-stu-id="fbeed-298">Predict the test data outcome with the saved model</span></span>

<span data-ttu-id="fbeed-299">Erstellen Sie die `Predict`-Methode mit dem folgenden Code direkt nach der `Evaluate`-Methode:</span><span class="sxs-lookup"><span data-stu-id="fbeed-299">Create the `Predict` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void Predict(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="fbeed-300">Die `Predict`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="fbeed-300">The `Predict` method executes the following tasks:</span></span>

* <span data-ttu-id="fbeed-301">Erstellen eines einzelnen Kommentars aus Testdaten.</span><span class="sxs-lookup"><span data-stu-id="fbeed-301">Creates a single comment of test data.</span></span>
* <span data-ttu-id="fbeed-302">Vorhersagen des Standpunkts anhand der Testdaten.</span><span class="sxs-lookup"><span data-stu-id="fbeed-302">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="fbeed-303">Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.</span><span class="sxs-lookup"><span data-stu-id="fbeed-303">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="fbeed-304">Anzeigen der vorhergesagten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="fbeed-304">Displays the predicted results.</span></span>

<span data-ttu-id="fbeed-305">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Evaluate`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-305">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Call the Predict method")]

<span data-ttu-id="fbeed-306">Das `model` ist ein `transformer`, der auf vielen Datenzeilen arbeitet, wohingegen ein sehr gängiges Produktionsszenario die Notwendigkeit von Vorhersagen für einzelne Beispiele ist.</span><span class="sxs-lookup"><span data-stu-id="fbeed-306">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="fbeed-307"><xref:Microsoft.ML.PredictionEngine%602> ist ein Wrapper, der von der `CreatePredictionEngine`-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fbeed-307">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="fbeed-308">Fügen wir den folgenden Code hinzu, um die `PredictionEngine` als erste Zeile in der `Predict`-Methode zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="fbeed-308">Let's add the following code to create the `PredictionEngine` as the first line in the `Predict` Method:</span></span>

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Create the PredictionEngine")]
  
<span data-ttu-id="fbeed-309">Fügen Sie einen Kommentar hinzu, um die Vorhersage des trainierten Modells in der `Predict`-Methode zu testen, indem Sie eine `SentimentData`-Instanz erstellen:</span><span class="sxs-lookup"><span data-stu-id="fbeed-309">Add a comment to test the trained model's prediction in the `Predict` method by creating an instance of `SentimentData`:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for single prediction")]

 <span data-ttu-id="fbeed-310">Damit können Sie den schädlichen oder unschädlichen Standpunkt einer einzelnen Instanz der Kommentardaten vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="fbeed-310">You can use that to predict the Toxic or Non Toxic sentiment of a single instance of the comment data.</span></span> <span data-ttu-id="fbeed-311">Verwenden Sie zum Abrufen einer Vorhersage <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> für die Daten.</span><span class="sxs-lookup"><span data-stu-id="fbeed-311">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="fbeed-312">Beachten Sie, dass die Eingabedaten eine Zeichenfolge sind und das Modell die Featurebereitstellungsschritt umfasst.</span><span class="sxs-lookup"><span data-stu-id="fbeed-312">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="fbeed-313">Die Pipeline ist während Training und Vorhersage synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="fbeed-313">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="fbeed-314">Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="fbeed-314">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create a prediction of sentiment")]

### <a name="using-the-model-prediction"></a><span data-ttu-id="fbeed-315">Verwenden des Modells: Vorhersage</span><span class="sxs-lookup"><span data-stu-id="fbeed-315">Using the model: prediction</span></span>

<span data-ttu-id="fbeed-316">Anzeigen von `SentimentText` und entsprechender Standpunktvorhersage, um die Ergebnisse freizugeben und entsprechend mit ihnen zu agieren.</span><span class="sxs-lookup"><span data-stu-id="fbeed-316">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="fbeed-317">Dies wird als Operationalisierung bezeichnet, wobei die zurückgegebenen Daten als Teil der Betriebsrichtlinien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fbeed-317">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="fbeed-318">Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Anzeige für die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="fbeed-318">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction output")]

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="fbeed-319">Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen</span><span class="sxs-lookup"><span data-stu-id="fbeed-319">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="fbeed-320">Erstellen Sie die `PredictWithModelLoadedFromFile`-Methode mit dem folgenden Code direkt vor der `SaveModelAsFile`-Methode:</span><span class="sxs-lookup"><span data-stu-id="fbeed-320">Create the `PredictWithModelLoadedFromFile` method, just before the `SaveModelAsFile` method, using the following code:</span></span>

```csharp
public static void PredictWithModelLoadedFromFile(MLContext mlContext)
{

}
```

<span data-ttu-id="fbeed-321">Die `PredictWithModelLoadedFromFile`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="fbeed-321">The `PredictWithModelLoadedFromFile` method executes the following tasks:</span></span>

* <span data-ttu-id="fbeed-322">Erstellen von Batchtestdaten.</span><span class="sxs-lookup"><span data-stu-id="fbeed-322">Creates batch test data.</span></span>
* <span data-ttu-id="fbeed-323">Vorhersagen des Standpunkts anhand der Testdaten.</span><span class="sxs-lookup"><span data-stu-id="fbeed-323">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="fbeed-324">Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.</span><span class="sxs-lookup"><span data-stu-id="fbeed-324">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="fbeed-325">Anzeigen der vorhergesagten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="fbeed-325">Displays the predicted results.</span></span>

<span data-ttu-id="fbeed-326">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Predict`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-326">Add a call to the new method from the `Main` method, right under the `Predict` method call, using the following code:</span></span>

[!code-csharp[CallPredictModelLoaded](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#25 "Call the PredictWithModelLoadedFromFile method")]

<span data-ttu-id="fbeed-327">Fügen Sie einige Kommentare zum Testen der Vorhersagen des trainierten Modells in der `PredictWithModelLoadedFromFile`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-327">Add some comments to test the trained model's predictions in the `PredictWithModelLoadedFromFile` method:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#26 "Create test data for predictions")]

<span data-ttu-id="fbeed-328">Das des Modells</span><span class="sxs-lookup"><span data-stu-id="fbeed-328">Load the model</span></span>

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#27 "Load the model")]

<span data-ttu-id="fbeed-329">Nun besitzen Sie ein Modell, mit dem Sie den schädlichen oder nicht schädlichen Standpunkt der Kommentardaten unter Verwendung der <xref:Microsoft.ML.Core.Data.ITransformer.Transform%2A>-Methode vorhersagen können.</span><span class="sxs-lookup"><span data-stu-id="fbeed-329">Now that you have a model, you can use that to predict the Toxic or Non Toxic sentiment of the comment data using the <xref:Microsoft.ML.Core.Data.ITransformer.Transform%2A> method.</span></span> <span data-ttu-id="fbeed-330">Verwenden Sie zum Abrufen einer Vorhersage `Predict` mit neuen Daten.</span><span class="sxs-lookup"><span data-stu-id="fbeed-330">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="fbeed-331">Beachten Sie, dass die Eingabedaten eine Zeichenfolge sind und das Modell die Featurebereitstellungsschritt umfasst.</span><span class="sxs-lookup"><span data-stu-id="fbeed-331">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="fbeed-332">Die Pipeline ist während Training und Vorhersage synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="fbeed-332">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="fbeed-333">Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="fbeed-333">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="fbeed-334">Fügen Sie für die Vorhersage den folgenden Code zur `PredictWithModelLoadedFromFile`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-334">Add the following code to the `PredictWithModelLoadedFromFile` method for the predictions:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#28 "Create predictions of sentiments")]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="fbeed-335">Verwenden des geladenen Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="fbeed-335">Using the loaded model for prediction</span></span>

<span data-ttu-id="fbeed-336">Anzeigen von `SentimentText` und entsprechender Standpunktvorhersage, um die Ergebnisse freizugeben und entsprechend mit ihnen zu agieren.</span><span class="sxs-lookup"><span data-stu-id="fbeed-336">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="fbeed-337">Dies wird als Operationalisierung bezeichnet, wobei die zurückgegebenen Daten als Teil der Betriebsrichtlinien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fbeed-337">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="fbeed-338">Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Kopfzeile für die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="fbeed-338">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#29 "Display prediction outputs")]

<span data-ttu-id="fbeed-339">Kombinieren Sie vor der Anzeige der vorhergesagten Ergebnisse Standpunkt und Vorhersage, um den ursprünglichen Kommentar mit dem vorhergesagten Standpunkt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fbeed-339">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="fbeed-340">Der folgende Code verwendet hierzu die <xref:System.Linq.Enumerable.Zip%2A>-Methode, darum fügen Sie diesen Code als Nächstes hinzu:</span><span class="sxs-lookup"><span data-stu-id="fbeed-340">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#30 "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="fbeed-341">Da Sie nun `SentimentText` und `Sentiment` in einer Klasse kombiniert haben, können Sie die Ergebnisse mithilfe der <xref:System.Console.WriteLine?displayProperty=nameWithType>-Methode anzeigen:</span><span class="sxs-lookup"><span data-stu-id="fbeed-341">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#31 "Display the predictions")]

<span data-ttu-id="fbeed-342">Da abgeleitete Tupelelementnamen ein neues Feature in C# 7.1 sind und die Standardsprachversion des Projekts C# 7.0 ist, müssen Sie die Sprachversion auf C# 7.1 oder höher ändern.</span><span class="sxs-lookup"><span data-stu-id="fbeed-342">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="fbeed-343">Klicken Sie hierzu im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="fbeed-343">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="fbeed-344">Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="fbeed-344">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="fbeed-345">Wählen Sie in der Dropdownliste **C# 7.1** (oder eine höhere Version) aus.</span><span class="sxs-lookup"><span data-stu-id="fbeed-345">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="fbeed-346">Klicken Sie auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="fbeed-346">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="fbeed-347">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="fbeed-347">Results</span></span>

<span data-ttu-id="fbeed-348">Die Ergebnisse sollten den unten dargestellten ähneln.</span><span class="sxs-lookup"><span data-stu-id="fbeed-348">Your results should be similar to the following.</span></span> <span data-ttu-id="fbeed-349">Während der Pipelineverarbeitung werden Meldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fbeed-349">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="fbeed-350">Sie können Warnungen oder Verarbeitungsmeldungen sehen.</span><span class="sxs-lookup"><span data-stu-id="fbeed-350">You may see warnings, or processing messages.</span></span> <span data-ttu-id="fbeed-351">Diese wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="fbeed-351">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 94.44%
Auc: 98.77%
F1Score: 94.74%
=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.5297049
=============== End of Predictions ===============

=============== New iteration of Model ===============
=============== Create and Train the Model ===============
=============== End of training ===============


The model is saved to: C:\Tutorial\SentimentAnalysis\bin\Debug\netcoreapp2.1\Data\Model.zip

=============== Prediction Test of loaded model with a multiple sample ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.4585565
Sentiment: I love this article. | Prediction: Not Toxic | Probability: 0.09454837

```

<span data-ttu-id="fbeed-352">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="fbeed-352">Congratulations!</span></span> <span data-ttu-id="fbeed-353">Sie haben jetzt erfolgreich ein Machine Learning-Modell zum Klassifizieren und Vorhersagen von Standpunkten in Mitteilungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="fbeed-353">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> <span data-ttu-id="fbeed-354">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="fbeed-354">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fbeed-355">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="fbeed-355">Next steps</span></span>

<span data-ttu-id="fbeed-356">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="fbeed-356">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="fbeed-357">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="fbeed-357">Understand the problem</span></span>
> * <span data-ttu-id="fbeed-358">Auswählen des entsprechenden Machine Learning-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="fbeed-358">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="fbeed-359">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="fbeed-359">Prepare your data</span></span>
> * <span data-ttu-id="fbeed-360">Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="fbeed-360">Transform the data</span></span>
> * <span data-ttu-id="fbeed-361">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="fbeed-361">Train the model</span></span>
> * <span data-ttu-id="fbeed-362">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="fbeed-362">Evaluate the model</span></span>
> * <span data-ttu-id="fbeed-363">Vorhersagen treffen mit dem trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="fbeed-363">Predict with the trained model</span></span>
> * <span data-ttu-id="fbeed-364">Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen</span><span class="sxs-lookup"><span data-stu-id="fbeed-364">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="fbeed-365">Wechseln Sie zum nächsten Tutorial, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="fbeed-365">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="fbeed-366">Klassifizierung von Issues</span><span class="sxs-lookup"><span data-stu-id="fbeed-366">Issue Classification</span></span>](github-issue-classification.md)
