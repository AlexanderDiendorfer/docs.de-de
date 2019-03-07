---
title: ICorProfilerInfo::GetClassFromToken-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a74e99e0b669c1b3d8e36d881391f27ef71ae306
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493543"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a>ICorProfilerInfo::GetClassFromToken-Methode
Ruft die ID der Klasse, mit dem angegebenen Metadatentoken ab. Diese Methode ist in .NET Framework, Version 2.0, veraltet. Verwendung [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleID`  
 [in] Die ID des Moduls, das die Klasse enthält.  
  
 `typeDef`  
 [in] Ein `mdTypeDef` Metadatentoken, das die Klasse verweist.  
  
 `cTypeArgs`  
 [out] Ein Zeiger auf die Klasse-ID  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ist veraltet. Verwenden Sie stattdessen `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` für alle Typen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 1.0, 1.1  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
