---
title: ICorDebugMDA-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cea8f6827d3e361b3f6498e6612d8b11a2357285
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098656"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="77f23-102">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77f23-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="77f23-103">Stellt eine Nachricht des Assistenten für verwaltetes Debuggen (MDA) dar.</span><span class="sxs-lookup"><span data-stu-id="77f23-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="77f23-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="77f23-104">Methods</span></span>  
  
|<span data-ttu-id="77f23-105">Methode</span><span class="sxs-lookup"><span data-stu-id="77f23-105">Method</span></span>|<span data-ttu-id="77f23-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77f23-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="77f23-107">GetDescription-Methode</span><span class="sxs-lookup"><span data-stu-id="77f23-107">GetDescription Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|<span data-ttu-id="77f23-108">Ruft eine Zeichenfolge, die mit einer Beschreibung dieses MDA.</span><span class="sxs-lookup"><span data-stu-id="77f23-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="77f23-109">GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="77f23-109">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|<span data-ttu-id="77f23-110">Ruft die Flags, die mit diesem aktiven MDA ab.</span><span class="sxs-lookup"><span data-stu-id="77f23-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="77f23-111">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="77f23-111">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|<span data-ttu-id="77f23-112">Ruft eine Zeichenfolge, die mit dem Namen dieses MDA.</span><span class="sxs-lookup"><span data-stu-id="77f23-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="77f23-113">GetOSThreadId-Methode</span><span class="sxs-lookup"><span data-stu-id="77f23-113">GetOSThreadId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|<span data-ttu-id="77f23-114">Ruft ab, der Betriebssystem-Thread-ID auf dem dieser MDA ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="77f23-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="77f23-115">GetXML-Methode</span><span class="sxs-lookup"><span data-stu-id="77f23-115">GetXML Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|<span data-ttu-id="77f23-116">Ruft den vollständigen XML-Stream dieser MDA zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="77f23-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77f23-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="77f23-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77f23-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="77f23-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77f23-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="77f23-119">Requirements</span></span>  
 <span data-ttu-id="77f23-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77f23-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77f23-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77f23-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77f23-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77f23-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="77f23-123">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="77f23-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="77f23-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77f23-124">See also</span></span>

- [<span data-ttu-id="77f23-125">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="77f23-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="77f23-126">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="77f23-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
