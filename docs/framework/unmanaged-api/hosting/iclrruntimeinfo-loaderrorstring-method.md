---
title: ICLRRuntimeInfo::LoadErrorString-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a565c19285b00c807ef6fbfc018a40467139638e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466348"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="050e2-102">ICLRRuntimeInfo::LoadErrorString-Methode</span><span class="sxs-lookup"><span data-stu-id="050e2-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="050e2-103">Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.</span><span class="sxs-lookup"><span data-stu-id="050e2-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="050e2-104">Diese Methode ersetzt die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="050e2-104">This method supersedes the following functions:</span></span>  
  
-   [<span data-ttu-id="050e2-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="050e2-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
-   [<span data-ttu-id="050e2-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="050e2-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="050e2-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="050e2-107">Syntax</span></span>  
  
```  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="050e2-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="050e2-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="050e2-109">[in] Das HRESULT, um zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="050e2-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="050e2-110">[out] Die Meldungszeichenfolge, die dem angegebenen HRESULT zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="050e2-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="050e2-111">[in, out] Die Größe des `pwzbuffer` um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="050e2-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="050e2-112">Wenn `pwzbuffer` null ist, `pcchBuffer` bietet die geforderte Größe des `pwzbuffer` um die Vorabbelegung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="050e2-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="050e2-113">[in] Der Kulturbezeichner.</span><span class="sxs-lookup"><span data-stu-id="050e2-113">[in] The culture identifier.</span></span> <span data-ttu-id="050e2-114">Um die Standardkultur verwenden zu können, müssen Sie-1 angeben.</span><span class="sxs-lookup"><span data-stu-id="050e2-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="050e2-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="050e2-115">Return Value</span></span>  
 <span data-ttu-id="050e2-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="050e2-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="050e2-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="050e2-117">HRESULT</span></span>|<span data-ttu-id="050e2-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="050e2-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="050e2-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="050e2-119">S_OK</span></span>|<span data-ttu-id="050e2-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="050e2-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="050e2-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="050e2-121">E_POINTER</span></span>|<span data-ttu-id="050e2-122">`pcchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="050e2-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="050e2-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="050e2-123">E_INVALIDARG</span></span>|<span data-ttu-id="050e2-124">`pwzBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="050e2-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="050e2-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="050e2-125">Requirements</span></span>  
 <span data-ttu-id="050e2-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="050e2-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="050e2-127">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="050e2-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="050e2-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="050e2-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="050e2-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="050e2-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="050e2-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="050e2-130">See also</span></span>
- [<span data-ttu-id="050e2-131">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="050e2-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="050e2-132">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="050e2-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="050e2-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="050e2-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
