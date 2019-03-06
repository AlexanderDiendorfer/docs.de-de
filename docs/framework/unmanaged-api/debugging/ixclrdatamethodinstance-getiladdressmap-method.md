---
title: IXCLRDataMethodInstance::GetILAddressMap-Methode
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance::GetILAddressMap Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method
helpviewer.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5e6fde6e4e5bf006da00b62b035cee112efae1d7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373490"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a>IXCLRDataMethodInstance::GetILAddressMap-Methode

Ruft den IL-Code mit Adressinformationen für die Zuordnung ab.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

### <a name="parameters"></a>Parameter

`mapLen`\
[in] Die Länge des Arrays bereitgestellten Zuordnungen.

`mapNeeded`\
[out] Die Anzahl der Map-Einträge, die die Methode muss.

`maps`\
[Out, size_is(mapLen)] Das Array zum Speichern der Map-Einträge.

## <a name="remarks"></a>Hinweise

Die angegebene Methode ist Teil der `IXCLRDataMethodInstance` Schnittstelle, und mit dem 14. Steckplatz der virtuellen Methodentabelle entspricht.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Keine  
**Bibliothek:** Keine  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [IXCLRDataMethodInstance-Schnittstelle](ixclrdatamethodinstance-interface.md)
