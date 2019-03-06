---
title: 'Vorgehensweise: Behandeln des MouseDoubleClick-Ereignisses für die einzelnen ListView-Einträge'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: a4a93ffdf7c9cf2737c41a7fd196d8cfff716ea1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377198"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="54575-102">Vorgehensweise: Behandeln des MouseDoubleClick-Ereignisses für die einzelnen ListView-Einträge</span><span class="sxs-lookup"><span data-stu-id="54575-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="54575-103">Behandeln eines Ereignisses für ein Element in einem <xref:System.Windows.Controls.ListView>, müssen Sie zum Hinzufügen eines ereignishandlers zu jeder <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="54575-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="54575-104">Wenn eine <xref:System.Windows.Controls.ListView> gebunden ist Sie nicht explizit erstellen, mit einer Datenquelle eine <xref:System.Windows.Controls.ListViewItem>, aber Sie können das Ereignis für jedes Element behandeln, durch das Hinzufügen eine <xref:System.Windows.EventSetter> , einem Stil ein <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="54575-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54575-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="54575-105">Example</span></span>  
 <span data-ttu-id="54575-106">Das folgende Beispiel erstellt eine datengebundene <xref:System.Windows.Controls.ListView> und erstellt eine <xref:System.Windows.Style> zum Hinzufügen eines ereignishandlers zu jeder <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="54575-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="54575-107">Das folgende Beispiel verarbeitet die <xref:System.Windows.Controls.Control.MouseDoubleClick> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="54575-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  <span data-ttu-id="54575-108">Obwohl es am häufigsten verwendeten gebunden ist, eine <xref:System.Windows.Controls.ListView> mit einer Datenquelle können Sie einen Stil verwenden, um einen Ereignishandler hinzuzufügen <xref:System.Windows.Controls.ListViewItem> in einer nicht-datengebundenen <xref:System.Windows.Controls.ListView> unabhängig davon, ob Sie explizit erstellen eine <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="54575-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="54575-109">Weitere Informationen zu explizit und implizit erstellten <xref:System.Windows.Controls.ListViewItem> Steuerelemente finden Sie <xref:System.Windows.Controls.ItemsControl>.</span><span class="sxs-lookup"><span data-stu-id="54575-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54575-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54575-110">See also</span></span>
- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="54575-111">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="54575-111">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="54575-112">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="54575-112">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="54575-113">Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen</span><span class="sxs-lookup"><span data-stu-id="54575-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="54575-114">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="54575-114">ListView Overview</span></span>](listview-overview.md)
