---
title: IHostMemoryManager::ReleasedVirtualAddressSpace-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.ReleasedVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f337ece4e68c1685f7474df4b96074597e16271a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501414"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a>IHostMemoryManager::ReleasedVirtualAddressSpace-Methode
Benachrichtigt den Host, dass die common Language Runtime (CLR) über den angegebenen Speicher abgeschlossen ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `startAddress`  
 [in] Zeiger auf die Startadresse des Arbeitsspeichers, der freigegeben werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `ReleasedVirtualAddressSpace` -Methode ist eine Rückrufmethode und muss vom Writer der hostanwendung implementiert werden. Sie wird von der CLR aufgerufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
