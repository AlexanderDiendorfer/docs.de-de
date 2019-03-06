---
title: ICLRStrongName::StrongNameKeyGen-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98a53f488467ed1c66543c9861f056bc9890f617
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478517"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="e1e6f-102">ICLRStrongName::StrongNameKeyGen-Methode</span><span class="sxs-lookup"><span data-stu-id="e1e6f-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="e1e6f-103">Erstellt ein neues öffentliches/privates Schlüsselpaar für die Verwendung starker Namen.</span><span class="sxs-lookup"><span data-stu-id="e1e6f-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1e6f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1e6f-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1e6f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e1e6f-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="e1e6f-106">[in] Der angeforderte Schlüsselcontainer-Name.</span><span class="sxs-lookup"><span data-stu-id="e1e6f-106">[in] The requested key container name.</span></span> <span data-ttu-id="e1e6f-107">`wszKeyContainer` muss entweder eine nicht leere Zeichenfolge oder Null, um einen temporären Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e1e6f-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e1e6f-108">[in] Ein Wert, der angibt, ob der Schlüssel verlassen registriert.</span><span class="sxs-lookup"><span data-stu-id="e1e6f-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="e1e6f-109">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="e1e6f-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="e1e6f-110">0 x 00000000 - wird verwendet, wenn `wszKeyContainer` null ist, um einen temporären Schlüsselcontainernamen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e1e6f-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="e1e6f-111">0 x 00000001 (`SN_LEAVE_KEY`) – gibt an, dass der Schlüssel registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e1e6f-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="e1e6f-112">[out] Das zurückgegebene öffentliches/privates Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="e1e6f-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="e1e6f-113">[out] Die Größe in Bytes, des `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="e1e6f-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1e6f-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e1e6f-114">Return Value</span></span>  
 <span data-ttu-id="e1e6f-115">`S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="e1e6f-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1e6f-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e1e6f-116">Remarks</span></span>  
 <span data-ttu-id="e1e6f-117">Die [ICLRStrongName:: StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) Methode wird ein 1024-Bit-Schlüssel erstellt.</span><span class="sxs-lookup"><span data-stu-id="e1e6f-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="e1e6f-118">Nachdem der Schlüssel abgerufen werden, sollten Sie Aufrufen der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode, um den belegten Arbeitsspeicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="e1e6f-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1e6f-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e1e6f-119">Requirements</span></span>  
 <span data-ttu-id="e1e6f-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1e6f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1e6f-121">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e1e6f-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e1e6f-122">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e1e6f-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1e6f-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1e6f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e6f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1e6f-124">See also</span></span>
- [<span data-ttu-id="e1e6f-125">StrongNameKeyGenEx-Methode</span><span class="sxs-lookup"><span data-stu-id="e1e6f-125">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="e1e6f-126">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e1e6f-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
