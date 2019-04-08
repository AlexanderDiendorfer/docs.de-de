---
title: ICLRTaskManager::GetCurrentTaskType-Methode
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2963e2a31fd62470e3ed6933edb38119d286071b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59071973"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="6818a-102">ICLRTaskManager::GetCurrentTaskType-Methode</span><span class="sxs-lookup"><span data-stu-id="6818a-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="6818a-103">Ruft den Typ der Aufgabe, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6818a-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6818a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6818a-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6818a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6818a-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="6818a-106">[out] Ein Zeiger auf den Wert der [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) -Enumeration, der den Typ der Aufgabe gibt an, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6818a-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6818a-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6818a-107">Requirements</span></span>  
 <span data-ttu-id="6818a-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6818a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6818a-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6818a-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6818a-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6818a-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6818a-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="6818a-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6818a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6818a-112">See also</span></span>

- [<span data-ttu-id="6818a-113">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6818a-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
