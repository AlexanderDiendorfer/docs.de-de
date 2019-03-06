---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 5b60c7281b92a487ba3ee275f7405cb82bd6cd87
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354998"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="fcb68-101">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="fcb68-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="fcb68-102">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="fcb68-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="fcb68-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fcb68-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fcb68-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="fcb68-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcb68-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcb68-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fcb68-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fcb68-106">Attributes and Elements</span></span>  
 <span data-ttu-id="fcb68-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fcb68-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fcb68-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="fcb68-108">Attributes</span></span>  
  
|<span data-ttu-id="fcb68-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="fcb68-109">Attribute</span></span>|<span data-ttu-id="fcb68-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcb68-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fcb68-111">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="fcb68-111">discoveryEndpoint</span></span>|<span data-ttu-id="fcb68-112">Eine Zeichenfolge mit dem Namen des Ermittlungsendpunkts, der einer Clientanwendung ermöglicht, automatisch nach einem sichtbaren Dienst zu suchen und zur Laufzeit dessen Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fcb68-112">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fcb68-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fcb68-113">Child Elements</span></span>  
  
|<span data-ttu-id="fcb68-114">Element</span><span class="sxs-lookup"><span data-stu-id="fcb68-114">Element</span></span>|<span data-ttu-id="fcb68-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcb68-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fcb68-116">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="fcb68-116">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="fcb68-117">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fcb68-117">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="fcb68-118">Kriterien können in Suchkriterien (nach welchen Diensten soll gesucht werden, für die) gruppiert werden und Beendigungskriterien (wie lange soll die Suche dauern).</span><span class="sxs-lookup"><span data-stu-id="fcb68-118">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fcb68-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fcb68-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fcb68-120">Element</span><span class="sxs-lookup"><span data-stu-id="fcb68-120">Element</span></span>|<span data-ttu-id="fcb68-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcb68-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fcb68-122">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="fcb68-122">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="fcb68-123">Definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.</span><span class="sxs-lookup"><span data-stu-id="fcb68-123">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fcb68-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcb68-124">See also</span></span>
- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
