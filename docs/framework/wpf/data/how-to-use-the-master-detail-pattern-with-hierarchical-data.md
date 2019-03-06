---
title: 'Vorgehensweise: Verwenden des Master-/Detailmusters mit hierarchischen Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: 41f02013feb1405e5640afa73b954dc84921c924
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351481"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>Vorgehensweise: Verwenden des Master-/Detailmusters mit hierarchischen Daten
Dieses Beispiel zeigt, wie Sie das Master / Detail-Szenario zu implementieren.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel `LeagueList` ist eine Sammlung von `Leagues`. Jede `League` verfügt über eine `Name` und eine Sammlung von `Divisions`, und jede `Division` hat einen Namen und eine Auflistung von `Teams`. Jede `Team` verfügt über ein Teamname.  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 Im Folgenden finden Sie ein Bildschirmfoto des Beispiels. Die `Divisions` <xref:System.Windows.Controls.ListBox> verfolgt automatisch die Auswahlmöglichkeiten in den `Leagues` <xref:System.Windows.Controls.ListBox> und die entsprechenden Daten anzuzeigen. Die `Teams` <xref:System.Windows.Controls.ListBox> verfolgt die Auswahlmöglichkeiten in den anderen beiden <xref:System.Windows.Controls.ListBox> Steuerelemente.  
  
 ![Master&#45;Detail-Beispiel](./media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")  
  
 Die beiden in diesem Beispiel sind zu beachten:  
  
1.  Die drei <xref:System.Windows.Controls.ListBox> Steuerelemente an dieselbe Quelle binden. Festlegen der <xref:System.Windows.Data.Binding.Path%2A> -Eigenschaft der Bindung angeben, welche Ebene der Daten sollen die <xref:System.Windows.Controls.ListBox> angezeigt.  
  
2.  Müssen Sie festlegen, die <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> Eigenschaft `true` auf die <xref:System.Windows.Controls.ListBox> Steuerelemente, von denen die Auswahl, die Sie verfolgen. Durch Festlegen dieser Eigenschaft wird sichergestellt, dass das ausgewählte Element immer, als festgelegt ist die <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. Auch wenn die <xref:System.Windows.Controls.ListBox> ruft es die Daten aus einer <xref:System.Windows.Data.CollectionViewSource>, diese Auswahl und Aktualität wird automatisch synchronisiert.  
  
 Das Verfahren unterscheidet sich geringfügig bei Verwendung von [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten. Ein Beispiel finden Sie unter [verwenden Sie die Master-/ Detailmusters mit hierarchischen XML-Daten](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.HierarchicalDataTemplate>
- [Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Übersicht über Datenvorlagen](data-templating-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
