---
title: 'Vorgehensweise: Anwenden von Animationen auf Text'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: e62c8288460206e7ebfbc18787bd9c2f2144a5bc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356961"
---
# <a name="how-to-apply-animations-to-text"></a><span data-ttu-id="a42d0-102">Vorgehensweise: Anwenden von Animationen auf Text</span><span class="sxs-lookup"><span data-stu-id="a42d0-102">How to: Apply Animations to Text</span></span>
<span data-ttu-id="a42d0-103">Animationen können die Anzeige und die Darstellung von Text in Ihrer Anwendung ändern.</span><span class="sxs-lookup"><span data-stu-id="a42d0-103">Animations can alter the display and appearance of text in your application.</span></span> <span data-ttu-id="a42d0-104">Die folgenden Beispiele verwenden die verschiedene Arten von Animationen die Anzeige von Text in beeinflusst eine <xref:System.Windows.Controls.TextBlock> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a42d0-104">The following examples use different types of animations to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a42d0-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a42d0-105">Example</span></span>  
 <span data-ttu-id="a42d0-106">Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> die Breite des Textblocks animiert.</span><span class="sxs-lookup"><span data-stu-id="a42d0-106">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the width of the text block.</span></span> <span data-ttu-id="a42d0-107">Der Breitenwert ändert sich innerhalb von 10 Sekunden von der Breite des Textblocks auf 0. Anschließend werden die Breitenwerte umgekehrt und es wird fortgefahren.</span><span class="sxs-lookup"><span data-stu-id="a42d0-107">The width value changes from the width of the text block to 0 over a duration of 10 seconds, and then reverses the width values and continues.</span></span> <span data-ttu-id="a42d0-108">Dieser Animationstyp erstellt einen Wipe-Effekt.</span><span class="sxs-lookup"><span data-stu-id="a42d0-108">This type of animation creates a wipe effect.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 <span data-ttu-id="a42d0-109">Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> die Deckkraft des Textblocks animiert.</span><span class="sxs-lookup"><span data-stu-id="a42d0-109">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the opacity of the text block.</span></span> <span data-ttu-id="a42d0-110">Der Deckkraftwert wird über einen Zeitraum von 5 Sekunden von 1,0 auf 0 geändert. Anschließend werden die Deckkraftwerte umgekehrt und es wird fortgefahren.</span><span class="sxs-lookup"><span data-stu-id="a42d0-110">The opacity value changes from 1.0 to 0 over a duration of 5 seconds, and then reverses the opacity values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 <span data-ttu-id="a42d0-111">Das folgende Diagramm zeigt die Auswirkung des der <xref:System.Windows.Controls.TextBlock> Steuerelement Änderung der Durchlässigkeit von `1.00` zu `0.00` während des 5-Sekunden-Intervalls von definiert die <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span><span class="sxs-lookup"><span data-stu-id="a42d0-111">The following diagram shows the effect of the <xref:System.Windows.Controls.TextBlock> control changing its opacity from `1.00` to `0.00` during the 5-second interval defined by the <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span></span>  
  
 <span data-ttu-id="a42d0-112">![Text, der sich ändernder Deckkraft von 1,00 in 0,00](./media/fadedtext01.png "FadedText01")</span><span class="sxs-lookup"><span data-stu-id="a42d0-112">![Text changing opacity from 1.00 to 0.00](./media/fadedtext01.png "FadedText01")</span></span>  
<span data-ttu-id="a42d0-113">Änderung der Deckkraft des Textes von 1,00 in 0,00</span><span class="sxs-lookup"><span data-stu-id="a42d0-113">Text Opacity changing from 1.00 to 0.00</span></span>  
  
 <span data-ttu-id="a42d0-114">Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.ColorAnimation> die Vordergrundfarbe des Textblocks animiert.</span><span class="sxs-lookup"><span data-stu-id="a42d0-114">The following example uses a <xref:System.Windows.Media.Animation.ColorAnimation> to animate the foreground color of the text block.</span></span> <span data-ttu-id="a42d0-115">Der Wert für die Vordergrundfarbe ändert sich im Verlauf von 5 Sekunden von einer Farbe in eine zweite Farbe. Anschließend werden die Farbwerte umgekehrt und es wird fortgefahren.</span><span class="sxs-lookup"><span data-stu-id="a42d0-115">The foreground color value changes from one color to a second color over a duration of 5 seconds, and then reverses the color values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 <span data-ttu-id="a42d0-116">Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> den Textblock gedreht.</span><span class="sxs-lookup"><span data-stu-id="a42d0-116">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to rotate the text block.</span></span> <span data-ttu-id="a42d0-117">Der Textblock führt eine vollständige Drehung über einen Zeitraum von 20 Sekunden aus, und anschließend wird die Drehung wiederholt.</span><span class="sxs-lookup"><span data-stu-id="a42d0-117">The text block performs a full rotation over a duration of 20 seconds, and then continues to repeat the rotation.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a><span data-ttu-id="a42d0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a42d0-118">See also</span></span>
- [<span data-ttu-id="a42d0-119">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="a42d0-119">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
