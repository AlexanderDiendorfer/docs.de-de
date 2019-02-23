---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: f88a0001bb2ba55c0a3eac3ed208f14292d86734
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745663"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="2b24f-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="2b24f-102">-moduleassemblyname</span></span>
<span data-ttu-id="2b24f-103">Gibt den Namen der Assembly an, zu der dieses Modul gehört.</span><span class="sxs-lookup"><span data-stu-id="2b24f-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b24f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b24f-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="2b24f-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="2b24f-105">Arguments</span></span>  
  
|<span data-ttu-id="2b24f-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="2b24f-106">Term</span></span>|<span data-ttu-id="2b24f-107">Definition</span><span class="sxs-lookup"><span data-stu-id="2b24f-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="2b24f-108">Der Name der Assembly, der dieses Modul eine angehören soll.</span><span class="sxs-lookup"><span data-stu-id="2b24f-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b24f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b24f-109">Remarks</span></span>  
 <span data-ttu-id="2b24f-110">Der Compiler verarbeitet die `-moduleassemblyname` Option nur, wenn die `-target:module` -Option wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="2b24f-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="2b24f-111">Dies bewirkt, dass den Compiler ein Modul zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2b24f-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="2b24f-112">Das Modul, das vom Compiler erstellten gilt nur für die Assembly mit angegebenen die `-moduleassemblyname` Option.</span><span class="sxs-lookup"><span data-stu-id="2b24f-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="2b24f-113">Wenn Sie das Modul in einer anderen Assembly platzieren, werden Laufzeitfehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="2b24f-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="2b24f-114">Die `-moduleassemblyname` Option ist nur erforderlich, wenn Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2b24f-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
-   <span data-ttu-id="2b24f-115">Ein Datentyp in das Modul benötigt Zugriff auf eine `Friend` Typ in einer referenzierten Assembly.</span><span class="sxs-lookup"><span data-stu-id="2b24f-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
-   <span data-ttu-id="2b24f-116">Die referenzierte Assembly wurde Friend-Assembly-Zugriff auf die Assembly gewährt werden, in dem das Modul erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2b24f-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="2b24f-117">Weitere Informationen zum Erstellen eines Moduls finden Sie unter [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="2b24f-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="2b24f-118">Weitere Informationen zu Friend-Assemblys, finden Sie unter [Friend-Assemblys](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="2b24f-118">For more information about friend assemblies, see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b24f-119">Die `-moduleassemblyname` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie an einer Eingabeaufforderung kompilieren.</span><span class="sxs-lookup"><span data-stu-id="2b24f-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b24f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b24f-120">See also</span></span>
- [<span data-ttu-id="2b24f-121">Vorgehensweise: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="2b24f-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="2b24f-122">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="2b24f-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2b24f-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b24f-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="2b24f-124">-main</span><span class="sxs-lookup"><span data-stu-id="2b24f-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="2b24f-125">-Referenz (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b24f-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="2b24f-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="2b24f-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="2b24f-127">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="2b24f-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="2b24f-128">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="2b24f-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="2b24f-129">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="2b24f-129">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)
