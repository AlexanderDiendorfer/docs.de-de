---
title: AddHandler-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: dd57f63b5741822de7b11c1fafe90452a767aa34
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965643"
---
# <a name="addhandler-statement"></a><span data-ttu-id="a9c20-102">AddHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a9c20-102">AddHandler Statement</span></span>
<span data-ttu-id="a9c20-103">Ordnet ein Ereignis ein Ereignishandler zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="a9c20-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9c20-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9c20-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="a9c20-105">Teile</span><span class="sxs-lookup"><span data-stu-id="a9c20-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="a9c20-106">event</span><span class="sxs-lookup"><span data-stu-id="a9c20-106">event</span></span>|<span data-ttu-id="a9c20-107">Der Name des zu behandelnden Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="a9c20-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="a9c20-108">Der Name einer Prozedur, die das Ereignis behandelt.</span><span class="sxs-lookup"><span data-stu-id="a9c20-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="a9c20-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a9c20-109">Remarks</span></span>  
 <span data-ttu-id="a9c20-110">Die `AddHandler` und `RemoveHandler` Anweisungen ermöglichen das Starten und beenden die Behandlung von Ereignissen zu einem beliebigen Zeitpunkt während der programmausführung.</span><span class="sxs-lookup"><span data-stu-id="a9c20-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="a9c20-111">Die Signatur der `eventhandler` Verfahren muss der Signatur des Ereignisses entsprechen `event`.</span><span class="sxs-lookup"><span data-stu-id="a9c20-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="a9c20-112">Mit dem Schlüsselwort `Handles` und der Anweisung `AddHandler` können Sie angeben, dass diese bestimmten Prozeduren bestimmte Ereignisse verarbeiten. Es bestehen jedoch keine Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="a9c20-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="a9c20-113">Die Anweisung `AddHandler` verbindet Prozeduren zur Laufzeit mit Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="a9c20-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="a9c20-114">Verwenden Sie das Schlüsselwort `Handles`, wenn Sie eine Prozedur definieren, um anzugeben, dass sie ein bestimmtes Ereignis verarbeitet. </span><span class="sxs-lookup"><span data-stu-id="a9c20-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="a9c20-115">Weitere Informationen finden Sie unter [behandelt](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a9c20-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9c20-116">Für benutzerdefinierte Ereignisse die `AddHandler` -Anweisung ruft des Ereignisses `AddHandler` Accessor.</span><span class="sxs-lookup"><span data-stu-id="a9c20-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="a9c20-117">Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a9c20-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9c20-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9c20-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="a9c20-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9c20-119">See also</span></span>
- [<span data-ttu-id="a9c20-120">RemoveHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a9c20-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="a9c20-121">Handles</span><span class="sxs-lookup"><span data-stu-id="a9c20-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="a9c20-122">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a9c20-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="a9c20-123">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="a9c20-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
