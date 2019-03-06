---
title: INotifyConnection2::UnregisterNotifySource-Methode
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8b7125ad38bcec773fa2afa8eca09c1d56d90591
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475770"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a>INotifyConnection2::UnregisterNotifySource-Methode
Entfernt eine angegebene Benachrichtigung-Quellobjekt aus der Verbindung an.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `in_pNotifySource`  
 [in] Benachrichtigungsobjekt, das nicht aufgehoben werden.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>Siehe auch
- [INotifyConnection2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [INotifySource2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [INotifySink2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [RegisterNotifySource-Methode](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
