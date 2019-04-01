---
title: <=-Operator - C#-Referenz
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- <=_CSharpKeyword
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
ms.openlocfilehash: 54c8300ad883e81cfb3d4886881984fd5a0ebdb3
ms.sourcegitcommit: 4a8c2b8d0df44142728b68ebc842575840476f6d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545376"
---
# <a name="-operator-c-reference"></a>Operator \<= (C#-Referenz)

Der relationale Operator „kleiner als oder gleich“ `<=` gibt `true` zurück, wenn sein erster Operand kleiner gleich seinem zweiten Operanden ist; andernfalls `false`. Alle numerischen Typen und Enumerationstypen unterstützen den `<=`-Operator. Für Operanden desselben [enum](../keywords/enum.md)-Typs werden die entsprechenden Werte des zugrunde liegenden integralen Typs verglichen.

> [!NOTE]
> Für die relationalen Operatoren `==`, `>`, `<`, `>=` und `<=` ist das Ergebnis eines Vorgangs gleich `false`, wenn einer der Operanden keine Zahl ist (<xref:System.Double.NaN?displayProperty=nameWithType> oder <xref:System.Single.NaN?displayProperty=nameWithType>). Dies bedeutet, dass der `NaN`-Wert weder größer als noch kleiner als noch gleich einem anderen `double`-Wert (oder `float`-Wert) ist. Weitere Informationen und Beispiele finden Sie im <xref:System.Double.NaN?displayProperty=nameWithType>- oder <xref:System.Single.NaN?displayProperty=nameWithType>-Referenzartikel.

Im folgenden Beispiel wird die Verwendung des `<=`-Operators veranschaulicht:

[!code-csharp-interactive[less than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#LessOrEqual)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Benutzerdefinierte Typen können den Operator `<=` [überladen](../keywords/operator.md). Wenn ein Typ den „kleiner als oder gleich“-Operator `<=` überlädt, muss er auch den [„größer als oder gleich“-Operator](greater-than-equal-operator.md) `>=` überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Relationale und Typtestoperatoren](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) in der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [<-Operator](less-than-operator.md)
- [==-Operator](equality-operators.md#equality-operator-)
- <xref:System.IComparable%601?displayProperty=nameWithType>
