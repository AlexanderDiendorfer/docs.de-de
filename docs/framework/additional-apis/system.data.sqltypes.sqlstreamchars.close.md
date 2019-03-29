---
title: SqlStreamChars.Close-Methode (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Close
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d0c29bbc5c6bea98cf36e3c2b6bf7825d6843ccc
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634023"
---
# <a name="sqlstreamcharsclose-method"></a><span data-ttu-id="25341-102">SqlStreamChars.Close-Methode</span><span class="sxs-lookup"><span data-stu-id="25341-102">SqlStreamChars.Close Method</span></span>

<span data-ttu-id="25341-103">Schließt den aktuellen Stream und gibt alle dem Stream zugeordneten Systemressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="25341-103">Closes the current stream and releases any system resources associated with the stream.</span></span> <span data-ttu-id="25341-104">Die Assembly mit dieser Methode hat eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="25341-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="25341-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="25341-105">It's intended for use by SQL Server.</span></span><span data-ttu-id="25341-106"> Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="25341-106"> For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public virtual void Close ();
```

## <a name="remarks"></a><span data-ttu-id="25341-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25341-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="25341-108">Die `SqlStreamChars.Close` Methode privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="25341-108">The `SqlStreamChars.Close` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="25341-109">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="25341-109">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="25341-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="25341-110">Requirements</span></span>

<span data-ttu-id="25341-111">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="25341-111">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="25341-112">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="25341-112">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="25341-113">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="25341-113">**.NET Framework versions:** Available since 2.0.</span></span>