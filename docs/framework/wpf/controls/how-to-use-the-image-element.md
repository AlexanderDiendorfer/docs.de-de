---
title: 'Vorgehensweise: Verwenden des Image-Elements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Image
- Image control [WPF]
- rendering images [WPF]
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
ms.openlocfilehash: ec3ca16915038ebbb68df24bfd071168c346663d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372463"
---
# <a name="how-to-use-the-image-element"></a><span data-ttu-id="c7118-102">Vorgehensweise: Verwenden des Image-Elements</span><span class="sxs-lookup"><span data-stu-id="c7118-102">How to: Use the Image Element</span></span>
<span data-ttu-id="c7118-103">Dieses Beispiel zeigt, wie Sie Bilder in einer Anwendung einfügen, mit der <xref:System.Windows.Controls.Image> Element.</span><span class="sxs-lookup"><span data-stu-id="c7118-103">This example shows how to include images in an application by using the <xref:System.Windows.Controls.Image> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7118-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7118-104">Example</span></span>  
 <span data-ttu-id="c7118-105">Im folgenden Beispiel wird veranschaulicht, wie ein Bild auf eine Breite von 200 Pixel gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="c7118-105">The following example shows how to render an image 200 pixels wide.</span></span> <span data-ttu-id="c7118-106">In diesem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Beispielwerden die Attributsyntax und die Syntax der Eigenschaftstags dazu verwendet, um das Bild zu definieren.</span><span class="sxs-lookup"><span data-stu-id="c7118-106">In this [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example, both attribute syntax and property tag syntax are used to define the image.</span></span> <span data-ttu-id="c7118-107">Weitere Informationen über Attributsyntax und Eigenschaftensyntax finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c7118-107">For more information on attribute syntax and property syntax, see [Dependency Properties Overview](../advanced/dependency-properties-overview.md).</span></span> <span data-ttu-id="c7118-108">Ein <xref:System.Windows.Media.Imaging.BitmapImage> wird zum Definieren der Quelldaten des Bilds verwendet und für die Eigenschaft Tag Syntaxbeispiel explizit definiert.</span><span class="sxs-lookup"><span data-stu-id="c7118-108">A <xref:System.Windows.Media.Imaging.BitmapImage> is used to define the image's source data and is explicitly defined for the property tag syntax example.</span></span> <span data-ttu-id="c7118-109">Darüber hinaus die <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> von der <xref:System.Windows.Media.Imaging.BitmapImage> festgelegt ist, auf die gleiche Breite wie die <xref:System.Windows.FrameworkElement.Width%2A> von der <xref:System.Windows.Controls.Image>.</span><span class="sxs-lookup"><span data-stu-id="c7118-109">In addition, the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> of the <xref:System.Windows.Media.Imaging.BitmapImage> is set to the same width as the <xref:System.Windows.FrameworkElement.Width%2A> of the <xref:System.Windows.Controls.Image>.</span></span> <span data-ttu-id="c7118-110">Hiermit wird sichergestellt, dass die Mindestmenge an Arbeitsspeicher zum Rendern des Bilds verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7118-110">This is done to ensure that the minimum amount of memory is used rendering the image.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7118-111">Im Allgemeinen, wenn Sie die Größe eines gerenderten Bilds angeben möchten, geben Sie nur die <xref:System.Windows.FrameworkElement.Width%2A> oder <xref:System.Windows.FrameworkElement.Height%2A> jedoch nicht beides.</span><span class="sxs-lookup"><span data-stu-id="c7118-111">In general, if you want to specify the size of a rendered image, specify only the <xref:System.Windows.FrameworkElement.Width%2A> or the <xref:System.Windows.FrameworkElement.Height%2A> but not both.</span></span> <span data-ttu-id="c7118-112">Wenn Sie nur eines angeben, wird das Seitenverhältnis des Bilds beibehalten.</span><span class="sxs-lookup"><span data-stu-id="c7118-112">If you only specify one, the image's aspect ratio is preserved.</span></span> <span data-ttu-id="c7118-113">Andernfalls wird das Bild möglicherweise unerwartet gestreckt oder verzerrt.</span><span class="sxs-lookup"><span data-stu-id="c7118-113">Otherwise, the image may unexpectedly appear stretched or warped.</span></span> <span data-ttu-id="c7118-114">Steuern Sie das Image streckungsverhalten, verwenden Sie die <xref:System.Windows.Controls.Image.Stretch%2A> und <xref:System.Windows.Controls.Image.StretchDirection%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c7118-114">To control the image's stretching behavior, use the <xref:System.Windows.Controls.Image.Stretch%2A> and <xref:System.Windows.Controls.Image.StretchDirection%2A> properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7118-115">Wenn Sie die Größe eines Bilds angeben, mit einem <xref:System.Windows.FrameworkElement.Width%2A> oder <xref:System.Windows.FrameworkElement.Height%2A>, Sie sollten auch festlegen, entweder <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> oder <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> auf dieselbe Größe.</span><span class="sxs-lookup"><span data-stu-id="c7118-115">When you specify the size of an image with either <xref:System.Windows.FrameworkElement.Width%2A> or <xref:System.Windows.FrameworkElement.Height%2A>, you should also set either <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> or <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> to the same respective size.</span></span>  
  
 <span data-ttu-id="c7118-116">Die <xref:System.Windows.Controls.Image.Stretch%2A> Eigenschaft bestimmt, wie die Bildquelle gestreckt wird, um das Image-Element auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="c7118-116">The <xref:System.Windows.Controls.Image.Stretch%2A> property determines how the image source is stretched to fill the image element.</span></span> <span data-ttu-id="c7118-117">Weitere Informationen finden Sie unter der <xref:System.Windows.Media.Stretch>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="c7118-117">For more information, see the <xref:System.Windows.Media.Stretch> enumeration.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="c7118-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7118-118">Example</span></span>  
 <span data-ttu-id="c7118-119">Im folgenden Beispiel wird veranschaulicht, wie ein Bild mithilfe von Code auf eine Breite von 200 Pixel gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="c7118-119">The following example shows how to render an image 200 pixels wide using code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7118-120">Festlegen von <xref:System.Windows.Media.Imaging.BitmapImage> Eigenschaften müssen ausgeführt werden, in einem <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> und <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> Block.</span><span class="sxs-lookup"><span data-stu-id="c7118-120">Setting <xref:System.Windows.Media.Imaging.BitmapImage> properties must be done within a <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> and <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> block.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="c7118-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7118-121">See also</span></span>
- [<span data-ttu-id="c7118-122">Übersicht über die Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="c7118-122">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)
