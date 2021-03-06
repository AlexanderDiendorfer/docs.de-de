---
title: 'Vorgehensweise: Löschen oder Ausblenden von Spalten im DataGrid-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
ms.openlocfilehash: 42a697992d4c6c75fe5958a7a17d6df8a7b4f6e4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724514"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>Vorgehensweise: Löschen oder Ausblenden von Spalten im DataGrid-Steuerelement in Windows Forms
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Sie können programmgesteuert zu löschen oder Ausblenden von Spalten in der Windows Forms <xref:System.Windows.Forms.DataGrid> -Steuerelement unter Verwendung der Eigenschaften und Methoden des der <xref:System.Windows.Forms.GridColumnStylesCollection> und <xref:System.Windows.Forms.DataGridColumnStyle> Objekte (Member der der <xref:System.Windows.Forms.DataGridTableStyle> Klasse).  
  
 Die gelöschten oder ausgeblendeten Spalten sind noch vorhanden, in der Datenquelle, die dem Raster gebunden ist, und weiterhin programmgesteuert zugegriffen werden. Sie sind lediglich nicht mehr sichtbar, in das DataGrid-Steuerelement.  
  
> [!NOTE]
>  Wenn Ihre Anwendung greift nicht auf bestimmte Spalten der Daten, und Sie nicht in das DataGrid-Steuerelement angezeigt werden möchten, ist es wahrscheinlich nicht erforderlich, um sie in der Datenquelle im vornherein einzuschließen.  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>So löschen Sie eine Spalte programmgesteuert aus dem DataGrid  
  
1.  Deklarieren Sie eine neue Instanz der im Deklarationsbereich des Formulars die <xref:System.Windows.Forms.DataGridTableStyle> Klasse.  
  
2.  Legen Sie die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> Eigenschaft, um die Tabelle in der Datenquelle, die auf den der Stil angewendet werden sollen. Im folgenden Beispiel wird die <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> -Eigenschaft, die es wird davon ausgegangen ist bereits festgelegt.  
  
3.  Hinzufügen des neuen <xref:System.Windows.Forms.DataGridTableStyle> Objekt, das das DataGrid-Steuerelement Tabellenformate der Auflistung.  
  
4.  Rufen Sie die <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> Methode der <xref:System.Windows.Forms.DataGrid>des <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> Auflistung, die den Spaltenindex der zu löschenden Spalte angeben.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a>So blenden Sie eine Spalte in das DataGrid-Steuerelement programmgesteuert aus  
  
1.  Deklarieren Sie eine neue Instanz der im Deklarationsbereich des Formulars die <xref:System.Windows.Forms.DataGridTableStyle> Klasse.  
  
2.  Legen Sie die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> Eigenschaft der <xref:System.Windows.Forms.DataGridTableStyle> in die Tabelle in der Datenquelle, die auf den der Stil angewendet werden sollen. Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> -Eigenschaft, die es wird davon ausgegangen ist bereits festgelegt.  
  
3.  Hinzufügen des neuen <xref:System.Windows.Forms.DataGridTableStyle> Objekt, das das DataGrid-Steuerelement Tabellenformate der Auflistung.  
  
4.  Blenden Sie die Spalte durch Festlegen seiner `Width` Eigenschaft auf 0 (null), die den Spaltenindex der Spalte ausblenden angibt.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Ändern der angezeigten Daten zur Laufzeit in das DataGrid-Steuerelement in Windows Forms](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [Vorgehensweise: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement von Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
