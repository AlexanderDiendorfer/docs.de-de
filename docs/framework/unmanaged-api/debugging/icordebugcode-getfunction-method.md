---
title: ICorDebugCode::GetFunction-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5d8168649f6a0c75844da0ee68bf3782efc9024
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57483861"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="27d7c-102">ICorDebugCode::GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="27d7c-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="27d7c-103">Ruft ab, der "ICorDebugFunction" diesem "ICorDebugCode" zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="27d7c-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27d7c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27d7c-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27d7c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="27d7c-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="27d7c-106">[out] Ein Zeiger auf die Adresse der Funktion.</span><span class="sxs-lookup"><span data-stu-id="27d7c-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27d7c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="27d7c-107">Remarks</span></span>  
 <span data-ttu-id="27d7c-108">`ICorDebugCode` und `ICorDebugFunction` eine direkte Beziehung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="27d7c-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27d7c-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="27d7c-109">Requirements</span></span>  
 <span data-ttu-id="27d7c-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27d7c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27d7c-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27d7c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27d7c-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27d7c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27d7c-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27d7c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d7c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27d7c-114">See also</span></span>

