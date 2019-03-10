---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Menüelementen mit der ContextMenu-Komponente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], removing items
- ContextMenu component [Windows Forms], adding items
- shortcut menus [Windows Forms], removing items
- shortcut menus [Windows Forms], examples
- context menus [Windows Forms], adding items
- shortcut menus [Windows Forms], adding items
- ContextMenu component [Windows Forms], removing items
- context menus [Windows Forms], examples
- examples [Windows Forms], context menus
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
ms.openlocfilehash: 8b63182bdb37e47a71bee2d22500263cd4889ac9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725063"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a>Vorgehensweise: Hinzufügen und Entfernen von Menüelementen mit der ContextMenu-Komponente in Windows Forms
Erläutert das Hinzufügen und Entfernen von Tastenkombinations-Menüelemente in Windows Forms.  
  
 Die Windows-Formulare <xref:System.Windows.Forms.ContextMenu> Komponente stellt ein Menü der häufig verwendete Befehle, die auf das ausgewählte Objekt relevant sind. Sie können Elemente zum Kontextmenü hinzufügen, durch das Hinzufügen <xref:System.Windows.Forms.MenuItem> Objekte die <xref:System.Windows.Forms.Menu.MenuItems%2A> Auflistung.  
  
 Sie können Elemente aus einem Kontextmenü dauerhaft entfernen. Allerdings zur Laufzeit es möglicherweise besser geeignet ist, ausblenden oder deaktivieren stattdessen die Elemente.  
  
> [!IMPORTANT]
>  Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzen und Erweitern der Funktionalität für die <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> Steuerelemente aus früheren Versionen, <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> werden für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, wenn Sie auswählen.  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a>So entfernen Sie Elemente aus einem Kontextmenü  
  
1.  Verwenden der <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> oder <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> Methode der <xref:System.Windows.Forms.Menu.MenuItems%2A> Auflistung von der <xref:System.Windows.Forms.ContextMenu> Komponente, um ein bestimmtes Element zu entfernen.  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     - oder -   
  
2.  Verwenden der `Clear` Methode der `MenuItems` Auflistung von der <xref:System.Windows.Forms.ContextMenu> Komponente, um alle Elemente aus dem Menü zu entfernen.  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.ContextMenu>
- [ContextMenu-Komponente](contextmenu-component-windows-forms.md)
- [Übersicht über die ContextMenu-Komponente](contextmenu-component-overview-windows-forms.md)
