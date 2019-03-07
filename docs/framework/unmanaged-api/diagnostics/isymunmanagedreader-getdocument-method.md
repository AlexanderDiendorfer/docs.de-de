---
title: ISymUnmanagedReader::GetDocument-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f20f7aabc05bb9e15b040d968c08d10444efd8fc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485809"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="9d722-102">ISymUnmanagedReader::GetDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="9d722-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="9d722-103">Sucht ein Dokument an.</span><span class="sxs-lookup"><span data-stu-id="9d722-103">Finds a document.</span></span> <span data-ttu-id="9d722-104">Die Sprache des Dokuments, Hersteller und Typ sind optional.</span><span class="sxs-lookup"><span data-stu-id="9d722-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d722-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d722-105">Syntax</span></span>  
  
```  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d722-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9d722-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="9d722-107">[in] Die URL, die das Dokument kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="9d722-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="9d722-108">[in] Die Sprache des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="9d722-108">[in] The document language.</span></span> <span data-ttu-id="9d722-109">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="9d722-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="9d722-110">[in] Die Identität des Herstellers für die Sprache des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="9d722-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="9d722-111">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="9d722-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="9d722-112">[in] Der Typ des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="9d722-112">[in] The type of the document.</span></span> <span data-ttu-id="9d722-113">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="9d722-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="9d722-114">[out] Ein Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9d722-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d722-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9d722-115">Return Value</span></span>  
 <span data-ttu-id="9d722-116">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="9d722-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d722-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9d722-117">Requirements</span></span>  
 <span data-ttu-id="9d722-118">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9d722-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d722-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d722-119">See also</span></span>
- [<span data-ttu-id="9d722-120">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9d722-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
