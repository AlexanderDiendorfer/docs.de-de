---
title: 'Vorgehensweise: Positionieren der untergeordneten Elemente eines Rasters'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 90115bc6192a33f4c27eaa75ebfe6a7c9d1458e5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369174"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a>Vorgehensweise: Positionieren der untergeordneten Elemente eines Rasters
Dieses Beispiel zeigt, wie Get und set-Methoden, die auf definiert sind <xref:System.Windows.Controls.Grid> zum Positionieren der untergeordneten Elemente.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert ein übergeordnetes Element <xref:System.Windows.Controls.Grid> Element (`grid1`) über drei Spalten und drei Zeilen verfügt. Ein untergeordnetes Element <xref:System.Windows.Shapes.Rectangle> Element (`rect1`) hinzugefügt wird, um die <xref:System.Windows.Controls.Grid> an Position der Spalte 0 (null), Zeile Position 0 (null). <xref:System.Windows.Controls.Button> Elemente darstellen, die Methoden, die aufgerufen werden können, um die Position der <xref:System.Windows.Shapes.Rectangle> Element innerhalb der <xref:System.Windows.Controls.Grid>. Wenn ein Benutzer eine Schaltfläche klickt, wird die entsprechende Methode aktiviert.  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 Im folgenden Code-Behind-Beispiel werden die Methoden behandelt, die die Schaltfläche mit den <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Auslösen von Ereignissen. Das Beispiel schreibt diese Methodenaufrufe in <xref:System.Windows.Controls.TextBlock> Elemente, die Verwendung im Zusammenhang mit get-Methoden, um die neuen Eigenschaftswerte als Zeichenfolgen auszugeben.  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 Hier ist das Endergebnis!
 
 ![ein Screenshot zeigt eine WPF-Benutzeroberfläche mit zwei Spalten, die rechte Seite ist eine 3 x 3-Raster und der linken Seite verfügt über die Schaltflächen, um ein farbiges Rechteck zwischen den Spalten und Zeilen des Rasters zu verschieben.](././media/grid-methods-sample.png) 
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.Grid>
- [Übersicht über Panel-Elemente](panels-overview.md)
