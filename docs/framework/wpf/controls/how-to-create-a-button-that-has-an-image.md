---
title: 'Vorgehensweise: Erstellen einer Schaltfläche mit einem Bild'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: fe9f35a6f83c5a839823d94c4d3c55e01b192fb1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352034"
---
# <a name="how-to-create-a-button-that-has-an-image"></a>Vorgehensweise: Erstellen einer Schaltfläche mit einem Bild
Dieses Beispiel zeigt, wie Sie ein Bild enthalten, auf eine <xref:System.Windows.Controls.Button>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt zwei <xref:System.Windows.Controls.Button> Steuerelemente. Eine <xref:System.Windows.Controls.Button> enthält Text und das andere ein Bild. Das Image ist in einem Ordner namens Daten, d. h. einen Unterordner des Projektordners des Beispiels. Wenn ein Benutzer klickt auf die <xref:System.Windows.Controls.Button> über das Image, Hintergrund und den Text der anderen verfügt <xref:System.Windows.Controls.Button> ändern.  
  
 In diesem Beispiel wird <xref:System.Windows.Controls.Button> steuert mithilfe von Markup wird jedoch Code schreiben verwendet die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler.  
  
 [!code-xaml[BtnColor#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a>Siehe auch
- [Steuerelemente](index.md)
- [Steuerelementbibliothek](control-library.md)
