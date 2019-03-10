---
title: 'Vorgehensweise: Aktualisieren der Definition einer ausgeführten Workflowinstanz'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 26dfac36-ae23-4909-9867-62495b55fb5e
ms.openlocfilehash: d3ff9d217d085e3afe5171cce9d80f8dbc32ff36
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722905"
---
# <a name="how-to-update-the-definition-of-a-running-workflow-instance"></a><span data-ttu-id="b3da5-102">Vorgehensweise: Aktualisieren der Definition einer ausgeführten Workflowinstanz</span><span class="sxs-lookup"><span data-stu-id="b3da5-102">How to: Update the Definition of a Running Workflow Instance</span></span>

<span data-ttu-id="b3da5-103">Dynamische Updates bieten Entwicklern von Workflowanwendungen die Möglichkeit, die Workflowdefinition einer persistenten Workflowinstanz zu aktualisieren,</span><span class="sxs-lookup"><span data-stu-id="b3da5-103">Dynamic update provides a mechanism for workflow application developers to update the workflow definition of a persisted workflow instance.</span></span> <span data-ttu-id="b3da5-104">beispielsweise um eine Fehlerkorrektur oder neue Anforderungen zu implementieren oder um unerwartete Änderungen zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-104">The required change can be to implement a bug fix, new requirements, or to accommodate unexpected changes.</span></span> <span data-ttu-id="b3da5-105">Dieser Schritt in diesem Tutorial wird veranschaulicht, wie dynamische Updates verwenden, um persistente Instanzen zu ändern. die `v1` schätzen von Zahlen Workflow entsprechend der neue Funktionen, eingeführt in [Vorgehensweise: Hosten mehrerer Workflowversionen zu einem Workflow Seite-an-Seite](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span><span class="sxs-lookup"><span data-stu-id="b3da5-105">This step in the tutorial demonstrates how to use dynamic update to modify  persisted instances of the `v1` number guessing workflow to match the new functionality introduced in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b3da5-106">Um den download einer vervollständigten Version oder eine Videodemonstration des Lernprogramms anzuzeigen, finden Sie unter [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="b3da5-106">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="in-this-topic"></a><span data-ttu-id="b3da5-107">In diesem Thema</span><span class="sxs-lookup"><span data-stu-id="b3da5-107">In this topic</span></span>

- [<span data-ttu-id="b3da5-108">Um das CreateUpdateMaps-Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-108">To create the CreateUpdateMaps project</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_CreateProject)

- [<span data-ttu-id="b3da5-109">So aktualisieren Sie StateMachineNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="b3da5-109">To update StateMachineNumberGuessWorkflow</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_StateMachine)

- [<span data-ttu-id="b3da5-110">So aktualisieren Sie FlowchartNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="b3da5-110">To update FlowchartNumberGuessWorkflow</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_Flowchart)

- [<span data-ttu-id="b3da5-111">So aktualisieren Sie SequentialNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="b3da5-111">To update SequentialNumberGuessWorkflow</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_Sequential)

- [<span data-ttu-id="b3da5-112">So erstellen und führen die CreateUpdateMaps-Anwendung</span><span class="sxs-lookup"><span data-stu-id="b3da5-112">To build and run the CreateUpdateMaps application</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_CreateUpdateMaps)

- [<span data-ttu-id="b3da5-113">Um die aktualisierte Workflowassembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-113">To build the updated workflow assembly</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_BuildAssembly)

- [<span data-ttu-id="b3da5-114">So aktualisieren Sie WorkflowVersionMap anhand der neuen Versionen</span><span class="sxs-lookup"><span data-stu-id="b3da5-114">To update WorkflowVersionMap with the new versions</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_UpdateWorkflowVersionMap)

- [<span data-ttu-id="b3da5-115">Die dynamische Updates</span><span class="sxs-lookup"><span data-stu-id="b3da5-115">To apply the dynamic updates</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_ApplyUpdate)

- [<span data-ttu-id="b3da5-116">Zum Ausführen der Anwendung mit der aktualisierten workflows</span><span class="sxs-lookup"><span data-stu-id="b3da5-116">To run the application with the updated workflows</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_BuildAndRun)

- [<span data-ttu-id="b3da5-117">Zum Starten von Vorgängerversionen der Workflows zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="b3da5-117">To enable starting previous versions of the workflows</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_StartPreviousVersions)

### <a name="BKMK_CreateProject"></a> <span data-ttu-id="b3da5-118">Um das CreateUpdateMaps-Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-118">To create the CreateUpdateMaps project</span></span>

1. <span data-ttu-id="b3da5-119">Mit der rechten Maustaste **WF45GettingStartedTutorial** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-119">Right-click **WF45GettingStartedTutorial** in **Solution Explorer** and choose **Add**, **New Project**.</span></span>

2. <span data-ttu-id="b3da5-120">In der **installiert** Knoten **Visual C#-**, **Windows** (oder **Visual Basic**, **Windows**).</span><span class="sxs-lookup"><span data-stu-id="b3da5-120">In the **Installed** node, select **Visual C#**, **Windows** (or **Visual Basic**, **Windows**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3da5-121">Je nachdem, welche Programmiersprache als die primäre Sprache in Visual Studio konfiguriert ist, befindet sich der Knoten **Visual C#** oder **Visual Basic** möglicherweise nicht unter dem Knoten **Andere Sprachen** im Knoten **Installiert** .</span><span class="sxs-lookup"><span data-stu-id="b3da5-121">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>

     <span data-ttu-id="b3da5-122">Stellen Sie sicher, dass in der Dropdownliste mit der .NET Framework-Version **.NET Framework 4.5** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="b3da5-122">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="b3da5-123">Wählen Sie **Konsolenanwendung** aus der **Windows** Liste.</span><span class="sxs-lookup"><span data-stu-id="b3da5-123">Select **Console Application** from the **Windows** list.</span></span> <span data-ttu-id="b3da5-124">Typ **CreateUpdateMaps** in die **Namen** ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-124">Type **CreateUpdateMaps** into the **Name** box and click **OK**.</span></span>

3. <span data-ttu-id="b3da5-125">Mit der rechten Maustaste **CreateUpdateMaps** in **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-125">Right-click **CreateUpdateMaps** in **Solution Explorer** and choose **Add Reference**.</span></span>

4. <span data-ttu-id="b3da5-126">Wählen Sie **Framework** aus der **Assemblys** Knoten in der **Verweis hinzufügen** Liste.</span><span class="sxs-lookup"><span data-stu-id="b3da5-126">Select **Framework** from the **Assemblies** node in the **Add Reference** list.</span></span> <span data-ttu-id="b3da5-127">Typ **System.Activities** in die **Assemblys suchen** Feld, um die Assemblys gefiltert, und stellen die gewünschten Verweise einfacher auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-127">Type **System.Activities** into the **Search Assemblies** box to filter the assemblies and make the desired references easier to select.</span></span>

5. <span data-ttu-id="b3da5-128">Aktivieren Sie das Kontrollkästchen neben **System.Activities** aus der **Suchergebnisse** Liste.</span><span class="sxs-lookup"><span data-stu-id="b3da5-128">Check the checkbox beside **System.Activities** from the **Search Results** list.</span></span>

6. <span data-ttu-id="b3da5-129">Typ **Serialisierung** in die **Assemblys suchen** ein, und aktivieren Sie das Kontrollkästchen neben **System.Runtime.Serialization** aus der **Suchergebnisse**  Liste.</span><span class="sxs-lookup"><span data-stu-id="b3da5-129">Type **Serialization** into the **Search Assemblies** box, and check the checkbox beside **System.Runtime.Serialization** from the **Search Results** list.</span></span>

7. <span data-ttu-id="b3da5-130">Typ **"System.xaml"** in die **Assemblys suchen** ein, und aktivieren Sie das Kontrollkästchen neben **"System.xaml"** aus der **Suchergebnisse** Liste.</span><span class="sxs-lookup"><span data-stu-id="b3da5-130">Type **System.Xaml** into the **Search Assemblies** box, and check the checkbox beside **System.Xaml** from the **Search Results** list.</span></span>

8. <span data-ttu-id="b3da5-131">Klicken Sie auf **OK** schließen **Verweis-Manager** und die Verweise hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-131">Click **OK** to close **Reference Manager** and add the references.</span></span>

9. <span data-ttu-id="b3da5-132">Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-132">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Activities
    Imports System.Activities.Statements
    Imports System.Xaml
    Imports System.Reflection
    Imports System.IO
    Imports System.Activities.XamlIntegration
    Imports System.Activities.DynamicUpdate
    Imports System.Runtime.Serialization
    Imports Microsoft.VisualBasic.Activities
    ```

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    using System.IO;
    using System.Xaml;
    using System.Reflection;
    using System.Activities.XamlIntegration;
    using System.Activities.DynamicUpdate;
    using System.Runtime.Serialization;
    using Microsoft.CSharp.Activities;
    ```

10. <span data-ttu-id="b3da5-133">Fügen Sie der `Program`-Klasse (bzw. `Module1`) die folgenden beiden Zeichenfolgenmember hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-133">Add the following two string members to the `Program` class (or `Module1`).</span></span>

    ```vb
    Const mapPath = "..\..\..\PreviousVersions"
    Const definitionPath = "..\..\..\NumberGuessWorkflowActivities_du"
    ```

    ```csharp
    const string mapPath = @"..\..\..\PreviousVersions";
    const string definitionPath = @"..\..\..\NumberGuessWorkflowActivities_du";
    ```

11. <span data-ttu-id="b3da5-134">Fügen Sie der `StartUpdate`-Klasse (bzw. `Program`) die folgende `Module1`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-134">Add the following `StartUpdate` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="b3da5-135">Durch diese Methode wird die angegebene XAML-Workflowdefinition in einen `ActivityBuilder` geladen und dann `DynamicUpdate.PrepareForUpdate` aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-135">This method loads up the specified xaml workflow definition into an `ActivityBuilder`, and then calls `DynamicUpdate.PrepareForUpdate`.</span></span> <span data-ttu-id="b3da5-136">`PrepareForUpdate` erstellt eine Kopie der Workflowdefinition in `ActivityBuilder`.</span><span class="sxs-lookup"><span data-stu-id="b3da5-136">`PrepareForUpdate` makes a copy of the workflow definition inside the `ActivityBuilder`.</span></span> <span data-ttu-id="b3da5-137">Nachdem die Workflowdefinition geändert wurde, wird diese Kopie zusammen mit der geänderten Workflowdefinition verwendet, um die Updatezuordnung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-137">After the workflow definition is modified, this copy is used along with the modified workflow definition to create the update map.</span></span>

    ```vb
    Private Function StartUpdate(name As String) As ActivityBuilder
        'Create the XamlXmlReaderSettings.
        Dim readerSettings As XamlReaderSettings = New XamlXmlReaderSettings()
        'In the XAML the "local" namespace refers to artifacts that come from
        'the same project as the XAML. When loading XAML if the currently executing
        'assembly is not the same assembly that was referred to as "local" in the XAML
        'LocalAssembly must be set to the assembly containing the artifacts.
        'Assembly.LoadFile requires an absolute path so convert this relative path
        'to an absolute path.
        readerSettings.LocalAssembly = Assembly.LoadFile(
            Path.GetFullPath(Path.Combine(mapPath, "NumberGuessWorkflowActivities_v1.dll")))

        Dim fullPath As String = Path.Combine(definitionPath, name)
        Dim xamlReader As XamlXmlReader = New XamlXmlReader(fullPath, readerSettings)

        'Load the workflow definition into an ActivityBuilder.
        Dim wf As ActivityBuilder = XamlServices.Load(
            ActivityXamlServices.CreateBuilderReader(xamlReader))

        'PrepareForUpdate makes a copy of the workflow definition in the
        'ActivityBuilder that is used for comparison when the update
        'map is created.
        DynamicUpdateServices.PrepareForUpdate(wf)

        Return wf
    End Function
    ```

    ```csharp
    private static ActivityBuilder StartUpdate(string name)
    {
        // Create the XamlXmlReaderSettings.
        XamlXmlReaderSettings readerSettings = new XamlXmlReaderSettings()
        {
            // In the XAML the "local" namespace refers to artifacts that come from
            // the same project as the XAML. When loading XAML if the currently executing
            // assembly is not the same assembly that was referred to as "local" in the XAML
            // LocalAssembly must be set to the assembly containing the artifacts.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            LocalAssembly = Assembly.LoadFile(
                Path.GetFullPath(Path.Combine(mapPath, "NumberGuessWorkflowActivities_v1.dll")))
        };

        string path = Path.Combine(definitionPath, name);
        XamlXmlReader xamlReader = new XamlXmlReader(path, readerSettings);

        // Load the workflow definition into an ActivityBuilder.
        ActivityBuilder wf = XamlServices.Load(
            ActivityXamlServices.CreateBuilderReader(xamlReader))
            as ActivityBuilder;

        // PrepareForUpdate makes a copy of the workflow definition in the
        // ActivityBuilder that is used for comparison when the update
        // map is created.
        DynamicUpdateServices.PrepareForUpdate(wf);

        return wf;
    }
    ```

12. <span data-ttu-id="b3da5-138">Als Nächstes fügen Sie der `CreateUpdateMethod`-Klasse (bzw. `Program`) die folgende `Module1` hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-138">Next, add the following `CreateUpdateMethod` to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="b3da5-139">Dadurch wird durch Aufrufen von DynamicUpdateServices.CreateUpdateMap eine dynamische Updatezuordnung erstellt und unter dem angegebenen Namen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b3da5-139">This creates a dynamic update map by calling DynamicUpdateServices.CreateUpdateMap, and then saves the update map using the specified name.</span></span> <span data-ttu-id="b3da5-140">Diese Updatezuordnung enthält die Informationen, die von der Workflowlaufzeit zur Aktualisierung einer persistenten Workflowinstanz benötigt werden, die mithilfe der ursprünglichen, in `ActivityBuilder` enthaltenen Workflowdefinition gestartet wurde. Die Instanz kann so mithilfe der aktualisierten Workflowdefinition abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="b3da5-140">This update map contains the information needed by the workflow runtime to update a persisted workflow instance that was started using the original workflow definition contained in the `ActivityBuilder` so that it completes using the updated workflow definition.</span></span>

    ```vb
    Private Sub CreateUpdateMaps(wf As ActivityBuilder, name As String)
        'Create the UpdateMap.
        Dim map As DynamicUpdateMap =
            DynamicUpdateServices.CreateUpdateMap(wf)

        'Serialize it to a file.
        Dim mapFullPath As String = Path.Combine(mapPath, name)
        Dim sz As DataContractSerializer = New DataContractSerializer(GetType(DynamicUpdateMap))
        Using fs As FileStream = File.Open(mapFullPath, FileMode.Create)
            sz.WriteObject(fs, map)
        End Using
    End Sub
    ```

    ```csharp
    private static void CreateUpdateMaps(ActivityBuilder wf, string name)
    {
        // Create the UpdateMap.
        DynamicUpdateMap map =
            DynamicUpdateServices.CreateUpdateMap(wf);

        // Serialize it to a file.
        string path = Path.Combine(mapPath, name);
        DataContractSerializer sz = new DataContractSerializer(typeof(DynamicUpdateMap));
        using (FileStream fs = System.IO.File.Open(path, FileMode.Create))
        {
            sz.WriteObject(fs, map);
        }
    }
    ```

13. <span data-ttu-id="b3da5-141">Fügen Sie der `SaveUpdatedDefinition`-Klasse (bzw. `Program`) die folgende `Module1`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-141">Add the following `SaveUpdatedDefinition` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="b3da5-142">Durch diese Methode wird die aktualisierte Workflowdefinition gespeichert, nachdem die Updatezuordnung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b3da5-142">This method saves the updated workflow definition once the update map is created.</span></span>

    ```vb
    Private Sub SaveUpdatedDefinition(wf As ActivityBuilder, name As String)
        Dim xamlPath As String = Path.Combine(definitionPath, name)
        Dim sw As StreamWriter = File.CreateText(xamlPath)
        Dim xw As XamlWriter = ActivityXamlServices.CreateBuilderWriter(
            New XamlXmlWriter(sw, New XamlSchemaContext()))
        XamlServices.Save(xw, wf)
        sw.Close()
    End Sub
    ```

    ```csharp
    private static void SaveUpdatedDefinition(ActivityBuilder wf, string name)
    {
        string xamlPath = Path.Combine(definitionPath, name);
        StreamWriter sw = File.CreateText(xamlPath);
        XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(
            new XamlXmlWriter(sw, new XamlSchemaContext()));
        XamlServices.Save(xw, wf);
        sw.Close();
    }
    ```

### <a name="BKMK_StateMachine"></a> <span data-ttu-id="b3da5-143">So aktualisieren Sie StateMachineNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="b3da5-143">To update StateMachineNumberGuessWorkflow</span></span>

1. <span data-ttu-id="b3da5-144">Fügen Sie der `CreateStateMachineUpdateMap`-Klasse (bzw. `Program`) eine `Module1` hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-144">Add a `CreateStateMachineUpdateMap` to the `Program` class (or `Module1`).</span></span>

    ```vb
    Private Sub CreateStateMachineUpdateMap()

    End Sub
    ```

    ```csharp
    private static void CreateStateMachineUpdateMap()
    {
    }
    ```

2. <span data-ttu-id="b3da5-145">Rufen Sie `StartUpdate` auf, und rufen Sie anschließend einen Verweis auf die `StateMachine`-Stammaktivität des Workflows ab.</span><span class="sxs-lookup"><span data-stu-id="b3da5-145">Make a call to `StartUpdate` and then get a reference to the root `StateMachine` activity of the workflow.</span></span>

    ```vb
    Dim wf As ActivityBuilder = StartUpdate("StateMachineNumberGuessWorkflow.xaml")

    'Get a reference to the root StateMachine activity.
    Dim sm As StateMachine = wf.Implementation
    ```

    ```csharp
    ActivityBuilder wf = StartUpdate("StateMachineNumberGuessWorkflow.xaml");

    // Get a reference to the root StateMachine activity.
    StateMachine sm = wf.Implementation as StateMachine;
    ```

3. <span data-ttu-id="b3da5-146">Als Nächstes aktualisieren Sie die Ausdrücke der beiden `WriteLine` Aktivitäten, die anzeigen, ob der Schätzwert des Benutzers ist zu hoch oder zu niedrig, damit diese übereinstimmen, dass die Updates im [Vorgehensweise: Hosten mehrerer Workflowversionen zu einem Workflow Seite-an-Seite](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span><span class="sxs-lookup"><span data-stu-id="b3da5-146">Next, update the expressions of the two `WriteLine` activities that display whether the user's guess is too high or too low so that they match the updates made in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

    ```vb
    'Update the Text of the two WriteLine activities that write the
    'results of the user's guess. They are contained in the workflow as the
    'Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
    Dim guessLow As Statements.If = sm.States(1).Transitions(1).Action

    'Update the "too low" message.
    Dim tooLow As WriteLine = guessLow.Then
    tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")

    'Update the "too high" message.
    Dim tooHigh As WriteLine = guessLow.Else
    tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")
    ```

    ```csharp
    // Update the Text of the two WriteLine activities that write the
    // results of the user's guess. They are contained in the workflow as the
    // Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
    If guessLow = sm.States[1].Transitions[1].Action as If;

    // Update the "too low" message.
    WriteLine tooLow = guessLow.Then as WriteLine;
    tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");

    // Update the "too high" message.
    WriteLine tooHigh = guessLow.Else as WriteLine;
    tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");
    ```

4. <span data-ttu-id="b3da5-147">Als Nächstes fügen Sie die neue `WriteLine`-Aktivität hinzu, durch die die abschließende Meldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b3da5-147">Next, add the new `WriteLine` activity that displays the closing message.</span></span>

    ```vb
    'Create the new WriteLine that displays the closing message.
    Dim wl As New WriteLine() With
    {
        .Text = New VisualBasicValue(Of String) _
            ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
    }

    'Add it as the Action for the Guess Correct transition. The Guess Correct
    'transition is the first transition of States[1]. The transitions are listed
    'at the bottom of the State activity designer.
    sm.States(1).Transitions(0).Action = wl
    ```

    ```csharp
    // Create the new WriteLine that displays the closing message.
    WriteLine wl = new WriteLine
    {
        Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
    };

    // Add it as the Action for the Guess Correct transition. The Guess Correct
    // transition is the first transition of States[1]. The transitions are listed
    // at the bottom of the State activity designer.
    sm.States[1].Transitions[0].Action = wl;
    ```

5. <span data-ttu-id="b3da5-148">Nach der Aktualisierung des Workflows rufen Sie `CreateUpdateMaps` und `SaveUpdatedDefinition` auf.</span><span class="sxs-lookup"><span data-stu-id="b3da5-148">After the workflow is updated, call `CreateUpdateMaps` and `SaveUpdatedDefinition`.</span></span> <span data-ttu-id="b3da5-149">Durch `CreateUpdateMaps` wird `DynamicUpdateMap` erstellt und gespeichert, und durch `SaveUpdatedDefinition` wird die aktualisierte Workflowdefinition gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b3da5-149">`CreateUpdateMaps` creates and saves the `DynamicUpdateMap`, and `SaveUpdatedDefinition` saves the updated workflow definition.</span></span>

    ```vb
    'Create the update map.
    CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map")

    'Save the updated workflow definition.
    SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml")
    ```

    ```csharp
    // Create the update map.
    CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map");

    // Save the updated workflow definition.
    SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml");
    ```

    <span data-ttu-id="b3da5-150">Im folgenden Beispiel ist die abgeschlossene `CreateStateMachineUpdateMap`-Methode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b3da5-150">The following example is the completed `CreateStateMachineUpdateMap` method.</span></span>

    ```vb
    Private Sub CreateStateMachineUpdateMap()
        Dim wf As ActivityBuilder = StartUpdate("StateMachineNumberGuessWorkflow.xaml")

        'Get a reference to the root StateMachine activity.
        Dim sm As StateMachine = wf.Implementation

        'Update the Text of the two WriteLine activities that write the
        'results of the user's guess. They are contained in the workflow as the
        'Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
        Dim guessLow As Statements.If = sm.States(1).Transitions(1).Action

        'Update the "too low" message.
        Dim tooLow As WriteLine = guessLow.Then
        tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")

        'Update the "too high" message.
        Dim tooHigh As WriteLine = guessLow.Else
        tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")

        'Create the new WriteLine that displays the closing message.
        Dim wl As New WriteLine() With
        {
            .Text = New VisualBasicValue(Of String) _
                ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
        }

        'Add it as the Action for the Guess Correct transition. The Guess Correct
        'transition is the first transition of States[1]. The transitions are listed
        'at the bottom of the State activity designer.
        sm.States(1).Transitions(0).Action = wl

        'Create the update map.
        CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map")

        'Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml")
    End Sub
    ```

    ```csharp
    private static void CreateStateMachineUpdateMap()
    {
        ActivityBuilder wf = StartUpdate("StateMachineNumberGuessWorkflow.xaml");

        // Get a reference to the root StateMachine activity.
        StateMachine sm = wf.Implementation as StateMachine;

        // Update the Text of the two WriteLine activities that write the
        // results of the user's guess. They are contained in the workflow as the
        // Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
        If guessLow = sm.States[1].Transitions[1].Action as If;

        // Update the "too low" message.
        WriteLine tooLow = guessLow.Then as WriteLine;
        tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");

        // Update the "too high" message.
        WriteLine tooHigh = guessLow.Else as WriteLine;
        tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");

        // Create the new WriteLine that displays the closing message.
        WriteLine wl = new WriteLine
        {
            Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
        };

        // Add it as the Action for the Guess Correct transition. The Guess Correct
        // transition is the first transition of States[1]. The transitions are listed
        // at the bottom of the State activity designer.
        sm.States[1].Transitions[0].Action = wl;

        // Create the update map.
        CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map");

        // Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml");
    }
    ```

### <a name="BKMK_Flowchart"></a> <span data-ttu-id="b3da5-151">So aktualisieren Sie FlowchartNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="b3da5-151">To update FlowchartNumberGuessWorkflow</span></span>

1. <span data-ttu-id="b3da5-152">Fügen Sie der `CreateFlowchartUpdateMethod`-Klasse (bzw. `Program`) die folgende `Module1` hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-152">Add the following `CreateFlowchartUpdateMethod` to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="b3da5-153">Diese Methode ist vergleichbar mit `CreateStateMachineUpdateMap`.</span><span class="sxs-lookup"><span data-stu-id="b3da5-153">This method is similar to `CreateStateMachineUpdateMap`.</span></span> <span data-ttu-id="b3da5-154">Sie beginnt mit einem Aufruf von `StartUpdate`, aktualisiert die Definition des Flussdiagrammworkflows und endet mit dem Speichern der Updatezuordnung und der aktualisierten Workflowdefinition.</span><span class="sxs-lookup"><span data-stu-id="b3da5-154">It starts with a call to `StartUpdate`, updates the flowchart workflow definition, and finishes by saving the update map and the updated workflow definition.</span></span>

    ```vb
    Private Sub CreateFlowchartUpdateMap()
        Dim wf As ActivityBuilder = StartUpdate("FlowchartNumberGuessWorkflow.xaml")

        'Get a reference to the root Flowchart activity.
        Dim fc As Flowchart = wf.Implementation

        'Update the Text of the two WriteLine activities that write the
        'results of the user's guess. They are contained in the workflow as the
        'True and False action of the "Guess < Target" FlowDecision, which is
        'Nodes[4].
        Dim guessLow As FlowDecision = fc.Nodes(4)

        'Update the "too low" message.
        Dim trueStep As FlowStep = guessLow.True
        Dim tooLow As WriteLine = trueStep.Action
        tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")

        'Update the "too high" message.
        Dim falseStep As FlowStep = guessLow.False
        Dim tooHigh As WriteLine = falseStep.Action
        tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")

        'Create the new WriteLine that displays the closing message.
        Dim wl As New WriteLine() With
        {
            .Text = New VisualBasicValue(Of String) _
                ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
        }

        'Create a FlowStep to hold the WriteLine.
        Dim closingStep As New FlowStep() With
        {
            .Action = wl
        }

        'Add this new FlowStep to the True action of the
        '"Guess = Guess" FlowDecision
        Dim guessCorrect As FlowDecision = fc.Nodes(3)
        guessCorrect.True = closingStep

        'Add the new FlowStep to the Nodes collection.
        'If closingStep was replacing an existing node then
        'we would need to remove that Step from the collection.
        'In this example there was no existing True step to remove.
        fc.Nodes.Add(closingStep)

        'Create the update map.
        CreateUpdateMaps(wf, "FlowchartNumberGuessWorkflow.map")

        'Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "FlowchartNumberGuessWorkflow_du.xaml")
    End Sub
    ```

    ```csharp
    private static void CreateFlowchartUpdateMap()
    {
        ActivityBuilder wf = StartUpdate("FlowchartNumberGuessWorkflow.xaml");

        // Get a reference to the root Flowchart activity.
        Flowchart fc = wf.Implementation as Flowchart;

        // Update the Text of the two WriteLine activities that write the
        // results of the user's guess. They are contained in the workflow as the
        // True and False action of the "Guess < Target" FlowDecision, which is
        // Nodes[4].
        FlowDecision guessLow = fc.Nodes[4] as FlowDecision;

        // Update the "too low" message.
        FlowStep trueStep = guessLow.True as FlowStep;
        WriteLine tooLow = trueStep.Action as WriteLine;
        tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");

        // Update the "too high" message.
        FlowStep falseStep = guessLow.False as FlowStep;
        WriteLine tooHigh = falseStep.Action as WriteLine;
        tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");

        // Add the new WriteLine that displays the closing message.
        WriteLine wl = new WriteLine
        {
            Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
        };

        // Create a FlowStep to hold the WriteLine.
        FlowStep closingStep = new FlowStep
        {
            Action = wl
        };

        // Add this new FlowStep to the True action of the
        // "Guess == Guess" FlowDecision
        FlowDecision guessCorrect = fc.Nodes[3] as FlowDecision;
        guessCorrect.True = closingStep;

        // Add the new FlowStep to the Nodes collection.
        // If closingStep was replacing an existing node then
        // we would need to remove that Step from the collection.
        // In this example there was no existing True step to remove.
        fc.Nodes.Add(closingStep);

        // Create the update map.
        CreateUpdateMaps(wf, "FlowchartNumberGuessWorkflow.map");

        //  Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "FlowchartNumberGuessWorkflow_du.xaml");
    }
    ```

### <a name="BKMK_Sequential"></a> <span data-ttu-id="b3da5-155">So aktualisieren Sie SequentialNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="b3da5-155">To update SequentialNumberGuessWorkflow</span></span>

1. <span data-ttu-id="b3da5-156">Fügen Sie der `CreateSequentialUpdateMethod`-Klasse (bzw. `Program`) die folgende `Module1` hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-156">Add the following `CreateSequentialUpdateMethod` to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="b3da5-157">Diese Methode ist vergleichbar mit den anderen beiden Methoden.</span><span class="sxs-lookup"><span data-stu-id="b3da5-157">This method is similar to the other two methods.</span></span> <span data-ttu-id="b3da5-158">Sie beginnt mit einem Aufruf von `StartUpdate`, aktualisiert die Definition des sequenziellen Workflows und endet mit dem Speichern der Updatezuordnung und der aktualisierten Workflowdefinition.</span><span class="sxs-lookup"><span data-stu-id="b3da5-158">It starts with a call to `StartUpdate`, updates the sequential workflow definition, and finishes by saving the update map and the updated workflow definition.</span></span>

    ```vb
    Private Sub CreateSequentialUpdateMap()
        Dim wf As ActivityBuilder = StartUpdate("SequentialNumberGuessWorkflow.xaml")

        'Get a reference to the root activity in the workflow.
        Dim rootSequence As Sequence = wf.Implementation

        'Update the Text of the two WriteLine activities that write the
        'results of the user's guess. They are contained in the workflow as the
        'Then and Else action of the "Guess < Target" If activity.
        'Sequence[1]->DoWhile->Body->Sequence[2]->If->Then->If
        Dim gameLoop As Statements.DoWhile = rootSequence.Activities(1)
        Dim gameBody As Sequence = gameLoop.Body
        Dim guessCorrect As Statements.If = gameBody.Activities(2)
        Dim guessLow As Statements.If = guessCorrect.Then
        Dim tooLow As WriteLine = guessLow.Then
        tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")
        Dim tooHigh As WriteLine = guessLow.Else
        tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")

        'Create the new WriteLine that displays the closing message.
        Dim wl As New WriteLine() With
        {
            .Text = New VisualBasicValue(Of String) _
                ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
        }

        'Insert it as the third activity in the root sequence
        rootSequence.Activities.Insert(2, wl)

        'Create the update map.
        CreateUpdateMaps(wf, "SequentialNumberGuessWorkflow.map")

        'Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "SequentialNumberGuessWorkflow_du.xaml")
    End Sub
    ```

    ```csharp
    private static void CreateSequentialUpdateMap()
    {
        ActivityBuilder wf = StartUpdate("SequentialNumberGuessWorkflow.xaml");

        // Get a reference to the root activity in the workflow.
        Sequence rootSequence = wf.Implementation as Sequence;

        // Update the Text of the two WriteLine activities that write the
        // results of the user's guess. They are contained in the workflow as the
        // Then and Else action of the "Guess < Target" If activity.
        // Sequence[1]->DoWhile->Body->Sequence[2]->If->Then->If
        DoWhile gameLoop = rootSequence.Activities[1] as DoWhile;
        Sequence gameBody = gameLoop.Body as Sequence;
        If guessCorrect = gameBody.Activities[2] as If;
        If guessLow = guessCorrect.Then as If;
        WriteLine tooLow = guessLow.Then as WriteLine;
        tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");
        WriteLine tooHigh = guessLow.Else as WriteLine;
        tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");

        // Add the new WriteLine that displays the closing message.
        WriteLine wl = new WriteLine
        {
            Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
        };

        // Insert it as the third activity in the root sequence
        rootSequence.Activities.Insert(2, wl);

        // Create the update map.
        CreateUpdateMaps(wf, "SequentialNumberGuessWorkflow.map");

        // Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "SequentialNumberGuessWorkflow_du.xaml");
    }
    ```

### <a name="BKMK_CreateUpdateMaps"></a> <span data-ttu-id="b3da5-159">So erstellen und führen die CreateUpdateMaps-Anwendung</span><span class="sxs-lookup"><span data-stu-id="b3da5-159">To build and run the CreateUpdateMaps application</span></span>

1. <span data-ttu-id="b3da5-160">Aktualisieren Sie die `Main`-Methode, und fügen Sie die folgenden drei Methodenaufrufe hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-160">Update the `Main` method and add the following three method calls.</span></span> <span data-ttu-id="b3da5-161">Diese Methoden werden in den folgenden Abschnitten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b3da5-161">These methods are added in the following sections.</span></span> <span data-ttu-id="b3da5-162">Durch jede Methode wird der entsprechende Workflow für das Schätzen von Zahlen aktualisiert und eine `DynamicUpdateMap` erstellt, die die Updates beschreibt.</span><span class="sxs-lookup"><span data-stu-id="b3da5-162">Each method updates the corresponding number guess workflow and creates a `DynamicUpdateMap` that describes the updates.</span></span>

    ```vb
    Sub Main()
        'Create the update maps for the changes needed to the v1 activities
        'so they match the v2 activities.
        CreateSequentialUpdateMap()
        CreateFlowchartUpdateMap()
        CreateStateMachineUpdateMap()
    End Sub
    ```

    ```csharp
    static void Main(string[] args)
    {
        // Create the update maps for the changes needed to the v1 activities
        // so they match the v2 activities.
        CreateSequentialUpdateMap();
        CreateFlowchartUpdateMap();
        CreateStateMachineUpdateMap();
    }
    ```

2. <span data-ttu-id="b3da5-163">Mit der rechten Maustaste **CreateUpdateMaps** in **Projektmappen-Explorer** , und wählen Sie **als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-163">Right-click **CreateUpdateMaps** in **Solution Explorer** and choose **Set as StartUp Project**.</span></span>

3. <span data-ttu-id="b3da5-164">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen, und dann STRG+F5, um die `CreateUpdateMaps`-Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-164">Press CTRL+SHIFT+B to build the solution, and then CTRL+F5 to run the `CreateUpdateMaps` application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3da5-165">Die `CreateUpdateMaps` Anwendung zeigt keine keine Statusinformationen während der Ausführung jedoch der **NumberGuessWorkflowActivities_du** Ordner und die **PreviousVersions** Ordner wird angezeigt die aktualisierte Workflowdefinitions-Definitionsdateien und die updatezuordnungen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-165">The `CreateUpdateMaps` application does not display any status information while running, but if you look in the **NumberGuessWorkflowActivities_du** folder and the **PreviousVersions** folder you will see the updated workflow definition files and the update maps.</span></span>

    <span data-ttu-id="b3da5-166">Sobald die Updatezuordnungen erstellt und die Workflowdefinitionen aktualisiert sind, besteht der nächste Schritt darin, eine aktualisierte Workflowassembly zu erstellen, in der die aktualisierten Definitionen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b3da5-166">Once the update maps are created and the workflow definitions updated, the next step is to build an updated workflow assembly containing the updated definitions.</span></span>

### <a name="BKMK_BuildAssembly"></a> <span data-ttu-id="b3da5-167">Um die aktualisierte Workflowassembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-167">To build the updated workflow assembly</span></span>

1. <span data-ttu-id="b3da5-168">Öffnen Sie eine zweite Instanz von Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="b3da5-168">Open a second instance of Visual Studio 2012.</span></span>

2. <span data-ttu-id="b3da5-169">Wählen Sie **öffnen**, **Projekt/Projektmappe** aus der **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="b3da5-169">Choose **Open**, **Project/Solution** from the **File** menu.</span></span>

3. <span data-ttu-id="b3da5-170">Navigieren Sie zu der **NumberGuessWorkflowActivities_du** im erstellten Ordner [Vorgehensweise: Hosten mehrerer Workflowversionen zu einem Workflow Seite-an-Seite](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)Option **NumberGuessWorkflowActivities.csproj** (oder **Vbproj**), und klicken Sie auf **öffnen**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-170">Navigate to the **NumberGuessWorkflowActivities_du** folder you created in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md), select **NumberGuessWorkflowActivities.csproj** (or **vbproj**), and click **Open**.</span></span>

4. <span data-ttu-id="b3da5-171">In **Projektmappen-Explorer**, klicken Sie mit der rechten Maustaste auf **SequentialNumberGuessWorkflow.xaml** , und wählen Sie **aus Projekt ausschließen**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-171">In **Solution Explorer**, right click **SequentialNumberGuessWorkflow.xaml** and choose **Exclude From Project**.</span></span> <span data-ttu-id="b3da5-172">Führen Sie dieselben Schritte für **FlowchartNumberGuessWorkflow.xaml** und **StateMachineNumberGuessWorkflow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-172">Do the same thing for **FlowchartNumberGuessWorkflow.xaml** and **StateMachineNumberGuessWorkflow.xaml**.</span></span> <span data-ttu-id="b3da5-173">Durch diesen Schritt werden die Vorgängerversionen der Workflowdefinitionen aus dem Projekt entfernt.</span><span class="sxs-lookup"><span data-stu-id="b3da5-173">This step removes the previous versions of the workflow definitions from the project.</span></span>

5. <span data-ttu-id="b3da5-174">Wählen Sie **vorhandenes Element hinzufügen** aus der **Projekt** Menü.</span><span class="sxs-lookup"><span data-stu-id="b3da5-174">Choose **Add Existing Item** from the **Project** menu.</span></span>

6. <span data-ttu-id="b3da5-175">Navigieren Sie zu der **NumberGuessWorkflowActivities_du** im erstellten Ordner [Vorgehensweise: Hosten mehrerer Workflowversionen zu einem Workflow Seite-an-Seite](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span><span class="sxs-lookup"><span data-stu-id="b3da5-175">Navigate to the **NumberGuessWorkflowActivities_du** folder you created in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

7. <span data-ttu-id="b3da5-176">Wählen Sie **XAML-Dateien (\*.xaml;\*. Xoml)** aus der **Dateityp** Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="b3da5-176">Choose **XAML Files (\*.xaml;\*.xoml)** from the **Files of type** drop-down list.</span></span>

8. <span data-ttu-id="b3da5-177">Wählen Sie **SequentialNumberGuessWorkflow_du.xaml**, **FlowchartNumberGuessWorkflow_du.xaml**, und **StateMachineNumberGuessWorkflow_du.xaml** , und klicken Sie auf  **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-177">Select **SequentialNumberGuessWorkflow_du.xaml**, **FlowchartNumberGuessWorkflow_du.xaml**, and **StateMachineNumberGuessWorkflow_du.xaml** and click **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3da5-178">Klicken Sie mit gedrückter STRG-TASTE, um mehrere Elemente gleichzeitig auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-178">CTRL+Click to select multiple items at a time.</span></span>

    <span data-ttu-id="b3da5-179">Durch diesen Schritt werden dem Projekt die aktualisierten Versionen der Workflowdefinitionen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b3da5-179">This step adds the updated versions of the workflow definitions to the project.</span></span>

9. <span data-ttu-id="b3da5-180">Drücken Sie STRG+UMSCHALT+B, um das Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-180">Press CTRL+SHIFT+B to build the project.</span></span>

10. <span data-ttu-id="b3da5-181">Wählen Sie **Projektmappe schließen** aus der **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="b3da5-181">Choose **Close Solution** from the **File** menu.</span></span> <span data-ttu-id="b3da5-182">Eine Projektmappendatei für das Projekt ist nicht erforderlich ist, klicken Sie daher auf **keine** zu Visual Studio zu schließen, ohne zu eine Projektmappendatei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b3da5-182">A solution file for the project is not required, so click **No** to close Visual Studio without saving a solution file.</span></span> <span data-ttu-id="b3da5-183">Wählen Sie **beenden** aus der **Datei** Menü, um Visual Studio zu schließen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-183">Choose **Exit** from the **File** menu to close Visual Studio.</span></span>

11. <span data-ttu-id="b3da5-184">Öffnen Sie Windows Explorer, und navigieren Sie zu der **NumberGuessWorkflowActivities_du\bin\Debug** Ordner (oder **"bin\Release"** je nach den projekteinstellungen).</span><span class="sxs-lookup"><span data-stu-id="b3da5-184">Open Windows Explorer and navigate to the **NumberGuessWorkflowActivities_du\bin\Debug** folder (or **bin\Release** depending on your project settings).</span></span>

12. <span data-ttu-id="b3da5-185">Benennen Sie **NumberGuessWorkflowActivities.dll** zu **NumberGuessWorkflowActivities_v15.dll**, und kopieren Sie sie in der **PreviousVersions** Ordner, die Sie erstellt, im haben[Vorgehensweise: Hosten mehrerer Workflowversionen zu einem Workflow Seite-an-Seite](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span><span class="sxs-lookup"><span data-stu-id="b3da5-185">Rename **NumberGuessWorkflowActivities.dll** to **NumberGuessWorkflowActivities_v15.dll**, and copy it to the **PreviousVersions** folder you created in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

### <a name="BKMK_UpdateWorkflowVersionMap"></a> <span data-ttu-id="b3da5-186">So aktualisieren Sie WorkflowVersionMap anhand der neuen Versionen</span><span class="sxs-lookup"><span data-stu-id="b3da5-186">To update WorkflowVersionMap with the new versions</span></span>

1. <span data-ttu-id="b3da5-187">Wechseln Sie zurück zur ursprünglichen Instanz von Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="b3da5-187">Switch back to the initial instance of Visual Studio 2012.</span></span>

2. <span data-ttu-id="b3da5-188">Doppelklicken Sie auf **WorkflowVersionMap.cs** (oder **WorkflowVersionMap.vb**) unter den **NumberGuessWorkflowHost** Projekt, um ihn zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-188">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>

3. <span data-ttu-id="b3da5-189">Fügen Sie direkt unterhalb der sechs vorhandenen Deklarationen für Workflowidentitäten drei neue Workflowidentitäten hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-189">Add three new workflow identities just below the six existing workflow identity declarations.</span></span> <span data-ttu-id="b3da5-190">In diesem Lernprogramm wird `1.5.0.0` als `WorkflowIdentity.Version` für die dynamischen Updateidentitäten verwendet.</span><span class="sxs-lookup"><span data-stu-id="b3da5-190">In this tutorial, `1.5.0.0` is used as the `WorkflowIdentity.Version` for the dynamic update identities.</span></span> <span data-ttu-id="b3da5-191">Diese neuen `v15`-Workflowidentitäten werden verwendet, um die richtige Workflowdefinition für die dynamisch aktualisierten, persistenten Workflowinstanzen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-191">These new `v15` workflow identities will be used provide the correct workflow definition for the dynamically updated persisted workflow instances.</span></span>

    ```vb
    'Current version identities.
    Public StateMachineNumberGuessIdentity As WorkflowIdentity
    Public FlowchartNumberGuessIdentity As WorkflowIdentity
    Public SequentialNumberGuessIdentity As WorkflowIdentity

    'v1 identities.
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity

    'v1.5 (Dynamic Update) identities.
    Public StateMachineNumberGuessIdentity_v15 As WorkflowIdentity
    Public FlowchartNumberGuessIdentity_v15 As WorkflowIdentity
    Public SequentialNumberGuessIdentity_v15 As WorkflowIdentity
    ```

    ```csharp
    // Current version identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity;
    static public WorkflowIdentity FlowchartNumberGuessIdentity;
    static public WorkflowIdentity SequentialNumberGuessIdentity;

    // v1 identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;
    static public WorkflowIdentity SequentialNumberGuessIdentity_v1;

    // v1.5 (Dynamic Update) identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v15;
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v15;
    static public WorkflowIdentity SequentialNumberGuessIdentity_v15;
    ```

4. <span data-ttu-id="b3da5-192">Fügen Sie den folgenden Code am Ende des Konstruktors hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-192">Add the following code at the end of the constructor.</span></span> <span data-ttu-id="b3da5-193">Durch diesen Code werden die Workflowidentitäten für dynamische Updates initialisiert, die entsprechenden Workflowdefinitionen geladen und dem Wörterbuch der Workflowversionen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b3da5-193">This code initializes the dynamic update workflow identities, loads the corresponding workflow definitions, and adds them to the workflow version dictionary.</span></span>

    ```vb
    'Initialize the dynamic update workflow identities.
    StateMachineNumberGuessIdentity_v15 = New WorkflowIdentity With
    {
        .Name = "StateMachineNumberGuessWorkflow",
        .Version = New Version(1, 5, 0, 0)
    }

    FlowchartNumberGuessIdentity_v15 = New WorkflowIdentity With
    {
        .Name = "FlowchartNumberGuessWorkflow",
        .Version = New Version(1, 5, 0, 0)
    }

    SequentialNumberGuessIdentity_v15 = New WorkflowIdentity With
    {
        .Name = "SequentialNumberGuessWorkflow",
        .Version = New Version(1, 5, 0, 0)
    }

    'Add the dynamic update workflow identities to the dictionary along with
    'the corresponding workflow definitions loaded from the v15 assembly.
    'Assembly.LoadFile requires an absolute path so convert this relative path
    'to an absolute path.
    Dim v15AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll"
    v15AssemblyPath = Path.GetFullPath(v15AssemblyPath)
    Dim v15Assembly As Assembly = Assembly.LoadFile(v15AssemblyPath)

    map.Add(StateMachineNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

    map.Add(SequentialNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

    map.Add(FlowchartNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
    ```

    ```csharp
    // Initialize the dynamic update workflow identities.
    StateMachineNumberGuessIdentity_v15 = new WorkflowIdentity
    {
        Name = "StateMachineNumberGuessWorkflow",
        Version = new Version(1, 5, 0, 0)
    };

    FlowchartNumberGuessIdentity_v15 = new WorkflowIdentity
    {
        Name = "FlowchartNumberGuessWorkflow",
        Version = new Version(1, 5, 0, 0)
    };

    SequentialNumberGuessIdentity_v15 = new WorkflowIdentity
    {
        Name = "SequentialNumberGuessWorkflow",
        Version = new Version(1, 5, 0, 0)
    };

    // Add the dynamic update workflow identities to the dictionary along with
    // the corresponding workflow definitions loaded from the v15 assembly.
    // Assembly.LoadFile requires an absolute path so convert this relative path
    // to an absolute path.
    string v15AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll";
    v15AssemblyPath = Path.GetFullPath(v15AssemblyPath);
    Assembly v15Assembly = Assembly.LoadFile(v15AssemblyPath);

    map.Add(StateMachineNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

    map.Add(SequentialNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

    map.Add(FlowchartNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
    ```

     <span data-ttu-id="b3da5-194">Im folgenden Beispiel ist die abgeschlossene `WorkflowVersionMap`-Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b3da5-194">The following example is the completed `WorkflowVersionMap` class.</span></span>

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        'Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        'v1 identities.
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity

        'v1.5 (Dynamic Update) identities.
        Public StateMachineNumberGuessIdentity_v15 As WorkflowIdentity
        Public FlowchartNumberGuessIdentity_v15 As WorkflowIdentity
        Public SequentialNumberGuessIdentity_v15 As WorkflowIdentity

        Sub New()
            map = New Dictionary(Of WorkflowIdentity, Activity)

            'Add the current workflow version identities.
            StateMachineNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            SequentialNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())

            'Initialize the previous workflow version identities.
            StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            'Add the previous version workflow identities to the dictionary along with
            'the corresponding workflow definitions loaded from the v1 assembly.
            'Assembly.LoadFile requires an absolute path so convert this relative path
            'to an absolute path.
            Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)
            Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)

            map.Add(StateMachineNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

            map.Add(SequentialNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

            map.Add(FlowchartNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))

            'Initialize the dynamic update workflow identities.
            StateMachineNumberGuessIdentity_v15 = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 5, 0, 0)
            }

            FlowchartNumberGuessIdentity_v15 = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 5, 0, 0)
            }

            SequentialNumberGuessIdentity_v15 = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 5, 0, 0)
            }

            'Add the dynamic update workflow identities to the dictionary along with
            'the corresponding workflow definitions loaded from the v15 assembly.
            'Assembly.LoadFile requires an absolute path so convert this relative path
            'to an absolute path.
            Dim v15AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll"
            v15AssemblyPath = Path.GetFullPath(v15AssemblyPath)
            Dim v15Assembly As Assembly = Assembly.LoadFile(v15AssemblyPath)

            map.Add(StateMachineNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

            map.Add(SequentialNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

            map.Add(FlowchartNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
        End Sub

        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity
            Return map(identity)
        End Function

        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String
            Return identity.ToString()
        End Function
    End Module
    ```

    ```csharp
    public static class WorkflowVersionMap
    {
        static Dictionary<WorkflowIdentity, Activity> map;

        // Current version identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity;
        static public WorkflowIdentity FlowchartNumberGuessIdentity;
        static public WorkflowIdentity SequentialNumberGuessIdentity;

        // v1 identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;
        static public WorkflowIdentity SequentialNumberGuessIdentity_v1;

        // v1.5 (Dynamic Update) identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v15;
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v15;
        static public WorkflowIdentity SequentialNumberGuessIdentity_v15;

        static WorkflowVersionMap()
        {
            map = new Dictionary<WorkflowIdentity, Activity>();

            // Add the current workflow version identities.
            StateMachineNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            SequentialNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());

            // Initialize the previous workflow version identities.
            StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            SequentialNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            // Add the previous version workflow identities to the dictionary along with
            // the corresponding workflow definitions loaded from the v1 assembly.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);
            Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);

            map.Add(StateMachineNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

            map.Add(SequentialNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

            map.Add(FlowchartNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);

            // Initialize the dynamic update workflow identities.
            StateMachineNumberGuessIdentity_v15 = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 5, 0, 0)
            };

            FlowchartNumberGuessIdentity_v15 = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 5, 0, 0)
            };

            SequentialNumberGuessIdentity_v15 = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 5, 0, 0)
            };

            // Add the dynamic update workflow identities to the dictionary along with
            // the corresponding workflow definitions loaded from the v15 assembly.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            string v15AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll";
            v15AssemblyPath = Path.GetFullPath(v15AssemblyPath);
            Assembly v15Assembly = Assembly.LoadFile(v15AssemblyPath);

            map.Add(StateMachineNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

            map.Add(SequentialNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

            map.Add(FlowchartNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
        }

        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)
        {
            return map[identity];
        }

        public static string GetIdentityDescription(WorkflowIdentity identity)
        {
            return identity.ToString();
        }
    }
    ```

5. <span data-ttu-id="b3da5-195">Drücken Sie STRG+UMSCHALT+B, um das Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-195">Press CTRL+SHIFT+B to build the project.</span></span>

### <a name="BKMK_ApplyUpdate"></a> <span data-ttu-id="b3da5-196">Die dynamische Updates</span><span class="sxs-lookup"><span data-stu-id="b3da5-196">To apply the dynamic updates</span></span>

1. <span data-ttu-id="b3da5-197">Mit der rechten Maustaste **WF45GettingStartedTutorial** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-197">Right-click **WF45GettingStartedTutorial** in **Solution Explorer** and choose **Add**, **New Project**.</span></span>

2. <span data-ttu-id="b3da5-198">In der **installiert** Knoten **Visual C#-**, **Windows** (oder **Visual Basic**, **Windows**).</span><span class="sxs-lookup"><span data-stu-id="b3da5-198">In the **Installed** node, select **Visual C#**, **Windows** (or **Visual Basic**, **Windows**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3da5-199">Je nachdem, welche Programmiersprache als die primäre Sprache in Visual Studio konfiguriert ist, befindet sich der Knoten **Visual C#** oder **Visual Basic** möglicherweise nicht unter dem Knoten **Andere Sprachen** im Knoten **Installiert** .</span><span class="sxs-lookup"><span data-stu-id="b3da5-199">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>

    <span data-ttu-id="b3da5-200">Stellen Sie sicher, dass in der Dropdownliste mit der .NET Framework-Version **.NET Framework 4.5** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="b3da5-200">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="b3da5-201">Wählen Sie **Konsolenanwendung** aus der **Windows** Liste.</span><span class="sxs-lookup"><span data-stu-id="b3da5-201">Select **Console Application** from the **Windows** list.</span></span> <span data-ttu-id="b3da5-202">Typ **ApplyDynamicUpdate** in die **Namen** ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-202">Type **ApplyDynamicUpdate** into the **Name** box and click **OK**.</span></span>

3. <span data-ttu-id="b3da5-203">Mit der rechten Maustaste **ApplyDynamicUpdate** in **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-203">Right-click **ApplyDynamicUpdate** in **Solution Explorer** and choose **Add Reference**.</span></span>

4. <span data-ttu-id="b3da5-204">Klicken Sie auf **Lösung** und aktivieren Sie das Kontrollkästchen neben **NumberGuessWorkflowHost**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-204">Click **Solution** and check the box next to **NumberGuessWorkflowHost**.</span></span> <span data-ttu-id="b3da5-205">Dieser Verweis ist erforderlich, damit `ApplyDynamicUpdate` die `NumberGuessWorkflowHost.WorkflowVersionMap`-Klasse verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="b3da5-205">This reference is needed so that `ApplyDynamicUpdate` can use the `NumberGuessWorkflowHost.WorkflowVersionMap` class.</span></span>

5. <span data-ttu-id="b3da5-206">Wählen Sie **Framework** aus der **Assemblys** Knoten in der **Verweis hinzufügen** Liste.</span><span class="sxs-lookup"><span data-stu-id="b3da5-206">Select **Framework** from the **Assemblies** node in the **Add Reference** list.</span></span> <span data-ttu-id="b3da5-207">Typ **System.Activities** in die **Assemblys suchen** Feld.</span><span class="sxs-lookup"><span data-stu-id="b3da5-207">Type **System.Activities** into the **Search Assemblies** box.</span></span> <span data-ttu-id="b3da5-208">Dadurch werden die Assemblys gefiltert, sodass die gewünschten Verweise einfacher auszuwählen sind.</span><span class="sxs-lookup"><span data-stu-id="b3da5-208">This will filter the assemblies and make the desired references easier to select.</span></span>

6. <span data-ttu-id="b3da5-209">Aktivieren Sie das Kontrollkästchen neben **System.Activities** aus der **Suchergebnisse** Liste.</span><span class="sxs-lookup"><span data-stu-id="b3da5-209">Check the checkbox beside **System.Activities** from the **Search Results** list.</span></span>

7. <span data-ttu-id="b3da5-210">Typ **Serialisierung** in die **Assemblys suchen** ein, und aktivieren Sie das Kontrollkästchen neben **System.Runtime.Serialization** aus der **Suchergebnisse**  Liste.</span><span class="sxs-lookup"><span data-stu-id="b3da5-210">Type **Serialization** into the **Search Assemblies** box, and check the checkbox beside **System.Runtime.Serialization** from the **Search Results** list.</span></span>

8. <span data-ttu-id="b3da5-211">Typ **DurableInstancing** in die **Assemblys suchen** ein, und aktivieren Sie das Kontrollkästchen neben **System.Activities.DurableInstancing** und  **System.Activities.DurableInstancing** aus der **Suchergebnisse** Liste.</span><span class="sxs-lookup"><span data-stu-id="b3da5-211">Type **DurableInstancing** into the **Search Assemblies** box, and check the checkbox beside **System.Activities.DurableInstancing** and **System.Runtime.DurableInstancing** from the **Search Results** list.</span></span>

9. <span data-ttu-id="b3da5-212">Klicken Sie auf **OK** schließen **Verweis-Manager** und die Verweise hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-212">Click **OK** to close **Reference Manager** and add the references.</span></span>

10. <span data-ttu-id="b3da5-213">Mit der rechten Maustaste **ApplyDynamicUpdate** im Projektmappen-Explorer, und wählen Sie **hinzufügen**, **Klasse**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-213">Right-click **ApplyDynamicUpdate** in Solution Explorer and choose **Add**, **Class**.</span></span> <span data-ttu-id="b3da5-214">Typ `DynamicUpdateInfo` in die **Namen** ein, und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-214">Type `DynamicUpdateInfo` into the **Name** box and click **Add**.</span></span>

11. <span data-ttu-id="b3da5-215">Fügen Sie der `DynamicUpdateInfo`-Klasse die beiden folgenden Member hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-215">Add the following two members to the `DynamicUpdateInfo` class.</span></span> <span data-ttu-id="b3da5-216">Im folgenden Beispiel ist die abgeschlossene `DynamicUpdateInfo`-Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b3da5-216">The following example is the completed `DynamicUpdateInfo` class.</span></span> <span data-ttu-id="b3da5-217">Diese Klasse enthält Informationen über die Updatezuordnung und die neue Workflowidentität, die zur Aktualisierung einer Workflowinstanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b3da5-217">This class contains information on the update map and new workflow identity used when a workflow instance is updated.</span></span>

    ```vb
    Public Class DynamicUpdateInfo
        Public updateMap As DynamicUpdateMap
        Public newIdentity As WorkflowIdentity
    End Class
    ```

    ```csharp
    class DynamicUpdateInfo
    {
        public DynamicUpdateMap updateMap;
        public WorkflowIdentity newIdentity;
    }
    ```

12. <span data-ttu-id="b3da5-218">Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-218">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Activities
    Imports System.Activities.DynamicUpdate
    ```

    ```csharp
    using System.Activities;
    using System.Activities.DynamicUpdate;
    ```

13. <span data-ttu-id="b3da5-219">Doppelklicken Sie auf **"Program.cs"** (oder **"Module1.vb"**) im Projektmappen-Explorer.</span><span class="sxs-lookup"><span data-stu-id="b3da5-219">Double-click **Program.cs** (or **Module1.vb**) in Solution Explorer.</span></span>

14. <span data-ttu-id="b3da5-220">Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-220">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports NumberGuessWorkflowHost
    Imports System.Data.SqlClient
    Imports System.Activities.DynamicUpdate
    Imports System.IO
    Imports System.Runtime.Serialization
    Imports System.Activities
    Imports System.Activities.DurableInstancing
    ```

    ```csharp
    using NumberGuessWorkflowHost;
    using System.Data;
    using System.Data.SqlClient;
    using System.Activities;
    using System.Activities.DynamicUpdate;
    using System.IO;
    using System.Runtime.Serialization;
    using System.Activities.DurableInstancing;
    ```

15. <span data-ttu-id="b3da5-221">Fügen Sie der `Program`-Klasse (bzw. `Module1`) den folgenden Verbindungszeichenfolgen-Member hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-221">Add the following connection string member to the `Program` class (or `Module1`).</span></span>

    ```vb
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"
    ```

    ```csharp
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";
    ```

    > [!NOTE]
    > <span data-ttu-id="b3da5-222">Abhängig von der SQL Server-Version kann der Servername der Verbindungszeichenfolge abweichen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-222">Depending on your edition of SQL Server, the connection string server name may be different.</span></span>

16. <span data-ttu-id="b3da5-223">Fügen Sie der `GetIDs`-Klasse (bzw. `Program`) die folgende `Module1`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-223">Add the following `GetIDs` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="b3da5-224">Durch diese Methode wird eine Liste der persistenten Workflowinstanz-IDs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b3da5-224">This method returns a list of persisted workflow instance ids.</span></span>

    ```vb
    Function GetIds() As IList(Of Guid)
        Dim Ids As New List(Of Guid)
        Dim localCmd = _
            String.Format("Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]")
        Using localCon = New SqlConnection(connectionString)
            Dim cmd As SqlCommand = localCon.CreateCommand()
            cmd.CommandText = localCmd
            localCon.Open()
            Using reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)
                While reader.Read()
                    'Get the InstanceId of the persisted Workflow
                    Dim id As Guid = Guid.Parse(reader(0).ToString())

                    'Add it to the list.
                    Ids.Add(id)
                End While
            End Using
        End Using

        Return Ids
    End Function
    ```

    ```csharp
    static IList<Guid> GetIds()
    {
        List<Guid> Ids = new List<Guid>();
        string localCmd = string.Format("Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]");
        using (SqlConnection localCon = new SqlConnection(connectionString))
        {
            SqlCommand cmd = localCon.CreateCommand();
            cmd.CommandText = localCmd;
            localCon.Open();
            using (SqlDataReader reader = cmd.ExecuteReader(CommandBehavior.CloseConnection))
            {
                while (reader.Read())
                {
                    // Get the InstanceId of the persisted Workflow
                    Guid id = Guid.Parse(reader[0].ToString());

                    // Add it to the list.
                    Ids.Add(id);
                }
            }
        }

        return Ids;
    }
    ```

17. <span data-ttu-id="b3da5-225">Fügen Sie der `LoadMap`-Klasse (bzw. `Program`) die folgende `Module1`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-225">Add the following `LoadMap` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="b3da5-226">Durch diese Methode wird ein Wörterbuch erstellt, durch das `v1`-Workflowidentitäten den Updatezuordnungen und neuen Workflowidentitäten zugeordnet werden, die zum Aktualisieren der entsprechenden persistenten Workflowinstanzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b3da5-226">This method creates a dictionary that maps `v1` workflow identities to the update maps and new workflow identities used to update the corresponding persisted workflow instances.</span></span>

    ```vb
    Function LoadMap(mapName As String) As DynamicUpdateMap
        Dim mapPath As String = Path.Combine("..\..\..\PreviousVersions", mapName)

        Dim map As DynamicUpdateMap
        Using fs As FileStream = File.Open(mapPath, FileMode.Open)
            Dim serializer As DataContractSerializer = New DataContractSerializer(GetType(DynamicUpdateMap))
            Dim updateMap = serializer.ReadObject(fs)
            If updateMap Is Nothing Then
                Throw New ApplicationException("DynamicUpdateMap is null.")
            End If

            map = updateMap
        End Using

        Return map
    End Function
    ```

    ```csharp
    static DynamicUpdateMap LoadMap(string mapName)
    {
        string path = Path.Combine(@"..\..\..\PreviousVersions", mapName);

        DynamicUpdateMap map;
        using (FileStream fs = File.Open(path, FileMode.Open))
        {
            DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));
            object updateMap = serializer.ReadObject(fs);
            if (updateMap == null)
            {
                throw new ApplicationException("DynamicUpdateMap is null.");
            }

            map = updateMap as DynamicUpdateMap;
        }

        return map;
    }
    ```

18. <span data-ttu-id="b3da5-227">Fügen Sie der `LoadMaps`-Klasse (bzw. `Program`) die folgende `Module1`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-227">Add the following `LoadMaps` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="b3da5-228">Durch diese Methode werden die drei Updatezuordnungen geladen und ein Wörterbuch erstellt, das den Updatezuordnungen `v1`-Workflowidentitäten zuordnet.</span><span class="sxs-lookup"><span data-stu-id="b3da5-228">This method loads the three update maps and creates a dictionary that maps `v1` workflow identities to the update maps.</span></span>

    ```vb
    Function LoadMaps() As IDictionary(Of WorkflowIdentity, DynamicUpdateInfo)
        'There are 3 update maps to describe the changes to update v1 workflows,
        'one for reach of the 3 workflow types in the tutorial.
        Dim maps = New Dictionary(Of WorkflowIdentity, DynamicUpdateInfo)()

        Dim sequentialMap As DynamicUpdateMap = LoadMap("SequentialNumberGuessWorkflow.map")
        Dim sequentialInfo = New DynamicUpdateInfo With
        {
            .updateMap = sequentialMap,
            .newIdentity = WorkflowVersionMap.SequentialNumberGuessIdentity_v15
        }
        maps.Add(WorkflowVersionMap.SequentialNumberGuessIdentity_v1, sequentialInfo)

        Dim stateMap As DynamicUpdateMap = LoadMap("StateMachineNumberGuessWorkflow.map")
        Dim stateInfo = New DynamicUpdateInfo With
        {
            .updateMap = stateMap,
            .newIdentity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v15
        }
        maps.Add(WorkflowVersionMap.StateMachineNumberGuessIdentity_v1, stateInfo)

        Dim flowchartMap As DynamicUpdateMap = LoadMap("FlowchartNumberGuessWorkflow.map")
        Dim flowchartInfo = New DynamicUpdateInfo With
        {
            .updateMap = flowchartMap,
            .newIdentity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v15
        }
        maps.Add(WorkflowVersionMap.FlowchartNumberGuessIdentity_v1, flowchartInfo)

        Return maps
    End Function
    ```

    ```csharp
    static IDictionary<WorkflowIdentity, DynamicUpdateInfo> LoadMaps()
    {
        // There are 3 update maps to describe the changes to update v1 workflows,
        // one for reach of the 3 workflow types in the tutorial.
        Dictionary<WorkflowIdentity, DynamicUpdateInfo> maps =
            new Dictionary<WorkflowIdentity, DynamicUpdateInfo>();

        DynamicUpdateMap sequentialMap = LoadMap("SequentialNumberGuessWorkflow.map");
        DynamicUpdateInfo sequentialInfo = new DynamicUpdateInfo
        {
            updateMap = sequentialMap,
            newIdentity = WorkflowVersionMap.SequentialNumberGuessIdentity_v15
        };
        maps.Add(WorkflowVersionMap.SequentialNumberGuessIdentity_v1, sequentialInfo);

        DynamicUpdateMap stateMap = LoadMap("StateMachineNumberGuessWorkflow.map");
        DynamicUpdateInfo stateInfo = new DynamicUpdateInfo
        {
            updateMap = stateMap,
            newIdentity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v15
        };
        maps.Add(WorkflowVersionMap.StateMachineNumberGuessIdentity_v1, stateInfo);

        DynamicUpdateMap flowchartMap = LoadMap("FlowchartNumberGuessWorkflow.map");
        DynamicUpdateInfo flowchartInfo = new DynamicUpdateInfo
        {
            updateMap = flowchartMap,
            newIdentity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v15
        };
        maps.Add(WorkflowVersionMap.FlowchartNumberGuessIdentity_v1, flowchartInfo);

        return maps;
    }
    ```

19. <span data-ttu-id="b3da5-229">Fügen Sie `Main` den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-229">Add the following code to `Main`.</span></span> <span data-ttu-id="b3da5-230">Der Code durchläuft die persistenten Workflowinstanzen und überprüft jede `WorkflowIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b3da5-230">This code iterates the persisted workflow instances and examines each `WorkflowIdentity`.</span></span> <span data-ttu-id="b3da5-231">Wenn `WorkflowIdentity` einer `v1`-Workflowinstanz entspricht, wird eine `WorkflowApplication` mit der aktualisierten Workflowdefinition und einer aktualisierten Workflowidentität konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="b3da5-231">If the `WorkflowIdentity` maps to a `v1` workflow instance, a `WorkflowApplication` is configured with the updated workflow definition and an updated workflow identity.</span></span> <span data-ttu-id="b3da5-232">Anschließend wird `WorkflowApplication.Load` mit der Instanz und der Updatezuordnung aufgerufen, durch die die dynamische Updatezuordnung angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b3da5-232">Next, `WorkflowApplication.Load` is called with the instance and the update map, which applies the dynamic update map.</span></span> <span data-ttu-id="b3da5-233">Nachdem das Update angewendet wurde, wird die aktualisierte Instanz mit einem Aufruf von `Unload` persistent gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b3da5-233">Once the update is applied, the updated instance is persisted with a call to `Unload`.</span></span>

    ```vb
    Dim store = New SqlWorkflowInstanceStore(connectionString)
    WorkflowApplication.CreateDefaultInstanceOwner(store, Nothing, WorkflowIdentityFilter.Any)

    Dim updateMaps As IDictionary(Of WorkflowIdentity, DynamicUpdateInfo) = LoadMaps()

    For Each id As Guid In GetIds()
        'Get a proxy to the instance.
        Dim instance As WorkflowApplicationInstance = WorkflowApplication.GetInstance(id, store)

        Console.WriteLine("Inspecting: {0}", instance.DefinitionIdentity)

        'Only update v1 workflows.
        If Not instance.DefinitionIdentity Is Nothing AndAlso _
            instance.DefinitionIdentity.Version.Equals(New Version(1, 0, 0, 0)) Then

            Dim info As DynamicUpdateInfo = updateMaps(instance.DefinitionIdentity)

            'Associate the persisted WorkflowApplicationInstance with
            'a WorkflowApplication that is configured with the updated
            'definition and updated WorkflowIdentity.
            Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(info.newIdentity)
            Dim wfApp = New WorkflowApplication(wf, info.newIdentity)

            'Apply the Dynamic Update.
            wfApp.Load(instance, info.updateMap)

            'Persist the updated instance.
            wfApp.Unload()

            Console.WriteLine("Updated to: {0}", info.newIdentity)
        Else
            'Not updating this instance, so unload it.
            instance.Abandon()
        End If
    Next
    ```

    ```csharp
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);
    WorkflowApplication.CreateDefaultInstanceOwner(store, null, WorkflowIdentityFilter.Any);

    IDictionary<WorkflowIdentity, DynamicUpdateInfo> updateMaps = LoadMaps();

    foreach (Guid id in GetIds())
    {
        // Get a proxy to the instance.
        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(id, store);

        Console.WriteLine("Inspecting: {0}", instance.DefinitionIdentity);

        // Only update v1 workflows.
        if (instance.DefinitionIdentity != null &&
            instance.DefinitionIdentity.Version.Equals(new Version(1, 0, 0, 0)))
        {
            DynamicUpdateInfo info = updateMaps[instance.DefinitionIdentity];

            // Associate the persisted WorkflowApplicationInstance with
            // a WorkflowApplication that is configured with the updated
            // definition and updated WorkflowIdentity.
            Activity wf = WorkflowVersionMap.GetWorkflowDefinition(info.newIdentity);
            WorkflowApplication wfApp =
                new WorkflowApplication(wf, info.newIdentity);

            // Apply the Dynamic Update.
            wfApp.Load(instance, info.updateMap);

            // Persist the updated instance.
            wfApp.Unload();

            Console.WriteLine("Updated to: {0}", info.newIdentity);
        }
        else
        {
            // Not updating this instance, so unload it.
            instance.Abandon();
        }
    }
    ```

20. <span data-ttu-id="b3da5-234">Mit der rechten Maustaste **ApplyDynamicUpdate** in **Projektmappen-Explorer** , und wählen Sie **als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-234">Right-click **ApplyDynamicUpdate** in **Solution Explorer** and choose **Set as StartUp Project**.</span></span>

21. <span data-ttu-id="b3da5-235">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen, und STRG+F5, um die `ApplyDynamicUpdate`-Anwendung auszuführen und die persistenten Workflowinstanzen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b3da5-235">Press CTRL+SHIFT+B to build the solution, and then press CTRL+F5 to run the `ApplyDynamicUpdate` application and update the persisted workflow instances.</span></span> <span data-ttu-id="b3da5-236">Die Ausgabe sollte folgendem Beispiel entsprechen:</span><span class="sxs-lookup"><span data-stu-id="b3da5-236">You should see output similar to the following.</span></span> <span data-ttu-id="b3da5-237">Die Workflows der Version 1.0.0.0 werden auf die Version 1.5.0.0 aktualisiert, während die Workflows der Version 2.0.0.0 nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b3da5-237">The version 1.0.0.0 workflows are updated to version 1.5.0.0, while the version 2.0.0.0 workflows are not updated.</span></span>

    <span data-ttu-id="b3da5-238">**Untersuchen: StateMachineNumberGuessWorkflow; Version=1.0.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-238">**Inspecting: StateMachineNumberGuessWorkflow; Version=1.0.0.0**\\</span></span>
    <span data-ttu-id="b3da5-239">**Aktualisiert: StateMachineNumberGuessWorkflow; Version=1.5.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-239">**Updated to: StateMachineNumberGuessWorkflow; Version=1.5.0.0**\\</span></span>
    <span data-ttu-id="b3da5-240">**Untersuchen: StateMachineNumberGuessWorkflow; Version=1.0.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-240">**Inspecting: StateMachineNumberGuessWorkflow; Version=1.0.0.0**\\</span></span>
    <span data-ttu-id="b3da5-241">**Aktualisiert: StateMachineNumberGuessWorkflow; Version=1.5.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-241">**Updated to: StateMachineNumberGuessWorkflow; Version=1.5.0.0**\\</span></span>
    <span data-ttu-id="b3da5-242">**Untersuchen: FlowchartNumberGuessWorkflow; Version=1.0.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-242">**Inspecting: FlowchartNumberGuessWorkflow; Version=1.0.0.0**\\</span></span>
    <span data-ttu-id="b3da5-243">**Aktualisiert: FlowchartNumberGuessWorkflow; Version=1.5.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-243">**Updated to: FlowchartNumberGuessWorkflow; Version=1.5.0.0**\\</span></span>
    <span data-ttu-id="b3da5-244">**Untersuchen: FlowchartNumberGuessWorkflow; Version=1.0.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-244">**Inspecting: FlowchartNumberGuessWorkflow; Version=1.0.0.0**\\</span></span>
    <span data-ttu-id="b3da5-245">**Aktualisiert: FlowchartNumberGuessWorkflow; Version=1.5.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-245">**Updated to: FlowchartNumberGuessWorkflow; Version=1.5.0.0**\\</span></span>
    <span data-ttu-id="b3da5-246">**Untersuchen: SequentialNumberGuessWorkflow; Version=1.0.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-246">**Inspecting: SequentialNumberGuessWorkflow; Version=1.0.0.0**\\</span></span>
    <span data-ttu-id="b3da5-247">**Aktualisiert: SequentialNumberGuessWorkflow; Version=1.5.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-247">**Updated to: SequentialNumberGuessWorkflow; Version=1.5.0.0**\\</span></span>
    <span data-ttu-id="b3da5-248">**Untersuchen: SequentialNumberGuessWorkflow; Version=1.0.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-248">**Inspecting: SequentialNumberGuessWorkflow; Version=1.0.0.0**\\</span></span>
    <span data-ttu-id="b3da5-249">**Aktualisiert: SequentialNumberGuessWorkflow; Version=1.5.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-249">**Updated to: SequentialNumberGuessWorkflow; Version=1.5.0.0**\\</span></span>
    <span data-ttu-id="b3da5-250">**Untersuchen: SequentialNumberGuessWorkflow; Version=1.0.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-250">**Inspecting: SequentialNumberGuessWorkflow; Version=1.0.0.0**\\</span></span>
    <span data-ttu-id="b3da5-251">**Aktualisiert: SequentialNumberGuessWorkflow; Version=1.5.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-251">**Updated to: SequentialNumberGuessWorkflow; Version=1.5.0.0**\\</span></span>
    <span data-ttu-id="b3da5-252">**Untersuchen: StateMachineNumberGuessWorkflow; Version=1.0.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-252">**Inspecting: StateMachineNumberGuessWorkflow; Version=1.0.0.0**\\</span></span>
    <span data-ttu-id="b3da5-253">**Aktualisiert: StateMachineNumberGuessWorkflow; Version=1.5.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-253">**Updated to: StateMachineNumberGuessWorkflow; Version=1.5.0.0**\\</span></span>
    <span data-ttu-id="b3da5-254">**Untersuchen: FlowchartNumberGuessWorkflow; Version=1.0.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-254">**Inspecting: FlowchartNumberGuessWorkflow; Version=1.0.0.0**\\</span></span>
    <span data-ttu-id="b3da5-255">**Aktualisiert: FlowchartNumberGuessWorkflow; Version=1.5.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-255">**Updated to: FlowchartNumberGuessWorkflow; Version=1.5.0.0**\\</span></span>
    <span data-ttu-id="b3da5-256">**Untersuchen: StateMachineNumberGuessWorkflow; Version=2.0.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-256">**Inspecting: StateMachineNumberGuessWorkflow; Version=2.0.0.0**\\</span></span>
    <span data-ttu-id="b3da5-257">**Untersuchen: StateMachineNumberGuessWorkflow; Version=2.0.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-257">**Inspecting: StateMachineNumberGuessWorkflow; Version=2.0.0.0**\\</span></span>
    <span data-ttu-id="b3da5-258">**Untersuchen: FlowchartNumberGuessWorkflow; Version=2.0.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-258">**Inspecting: FlowchartNumberGuessWorkflow; Version=2.0.0.0**\\</span></span>
    <span data-ttu-id="b3da5-259">**Untersuchen: FlowchartNumberGuessWorkflow; Version=2.0.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-259">**Inspecting: FlowchartNumberGuessWorkflow; Version=2.0.0.0**\\</span></span>
    <span data-ttu-id="b3da5-260">**Untersuchen: SequentialNumberGuessWorkflow; Version=2.0.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-260">**Inspecting: SequentialNumberGuessWorkflow; Version=2.0.0.0**\\</span></span>
    <span data-ttu-id="b3da5-261">**Untersuchen: SequentialNumberGuessWorkflow; Version=2.0.0.0**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-261">**Inspecting: SequentialNumberGuessWorkflow; Version=2.0.0.0**\\</span></span>
    <span data-ttu-id="b3da5-262">**Drücken Sie eine beliebige Taste, um den Vorgang fortzusetzen...**</span><span class="sxs-lookup"><span data-stu-id="b3da5-262">**Press any key to continue . . .**</span></span>

### <a name="BKMK_BuildAndRun"></a> <span data-ttu-id="b3da5-263">Zum Ausführen der Anwendung mit der aktualisierten workflows</span><span class="sxs-lookup"><span data-stu-id="b3da5-263">To run the application with the updated workflows</span></span>

1. <span data-ttu-id="b3da5-264">Mit der rechten Maustaste **NumberGuessWorkflowHost** in **Projektmappen-Explorer** , und wählen Sie **als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-264">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Set as StartUp Project**.</span></span>

2. <span data-ttu-id="b3da5-265">Drücken Sie STRG+F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-265">Press CTRL+F5 to run the application.</span></span>

3. <span data-ttu-id="b3da5-266">Klicken Sie auf **neues Spiel** einen neuen Workflow gestartet, und notieren die Versionsinformationen unter das Statusfenster, das der Workflow wird eine `v2` Workflow.</span><span class="sxs-lookup"><span data-stu-id="b3da5-266">Click **New Game** to start a new workflow and note the version information below the status window that indicates the workflow is a `v2` workflow.</span></span>

4. <span data-ttu-id="b3da5-267">Wählen Sie eine der der `v1` Sie am Anfang des gestarteten Workflows die [Vorgehensweise: Hosten mehrerer Workflowversionen zu einem Workflow Seite-an-Seite](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="b3da5-267">Select one of the `v1` workflows you started at the beginning of the [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) topic.</span></span> <span data-ttu-id="b3da5-268">Beachten Sie, dass die Versionsinformationen unter dem Statusfenster gibt an, dass der Workflow eine Version **1.5.0.0** Workflow.</span><span class="sxs-lookup"><span data-stu-id="b3da5-268">Note that the version information under the status window indicates that the workflow is a version **1.5.0.0** workflow.</span></span> <span data-ttu-id="b3da5-269">Beachten Sie, dass abgesehen von der Meldung, dass die Schätzung zu hoch oder zu niedrig war, keine Informationen zu früheren Schätzungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b3da5-269">Note that there is no information indicated about previous guesses other than whether they were too high or too low.</span></span>

    <span data-ttu-id="b3da5-270">**Bitte geben Sie eine Zahl zwischen 1 und 10**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-270">**Please enter a number between 1 and 10**\\</span></span>
    <span data-ttu-id="b3da5-271">**Ihre Schätzung ist zu niedrig.**</span><span class="sxs-lookup"><span data-stu-id="b3da5-271">**Your guess is too low.**</span></span>

5. <span data-ttu-id="b3da5-272">Notieren Sie die `InstanceId`, und geben Sie dann Schätzungen ein, bis der Workflow beendet ist.</span><span class="sxs-lookup"><span data-stu-id="b3da5-272">Make a note of the `InstanceId` and then enter guesses until the workflow completes.</span></span> <span data-ttu-id="b3da5-273">Das Statusfenster zeigt Informationen über den Inhalt der Schätzung an, da die `WriteLine`-Aktivitäten durch das dynamische Update aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b3da5-273">The status window displays information about the content of the guess because the `WriteLine` activities were updated by the dynamic update.</span></span>

    <span data-ttu-id="b3da5-274">**Bitte geben Sie eine Zahl zwischen 1 und 10**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-274">**Please enter a number between 1 and 10**\\</span></span>
    <span data-ttu-id="b3da5-275">**Ihre Schätzung ist zu niedrig.**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-275">**Your guess is too low.**\\</span></span>
    <span data-ttu-id="b3da5-276">**Bitte geben Sie eine Zahl zwischen 1 und 10**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-276">**Please enter a number between 1 and 10**\\</span></span>
    <span data-ttu-id="b3da5-277">**5 ist zu niedrig.**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-277">**5 is too low.**\\</span></span>
    <span data-ttu-id="b3da5-278">**Bitte geben Sie eine Zahl zwischen 1 und 10**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-278">**Please enter a number between 1 and 10**\\</span></span>
    <span data-ttu-id="b3da5-279">**7 ist zu hoch.**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-279">**7 is too high.**\\</span></span>
    <span data-ttu-id="b3da5-280">**Bitte geben Sie eine Zahl zwischen 1 und 10**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-280">**Please enter a number between 1 and 10**\\</span></span>
    <span data-ttu-id="b3da5-281">**Herzlichen Glückwunsch, Sie die Zahl 4 wiederum erraten.**</span><span class="sxs-lookup"><span data-stu-id="b3da5-281">**Congratulations, you guessed the number in 4 turns.**</span></span>

6. <span data-ttu-id="b3da5-282">Öffnen Sie Windows Explorer, und navigieren Sie zu der **NumberGuessWorkflowHost\bin\debug** Ordner (oder **"bin\Release"** je nach den projekteinstellungen), und öffnen Sie die Nachverfolgungsdatei, die mit dem Editor, der entspricht mit dem abgeschlossenen Workflow.</span><span class="sxs-lookup"><span data-stu-id="b3da5-282">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="b3da5-283">Wenn Sie sich noch nicht vorgenommen haben die `InstanceId` möglicherweise die richtige Nachverfolgungsdatei mithilfe identifizieren die **Änderungsdatum** Informationen im Windows-Explorer.</span><span class="sxs-lookup"><span data-stu-id="b3da5-283">If you did not make a note of the `InstanceId` you may be able to identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span> <span data-ttu-id="b3da5-284">Die letzte Zeile der Nachverfolgungsinformationen enthält die Ausgabe der neu hinzugefügten `WriteLine`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b3da5-284">The last line of the tracking information contains the output of the newly added `WriteLine` activity.</span></span>

    <span data-ttu-id="b3da5-285">**Bitte geben Sie eine Zahl zwischen 1 und 10**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-285">**Please enter a number between 1 and 10**\\</span></span>
    <span data-ttu-id="b3da5-286">**Ihre Schätzung ist zu niedrig.**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-286">**Your guess is too low.**\\</span></span>
    <span data-ttu-id="b3da5-287">**Bitte geben Sie eine Zahl zwischen 1 und 10**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-287">**Please enter a number between 1 and 10**\\</span></span>
    <span data-ttu-id="b3da5-288">**5 ist zu niedrig.**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-288">**5 is too low.**\\</span></span>
    <span data-ttu-id="b3da5-289">**Bitte geben Sie eine Zahl zwischen 1 und 10**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-289">**Please enter a number between 1 and 10**\\</span></span>
    <span data-ttu-id="b3da5-290">**7 ist zu hoch.**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-290">**7 is too high.**\\</span></span>
    <span data-ttu-id="b3da5-291">**Bitte geben Sie eine Zahl zwischen 1 und 10**\\</span><span class="sxs-lookup"><span data-stu-id="b3da5-291">**Please enter a number between 1 and 10**\\</span></span>
    <span data-ttu-id="b3da5-292">**6 ist richtig. Sie ahnen es bereits in 4 deaktiviert.**</span><span class="sxs-lookup"><span data-stu-id="b3da5-292">**6 is correct. You guessed it in 4 turns.**</span></span>

### <a name="BKMK_StartPreviousVersions"></a> <span data-ttu-id="b3da5-293">Zum Starten von Vorgängerversionen der Workflows zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="b3da5-293">To enable starting previous versions of the workflows</span></span>

<span data-ttu-id="b3da5-294">Wenn keine zu aktualisierenden Workflows mehr verfügbar sind, können Sie die `NumberGuessWorkflowHost`-Anwendung ändern, um das Starten früherer Workflowversionen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b3da5-294">If you run out of workflows to update, you can modify the `NumberGuessWorkflowHost` application to enable starting previous versions of the workflows.</span></span>

1. <span data-ttu-id="b3da5-295">Doppelklicken Sie auf **WorkflowHostForm** in **Projektmappen-Explorer**, und wählen Sie die **WorkflowType** im Kombinationsfeld.</span><span class="sxs-lookup"><span data-stu-id="b3da5-295">Double-click **WorkflowHostForm** in **Solution Explorer**, and select the **WorkflowType** combo box.</span></span>

2. <span data-ttu-id="b3da5-296">In der **Eigenschaften** wählen Sie im Fenster der **Elemente** -Eigenschaft, und klicken Sie auf die Schaltfläche mit den Auslassungspunkten so bearbeiten Sie die **Elemente** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="b3da5-296">In the **Properties** window, select the **Items** property and click the ellipsis button to edit the **Items** collection.</span></span>

3. <span data-ttu-id="b3da5-297">Fügen Sie der Auflistung die folgenden drei Elemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3da5-297">Add the following three items to the collection.</span></span>

    ```
    StateMachineNumberGuessWorkflow v1
    FlowchartNumberGuessWorkflow v1
    SequentialNumberGuessWorkflow v1
    ```

    <span data-ttu-id="b3da5-298">Die abgeschlossene `Items`-Auflistung verfügt über sechs Elemente.</span><span class="sxs-lookup"><span data-stu-id="b3da5-298">The completed `Items` collection will have six items.</span></span>

    ```
    StateMachineNumberGuessWorkflow
    FlowchartNumberGuessWorkflow
    SequentialNumberGuessWorkflow
    StateMachineNumberGuessWorkflow v1
    FlowchartNumberGuessWorkflow v1
    SequentialNumberGuessWorkflow v1
    ```

4. <span data-ttu-id="b3da5-299">Doppelklicken Sie auf **WorkflowHostForm** in **Projektmappen-Explorer**, und wählen Sie **Ansichtscode**.</span><span class="sxs-lookup"><span data-stu-id="b3da5-299">Double-click **WorkflowHostForm** in **Solution Explorer**, and select **View Code**.</span></span>

5. <span data-ttu-id="b3da5-300">Fügen Sie drei neue Fälle, die die `switch` (oder `Select Case`)-Anweisung in der `NewGame_Click` Handler, der die neuen Elemente im Zuordnen der **WorkflowType** im Kombinationsfeld, um den entsprechenden workflowidentitäten.</span><span class="sxs-lookup"><span data-stu-id="b3da5-300">Add three new cases to the `switch` (or `Select Case`) statement in the `NewGame_Click` handler to map the new items in the **WorkflowType** combo box to the matching workflow identities.</span></span>

    ```vb
    Case "SequentialNumberGuessWorkflow v1"
        identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1

    Case "StateMachineNumberGuessWorkflow v1"
        identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1

    Case "FlowchartNumberGuessWorkflow v1"
        identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1
    ```

    ```csharp
    case "SequentialNumberGuessWorkflow v1":
        identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1;
        break;

    case "StateMachineNumberGuessWorkflow v1":
        identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1;
        break;

    case "FlowchartNumberGuessWorkflow v1":
        identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1;
        break;
    ```

    <span data-ttu-id="b3da5-301">Im folgenden Beispiel ist die gesamte `switch`-Anweisung (bzw. `Select Case`-Anweisung) enthalten.</span><span class="sxs-lookup"><span data-stu-id="b3da5-301">The following example contains the complete `switch` (or `Select Case`) statement.</span></span>

    ```vb
    Select Case WorkflowType.SelectedItem.ToString()
        Case "SequentialNumberGuessWorkflow"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity

        Case "StateMachineNumberGuessWorkflow"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

        Case "FlowchartNumberGuessWorkflow"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity

        Case "SequentialNumberGuessWorkflow v1"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1

        Case "StateMachineNumberGuessWorkflow v1"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1

        Case "FlowchartNumberGuessWorkflow v1"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1
    End Select
    ```

    ```csharp
    switch (WorkflowType.SelectedItem.ToString())
    {
        case "SequentialNumberGuessWorkflow":
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity;
            break;

        case "StateMachineNumberGuessWorkflow":
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;
            break;

        case "FlowchartNumberGuessWorkflow":
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;
            break;

        case "SequentialNumberGuessWorkflow v1":
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1;
            break;

        case "StateMachineNumberGuessWorkflow v1":
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1;
            break;

        case "FlowchartNumberGuessWorkflow v1":
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1;
            break;
    };
    ```

6. <span data-ttu-id="b3da5-302">Drücken Sie STRG+F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b3da5-302">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="b3da5-303">Sie können jetzt die `v1`-Versionen des Workflows sowie die aktuellen Versionen starten.</span><span class="sxs-lookup"><span data-stu-id="b3da5-303">You can now start the `v1` versions of the workflow as well as the current versions.</span></span> <span data-ttu-id="b3da5-304">Um diese neuen Instanzen dynamisch zu aktualisieren, führen Sie die **ApplyDynamicUpdate** Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b3da5-304">To dynamically update these new instances, run the **ApplyDynamicUpdate** application.</span></span>
