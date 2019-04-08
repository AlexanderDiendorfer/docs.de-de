---
title: AssemblyOptions-Enumeration
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 293787d7798768ff2b4e2fb8fec9ed201fdb85ff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085414"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="3d27a-102">AssemblyOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3d27a-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="3d27a-103">Listet die Assemblyoptionen.</span><span class="sxs-lookup"><span data-stu-id="3d27a-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d27a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d27a-104">Syntax</span></span>  
  
```  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a><span data-ttu-id="3d27a-105">Felder</span><span class="sxs-lookup"><span data-stu-id="3d27a-105">Fields</span></span>  
  
|<span data-ttu-id="3d27a-106">Feld</span><span class="sxs-lookup"><span data-stu-id="3d27a-106">Field</span></span>|<span data-ttu-id="3d27a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d27a-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3d27a-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="3d27a-108">optAssemTitle</span></span>|<span data-ttu-id="3d27a-109">Zeichenfolge – den Assemblytitel darstellt.</span><span class="sxs-lookup"><span data-stu-id="3d27a-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="3d27a-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="3d27a-110">optAssemDescription</span></span>|<span data-ttu-id="3d27a-111">Zeichenfolge – die Beschreibung der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="3d27a-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="3d27a-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="3d27a-112">optAssemConfig</span></span>|<span data-ttu-id="3d27a-113">Zeichenfolge – enthält die Assemblykonfiguration.</span><span class="sxs-lookup"><span data-stu-id="3d27a-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="3d27a-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="3d27a-114">optAssemOS</span></span>|<span data-ttu-id="3d27a-115">-Codierte Zeichenfolge: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="3d27a-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="3d27a-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="3d27a-116">optAssemProcessor</span></span>|<span data-ttu-id="3d27a-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="3d27a-117">ULONG</span></span>|  
|<span data-ttu-id="3d27a-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="3d27a-118">optAssemLocale</span></span>|<span data-ttu-id="3d27a-119">Zeichenfolge – das Gebietsschema der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="3d27a-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="3d27a-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="3d27a-120">optAssemVersion</span></span>|<span data-ttu-id="3d27a-121">Zeichenfolge – gibt an, codiert als: "Major.Minor.Build.Revision".</span><span class="sxs-lookup"><span data-stu-id="3d27a-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="3d27a-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="3d27a-122">optAssemCompany</span></span>|<span data-ttu-id="3d27a-123">Zeichenfolge – das Unternehmen enthält.</span><span class="sxs-lookup"><span data-stu-id="3d27a-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="3d27a-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="3d27a-124">optAssemProduct</span></span>|<span data-ttu-id="3d27a-125">Zeichenfolge – der Name des Produkts enthält.</span><span class="sxs-lookup"><span data-stu-id="3d27a-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="3d27a-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="3d27a-126">optAssemProductVersion</span></span>|<span data-ttu-id="3d27a-127">Zeichenfolge (auch bekannt als InformationalVersion bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="3d27a-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="3d27a-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="3d27a-128">optAssemCopyright</span></span>|<span data-ttu-id="3d27a-129">Zeichenfolge – die copyright-Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="3d27a-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="3d27a-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="3d27a-130">optAssemTrademark</span></span>|<span data-ttu-id="3d27a-131">Zeichenfolge – die Markeninformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="3d27a-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="3d27a-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="3d27a-132">optAssemKeyFile</span></span>|<span data-ttu-id="3d27a-133">Zeichenfolge (Dateiname).</span><span class="sxs-lookup"><span data-stu-id="3d27a-133">String (file name).</span></span>|  
|<span data-ttu-id="3d27a-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="3d27a-134">optAssemKeyName</span></span>|<span data-ttu-id="3d27a-135">Zeichenfolge (wichtigsten Name).</span><span class="sxs-lookup"><span data-stu-id="3d27a-135">String (The key name).</span></span>|  
|<span data-ttu-id="3d27a-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="3d27a-136">optAssemAlgID</span></span>|<span data-ttu-id="3d27a-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="3d27a-137">ULONG</span></span>|  
|<span data-ttu-id="3d27a-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="3d27a-138">optAssemFlags</span></span>|<span data-ttu-id="3d27a-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="3d27a-139">ULONG</span></span>|  
|<span data-ttu-id="3d27a-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="3d27a-140">optAssemHalfSign</span></span>|<span data-ttu-id="3d27a-141">"Bool" (auch als DelaySign bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="3d27a-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="3d27a-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="3d27a-142">optAssemFileVersion</span></span>|<span data-ttu-id="3d27a-143">Zeichenfolge – als "Hauptversion.Nebenversion.Build.Revision"--identisch mit ProductVersion codiert.</span><span class="sxs-lookup"><span data-stu-id="3d27a-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="3d27a-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="3d27a-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="3d27a-145">Zeichenfolge – als "Hauptversion.Nebenversion.Build.Revision" codiert.</span><span class="sxs-lookup"><span data-stu-id="3d27a-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="3d27a-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="3d27a-146">optLastAssemOption</span></span>|<span data-ttu-id="3d27a-147">Ein Zähler, der die Anzahl der Elemente.</span><span class="sxs-lookup"><span data-stu-id="3d27a-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d27a-148">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3d27a-148">Requirements</span></span>  
 <span data-ttu-id="3d27a-149">**Header:** alink.h</span><span class="sxs-lookup"><span data-stu-id="3d27a-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="3d27a-150">**Bibliothek**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="3d27a-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d27a-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d27a-151">See also</span></span>

- [<span data-ttu-id="3d27a-152">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="3d27a-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
