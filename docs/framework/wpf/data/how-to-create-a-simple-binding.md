---
title: 'Vorgehensweise: Erstellen von einfachen Bindungen'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: d617c8b97aa679398ed2d061a652f5164f1e499b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094384"
---
# <a name="how-to-create-a-simple-binding"></a>Vorgehensweise: Erstellen von einfachen Bindungen
Dieses Beispiel zeigt, wie zum Erstellen eines einfachen <xref:System.Windows.Data.Binding>.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel verfügen Sie über eine `Person` Objekt mit einer Zeichenfolgeneigenschaft, die mit dem Namen `PersonName`. Die `Person` Objekt wird definiert, in dem Namespace namens `SDKSample`.  
  
 Die hervorgehobene Zeile mit der `<src>` Element im folgenden Beispiel instanziiert die `Person` Objekt mit einer `PersonName` Eigenschaftswert `Joe`. Dies erfolgt in der `Resources` Abschnitt zugewiesen, und wählen Sie eine `x:Key`.  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Die hervorgehobene Zeile mit der `<TextBlock>` -Element bindet dann die <xref:System.Windows.Controls.TextBlock> die Steuerung an die `PersonName` Eigenschaft. Daher die <xref:System.Windows.Controls.TextBlock> mit dem Wert "Joe" angezeigt wird.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Datenbindung](data-binding-overview.md)
- [Gewusst wie-Themen](data-binding-how-to-topics.md)
