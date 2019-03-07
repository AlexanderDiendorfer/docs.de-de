---
title: CertTimestampAuthenticodeLicense-Funktion
ms.date: 03/30/2017
api_name:
- CertTimestampAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d468325a-21c5-43ce-8567-84e342b22308
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7b336d1372bdbe0d6dbdcf79d94e14c30ad2ebe
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497339"
---
# <a name="certtimestampauthenticodelicense-function"></a><span data-ttu-id="73a34-102">CertTimestampAuthenticodeLicense-Funktion</span><span class="sxs-lookup"><span data-stu-id="73a34-102">CertTimestampAuthenticodeLicense Function</span></span>
<span data-ttu-id="73a34-103">Fügt einer Authenticode-XrML-Lizenz einen Zeitstempel hinzu.</span><span class="sxs-lookup"><span data-stu-id="73a34-103">Time-stamps an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73a34-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="73a34-104">Syntax</span></span>  
  
```  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73a34-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="73a34-105">Parameters</span></span>  
 `pSignedLicenseBlob`  
 <span data-ttu-id="73a34-106">[in] Die signierte Authenticode-XrML-Lizenz, die einen Zeitstempel erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="73a34-106">[in] The signed Authenticode XrML license to be time-stamped.</span></span> <span data-ttu-id="73a34-107">Finden Sie unter den [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) Struktur.</span><span class="sxs-lookup"><span data-stu-id="73a34-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `pwszTimestampURI`  
 <span data-ttu-id="73a34-108">[in] Die URL des Zeitstempelservers.</span><span class="sxs-lookup"><span data-stu-id="73a34-108">[in] The time-stamp server's URI.</span></span>  
  
 `pTimestampSignatureBlob`  
 <span data-ttu-id="73a34-109">[out] Ein Zeiger auf CRYPT_DATA_BLOB, um die Base64-codierte Zeitstempelsignatur zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="73a34-109">[out] A pointer to CRYPT_DATA_BLOB to receive the base64-encoded time-stamp signature.</span></span> <span data-ttu-id="73a34-110">Es ist der Verantwortung des Aufrufers freigeben `pTimestampSignatureBlob` -> `pbData` mit `HepFree()` nach ihrer Verwendung.</span><span class="sxs-lookup"><span data-stu-id="73a34-110">It is the caller's responsibility to free `pTimestampSignatureBlob`->`pbData` with `HepFree()` after use.</span></span> <span data-ttu-id="73a34-111">Finden Sie unter den [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) Struktur.</span><span class="sxs-lookup"><span data-stu-id="73a34-111">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73a34-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="73a34-112">Remarks</span></span>  
 <span data-ttu-id="73a34-113">Die Zeitstempelsignatur ist eigentlich eine PKCS #7-SignedData-Nachricht, deren Inhalt die Binärform des SignatureValue aus der Signatur der Lizenz ist.</span><span class="sxs-lookup"><span data-stu-id="73a34-113">The time-stamp signature is actually a PKCS #7 SignedData message whose content is the binary form of the SignatureValue from the license's signature.</span></span> <span data-ttu-id="73a34-114">Im Prinzip agiert sie als Gegensignatur für die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="73a34-114">Basically, this acts as a counter-signature of the license.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73a34-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="73a34-115">Return Value</span></span>  
 <span data-ttu-id="73a34-116">`S_OK`, wenn die Funktion erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="73a34-116">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="73a34-117">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="73a34-117">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a34-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73a34-118">See also</span></span>
- [<span data-ttu-id="73a34-119">Authenticode</span><span class="sxs-lookup"><span data-stu-id="73a34-119">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
