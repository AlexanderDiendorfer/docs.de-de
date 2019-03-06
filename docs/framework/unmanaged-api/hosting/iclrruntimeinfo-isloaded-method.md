---
title: ICLRRuntimeInfo::IsLoaded-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd1d97d9f3a44e2237cfc7a9e054a5ecfa2ebb01
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470756"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="47038-102">ICLRRuntimeInfo::IsLoaded-Methode</span><span class="sxs-lookup"><span data-stu-id="47038-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="47038-103">Gibt an, ob die common Language Runtime (CLR) zugeordnet. die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle in einem Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="47038-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="47038-104">Eine Laufzeit kann geladen werden, auch ohne gestartet zu werden.</span><span class="sxs-lookup"><span data-stu-id="47038-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47038-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="47038-105">Syntax</span></span>  
  
```  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47038-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="47038-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="47038-107">[in] Ein Handle für den Prozess.</span><span class="sxs-lookup"><span data-stu-id="47038-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="47038-108">[out] `true` ist die CLR in den Prozess geladen ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="47038-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47038-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="47038-109">Return Value</span></span>  
 <span data-ttu-id="47038-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="47038-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="47038-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="47038-111">HRESULT</span></span>|<span data-ttu-id="47038-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47038-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="47038-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="47038-113">S_OK</span></span>|<span data-ttu-id="47038-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="47038-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="47038-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="47038-115">E_POINTER</span></span>|<span data-ttu-id="47038-116">`pbLoaded` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="47038-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47038-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="47038-117">Remarks</span></span>  
 <span data-ttu-id="47038-118">Diese Methode ist abwärtskompatibel mit den folgenden Funktionen und Schnittstellen:</span><span class="sxs-lookup"><span data-stu-id="47038-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
-   <span data-ttu-id="47038-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) -Schnittstelle (in der .NET Framework Version 1 hosting-API).</span><span class="sxs-lookup"><span data-stu-id="47038-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
-   <span data-ttu-id="47038-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) -Schnittstelle (in der .NET Framework 2.0-hosting-API).</span><span class="sxs-lookup"><span data-stu-id="47038-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
-   <span data-ttu-id="47038-121">Veraltete `CorBindTo*` Funktionen (finden Sie unter [Hosten von CLR-Funktionen als veraltet markiert](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in .NET Framework 2.0 hosting-API).</span><span class="sxs-lookup"><span data-stu-id="47038-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="47038-122">Ein Host ruft einer der veralteten `CorBindTo*` Funktionen wie die [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) -Funktion verwendet, um eine bestimmte Version der CLR zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="47038-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="47038-123">Der Host kann dann aufrufen, die [ICLRMetaHost:: GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) Methode, und geben Sie die gleiche Versionsnummer zum Abrufen einer [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="47038-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="47038-124">Wenn der Host dann Ruft die `IsLoaded` Methode für das zurückgegebene [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle, `pbLoaded` gibt `true`ist, andernfalls gibt `false`.</span><span class="sxs-lookup"><span data-stu-id="47038-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47038-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47038-125">Requirements</span></span>  
 <span data-ttu-id="47038-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47038-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47038-127">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="47038-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="47038-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="47038-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47038-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47038-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47038-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47038-130">See also</span></span>
- [<span data-ttu-id="47038-131">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47038-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="47038-132">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="47038-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="47038-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="47038-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
