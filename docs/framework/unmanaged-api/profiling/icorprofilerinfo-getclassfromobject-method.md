---
title: ICorProfilerInfo::GetClassFromObject-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d48006011ae50f1157d357a909eb6c93b25baf7e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496052"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="c04d6-102">ICorProfilerInfo::GetClassFromObject-Methode</span><span class="sxs-lookup"><span data-stu-id="c04d6-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="c04d6-103">Ruft die `ClassID` eines angegebenen Objekts an, dessen `ObjectID`.</span><span class="sxs-lookup"><span data-stu-id="c04d6-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c04d6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c04d6-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c04d6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c04d6-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="c04d6-106">[in] Die ID des Objekts, für das Abrufen der `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="c04d6-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="c04d6-107">[out] Ein Zeiger auf das zurückgegebene `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="c04d6-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c04d6-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c04d6-108">Remarks</span></span>  
 <span data-ttu-id="c04d6-109">Ein NULL-Wert `pClassId` gibt an, dass `objectId` verfügt über einen Typ, der entladen wird.</span><span class="sxs-lookup"><span data-stu-id="c04d6-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c04d6-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c04d6-110">Requirements</span></span>  
 <span data-ttu-id="c04d6-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c04d6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c04d6-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c04d6-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c04d6-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c04d6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c04d6-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c04d6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c04d6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c04d6-115">See also</span></span>
- [<span data-ttu-id="c04d6-116">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c04d6-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
