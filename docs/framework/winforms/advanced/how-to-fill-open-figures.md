---
title: 'Vorgehensweise: Füllen offener Körper aus'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: e9743d3268a7a2acfb6266872c3346a05269c369
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702724"
---
# <a name="how-to-fill-open-figures"></a>Vorgehensweise: Füllen offener Körper aus
Sie können einen Pfad eingeben, durch Übergeben einer <xref:System.Drawing.Drawing2D.GraphicsPath> -Objekt an die <xref:System.Drawing.Graphics.FillPath%2A> Methode. Die <xref:System.Drawing.Graphics.FillPath%2A> Methode füllt den Pfad entsprechend der Füllmodus (alternative oder wicklungsreihenfolgen), die derzeit für den Pfad festgelegt. Wenn der Pfad offener Körper enthält, wird der Pfad gefüllt, als ob diese Zahlen geschlossen wurden. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Schließt eine Abbildung durch Zeichnen einer geraden Linie vom Endpunkt zum Ausgangspunkt erforderlich.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt einen Pfad an, der eine offene Form (einen Bogen) und eine geschlossene Form (eine Ellipse) verfügt. Die <xref:System.Drawing.Graphics.FillPath%2A> Methode füllt den Pfad entsprechend der Standardmodus für die Füllung, handelt es sich <xref:System.Drawing.Drawing2D.FillMode.Alternate>.  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispielcodes. Beachten Sie, dass der Pfad gefüllt wird (gemäß <xref:System.Drawing.Drawing2D.FillMode.Alternate>), als ob der geöffnete Figur mit einer geraden Linie vom Endpunkt zum Ausgangspunkt geschlossen wurden.  
  
 ![Offenen Pfad ausfüllen](./media/fillopenpath.png "FillOpenPath")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [Grafikpfade in GDI+](graphics-paths-in-gdi.md)
