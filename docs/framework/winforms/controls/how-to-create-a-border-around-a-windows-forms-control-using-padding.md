---
title: 'Vorgehensweise: Erstellen eines Rahmens um ein Windows Forms Steuerelement mithilfe von Abständen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins
- controls [Windows Forms], Margin property
- padding [Windows Forms], Windows Forms
- controls [Windows Forms], Padding property
- controls [Windows Forms], outlining
- Padding property [Windows Forms]
- margins [Windows Forms], Windows Forms
- Margin property [Windows Forms]
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
ms.openlocfilehash: 66748eef299c9175814fb130a7eda359c5de0546
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720305"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a>Vorgehensweise: Erstellen eines Rahmens um ein Windows Forms Steuerelement mithilfe von Abständen
Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen eines Rahmens oder eine Kontur um eine <xref:System.Windows.Forms.RichTextBox> Steuerelement. Im Beispiel wird den Wert des einem <xref:System.Windows.Forms.Panel> des Steuerelements <xref:System.Windows.Forms.Padding> -Eigenschaft auf 5 und legt die <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft eines untergeordneten Elements <xref:System.Windows.Forms.RichTextBox> die Steuerung an <xref:System.Windows.Forms.DockStyle.Fill>. Die <xref:System.Windows.Forms.Control.BackColor%2A> von der <xref:System.Windows.Forms.Panel> -Steuerelement so eingestellt ist, dass <xref:System.Drawing.Color.Blue%2A>, erstellt einen blauen Rahmen um die <xref:System.Windows.Forms.RichTextBox> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Padding>
- [Rand und Abstand in Windows Forms-Steuerelementen](margin-and-padding-in-windows-forms-controls.md)
