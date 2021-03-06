---
title: IHostAssemblyStore::ProvideModule-Methode
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e07e2c3f2c6000f5a081b13316c269f322b1ef8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078337"
---
# <a name="ihostassemblystoreprovidemodule-method"></a>IHostAssemblyStore::ProvideModule-Methode
Löst eine Modul innerhalb einer Assembly oder ein verknüpftes (aber nicht auf ein eingebettetes) Ressourcendatei an.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pBindInfo`  
 [in] Ein Zeiger auf eine [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) Instanz, die des angeforderten Moduls beschreibt <xref:System.AppDomain>, Assembly und Modul mit Name.  
  
 `pdwModuleId`  
 [out] Ein Zeiger auf einen eindeutigen Bezeichner für die `IStream` , die das geladene Modul.  
  
 `ppStmModuleImage`  
 [out] Ein Zeiger auf die Adresse einer `IStream` Objekts, das enthält die Datei (portable Executable)-Image geladen werden, oder null, wenn das Modul nicht gefunden werden konnte.  
  
 `ppStmPDB`  
 [out] Ein Zeiger auf die Adresse einer `IStream` Objekts, das Programm (PDB) Debuginformationen für das angeforderte Modul enthält, oder null, wenn die PDB-Datei nicht gefunden werden konnte.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`ProvideModule` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|COR_E_FILENOTFOUND (0x80070002)|Die angeforderte Assembly oder eine verknüpfte Ressource konnte nicht gefunden werden.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId` ist nicht groß genug ist, den Bezeichner enthält, den der Host zurückgeben möchte.|  
  
## <a name="remarks"></a>Hinweise  
 Der Identitätswert zurückgegeben wird, für die `pdwModuleId` vom Host angegeben ist. Bezeichner müssen innerhalb der Lebensdauer eines Prozesses eindeutig sein. Die CLR verwendet diesen Wert als eindeutiger Bezeichner für den zugeordneten Stream. Er überprüft jeden Wert mit den Werten für `pAssemblyId` zurückgegeben, die durch Aufrufe von [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) und mit den Werten für `pdwModuleId` zurückgegeben, die von anderen Aufrufen von `ProvideModule`. Wenn der Host den gleichen Bezeichnerwert für eine andere zurückgibt `IStream`, die CLR wird überprüft, ob der Inhalt des Streams bereits zugeordnet wurde. Wenn dies der Fall ist, lädt die CLR die vorhandene Kopie des Bildes statt ein neues zuzuordnen. Aus diesem Grund der Bezeichner muss auch nicht überschneiden sich mit den Assemblybezeichnern, die von zurückgegeben `ProvideAssembly`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
