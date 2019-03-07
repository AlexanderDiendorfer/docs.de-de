---
title: ISymUnmanagedWriter2::DefineLocalVariable2-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d336b35e91abd1b7180c2b918edeba2e1eccdbde
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499588"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="6d4d5-102">ISymUnmanagedWriter2::DefineLocalVariable2-Methode</span><span class="sxs-lookup"><span data-stu-id="6d4d5-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="6d4d5-103">Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="6d4d5-104">Diese Methode kann mehrmals für eine Variable mit dem gleichen Namen aufgerufen werden, die mehrfach in einem Bereich verfügt.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="6d4d5-105">In diesem Fall jedoch die Werte der `startOffset` und `endOffset` Parameter dürfen sich nicht überschneiden.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d4d5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d4d5-106">Syntax</span></span>  
  
```  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d4d5-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="6d4d5-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="6d4d5-108">[in] Der Name der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="6d4d5-109">[in] Die Attribute der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="6d4d5-110">[in] Das Metadatentoken der Signatur.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="6d4d5-111">[in] Der Adresstyp.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="6d4d5-112">[in] Die erste Adresse für die Parameterangabe.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="6d4d5-113">[in] Die zweite Adresse für die Parameterangabe.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="6d4d5-114">[in] Die dritte Adresse für die Parameterangabe.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="6d4d5-115">[in] Der Anfangsoffset der Variablen.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="6d4d5-116">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-116">This parameter is optional.</span></span> <span data-ttu-id="6d4d5-117">Wenn dies 0 ist, wird dieser Parameter wird ignoriert, und die Variable ist im gesamten Gültigkeitsbereich definiert.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="6d4d5-118">Wenn es sich um einen Wert ungleich NULL ist, fällt die Variable, in die Offsets des aktuellen Gültigkeitsbereichs.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="6d4d5-119">[in] Der Endoffset der Variablen.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="6d4d5-120">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-120">This parameter is optional.</span></span> <span data-ttu-id="6d4d5-121">Wenn dies 0 ist, wird dieser Parameter wird ignoriert, und die Variable ist im gesamten Gültigkeitsbereich definiert.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="6d4d5-122">Wenn es sich um einen Wert ungleich NULL ist, fällt die Variable, in die Offsets des aktuellen Gültigkeitsbereichs.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d4d5-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6d4d5-123">Return Value</span></span>  
 <span data-ttu-id="6d4d5-124">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="6d4d5-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d4d5-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d4d5-125">Requirements</span></span>  
 <span data-ttu-id="6d4d5-126">**Header:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="6d4d5-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d4d5-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d4d5-127">See also</span></span>
- [<span data-ttu-id="6d4d5-128">ISymUnmanagedWriter2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6d4d5-128">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="6d4d5-129">DefineLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="6d4d5-129">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
