---
title: CertFreeAuthenticodeTimestamperInfo-Funktion
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 082ed24eb65de12f337ab4a379b088da0f6eea5a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497378"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a>CertFreeAuthenticodeTimestamperInfo-Funktion
Gibt zugeordnete Ressourcen frei, die [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pTimestamperInfo`  
 [in, out] Informationen über den Ersteller des Zeitstempels, die veröffentlicht werden sollen. Finden Sie unter den [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn die Funktion erfolgreich ausgeführt wird. Andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch
- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
