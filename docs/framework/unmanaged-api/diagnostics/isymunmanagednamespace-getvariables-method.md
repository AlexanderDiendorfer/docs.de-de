---
title: ISymUnmanagedNamespace::GetVariables-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 02fd9fd3a580946cda09f0c129f02cd1218a0c9a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471432"
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="88583-102">ISymUnmanagedNamespace::GetVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="88583-102">ISymUnmanagedNamespace::GetVariables Method</span></span>
<span data-ttu-id="88583-103">Gibt alle Variablen, die im globalen Gültigkeitsbereich innerhalb dieses Namespace definiert.</span><span class="sxs-lookup"><span data-stu-id="88583-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88583-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="88583-104">Syntax</span></span>  
  
```  
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88583-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="88583-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="88583-106">[in] Ein `ULONG32` , der angibt, dass der Größe des der `pVars` Array.</span><span class="sxs-lookup"><span data-stu-id="88583-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="88583-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die Namespaces enthalten.</span><span class="sxs-lookup"><span data-stu-id="88583-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="88583-108">[out] Ein Zeiger auf einen Puffer, der die Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="88583-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88583-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="88583-109">Return Value</span></span>  
 <span data-ttu-id="88583-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="88583-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88583-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="88583-111">Requirements</span></span>  
 <span data-ttu-id="88583-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="88583-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88583-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88583-113">See also</span></span>
- [<span data-ttu-id="88583-114">ISymUnmanagedNamespace-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="88583-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
