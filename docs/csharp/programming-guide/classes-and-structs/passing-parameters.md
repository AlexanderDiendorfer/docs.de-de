---
title: Übergeben von Parametern – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: c8da86d2a8f5101acf5b9cc1bcc2f9ad50378fa4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969543"
---
# <a name="passing-parameters-c-programming-guide"></a>Übergeben von Parametern (C#-Programmierhandbuch)
In C# können Argumente an Parameter entweder als Wert oder als Verweis übergeben werden. Durch die Übergabe als Verweis können Funktionsmember, Methoden, Eigenschaften, Indexer, Operatoren und Konstruktoren den Wert der Parameter ändern und behalten diese Änderung in der aufrufenden Umgebung bei. Wenn Sie den Wert ändern und darum den Parameter pro Verweis übergeben möchten, verwenden Sie die Schlüsselwörter `ref` oder `out`. Wenn Sie den Wert zwar ändern, aber keine Kopie erstellen möchten, und darum den Parameter pro Verweis übergeben möchten, verwenden Sie den Modifizierer `in`. Der Einfachheit halber wird in den Beispielen in diesem Thema nur das Schlüsselwort `ref` verwendet. Weitere Informationen zum Unterschied zwischen `in`, `ref` und `out` finden Sie unter [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) und [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md).  
  
 Das folgende Beispiel veranschaulicht die Unterschiede zwischen Wert- und Verweisparametern.  
  
 [!code-csharp[csProgGuideParameters#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#10)]  
  
 Weitere Informationen finden Sie unter den folgenden Themen:  
  
-   [Übergeben von Werttypparametern](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [Übergeben von Verweistypparametern](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  

Weitere Informationen erhalten Sie in den [Argumentlisten](~/_csharplang/spec/expressions.md#argument-lists) in der [C#-Sprachspezifikation](../../language-reference/language-specification/index.md). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)
