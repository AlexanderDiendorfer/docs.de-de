---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: d8efd2359ecb65bec1b427d8b1dca4b0c88a1152
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469026"
---
# <a name="c-visual-basic"></a><span data-ttu-id="c8490-102">\<c> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8490-102">\<c> (Visual Basic)</span></span>
<span data-ttu-id="c8490-103">Gibt an, dass Text in einer Beschreibung Code ist.</span><span class="sxs-lookup"><span data-stu-id="c8490-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8490-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8490-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8490-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c8490-105">Parameters</span></span>  
  
|<span data-ttu-id="c8490-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c8490-106">Parameter</span></span>|<span data-ttu-id="c8490-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8490-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="c8490-108">Der Text, der als Code angegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8490-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8490-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8490-109">Remarks</span></span>  
 <span data-ttu-id="c8490-110">Die `<c>` -Tag ermöglicht es eine Möglichkeit, um anzugeben, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8490-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="c8490-111">Zum Angeben mehrerer Zeilen als Code wird [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="c8490-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="c8490-112">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="c8490-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8490-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c8490-113">Example</span></span>  
 <span data-ttu-id="c8490-114">Dieses Beispiel verwendet die `<c>` -Tag im Abschnitt "Zusammenfassung" gibt an, dass `Counter` Code.</span><span class="sxs-lookup"><span data-stu-id="c8490-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c8490-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8490-115">See also</span></span>
- [<span data-ttu-id="c8490-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="c8490-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
