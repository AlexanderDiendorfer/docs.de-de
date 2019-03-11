---
title: 'Vorgehensweise: Legen Sie den Text von einer Windows Forms-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: 8ebb39e4e9337ede0dc8c7f5569ea27d8cfafd26
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716906"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a>Vorgehensweise: Legen Sie den Text von einer Windows Forms-Steuerelement
Windows Forms-Steuerelemente zeigen in der Regel Text an, der mit der Hauptfunktion des Steuerelements zusammenhängt. Beispielsweise verfügt ein <xref:System.Windows.Forms.Button>-Steuerelement üblicherweise über eine Beschriftung, die auf die beim Klicken der Schaltfläche ausgeführte Aktion hinweist. Bei allen Steuerelementen können Sie den Text mithilfe der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft festlegen oder zurückgeben. Sie können die Schriftart ändern, indem Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft verwenden. Sie können den Text aber auch mithilfe des Designers festlegen.   Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente, die mithilfe des Designers](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [Vorgehensweise: Legen Sie den Text von einer Windows Forms-Steuerelement mithilfe des Designers](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [Vorgehensweise: Das Bild angezeigt, die von einer Windows Forms-Steuerelement mithilfe des Designers](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md).  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a>So legen Sie den von einem Steuerelement angezeigten Text programmgesteuert fest  
  
1.  Legen Sie für die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft eine Zeichenfolge fest.  
  
     Wenn Sie eine unterstrichene Zugriffstaste erstellen möchten, setzen Sie ein kaufmännisches Und-Zeichen (&) vor den Buchstaben der Zugriffstaste.  
  
2.  Legen Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft auf ein Objekt des Typs <xref:System.Drawing.Font> fest.  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  Mit einem Escapezeichen können Sie ein Sonderzeichen in Benutzeroberflächenelementen anzeigen, das diese normalerweise anders interpretieren würde, z. B. Menüelemente. Mit der folgenden Codezeile wird der Text des Menüelements beispielsweise wie folgt festgelegt: "& Now For Something Completely Different":  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente](how-to-create-access-keys-for-windows-forms-controls.md)
- [Vorgehensweise: Reagieren Sie auf eine Windows Forms-Schaltfläche geklickt](how-to-respond-to-windows-forms-button-clicks.md)
