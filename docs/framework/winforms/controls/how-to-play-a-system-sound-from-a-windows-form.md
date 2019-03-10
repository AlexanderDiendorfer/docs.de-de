---
title: 'Vorgehensweise: Wiedergabe eines Systemsounds in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing for system events
- playing sounds [Windows Forms], Windows Forms
- system sounds [Windows Forms], playing from Windows Forms
- playing sounds [Windows Forms], system
- SoundPlayer class [Windows Forms], system sounds
- sounds [Windows Forms], playing
- examples [Windows Forms], sounds
ms.assetid: afb206ff-4824-4804-a8d4-185bf5ad8e7c
ms.openlocfilehash: b2ac6c4f2e3334a9b4c5ff4d2a6e31b6b9bf3673
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711224"
---
# <a name="how-to-play-a-system-sound-from-a-windows-form"></a><span data-ttu-id="386f9-102">Vorgehensweise: Wiedergabe eines Systemsounds in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="386f9-102">How to: Play a System Sound from a Windows Form</span></span>
<span data-ttu-id="386f9-103">Im folgenden Codebeispiel wird der Systemsound `Exclamation` zur Laufzeit wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="386f9-103">The following code example plays the `Exclamation` system sound at run time.</span></span> <span data-ttu-id="386f9-104">Weitere Informationen zu Systemsounds finden Sie unter <xref:System.Media.SystemSounds>.</span><span class="sxs-lookup"><span data-stu-id="386f9-104">For more information about system sounds, see <xref:System.Media.SystemSounds>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="386f9-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="386f9-105">Example</span></span>  
  
```vb  
Public Sub PlayExclamation()  
    SystemSounds.Exclamation.Play()  
End Sub  
```  
  
```csharp  
public void playExclamation()  
{  
    SystemSounds.Exclamation.Play();  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="386f9-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="386f9-106">Compiling the Code</span></span>  
 <span data-ttu-id="386f9-107">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="386f9-107">This example requires:</span></span>  
  
-   <span data-ttu-id="386f9-108">Einen Verweis auf den <xref:System.Media?displayProperty=nameWithType>-Namespace</span><span class="sxs-lookup"><span data-stu-id="386f9-108">A reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="386f9-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="386f9-109">See also</span></span>
- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
- [<span data-ttu-id="386f9-110">Vorgehensweise: Wiedergabe eines Signaltons in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="386f9-110">How to: Play a Beep from a Windows Form</span></span>](how-to-play-a-beep-from-a-windows-form.md)
- [<span data-ttu-id="386f9-111">Vorgehensweise: Wiedergabe von Sound in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="386f9-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
