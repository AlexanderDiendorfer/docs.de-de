---
title: IMetaDataAssemblyEmit::SetAssemblyProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 738789ee6b21b190302d5e5a204538bd14851b24
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484666"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a>IMetaDataAssemblyEmit::SetAssemblyProps-Methode
Ändert die angegebene `Assembly`-Metadatenstruktur.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pma`  
 [in] Das Metadatentoken, der angibt, die `Assembly` Metadatenstruktur geändert werden.  
  
 `pbPublicKey`  
 [in] Ein Zeiger auf den öffentlichen Schlüssel des Herausgebers der Assembly.  
  
 `cbPublicKey`  
 [in] Die Größe in Bytes der `pbPublicKey`.  
  
 `ulHashAlgId`  
 [in] Der Bezeichner für die Hash-Algorithmus verwendet, um die Assemblydateien hash.  
  
 `szName`  
 [in] Der Benutzer lesbarer Textname der Assembly.  
  
 `pMetaData`  
 [in] Ein Zeiger auf ASSEMBLYMETADATA, Version, Plattform und Gebietsschema-Informationen für die Assembly enthält.  
  
 `dwAssemblyFlags`  
 [in] Eine bitweise Kombination von [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) Werte, die verschiedenen Attribute der Assembly angeben.  
  
## <a name="remarks"></a>Hinweise  
 Zum Erstellen einer `Assembly` Metadatenstruktur, verwenden die [IMetaDataAssemblyEmit:: DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
