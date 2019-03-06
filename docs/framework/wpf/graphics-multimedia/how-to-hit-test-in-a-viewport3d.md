---
title: 'Vorgehensweise: Treffertest in Viewport3D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D visuals [WPF], hit-testing for
- hit tests [WPF], for 3-D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: d795f5aa768c360b6e27a9a1114179a5c27f0b23
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356571"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a><span data-ttu-id="22429-102">Vorgehensweise: Treffertest in Viewport3D</span><span class="sxs-lookup"><span data-stu-id="22429-102">How to: Hit Test in a Viewport3D</span></span>
<span data-ttu-id="22429-103">Dieses Beispiel zeigt, wie ein Treffertest für 3D-Elemente in einem <xref:System.Windows.Controls.Viewport3D>.</span><span class="sxs-lookup"><span data-stu-id="22429-103">This example shows how to hit test for 3D Visuals in a <xref:System.Windows.Controls.Viewport3D>.</span></span>  
  
 <span data-ttu-id="22429-104">Da <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 2D- und 3D-Spiele gibt Informationen zurück, es ist möglich, durchlaufen die Testergebnisse nur 3D Ergebnisse zu lesen.</span><span class="sxs-lookup"><span data-stu-id="22429-104">Because <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> returns 2D and 3D information, it is possible to iterate through the test results to read only 3D results.</span></span>  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 <span data-ttu-id="22429-105">Die <xref:System.Windows.Media.HitTestResultBehavior> in den folgenden Code bestimmt, wie die Treffertestergebnissen verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="22429-105">The <xref:System.Windows.Media.HitTestResultBehavior> in the following code determines how the hit test results are processed.</span></span>  <span data-ttu-id="22429-106">`UpdateResultInfo` und `UpdateMaterial` lokal definierte Methoden sind.</span><span class="sxs-lookup"><span data-stu-id="22429-106">`UpdateResultInfo` and `UpdateMaterial` are locally defined methods.</span></span>  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
  
## <a name="see-also"></a><span data-ttu-id="22429-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22429-107">See also</span></span>
- [<span data-ttu-id="22429-108">Drücken Sie Beispiel zu Leistungstests in 3D</span><span class="sxs-lookup"><span data-stu-id="22429-108">3-D Hit Testing Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159959)
