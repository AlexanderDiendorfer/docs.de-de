---
title: Das Argument „Zzr“ muss größer als 0 (null) sein.
ms.date: 07/20/2015
f1_keywords:
- vbrRate_NPerMustBeGTZero
ms.assetid: d49242df-dbd1-4b26-bd8c-ed56d24fdfcd
ms.openlocfilehash: 6f54a2da0eb0c1cc31a4aa536fdcb59026240a25
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "58023933"
---
# <a name="argument-nper-must-be-greater-than-zero"></a><span data-ttu-id="01545-102">Das Argument „Zzr“ muss größer als 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="01545-102">Argument 'NPer' must be greater than zero</span></span>
<span data-ttu-id="01545-103">Die `NPer` -Funktion, die als Anzahl der Zeiträume für eine Annuität basierend auf regelmäßigen, festen Zahlungen und einem festen Zinssatz `Double` zurückgibt, erfordert ein Argument, das größer als 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="01545-103">The `NPer` function, which returns a `Double` specifying the number of periods for an annuity based on periodic fixed payments and a fixed interest rate, requires an argument greater than zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="01545-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="01545-104">To correct this error</span></span>  
  
-   <span data-ttu-id="01545-105">Überprüfen Sie die Schreibweise der Argumente im Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="01545-105">Check the spelling of arguments in the expression.</span></span> <span data-ttu-id="01545-106">Ein falsch geschriebener Variablenname kann implizit eine numerische Variable erstellen, die mit Null initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="01545-106">A misspelled variable name can implicitly create a numeric variable that is initialized to zero.</span></span>  
  
-   <span data-ttu-id="01545-107">Überprüfen Sie vorherige Vorgänge für Variablen im Ausdruck, insbesondere solche, die als Argumente aus anderen Prozeduren an die Prozedur übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="01545-107">Check previous operations on variables in the expression, especially those passed into the procedure as arguments from other procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01545-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01545-108">See also</span></span>

- [<span data-ttu-id="01545-109">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="01545-109">Passing Arguments by Value and by Reference</span></span>](../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
