---
title: ICLRDataTarget::SetTLSValue-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 421fb371094c21948486e56d0881163e7a6961a0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465282"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="7b5dc-102">ICLRDataTarget::SetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="7b5dc-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="7b5dc-103">Legt einen Wert in den lokalen Threadspeicher (TLS) des angegebenen Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="7b5dc-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="7b5dc-104">Diese Methode wird von den Datenzugriffsdiensten der common Language Runtime (CLR) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="7b5dc-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b5dc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b5dc-105">Syntax</span></span>  
  
```  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b5dc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7b5dc-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="7b5dc-107">[in] Der Betriebssystem-Bezeichner eines Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="7b5dc-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="7b5dc-108">[in] Der Index der Position.</span><span class="sxs-lookup"><span data-stu-id="7b5dc-108">[in] The index of the location.</span></span> <span data-ttu-id="7b5dc-109">Dieser Wert muss ein gültiger Index im lokalen Speicher des angegebenen Threads sein.</span><span class="sxs-lookup"><span data-stu-id="7b5dc-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="7b5dc-110">[in] Ein `CLRDATA_ADDRESS` Wert, der angibt, den Wert, der in den angegebenen TLS-Speicherort zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="7b5dc-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b5dc-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b5dc-111">Remarks</span></span>  
 <span data-ttu-id="7b5dc-112">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="7b5dc-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b5dc-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b5dc-113">Requirements</span></span>  
 <span data-ttu-id="7b5dc-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b5dc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b5dc-115">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="7b5dc-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7b5dc-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b5dc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b5dc-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b5dc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b5dc-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b5dc-118">See also</span></span>
- [<span data-ttu-id="7b5dc-119">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b5dc-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
