---
title: Erstellen von Ereignishandlern in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- event handling [Windows Forms]
- Windows Forms controls, event handling
- Windows Forms, event handling
- events [Windows Forms], event handlers
- event handlers [Windows Forms]
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
ms.openlocfilehash: c77a004d52afc67a3811ff98e9a62c788c001803
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664782"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="d4f9a-102">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4f9a-102">Creating Event Handlers in Windows Forms</span></span>
<span data-ttu-id="d4f9a-103">Ein Ereignishandler stellt eine Prozedur in Ihrem Code dar, mit der festgelegt wird, welche Aktionen beim Eintreten eines bestimmten Ereignisses durchgeführt werden. Dies bezieht sich beispielsweise auf jene Fälle bei denen der Benutzer auf eine Schaltfläche klickt oder eine Meldungswarteschlange eine Meldung empfängt.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="d4f9a-104">Wenn ein Ereignis ausgelöst wird, werden der Ereignishandler oder jene Handler ausgeführt, die das betreffende Ereignis empfangen.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="d4f9a-105">Ereignisse lassen sich mehreren Handlern zuweisen. Außerdem können die Methoden, die besondere Ereignisse verwalten, dynamisch geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="d4f9a-106">Sie können zum Erstellen von Ereignishandlern auch den Windows Forms-Designer verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-106">You can also use the Windows Forms Designer to create event handlers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4f9a-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d4f9a-107">In This Section</span></span>  
 [<span data-ttu-id="d4f9a-108">Übersicht über Ereignisse</span><span class="sxs-lookup"><span data-stu-id="d4f9a-108">Events Overview</span></span>](../../../docs/framework/winforms/events-overview-windows-forms.md)  
 <span data-ttu-id="d4f9a-109">Erläutert das Ereignismodell und die Rolle der Delegaten.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-109">Explains the event model and the role of delegates.</span></span>  
  
 [<span data-ttu-id="d4f9a-110">Übersicht über Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="d4f9a-110">Event Handlers Overview</span></span>](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)  
 <span data-ttu-id="d4f9a-111">Beschreibt, wie Ereignisse behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-111">Describes how to handle events.</span></span>  
  
 [<span data-ttu-id="d4f9a-112">Vorgehensweise: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="d4f9a-112">How to: Create Event Handlers at Run Time for Windows Forms</span></span>](../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)  
 <span data-ttu-id="d4f9a-113">Gibt Richtungshinweise für eine dynamische Reaktion auf System- oder Benutzerereignisse an.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-113">Gives directions for responding to system or user events dynamically.</span></span>  
  
 [<span data-ttu-id="d4f9a-114">Vorgehensweise: Verbinden Sie mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4f9a-114">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)  
 <span data-ttu-id="d4f9a-115">Gibt Richtungshinweise zum Zuordnen derselben Funktionalität auf mehrere Steuerelemente bei Ereignissen an.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>  
  
 [<span data-ttu-id="d4f9a-116">Ereignisreihenfolge in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4f9a-116">Order of Events in Windows Forms</span></span>](../../../docs/framework/winforms/order-of-events-in-windows-forms.md)  
 <span data-ttu-id="d4f9a-117">Beschreibt die Reihenfolge, in der Ereignisse in den Windows Forms-Steuerelementen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-117">Describes the order in which events are raised in Windows Forms controls.</span></span>  
  
 <span data-ttu-id="d4f9a-118">[Vorgehensweise: Erstellen von Ereignishandlern mithilfe des Designers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d4f9a-118">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))</span></span>  
 <span data-ttu-id="d4f9a-119">Beschreibt, wie der Windows Forms-Designer zum Erstellen von Ereignishandlern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-119">Describes how to use the Windows Forms Designer to create event handlers.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d4f9a-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d4f9a-120">Related Sections</span></span>  
 [<span data-ttu-id="d4f9a-121">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="d4f9a-121">Events</span></span>](../../../docs/standard/events/index.md)  
 <span data-ttu-id="d4f9a-122">Bietet Links zu Themen bezüglich Behandlung und Auslösung von Ereignissen mit [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4f9a-122">Provides links to topics on handling and raising events using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
 [<span data-ttu-id="d4f9a-123">Problembehandlung für geerbte Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4f9a-123">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 <span data-ttu-id="d4f9a-124">Listet häufige Probleme, die bei Ereignishandlern in vererbten Komponenten auftreten.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-124">Lists common issues that occur with event handlers in inherited components.</span></span>
