---
title: ImportTypes2-Methode
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e2958fe31ff0065cfb028eaddf8bbb02f3618f9d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471731"
---
# <a name="importtypes2-method"></a><span data-ttu-id="ad102-102">ImportTypes2-Methode</span><span class="sxs-lookup"><span data-stu-id="ad102-102">ImportTypes2 Method</span></span>
<span data-ttu-id="ad102-103">Startet den Import von Typen.</span><span class="sxs-lookup"><span data-stu-id="ad102-103">Initiates the import of types.</span></span> <span data-ttu-id="ad102-104">Rufen Sie diese Methode zum Importieren von Typen aus jedem Bereich über importiert [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="ad102-104">Call this method to begin importing types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad102-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad102-105">Syntax</span></span>  
  
```  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad102-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ad102-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ad102-107">ID der Assembly in die importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad102-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ad102-108">Die ID der Datei, aus denen importiert.</span><span class="sxs-lookup"><span data-stu-id="ad102-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="ad102-109">Nullbasierte Bereich aus der importiert werden.</span><span class="sxs-lookup"><span data-stu-id="ad102-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="ad102-110">Empfängt Enumeratorhandle für die Typen im angegebenen Bereich.</span><span class="sxs-lookup"><span data-stu-id="ad102-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="ad102-111">Empfängt optional [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ad102-111">Optionally receives [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="ad102-112">Empfängt optional die Anzahl der Typen im angegebenen Bereich.</span><span class="sxs-lookup"><span data-stu-id="ad102-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad102-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ad102-113">Return Value</span></span>  
 <span data-ttu-id="ad102-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="ad102-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad102-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ad102-115">Requirements</span></span>  
 <span data-ttu-id="ad102-116">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="ad102-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad102-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad102-117">See also</span></span>
- [<span data-ttu-id="ad102-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad102-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ad102-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad102-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ad102-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="ad102-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
