---
title: ISymUnmanagedConstant::GetName-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e57ab385ce4d393b29ff5af867bf7a019bf2b824
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478933"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="6643f-102">ISymUnmanagedConstant::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="6643f-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="6643f-103">Ruft den Namen der Konstanten.</span><span class="sxs-lookup"><span data-stu-id="6643f-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6643f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6643f-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6643f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6643f-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="6643f-106">[in] Die Länge des Puffers, der die `szName` -Parameter zeigt.</span><span class="sxs-lookup"><span data-stu-id="6643f-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="6643f-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe in Zeichen des Puffers erforderlich, um den Namen und die null-Terminierung enthalten.</span><span class="sxs-lookup"><span data-stu-id="6643f-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="6643f-108">[out] Der Puffer, der Namen speichert.</span><span class="sxs-lookup"><span data-stu-id="6643f-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6643f-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6643f-109">Return Value</span></span>  
 <span data-ttu-id="6643f-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="6643f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6643f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6643f-111">Requirements</span></span>  
 <span data-ttu-id="6643f-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6643f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6643f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6643f-113">See also</span></span>
- [<span data-ttu-id="6643f-114">ISymUnmanagedConstant-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6643f-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="6643f-115">GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="6643f-115">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="6643f-116">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="6643f-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
