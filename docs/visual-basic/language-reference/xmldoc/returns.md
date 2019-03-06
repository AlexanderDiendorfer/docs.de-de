---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 670064084d3297a54b2860da3fe3acab00fa3ed8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469182"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="72f40-102">\<returns> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72f40-102">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="72f40-103">Gibt den Rückgabewert der Eigenschaft oder der Funktion an.</span><span class="sxs-lookup"><span data-stu-id="72f40-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72f40-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72f40-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="72f40-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="72f40-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="72f40-106">Eine Beschreibung des Rückgabewerts.</span><span class="sxs-lookup"><span data-stu-id="72f40-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72f40-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="72f40-107">Remarks</span></span>  
 <span data-ttu-id="72f40-108">Verwenden der `<returns>` Tag im Kommentar für eine Methodendeklaration, um den Rückgabewert beschreiben.</span><span class="sxs-lookup"><span data-stu-id="72f40-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="72f40-109">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="72f40-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72f40-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="72f40-110">Example</span></span>  
 <span data-ttu-id="72f40-111">Dieses Beispiel verwendet die `<returns>` -Tag erläutert, was die `DoesRecordExist` -Funktion zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="72f40-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="72f40-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72f40-112">See also</span></span>
- [<span data-ttu-id="72f40-113">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="72f40-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
