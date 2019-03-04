---
title: 'Vorgehensweise: Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- structs [C#], passing as method parameter
- passing parameters [C#], structs vs. classes
- methods [C#], passing classes vs. structs
ms.assetid: 9c1313a6-32a8-4ea7-a59f-450f66af628b
ms.openlocfilehash: 9664a3e5b5a68ae44bb129c9c550011683c81f16
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981296"
---
# <a name="how-to-know-the-difference-between-passing-a-struct-and-passing-a-class-reference-to-a-method-c-programming-guide"></a>Vorgehensweise: Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode (C#-Programmierhandbuch)
Das folgende Beispiel stellt dar, wie die Übergabe einer [Struktur](../../../csharp/language-reference/keywords/struct.md) an eine Methode sich von der Übergabe einer [Klasseninstanz](../../../csharp/language-reference/keywords/class.md) an eine Methode unterscheidet. Im Beispiel werden beide Argumente (Struktur und Klasseninstanz) nach Wert übergeben, und beide Methoden ändern den Wert eines Felds des Arguments. Allerdings sind die Ergebnisse der beiden Methoden nicht identisch, denn wenn Sie eine Struktur übergeben, unterscheidet sich dies von dem, wenn Sie eine Instanz einer Klasse übergeben.  
  
 Da eine Struktur ein [Werttyp](../../../csharp/language-reference/keywords/value-types.md) ist, wenn Sie [eine Struktur nach Wert](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md) an eine Methode übergeben, erhält und funktioniert die Methode nur mit einer Kopie des Strukturarguments. Die Methode hat keinen Zugriff auf die ursprüngliche Struktur in der aufrufenden Methode und kann sie deshalb nicht ändern. Die Methode kann nur die Kopie ändern.  
  
 Eine Instanz der Klasse ist ein [Verweistyp](../../../csharp/language-reference/keywords/reference-types.md), kein Werttyp. Wenn [ein Verweistyp als Wert](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) an eine Methode übergeben wird, erhält die Methode eine Kopie des Verweises auf die Klasseninstanz. Die Methode erhält also eine Kopie der Adresse der Instanz, keine Kopie der Instanz selbst. Die Klasseninstanz in der aufrufenden Methode verfügt über eine Adresse, der Parameter in der aufgerufenen Methode verfügt über eine Kopie der Adresse und beide Adressen verweisen auf dasselbe Objekt. Da der Parameter nur eine Kopie der Adresse enthält, kann die aufgerufene Methode nicht die Adresse der Klasseninstanz in der aufrufenden Methode ändern. Allerdings kann die aufgerufene Methode die Adresse verwenden, um auf die Klassenmember zuzugreifen, auf die sich die ursprüngliche Adresse sowie die Kopie beziehen. Wenn die aufgerufene Methode einen Klassenmember ändert, ändert sich auch die ursprüngliche Klasseninstanz in der aufrufenden Methode.  
  
 Die Ausgabe des folgenden Beispiels veranschaulicht den Unterschied. Der Wert des Felds `willIChange` der Klasseninstanz wird durch den Aufruf auf die Methode `ClassTaker` geändert, da die Methode die Adresse im Parameter verwendet, um das angegebene Feld der Klasseninstanz zu finden. Das Feld `willIChange` der Struktur in der aufrufenden Methode wird nicht durch den Aufruf auf die Methode `StructTaker` geändert, da der Wert des Arguments eine Kopie der Struktur selbst ist und keine Kopie deren Adresse. `StructTaker` ändert die Kopie, und die Kopie wird abgebrochen, wenn der Aufruf auf `StructTaker` abgeschlossen ist.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideObjects#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#32)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Klassen](../../../csharp/programming-guide/classes-and-structs/classes.md)
- [Strukturen](../../../csharp/programming-guide/classes-and-structs/structs.md)
- [Übergeben von Parametern](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)
