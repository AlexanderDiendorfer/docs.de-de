---
title: ICorPublishProcess::IsManaged-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 404403576b7fd32362a690d470a5ea4b48489d26
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484796"
---
# <a name="icorpublishprocessismanaged-method"></a>ICorPublishProcess::IsManaged-Methode
Ruft einen Wert, der angibt, ob von dieser vom Prozess verwiesen [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) ist bekannt, dass verwalteter Code haben.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pbManaged`  
 [out] Ein Zeiger auf einen booleschen Wert, der angibt, ob der Prozess über verwalteten Code hat. Der Wert ist `true` Wenn der Prozess über verwalteten Code; aufweist, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Da die aktuelle Version der `ICorPublishProcess` ermöglicht den Zugriff nur für Prozesse, die von Code verwaltetem, `IsManaged` gibt immer `true`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorPub.idl, CorPub.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorPublishProcess-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
