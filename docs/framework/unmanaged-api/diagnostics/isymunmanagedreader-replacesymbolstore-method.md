---
title: ISymUnmanagedReader::ReplaceSymbolStore-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.ReplaceSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1b863816bfb7ed1a5db1fa2234db224b01cb6c9e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481546"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a>ISymUnmanagedReader::ReplaceSymbolStore-Methode
Ersetzt den vorhandenen Symbolspeicher durch einen Deltasymbolspeicher. Diese Methode ähnelt der [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) -Methode, mit der Ausnahme an, dass das angegebene Delta vollständig ersetzt, sondern als ein Update fungiert.  
  
> [!NOTE]
>  Sie müssen nur eine der angeben der `filename` oder `pIStream` nicht beide Parameter. Wenn `filename` angegeben ist, wird für die Symbole in der Datei der Symbolspeicher aktualisiert werden. Wenn `pIStream` angegeben ist, wird mit den Daten aus der Speicher aktualisiert werden die <xref:System.Runtime.InteropServices.ComTypes.IStream>.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a>Parameter  
 `filename`  
 [in] Der Name der Datei mit dem Symbolspeicher.  
  
 `pIStream`  
 [in] Als Alternative zu den Datei-Stream der `filename` Parameter.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch
- [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
