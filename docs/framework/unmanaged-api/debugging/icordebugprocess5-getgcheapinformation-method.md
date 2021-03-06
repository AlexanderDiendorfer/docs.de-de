---
title: ICorDebugProcess5::GetGCHeapInformation-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81c590dd1f3f6682179645fb384cdd82d1d7ed96
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503254"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a>ICorDebugProcess5::GetGCHeapInformation-Methode
Enthält allgemeine Informationen zur Garbage Collection-Heap, z. B., ob sie derzeit aufzählbar ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pHeapInfo`  
 [out] Ein Zeiger auf eine [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Wert, der allgemeine Informationen zur Garbage Collection-Heap bereitstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugProcess5::GetGCHeapInformation` -Methode muss aufgerufen werden, vor der Enumeration des Heaps oder einzelne Heap-Regionen, um sicherzustellen, dass die Garbagecollection im Prozess Strukturen sind gültig. Garbage Collection-Heap kann nicht durchlaufen werden soll, während eine Sammlung ausgeführt wird. Andernfalls kann die Enumeration Garbage Collection-Strukturen erfassen, die ungültig sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebugProcess5-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
