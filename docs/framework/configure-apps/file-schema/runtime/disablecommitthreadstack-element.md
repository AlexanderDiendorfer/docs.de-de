---
title: <disableCommitThreadStack> Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08ffd6ffcb9a8fa356d486f6d2ae1113de0fa682
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106509"
---
# <a name="disablecommitthreadstack-element"></a><span data-ttu-id="d7150-102">\<DisableCommitThreadStack >-Element</span><span class="sxs-lookup"><span data-stu-id="d7150-102">\<disableCommitThreadStack> Element</span></span>
<span data-ttu-id="d7150-103">Gibt an, ob beim Starten eines Threads für den vollständigen Threadstapel ein Commit ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="d7150-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
 <span data-ttu-id="d7150-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d7150-104">\<configuration></span></span>  
<span data-ttu-id="d7150-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="d7150-105">\<runtime></span></span>  
<span data-ttu-id="d7150-106">\<disableCommitThreadStack></span><span class="sxs-lookup"><span data-stu-id="d7150-106">\<disableCommitThreadStack></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7150-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7150-107">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7150-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d7150-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d7150-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d7150-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7150-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="d7150-110">Attributes</span></span>  
  
|<span data-ttu-id="d7150-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="d7150-111">Attribute</span></span>|<span data-ttu-id="d7150-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7150-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7150-113">enabled</span><span class="sxs-lookup"><span data-stu-id="d7150-113">enabled</span></span>|<span data-ttu-id="d7150-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="d7150-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="d7150-115">Gibt an, ob das Standardverhalten, beim Starten des Threads den gesamten Threadstapel zu commiten, deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="d7150-115">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d7150-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="d7150-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="d7150-117">Wert</span><span class="sxs-lookup"><span data-stu-id="d7150-117">Value</span></span>|<span data-ttu-id="d7150-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7150-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d7150-119">0</span><span class="sxs-lookup"><span data-stu-id="d7150-119">0</span></span>|<span data-ttu-id="d7150-120">Das Standardverhalten der Common Language Runtime, beim Starten eines Threads einen Commit für den vollständigen Threadstapel auszuführen, ist nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d7150-120">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="d7150-121">1</span><span class="sxs-lookup"><span data-stu-id="d7150-121">1</span></span>|<span data-ttu-id="d7150-122">Das Standardverhalten der Common Language Runtime, beim Starten eines Threads einen Commit für den vollständigen Threadstapel auszuführen, ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d7150-122">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7150-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d7150-123">Child Elements</span></span>  
 <span data-ttu-id="d7150-124">Keine</span><span class="sxs-lookup"><span data-stu-id="d7150-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d7150-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d7150-125">Parent Elements</span></span>  
  
|<span data-ttu-id="d7150-126">Element</span><span class="sxs-lookup"><span data-stu-id="d7150-126">Element</span></span>|<span data-ttu-id="d7150-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7150-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d7150-128">Das Stammelement in jeder von der Common Language Runtime- und den [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] -Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="d7150-128">The root element in every configuration file used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
|`runtime`|<span data-ttu-id="d7150-129">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="d7150-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7150-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7150-130">Remarks</span></span>  
 <span data-ttu-id="d7150-131">Das Standardverhalten der Common Language Runtime ist, beim Starten eines Threads einen Commit für den vollständigen Threadstapel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d7150-131">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="d7150-132">Wenn eine große Anzahl von Threads auf einem Server erstellt werden muss, der nur über begrenzten Arbeitsspeicher verfügt, und der Großteil dieser Threads nur sehr wenig Stapelspeicher verwenden wird, ist die Leistung des Servers möglicherweise besser, wenn die Common Language Runtime nicht sofort einen Commit für den vollständigen Threadstapel ausführt, wenn ein Thread gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="d7150-132">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7150-133">Nicht verwaltete Hosts können das `STARTUP_DISABLE_COMMITTHREADSTACK` -Startflag in der [STARTUP_FLAGS](../../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) -Enumeration verwenden, um das gleiche Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="d7150-133">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7150-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7150-134">Example</span></span>  
 <span data-ttu-id="d7150-135">Das folgende Beispiel zeigt, wie Sie das Standardverhalten der Common Language Runtime deaktivieren, die während des Threadstarts einen Commit für den vollständigen Threadstapel ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="d7150-135">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7150-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7150-136">See also</span></span>

- [<span data-ttu-id="d7150-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="d7150-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="d7150-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="d7150-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
