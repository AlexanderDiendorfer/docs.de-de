---
title: IAssemblyName::GetName-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe0b465d0e15fadde48c2278aa367632bda3f9ef
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473825"
---
# <a name="iassemblynamegetname-method"></a>IAssemblyName::GetName-Methode
Ruft ab, die einfache nicht verschlüsselte Name der Assembly verwiesen wird, von diesem [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `lpcwBuffer`  
 [in, out] Die Größe des `pwzName` in Breitzeichen, einschließlich des null-Terminator-Zeichens.  
  
 `pwzName`  
 [out] Ein Puffer, der den Namen der Assembly, auf die verwiesen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IAssemblyName-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
