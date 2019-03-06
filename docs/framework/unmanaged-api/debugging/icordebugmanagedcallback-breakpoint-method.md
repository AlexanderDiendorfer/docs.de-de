---
title: ICorDebugManagedCallback::Breakpoint-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Breakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Breakpoint
helpviewer_keywords:
- ICorDebugManagedCallback::Breakpoint method [.NET Framework debugging]
- Breakpoint method [.NET Framework debugging]
ms.assetid: 60b279b0-a726-46d2-8c53-76986a007ebb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c13898443f27d7275a58823c8a94ec5657748f28
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477100"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="cdbc3-102">ICorDebugManagedCallback::Breakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="cdbc3-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="cdbc3-103">Benachrichtigt den Debugger an, wenn ein Breakpoint erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="cdbc3-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdbc3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cdbc3-104">Syntax</span></span>  
  
```  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdbc3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cdbc3-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="cdbc3-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die den Haltepunkt enthält.</span><span class="sxs-lookup"><span data-stu-id="cdbc3-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="cdbc3-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, der den Haltepunkt enthält.</span><span class="sxs-lookup"><span data-stu-id="cdbc3-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="cdbc3-108">[in] Ein Zeiger auf ein ICorDebugBreakpoint-Objekt, das den Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="cdbc3-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdbc3-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cdbc3-109">Requirements</span></span>  
 <span data-ttu-id="cdbc3-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdbc3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdbc3-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cdbc3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cdbc3-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdbc3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdbc3-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdbc3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdbc3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cdbc3-114">See also</span></span>
- [<span data-ttu-id="cdbc3-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cdbc3-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
