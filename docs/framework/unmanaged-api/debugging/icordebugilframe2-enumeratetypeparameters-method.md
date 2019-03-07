---
title: ICorDebugILFrame2::EnumerateTypeParameters-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7454b551edc546fecbd9d091f7c821e0a07b16df
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497820"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="1d63c-102">ICorDebugILFrame2::EnumerateTypeParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="1d63c-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="1d63c-103">Ruft ein ICorDebugTypeEnum-Objekt, enthält die <xref:System.Type> Parameter in diesem Frame.</span><span class="sxs-lookup"><span data-stu-id="1d63c-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d63c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d63c-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d63c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1d63c-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="1d63c-106">Ein Zeiger auf die Adresse des ICorDebugTypeEnum-Schnittstellenobjekts, die Enumeration von Typparametern ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="1d63c-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="1d63c-107">Die Liste der Parameter vom Typ enthalten die Klassentypparameter (sofern vorhanden) gefolgt von den Methodentypparametern (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="1d63c-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d63c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1d63c-108">Remarks</span></span>  
 <span data-ttu-id="1d63c-109">Verwenden der [IMetaDataImport2:: EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) Methode, um zu bestimmen, wie viele Parameter vom Typ Klasse und Methode Parameter geben Sie diese Liste enthält.</span><span class="sxs-lookup"><span data-stu-id="1d63c-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="1d63c-110">Die Typparameter sind nicht immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1d63c-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d63c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1d63c-111">Requirements</span></span>  
 <span data-ttu-id="1d63c-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d63c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d63c-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d63c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d63c-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d63c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d63c-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d63c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
