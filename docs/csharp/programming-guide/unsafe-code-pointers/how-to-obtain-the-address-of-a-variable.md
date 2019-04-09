---
title: 'Vorgehensweise: Abrufen der Adresse einer Variablen – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
ms.openlocfilehash: b12d3bf99f32a3526bd4a1ec8c49b1fd88afd68a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832345"
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="0af42-102">Gewusst wie: Abrufen der Adresse einer Variablen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="0af42-102">How to: obtain the address of a variable (C# Programming Guide)</span></span>

<span data-ttu-id="0af42-103">Verwenden Sie den address-of-Operator `&` zum Abrufen der Adresse eines unären Ausdrucks, der eine feste Variable ergibt:</span><span class="sxs-lookup"><span data-stu-id="0af42-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator `&`:</span></span>  
  
```csharp  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="0af42-104">Der address-of-Operator kann nur auf eine Variable angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0af42-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="0af42-105">Wenn die Variable beweglich ist, können Sie eine [feste Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md) verwenden, um die Variable vorübergehen zu befestigen, um ihre Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0af42-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span> <span data-ttu-id="0af42-106">Weitere Informationen zu verschiebbaren Variablen finden Sie unter [Feste und verschiebbare Variablen](/dotnet/csharp/language-reference/language-specification/unsafe-code#fixed-and-moveable-variables).</span><span class="sxs-lookup"><span data-stu-id="0af42-106">For more information about moveable variables, see [Fixed and moveable variables](/dotnet/csharp/language-reference/language-specification/unsafe-code#fixed-and-moveable-variables).</span></span> 
  
 <span data-ttu-id="0af42-107">Sie müssen sicherstellen, dass die Variable initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="0af42-107">It's your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="0af42-108">Der Compiler gibt keine Fehlermeldung aus, wenn die Variable nicht initialisiert ist.</span><span class="sxs-lookup"><span data-stu-id="0af42-108">The compiler doesn't issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="0af42-109">Sie können nicht die Adresse einer Konstanten oder eines Werts abrufen.</span><span class="sxs-lookup"><span data-stu-id="0af42-109">You can't get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0af42-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0af42-110">Example</span></span>  
 <span data-ttu-id="0af42-111">In diesem Beispiel wird ein Zeiger auf `int`, `p`, deklariert. Die Adresse einer ganzzahligen Variable, `number`, wird ihm zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0af42-111">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="0af42-112">Die Variable `number` wird als Ergebnis der Zuweisung zu `*p` initialisiert.</span><span class="sxs-lookup"><span data-stu-id="0af42-112">The variable `number` is initialized as a result of the assignment to `*p`.</span></span> <span data-ttu-id="0af42-113">Wenn Sie diese Zuweisungsanweisung auskommentieren, wird die Initialisierung der Variable `number` entfernt, jedoch wird kein Kompilierzeitfehler ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="0af42-113">If you comment out this assignment statement, the initialization of the variable `number` is removed, but no compile-time error is issued.</span></span>  

> [!NOTE]
> <span data-ttu-id="0af42-114">Kompilieren Sie dieses Beispiel mit der Compileroption [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="0af42-114">Compile this example with the [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
 [!code-csharp[address-of-a-variable](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="0af42-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0af42-115">See also</span></span>

- [<span data-ttu-id="0af42-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0af42-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="0af42-117">Zeigerausdrücke</span><span class="sxs-lookup"><span data-stu-id="0af42-117">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="0af42-118">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="0af42-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="0af42-119">Typen</span><span class="sxs-lookup"><span data-stu-id="0af42-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="0af42-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="0af42-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="0af42-121">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0af42-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="0af42-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="0af42-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
