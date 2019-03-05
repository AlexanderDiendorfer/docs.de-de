---
title: C#-Ausdrücke – Überblick über C#
description: Ausdrücke, Operanden und Operatoren sind Bausteine der Sprache C#.
ms.date: 11/06/2016
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 682f98d51bf4eb3c1641297972afb86956e06d3e
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212091"
---
# <a name="expressions"></a><span data-ttu-id="0168d-103">Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="0168d-103">Expressions</span></span>

<span data-ttu-id="0168d-104">*Ausdrücke* bestehen aus *Operanden* und *Operatoren*.</span><span class="sxs-lookup"><span data-stu-id="0168d-104">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="0168d-105">Die Operatoren eines Ausdrucks geben an, welche Operationen auf die Operanden angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0168d-105">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="0168d-106">Beispiele für Operatoren sind `+`, `-`, `*`, `/` und `new`.</span><span class="sxs-lookup"><span data-stu-id="0168d-106">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="0168d-107">Beispiele für Operanden sind Literale, Felder, lokale Variablen und Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="0168d-107">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="0168d-108">Wenn ein Ausdruck mehrere Operatoren enthält, bestimmt die *Rangfolge* der Operatoren die Reihenfolge, in der die einzelnen Operatoren ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="0168d-108">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="0168d-109">Der Ausdruck `x + y * z` wird z.B. als `x + (y * z)` ausgewertet, da der `*`-Operator Vorrang vor dem `+`-Operator hat.</span><span class="sxs-lookup"><span data-stu-id="0168d-109">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="0168d-110">Tritt ein Operand zwischen zwei Operatoren mit gleicher Rangfolge auf, steuert die *Assoziativität* der Operatoren die Reihenfolge, in der die Vorgänge ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="0168d-110">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

*   <span data-ttu-id="0168d-111">Mit Ausnahme der Zuweisungsoperatoren sind alle binären Operatoren *linksassoziativ*, was bedeutet, dass Vorgänge von links nach rechts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0168d-111">Except for the assignment operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="0168d-112">`x + y + z` wird beispielsweise als `(x + y) + z` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="0168d-112">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
*   <span data-ttu-id="0168d-113">Die Zuweisungsoperatoren und der bedingte Operator (`?:`) sind *rechtsassoziativ*, d.h., die Operationen werden von rechts nach links ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0168d-113">The assignment operators and the conditional operator (`?:`) are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="0168d-114">`x = y = z` wird beispielsweise als `x = (y = z)` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="0168d-114">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="0168d-115">Rangfolge und Assoziativität können mit Klammern gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="0168d-115">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="0168d-116">In `x + y * z` wird beispielsweise zuerst `y` mit `z` multipliziert und dann das Ergebnis zu `x` addiert, aber in `(x + y) * z` werden zunächst `x` und `y` addiert, und dann wird das Ergebnis mit `z` multipliziert.</span><span class="sxs-lookup"><span data-stu-id="0168d-116">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="0168d-117">Die meisten Operatoren können *überladen* werden.</span><span class="sxs-lookup"><span data-stu-id="0168d-117">Most operators can be *overloaded*.</span></span> <span data-ttu-id="0168d-118">Das Überladen von Operatoren ermöglicht die Angabe benutzerdefinierter Operatorimplementierungen für Vorgänge, in denen einer der Operanden oder beide einer benutzerdefinierten Klasse oder einem benutzerdefinierten Strukturtyp angehören.</span><span class="sxs-lookup"><span data-stu-id="0168d-118">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="0168d-119">In der folgenden Übersicht der C#-Operatoren werden die Operatorkategorien gemäß der Rangfolge von oben nach unten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="0168d-119">The following summarizes C#’s operators, listing the operator categories in order of precedence from highest to lowest.</span></span> <span data-ttu-id="0168d-120">Operatoren der gleichen Kategorie haben den gleichen Rang.</span><span class="sxs-lookup"><span data-stu-id="0168d-120">Operators in the same category have equal precedence.</span></span> <span data-ttu-id="0168d-121">Jede Kategorie enthält eine Liste von Ausdrücken mit der Beschreibung des jeweiligen Ausdruckstyps.</span><span class="sxs-lookup"><span data-stu-id="0168d-121">Under each category is a list of expressions in that category along with the description of that expression type.</span></span>

* <span data-ttu-id="0168d-122">Primär</span><span class="sxs-lookup"><span data-stu-id="0168d-122">Primary</span></span>
    - <span data-ttu-id="0168d-123">`x.m`: Memberzugriff</span><span class="sxs-lookup"><span data-stu-id="0168d-123">`x.m`: Member access</span></span>
    - <span data-ttu-id="0168d-124">`x(...)`: Methoden- und Delegataufruf</span><span class="sxs-lookup"><span data-stu-id="0168d-124">`x(...)`: Method and delegate invocation</span></span>
    - <span data-ttu-id="0168d-125">`x[...]`: Array- und Indexerzugriff</span><span class="sxs-lookup"><span data-stu-id="0168d-125">`x[...]`: Array and indexer access</span></span>
    - <span data-ttu-id="0168d-126">`x++`: Postinkrement</span><span class="sxs-lookup"><span data-stu-id="0168d-126">`x++`: Post-increment</span></span>
    - <span data-ttu-id="0168d-127">`x--`: Postdekrement</span><span class="sxs-lookup"><span data-stu-id="0168d-127">`x--`: Post-decrement</span></span>
    - <span data-ttu-id="0168d-128">`new T(...)`: Objekt- und Delegaterstellung</span><span class="sxs-lookup"><span data-stu-id="0168d-128">`new T(...)`: Object and delegate creation</span></span>
    - <span data-ttu-id="0168d-129">`new T(...){...}`: Objekterstellung mit Initialisierer</span><span class="sxs-lookup"><span data-stu-id="0168d-129">`new T(...){...}`: Object creation with initializer</span></span>
    - <span data-ttu-id="0168d-130">`new {...}`:  Anonymer Objektinitialisierer</span><span class="sxs-lookup"><span data-stu-id="0168d-130">`new {...}`:  Anonymous object initializer</span></span>
    - <span data-ttu-id="0168d-131">`new T[...]`: Arrayerstellung</span><span class="sxs-lookup"><span data-stu-id="0168d-131">`new T[...]`: Array creation</span></span>
    - <span data-ttu-id="0168d-132">`typeof(T)`: Abrufen von <xref:System.Type>-Objekt für `T`</span><span class="sxs-lookup"><span data-stu-id="0168d-132">`typeof(T)`: Obtain <xref:System.Type> object for `T`</span></span>
    - <span data-ttu-id="0168d-133">`checked(x)`: Auswerten von Ausdrücken in geprüftem Kontext</span><span class="sxs-lookup"><span data-stu-id="0168d-133">`checked(x)`: Evaluate expression in checked context</span></span>
    - <span data-ttu-id="0168d-134">`unchecked(x)`: Auswerten von Ausdrücken in nicht geprüftem Kontext</span><span class="sxs-lookup"><span data-stu-id="0168d-134">`unchecked(x)`: Evaluate expression in unchecked context</span></span>
    - <span data-ttu-id="0168d-135">`default(T)`: Abrufen des Standardwerts vom Typ `T`</span><span class="sxs-lookup"><span data-stu-id="0168d-135">`default(T)`: Obtain default value of type `T`</span></span>
    - <span data-ttu-id="0168d-136">`delegate {...}`: Anonyme Funktion (anonyme Methode)</span><span class="sxs-lookup"><span data-stu-id="0168d-136">`delegate {...}`: Anonymous function (anonymous method)</span></span>
* <span data-ttu-id="0168d-137">Unär</span><span class="sxs-lookup"><span data-stu-id="0168d-137">Unary</span></span>
    - <span data-ttu-id="0168d-138">`+x`: Identität</span><span class="sxs-lookup"><span data-stu-id="0168d-138">`+x`: Identity</span></span>
    - <span data-ttu-id="0168d-139">`-x`: Negation</span><span class="sxs-lookup"><span data-stu-id="0168d-139">`-x`: Negation</span></span>
    - <span data-ttu-id="0168d-140">`!x`: Logische Negation</span><span class="sxs-lookup"><span data-stu-id="0168d-140">`!x`: Logical negation</span></span>
    - <span data-ttu-id="0168d-141">`~x`: Bitweise Negation</span><span class="sxs-lookup"><span data-stu-id="0168d-141">`~x`: Bitwise negation</span></span>
    - <span data-ttu-id="0168d-142">`++x`: Präinkrement</span><span class="sxs-lookup"><span data-stu-id="0168d-142">`++x`: Pre-increment</span></span>
    - <span data-ttu-id="0168d-143">`--x`: Prädekrement</span><span class="sxs-lookup"><span data-stu-id="0168d-143">`--x`: Pre-decrement</span></span>
    - <span data-ttu-id="0168d-144">`(T)x`: Explizites Konvertieren von `x` in den Typ `T`</span><span class="sxs-lookup"><span data-stu-id="0168d-144">`(T)x`: Explicitly convert `x` to type `T`</span></span>
    - <span data-ttu-id="0168d-145">`await x`: Asynchrones Warten auf den Abschluss von `x`</span><span class="sxs-lookup"><span data-stu-id="0168d-145">`await x`: Asynchronously wait for `x` to complete</span></span>
* <span data-ttu-id="0168d-146">Multiplikativ</span><span class="sxs-lookup"><span data-stu-id="0168d-146">Multiplicative</span></span>
    - <span data-ttu-id="0168d-147">`x * y`: Multiplikation</span><span class="sxs-lookup"><span data-stu-id="0168d-147">`x * y`: Multiplication</span></span>
    - <span data-ttu-id="0168d-148">`x / y`: Division</span><span class="sxs-lookup"><span data-stu-id="0168d-148">`x / y`: Division</span></span>
    - <span data-ttu-id="0168d-149">`x % y`: Rest</span><span class="sxs-lookup"><span data-stu-id="0168d-149">`x % y`: Remainder</span></span>
* <span data-ttu-id="0168d-150">Additiv</span><span class="sxs-lookup"><span data-stu-id="0168d-150">Additive</span></span>
    - <span data-ttu-id="0168d-151">`x + y`: Addition, Zeichenfolgenverkettung, Delegatkombination</span><span class="sxs-lookup"><span data-stu-id="0168d-151">`x + y`: Addition, string concatenation, delegate combination</span></span>
    - <span data-ttu-id="0168d-152">`x – y`: Subtraktion, Delegatentfernung</span><span class="sxs-lookup"><span data-stu-id="0168d-152">`x – y`: Subtraction, delegate removal</span></span>
* <span data-ttu-id="0168d-153">Shift</span><span class="sxs-lookup"><span data-stu-id="0168d-153">Shift</span></span>
    - <span data-ttu-id="0168d-154">`x << y`: Linksverschiebung</span><span class="sxs-lookup"><span data-stu-id="0168d-154">`x << y`: Shift left</span></span>
    - <span data-ttu-id="0168d-155">`x >> y`: Rechtsverschiebung</span><span class="sxs-lookup"><span data-stu-id="0168d-155">`x >> y`: Shift right</span></span>
* <span data-ttu-id="0168d-156">Relational und Typtest</span><span class="sxs-lookup"><span data-stu-id="0168d-156">Relational and type testing</span></span>
    - <span data-ttu-id="0168d-157">`x < y`: Kleiner als </span><span class="sxs-lookup"><span data-stu-id="0168d-157">`x < y`: Less than</span></span>
    - <span data-ttu-id="0168d-158">`x > y`: Größer als</span><span class="sxs-lookup"><span data-stu-id="0168d-158">`x > y`: Greater than</span></span>
    - <span data-ttu-id="0168d-159">`x <= y`: Kleiner oder gleich </span><span class="sxs-lookup"><span data-stu-id="0168d-159">`x <= y`: Less than or equal</span></span>
    - <span data-ttu-id="0168d-160">`x >= y`: Größer oder gleich</span><span class="sxs-lookup"><span data-stu-id="0168d-160">`x >= y`: Greater than or equal</span></span>
    - <span data-ttu-id="0168d-161">`x is T`: `true` zurückgeben, wenn `x` ein `T` ist, andernfalls `false`</span><span class="sxs-lookup"><span data-stu-id="0168d-161">`x is T`: Return `true` if `x` is a `T`, `false` otherwise</span></span>
    - <span data-ttu-id="0168d-162">`x as T`: `x` als `T` typisiert zurückgeben, oder `null`, wenn `x` kein `T` ist</span><span class="sxs-lookup"><span data-stu-id="0168d-162">`x as T`: Return `x` typed as `T`, or `null` if `x` is not a `T`</span></span>
* <span data-ttu-id="0168d-163">Gleichheit</span><span class="sxs-lookup"><span data-stu-id="0168d-163">Equality</span></span>
    - <span data-ttu-id="0168d-164">`x == y`: Gleich</span><span class="sxs-lookup"><span data-stu-id="0168d-164">`x == y`: Equal</span></span>
    - <span data-ttu-id="0168d-165">`x != y`: Ungleich</span><span class="sxs-lookup"><span data-stu-id="0168d-165">`x != y`: Not equal</span></span>
* <span data-ttu-id="0168d-166">Logisches AND</span><span class="sxs-lookup"><span data-stu-id="0168d-166">Logical AND</span></span>
    - <span data-ttu-id="0168d-167">`x & y`: Ganzzahliges bitweises AND, boolesches logisches AND</span><span class="sxs-lookup"><span data-stu-id="0168d-167">`x & y`: Integer bitwise AND, boolean logical AND</span></span>
* <span data-ttu-id="0168d-168">Logisches XOR</span><span class="sxs-lookup"><span data-stu-id="0168d-168">Logical XOR</span></span>
    - <span data-ttu-id="0168d-169">`x ^ y`: Ganzzahliges bitweises XOR, boolesches logisches XOR</span><span class="sxs-lookup"><span data-stu-id="0168d-169">`x ^ y`: Integer bitwise XOR, boolean logical XOR</span></span>
* <span data-ttu-id="0168d-170">Logisches OR</span><span class="sxs-lookup"><span data-stu-id="0168d-170">Logical OR</span></span>
    - <span data-ttu-id="0168d-171">`x | y`: Ganzzahliges bitweises OR, boolesches logisches OR</span><span class="sxs-lookup"><span data-stu-id="0168d-171">`x | y`: Integer bitwise OR, boolean logical OR</span></span>
* <span data-ttu-id="0168d-172">Bedingtes AND</span><span class="sxs-lookup"><span data-stu-id="0168d-172">Conditional AND</span></span>
    - <span data-ttu-id="0168d-173">`x && y`: Wertet `y` nur aus, wenn `x` nicht `false` ist</span><span class="sxs-lookup"><span data-stu-id="0168d-173">`x && y`: Evaluates `y` only if `x` is not `false`</span></span>
* <span data-ttu-id="0168d-174">Bedingtes OR</span><span class="sxs-lookup"><span data-stu-id="0168d-174">Conditional OR</span></span>
    - <span data-ttu-id="0168d-175">`x || y`: Wertet `y` nur aus, wenn `x` nicht `true` ist</span><span class="sxs-lookup"><span data-stu-id="0168d-175">`x || y`: Evaluates `y` only if `x` is not `true`</span></span>
* <span data-ttu-id="0168d-176">NULL-Sammeloperator</span><span class="sxs-lookup"><span data-stu-id="0168d-176">Null coalescing</span></span>
    - <span data-ttu-id="0168d-177">`x ?? y`: Wird zu `y` ausgewertet, wenn `x` NULL ist, andernfalls zu `x`</span><span class="sxs-lookup"><span data-stu-id="0168d-177">`x ?? y`: Evaluates to `y` if `x` is null, to `x` otherwise</span></span>
* <span data-ttu-id="0168d-178">Bedingt</span><span class="sxs-lookup"><span data-stu-id="0168d-178">Conditional</span></span>
    - <span data-ttu-id="0168d-179">`x ? y : z`: Wertet `y` aus, wenn `x` `true` ist, `z`, wenn `x` `false` ist</span><span class="sxs-lookup"><span data-stu-id="0168d-179">`x ? y : z`: Evaluates `y` if `x` is `true`, `z` if `x` is `false`</span></span>
* <span data-ttu-id="0168d-180">Zuweisung oder anonyme Funktion</span><span class="sxs-lookup"><span data-stu-id="0168d-180">Assignment or anonymous function</span></span>
    - <span data-ttu-id="0168d-181">`x = y`: Zuweisung</span><span class="sxs-lookup"><span data-stu-id="0168d-181">`x = y`: Assignment</span></span>
    - <span data-ttu-id="0168d-182">`x op= y`: Zusammengesetzte Zuweisung; unterstützte Operatoren sind</span><span class="sxs-lookup"><span data-stu-id="0168d-182">`x op= y`: Compound assignment; supported operators are</span></span>
        - <span data-ttu-id="0168d-183">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span><span class="sxs-lookup"><span data-stu-id="0168d-183">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span></span>
    - <span data-ttu-id="0168d-184">`(T x) => y`: Anonyme Funktion (Lambda-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="0168d-184">`(T x) => y`: Anonymous function (lambda expression)</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="0168d-185">[Zurück](types-and-variables.md)
> [Weiter](statements.md)</span><span class="sxs-lookup"><span data-stu-id="0168d-185">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>