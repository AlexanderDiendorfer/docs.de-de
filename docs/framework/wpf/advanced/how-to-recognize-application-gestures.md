---
title: 'Vorgehensweise: Erkennen von Bewegungen in Anwendungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application gestures [WPF], recognizing
- gestures [WPF], recognizing
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
ms.openlocfilehash: 99deaa528a089f2d16268747f2e946873f3420a0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370513"
---
# <a name="how-to-recognize-application-gestures"></a><span data-ttu-id="2a784-102">Vorgehensweise: Erkennen von Bewegungen in Anwendungen</span><span class="sxs-lookup"><span data-stu-id="2a784-102">How To: Recognize Application Gestures</span></span>
<span data-ttu-id="2a784-103">Das folgende Beispiel zeigt, wie Sie Freihandeingaben zu löschen, wenn ein Benutzer stellt eine <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> Gesten auf einem <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="2a784-103">The following example demonstrates how to erase ink when a user makes a <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> gesture on an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="2a784-104">In diesem Beispiel geht davon aus einem <xref:System.Windows.Controls.InkCanvas>namens `inkCanvas1`, in der XAML-Datei deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="2a784-104">This example assumes an <xref:System.Windows.Controls.InkCanvas>, called `inkCanvas1`, is declared in the XAML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a784-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2a784-105">Example</span></span>  
 [!code-csharp[HowToRecognizeGestures#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2a784-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a784-106">See also</span></span>
- <xref:System.Windows.Ink.ApplicationGesture>
- <xref:System.Windows.Controls.InkCanvas>
- <xref:System.Windows.Controls.InkCanvas.Gesture>
