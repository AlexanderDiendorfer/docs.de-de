---
title: <type1> '<typename>' muss '<methodname>' für die <interfacename>-Schnittstelle implementieren.
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: c5dd7c6889a3fb5344142ee9914f98e8922d748b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55264432"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a>\<Typ1 >'\<Typname > 'implementieren muss'\<Methodname > 'für Schnittstelle'\<Schnittstellenname >'
Eine Klasse oder Struktur vorgibt, eine Schnittstelle zu implementieren, ohne dass eine Prozedur, die von der Schnittstelle definierten implementiert. Jeder Member der Schnittstelle muss implementiert werden.  
  
 **Fehler-ID:** BC30149  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Deklarieren Sie eine Prozedur mit dem gleichen Namen und die gleiche Signatur wie in der Schnittstelle definiert. Müssen Sie mindestens die `End Function` oder `End Sub` Anweisung.  
  
2.  Hinzufügen einer `Implements` Klausel am Ende der `Function` oder `Sub` Anweisung. Zum Beispiel:  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>Siehe auch
- [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
