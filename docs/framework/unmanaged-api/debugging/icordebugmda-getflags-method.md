---
title: ICorDebugMDA::GetFlags-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetFlags
helpviewer_keywords:
- ICorDebugMDA::GetFlags method [.NET Framework debugging]
- GetFlags method [.NET Framework debugging]
ms.assetid: 87ce7c5b-fd82-453e-bf55-c8a32150b183
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a35e9f7cf43105db05408f285cd89dbd839a4cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093487"
---
# <a name="icordebugmdagetflags-method"></a>ICorDebugMDA::GetFlags-Methode
Ruft die Flags, die mit managed debugging Assistant (MDA) durch dargestellt [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pFlags`  
 [in] Eine bitweise Kombination der [CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md) Enumerationswerte, der die Einstellungen der Flags, die für diesen MDA angeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugMDA-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
