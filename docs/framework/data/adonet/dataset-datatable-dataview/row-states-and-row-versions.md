---
title: Zeilenstatus und Zeilenversionen
ms.date: 07/19/2018
dev_langs:
- csharp
- vb
ms.assetid: 2e6642c9-bfc6-425c-b3a7-e4912ffa6c1f
ms.openlocfilehash: 83147c3f9d70434f5c8dd34e2e56f44f71adc53d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092902"
---
# <a name="row-states-and-row-versions"></a><span data-ttu-id="1f1ab-102">Zeilenstatus und Zeilenversionen</span><span class="sxs-lookup"><span data-stu-id="1f1ab-102">Row States and Row Versions</span></span>
<span data-ttu-id="1f1ab-103">ADO.NET verwaltet Zeilen in Tabellen mithilfe des Zeilenstatus und der Zeilenversion.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-103">ADO.NET manages rows in tables using row states and versions.</span></span> <span data-ttu-id="1f1ab-104">Ein Zeilenstatus gibt den Status einer Zeile an. In Zeilenversionen werden die Werte, die in einer Zeile gespeichert werden, während der Bearbeitung verwaltet. Zu diesen Werten zählen z. B. die Werte current, original und default.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-104">A row state indicates the status of a row; row versions maintain the values stored in a row as it is modified, including current, original, and default values.</span></span> <span data-ttu-id="1f1ab-105">Wenn Sie beispielsweise eine Spalte in einer Zeile geändert haben, weist die Zeile den Zeilenstatus `Modified` und die folgenden beiden Zeilenversionen auf: `Current` mit den aktuellen Zeilenwerten und `Original` mit den Zeilenwerten vor den Änderungen der Spalte.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-105">For example, after you have made a modification to a column in a row, the row will have a row state of `Modified`, and two row versions: `Current`, which contains the current row values, and `Original`, which contains the row values before the column was modified.</span></span>  
  
 <span data-ttu-id="1f1ab-106">Jedes <xref:System.Data.DataRow>-Objekt hat eine <xref:System.Data.DataRow.RowState%2A>-Eigenschaft, über die Sie den aktuellen Status der Zeile überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-106">Each <xref:System.Data.DataRow> object has a <xref:System.Data.DataRow.RowState%2A> property that you can examine to determine the current state of the row.</span></span> <span data-ttu-id="1f1ab-107">Die folgende Tabelle enthält eine kurze Beschreibung aller `RowState`-Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-107">The following table gives a brief description of each `RowState` enumeration value.</span></span>  
  
|<span data-ttu-id="1f1ab-108">"RowState"-Wert</span><span class="sxs-lookup"><span data-stu-id="1f1ab-108">RowState value</span></span>|<span data-ttu-id="1f1ab-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1f1ab-109">Description</span></span>|  
|--------------------|-----------------|  
|<xref:System.Data.DataRowState.Unchanged>|<span data-ttu-id="1f1ab-110">Seit dem letzten Aufruf von `AcceptChanges` oder seit der Erstellung der Zeile durch `DataAdapter.Fill` wurden keine Änderungen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-110">No changes have been made since the last call to `AcceptChanges` or since the row was created by `DataAdapter.Fill`.</span></span>|  
|<xref:System.Data.DataRowState.Added>|<span data-ttu-id="1f1ab-111">Die Zeile wurde der Tabelle hinzugefügt, `AcceptChanges` wurde aber nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-111">The row has been added to the table, but `AcceptChanges` has not been called.</span></span>|  
|<xref:System.Data.DataRowState.Modified>|<span data-ttu-id="1f1ab-112">Ein Element der Zeile wurde geändert.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-112">Some element of the row has been changed.</span></span>|  
|<xref:System.Data.DataRowState.Deleted>|<span data-ttu-id="1f1ab-113">Die Zeile wurde aus einer Tabelle gelöscht, und `AcceptChanges` wurde nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-113">The row has been deleted from a table, and `AcceptChanges` has not been called.</span></span>|  
|<xref:System.Data.DataRowState.Detached>|<span data-ttu-id="1f1ab-114">Die Zeile ist nicht Teil einer `DataRowCollection`.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-114">The row is not part of any `DataRowCollection`.</span></span> <span data-ttu-id="1f1ab-115">Der `RowState` einer neu erstellten Zeile wird auf `Detached` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-115">The `RowState` of a newly created row is set to `Detached`.</span></span> <span data-ttu-id="1f1ab-116">Nach dem Hinzufügen der neuen `DataRow` zur `DataRowCollection` durch Aufrufen der `Add`-Methode wird der Wert der `RowState`-Eigenschaft auf `Added` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-116">After the new `DataRow` is added to the `DataRowCollection` by calling the `Add` method, the value of the `RowState` property is set to `Added`.</span></span><br /><br /> `Detached` <span data-ttu-id="1f1ab-117">für eine Zeile, die von entfernt wurde ebenfalls festgelegt wird eine `DataRowCollection` mithilfe der `Remove` -Methode, oder durch die `Delete` Methode, gefolgt von der `AcceptChanges` Methode.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-117">is also set for a row that has been removed from a `DataRowCollection` using the `Remove` method, or by the `Delete` method followed by the `AcceptChanges` method.</span></span>|  
  
 <span data-ttu-id="1f1ab-118">Wenn `AcceptChanges` für einen <xref:System.Data.DataSet>, eine <xref:System.Data.DataTable> oder eine <xref:System.Data.DataRow> aufgerufen wird, werden alle Zeilen mit dem Zeilenstatus `Deleted` entfernt.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-118">When `AcceptChanges` is called on a <xref:System.Data.DataSet>, <xref:System.Data.DataTable> , or <xref:System.Data.DataRow>, all rows with a row state of `Deleted` are removed.</span></span> <span data-ttu-id="1f1ab-119">Die verbleibenden Zeilen erhalten den Zeilenstatus `Unchanged`, und die Werte in der Zeilenversion `Original` werden mit den Werten der Zeilenversion `Current` überschrieben.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-119">The remaining rows are given a row state of `Unchanged`, and the values in the `Original` row version are overwritten with the `Current` row version values.</span></span> <span data-ttu-id="1f1ab-120">Wenn `RejectChanges` aufgerufen wird, werden alle Zeilen mit dem Zeilenstatus `Added` entfernt.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-120">When `RejectChanges` is called, all rows with a row state of `Added` are removed.</span></span> <span data-ttu-id="1f1ab-121">Die verbleibenden Zeilen erhalten den Zeilenstatus `Unchanged`, und die Werte in der Zeilenversion `Current` werden mit den Werten der Zeilenversion `Original` überschrieben.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-121">The remaining rows are given a row state of `Unchanged`, and the values in the `Current` row version are overwritten with the `Original` row version values.</span></span>  
  
 <span data-ttu-id="1f1ab-122">Sie können die verschiedenen Zeilenversionen einer Zeile anzeigen, indem Sie einen <xref:System.Data.DataRowVersion>-Parameter mit dem Spaltenverweis übergeben. Dies wird im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-122">You can view the different row versions of a row by passing a <xref:System.Data.DataRowVersion> parameter with the column reference, as shown in the following example.</span></span>  
  
```vb  
Dim custRow As DataRow = custTable.Rows(0)  
Dim custID As String = custRow("CustomerID", DataRowVersion.Original).ToString()  
```  
  
```csharp  
DataRow custRow = custTable.Rows[0];  
string custID = custRow["CustomerID", DataRowVersion.Original].ToString();  
```  
  
 <span data-ttu-id="1f1ab-123">Die folgende Tabelle enthält eine kurze Beschreibung aller `DataRowVersion`-Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-123">The following table gives a brief description of each `DataRowVersion` enumeration value.</span></span>  
  
|<span data-ttu-id="1f1ab-124">"DataRowVersion"-Wert</span><span class="sxs-lookup"><span data-stu-id="1f1ab-124">DataRowVersion value</span></span>|<span data-ttu-id="1f1ab-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1f1ab-125">Description</span></span>|  
|--------------------------|-----------------|  
|<xref:System.Data.DataRowVersion.Current>|<span data-ttu-id="1f1ab-126">Die aktuellen Werte der Zeile.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-126">The current values for the row.</span></span> <span data-ttu-id="1f1ab-127">Diese Zeilenversion ist für Zeilen, deren `RowState` auf `Deleted` festgelegt ist, nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-127">This row version does not exist for rows with a `RowState` of `Deleted`.</span></span>|  
|<xref:System.Data.DataRowVersion.Default>|<span data-ttu-id="1f1ab-128">Die Standardzeilenversion einer bestimmten Zeile.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-128">The default row version for a particular row.</span></span> <span data-ttu-id="1f1ab-129">Die Standardzeilenversion für eine Zeile mit dem Status `Added`, `Modified` oder `Deleted` lautet `Current`.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-129">The default row version for an `Added`, `Modified`, or `Deleted` row is `Current`.</span></span> <span data-ttu-id="1f1ab-130">Die Standardzeilenversion für eine Zeile mit dem Status `Detached` lautet `Proposed`.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-130">The default row version for a `Detached` row is `Proposed`.</span></span>|  
|<xref:System.Data.DataRowVersion.Original>|<span data-ttu-id="1f1ab-131">Die ursprünglichen Werte der Zeile.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-131">The original values for the row.</span></span> <span data-ttu-id="1f1ab-132">Diese Zeilenversion ist für Zeilen, deren `RowState` auf `Added` festgelegt ist, nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-132">This row version does not exist for rows with a `RowState` of `Added`.</span></span>|  
|<xref:System.Data.DataRowVersion.Proposed>|<span data-ttu-id="1f1ab-133">Die vorgeschlagenen Werte für die Zeile.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-133">The proposed values for the row.</span></span> <span data-ttu-id="1f1ab-134">Diese Zeilenversion ist während der Bearbeitung einer Zeile vorhanden oder wird für Zeilen verwendet, die nicht Teil einer `DataRowCollection` sind.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-134">This row version exists during an edit operation on a row, or for a row that is not part of a `DataRowCollection`.</span></span>|  
  
 <span data-ttu-id="1f1ab-135">Sie können überprüfen, ob eine `DataRow` eine bestimmte Zeilenversion aufweist, indem Sie die <xref:System.Data.DataRow.HasVersion%2A>-Methode aufrufen und eine `DataRowVersion` als Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-135">You can test whether a `DataRow` has a particular row version by calling the <xref:System.Data.DataRow.HasVersion%2A> method and passing a `DataRowVersion` as an argument.</span></span> <span data-ttu-id="1f1ab-136">So gibt z. B. `DataRow.HasVersion(DataRowVersion.Original)` für neu hinzugefügte Zeilen vor dem Aufrufen von `false` den Wert `AcceptChanges` zurück.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-136">For example, `DataRow.HasVersion(DataRowVersion.Original)` will return `false` for newly added rows before `AcceptChanges` has been called.</span></span>  
  
 <span data-ttu-id="1f1ab-137">Im folgenden Codebeispiel werden die Werte in allen gelöschten Zeilen einer Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-137">The following code example displays the values in all the deleted rows of a table.</span></span> `Deleted` <span data-ttu-id="1f1ab-138">-Zeilen haben keine `Current` Zeilenversion, daher müssen Sie übergeben `DataRowVersion.Original` beim Zugriff auf die Spaltenwerte.</span><span class="sxs-lookup"><span data-stu-id="1f1ab-138">rows do not have a `Current` row version, so you must pass `DataRowVersion.Original` when accessing the column values.</span></span>  
  
```vb  
Dim catTable As DataTable = catDS.Tables("Categories")  
  
Dim delRows() As DataRow = catTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
Console.WriteLine("Deleted rows:" & vbCrLf)  
  
Dim catCol As DataColumn  
Dim delRow As DataRow  
  
For Each catCol In catTable.Columns  
  Console.Write(catCol.ColumnName & vbTab)  
Next  
Console.WriteLine()  
  
For Each delRow In delRows  
  For Each catCol In catTable.Columns  
    Console.Write(delRow(catCol, DataRowVersion.Original) & vbTab)  
  Next  
  Console.WriteLine()  
Next  
```  
  
```csharp  
DataTable catTable = catDS.Tables["Categories"];  
  
DataRow[] delRows = catTable.Select(null, null, DataViewRowState.Deleted);  
  
Console.WriteLine("Deleted rows:\n");  
  
foreach (DataColumn catCol in catTable.Columns)  
  Console.Write(catCol.ColumnName + "\t");  
Console.WriteLine();  
  
foreach (DataRow delRow in delRows)  
{  
  foreach (DataColumn catCol in catTable.Columns)  
    Console.Write(delRow[catCol, DataRowVersion.Original] + "\t");  
  Console.WriteLine();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f1ab-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f1ab-139">See also</span></span>

- [<span data-ttu-id="1f1ab-140">Bearbeiten von Daten in einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="1f1ab-140">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="1f1ab-141">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="1f1ab-141">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="1f1ab-142">"DataAdapters" und "DataReaders"</span><span class="sxs-lookup"><span data-stu-id="1f1ab-142">DataAdapters and DataReaders</span></span>](../../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="1f1ab-143">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="1f1ab-143">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
