---
title: 'Vorgehensweise: Zeichnen einer Linie'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a194fad5471cafcb567aa00522a597a4186ef4af
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374184"
---
# <a name="how-to-draw-a-line"></a>Vorgehensweise: Zeichnen einer Linie
Dieses Beispiel zeigt, wie zum Zeichnen von Linien mit dem <xref:System.Windows.Shapes.Line> Element.  
  
 Um eine Linie zu zeichnen, erstellen eine <xref:System.Windows.Shapes.Line> Element. Verwenden Sie die <xref:System.Windows.Shapes.Line.X1%2A> und <xref:System.Windows.Shapes.Line.Y1%2A> Eigenschaften legen Sie dessen Start, zeigen Sie; und verwenden dessen <xref:System.Windows.Shapes.Line.X2%2A> und <xref:System.Windows.Shapes.Line.Y2%2A> Eigenschaften legen Sie seinen Endpunkt. Legen Sie schließlich die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> da eine Zeile ohne einen Strich nicht sichtbar ist.  
  
 Festlegen der <xref:System.Windows.Shapes.Shape.Fill%2A> -Element für eine Zeile hat keine Auswirkungen, da es sich bei eine Zeile keine Inneres hat.  
  
 Das folgende Beispiel zeichnet drei Linien in einem <xref:System.Windows.Controls.Canvas> Element.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Shapes.Line>
- [Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037)
