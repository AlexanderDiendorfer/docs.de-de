---
title: Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit
description: Erfahren Sie, wie Sie eine app mithilfe von Azure Kubernetes Service bereitstellen.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 82a1cf7f3cc367bfb8b8f67a130600815f2a21c4
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664964"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a><span data-ttu-id="fcf27-103">Bereitstellen von Azure Kubernetes Service (AKS)</span><span class="sxs-lookup"><span data-stu-id="fcf27-103">Deploy to Azure Kubernetes Service (AKS)</span></span>

<span data-ttu-id="fcf27-104">Sie können mithilfe des Betriebssystems der bevorzugten Client AKS interagieren, hier wir zeigen, wie Sie ihn mit Microsoft Windows und einer eingebetteten Version von Ubuntu Linux in Windows, mithilfe von Bash-Befehle.</span><span class="sxs-lookup"><span data-stu-id="fcf27-104">You can interact with AKS using your preferred client operating system, here we show how to do it with Microsoft Windows and an embedded version of Ubuntu Linux in Windows, using Bash commands.</span></span>

<span data-ttu-id="fcf27-105">Voraussetzungen für die verfügen, bevor Sie mit AKS werden:</span><span class="sxs-lookup"><span data-stu-id="fcf27-105">Prerequisites to have before using AKS are:</span></span>

- <span data-ttu-id="fcf27-106">Linux oder Mac-Entwicklungscomputer</span><span class="sxs-lookup"><span data-stu-id="fcf27-106">Linux or Mac development machine</span></span>
- <span data-ttu-id="fcf27-107">Windows-Entwicklungscomputer</span><span class="sxs-lookup"><span data-stu-id="fcf27-107">Windows development machine</span></span>
  - <span data-ttu-id="fcf27-108">Entwicklermodus aktiviert ist, auf Windows</span><span class="sxs-lookup"><span data-stu-id="fcf27-108">Developer Mode enabled on Windows</span></span>
  - <span data-ttu-id="fcf27-109">Windows-Subsystem für Linux</span><span class="sxs-lookup"><span data-stu-id="fcf27-109">Windows Subsystem for Linux</span></span>
- <span data-ttu-id="fcf27-110">Azure-CLI installiert [Windows, Mac oder Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)</span><span class="sxs-lookup"><span data-stu-id="fcf27-110">Azure-CLI installed on [Windows, Mac or Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)</span></span>

> [!NOTE]
> <span data-ttu-id="fcf27-111">Um vollständige Informationen zu finden:</span><span class="sxs-lookup"><span data-stu-id="fcf27-111">To find complete information about:</span></span>
>
> <span data-ttu-id="fcf27-112">Azure-Befehlszeilenschnittstelle: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest></span><span class="sxs-lookup"><span data-stu-id="fcf27-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest></span></span>
>
> <span data-ttu-id="fcf27-113">Windows-Subsystem für Linux: <https://docs.microsoft.com/windows/wsl/about></span><span class="sxs-lookup"><span data-stu-id="fcf27-113">Windows Subsystem for Linux: <https://docs.microsoft.com/windows/wsl/about></span></span>

## <a name="create-the-aks-environment-in-azure"></a><span data-ttu-id="fcf27-114">Erstellen Sie die AKS-Umgebung in Azure</span><span class="sxs-lookup"><span data-stu-id="fcf27-114">Create the AKS environment in Azure</span></span>

<span data-ttu-id="fcf27-115">Es gibt mehrere Möglichkeiten zum Erstellen der AKS-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="fcf27-115">There are several ways to create the AKS Environment.</span></span> <span data-ttu-id="fcf27-116">Sie können mithilfe von Azure-CLI-Befehlen oder mithilfe von Azure-Portal erfolgen.</span><span class="sxs-lookup"><span data-stu-id="fcf27-116">It can be done by using Azure-CLI commands or by using the Azure portal.</span></span>

<span data-ttu-id="fcf27-117">Hier können Sie einige Beispiele zur Verwendung der Azure-CLI zum Erstellen des Clusters und das Azure-Portal die Ergebnisse zu überprüfen ist.</span><span class="sxs-lookup"><span data-stu-id="fcf27-117">Here you can explore some examples using the Azure-CLI to create the cluster and the Azure portal to review the results.</span></span> <span data-ttu-id="fcf27-118">Sie müssen sich auch um "kubectl" und Docker auf dem Entwicklungscomputer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fcf27-118">You also need to have Kubectl and Docker in your development machine.</span></span>  

## <a name="create-the-aks-cluster"></a><span data-ttu-id="fcf27-119">Erstellen des AKS-Clusters</span><span class="sxs-lookup"><span data-stu-id="fcf27-119">Create the AKS cluster</span></span>

<span data-ttu-id="fcf27-120">Erstellen des AKS-Clusters mithilfe des folgenden Befehls:</span><span class="sxs-lookup"><span data-stu-id="fcf27-120">Create the AKS cluster using this command:</span></span>

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

<span data-ttu-id="fcf27-121">Nachdem der Auftrag abgeschlossen ist, können Sie den im Azure-Portal erstellt AKS sehen:</span><span class="sxs-lookup"><span data-stu-id="fcf27-121">After the creation job finishes, you can see the AKS created in the Azure portal:</span></span>

<span data-ttu-id="fcf27-122">Die Ressourcengruppe:</span><span class="sxs-lookup"><span data-stu-id="fcf27-122">The resource group:</span></span>

![Browseransicht zur der die Azure-AKS-Ressourcengruppe.](media/aks-resource-group-view.png)

<span data-ttu-id="fcf27-124">**Abbildung 4-17**.</span><span class="sxs-lookup"><span data-stu-id="fcf27-124">**Figure 4-17**.</span></span> <span data-ttu-id="fcf27-125">AKS-Ressourcengruppe Ansicht von Azure.</span><span class="sxs-lookup"><span data-stu-id="fcf27-125">AKS Resource Group view from Azure.</span></span>

<span data-ttu-id="fcf27-126">Der AKS-Cluster:</span><span class="sxs-lookup"><span data-stu-id="fcf27-126">The AKS cluster:</span></span>

![Browseransicht einer AKS-Ressourcengruppe.](media/aks-cluster-view.png)

<span data-ttu-id="fcf27-128">**Abbildung 4-18.**</span><span class="sxs-lookup"><span data-stu-id="fcf27-128">**Figure 4-18**.</span></span> <span data-ttu-id="fcf27-129">AKS-Ansicht von Azure.</span><span class="sxs-lookup"><span data-stu-id="fcf27-129">AKS view from Azure.</span></span>

<span data-ttu-id="fcf27-130">Sie können auch anzeigen, den Knoten mit erstellt `Azure-CLI` und `Kubectl`.</span><span class="sxs-lookup"><span data-stu-id="fcf27-130">You can also view the node created using `Azure-CLI` and `Kubectl`.</span></span>

<span data-ttu-id="fcf27-131">Erste zuerst die Anmeldeinformationen ein:</span><span class="sxs-lookup"><span data-stu-id="fcf27-131">First, getting the credentials:</span></span>

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![Konsolenausgabe des obigen Befehls: Zusammengeführte "MsSampleK8Cluster als den aktuellen Kontext im /root/.kube/config.](media/get-credentials-command-result.png)

<span data-ttu-id="fcf27-133">**Abbildung 4-19.**</span><span class="sxs-lookup"><span data-stu-id="fcf27-133">**Figure 4-19**.</span></span> <span data-ttu-id="fcf27-134">`aks get-credentials` Ergebnis des Befehls.</span><span class="sxs-lookup"><span data-stu-id="fcf27-134">`aks get-credentials` command result.</span></span>

<span data-ttu-id="fcf27-135">Und anschließend, Abrufen von Knoten aus "kubectl":</span><span class="sxs-lookup"><span data-stu-id="fcf27-135">And then, getting nodes from Kubectl:</span></span>

```console
kubectl get nodes
```

![Konsolenausgabe erwähnte Befehl: Liste von Knoten mit dem Status, Alter (Zeit, die ausgeführt werden) und version](media/kubectl-get-nodes-command-result.png)

<span data-ttu-id="fcf27-137">**Abbildung 4-20:**</span><span class="sxs-lookup"><span data-stu-id="fcf27-137">**Figure 4-20**.</span></span> <span data-ttu-id="fcf27-138">`kubectl get nodes` Ergebnis des Befehls.</span><span class="sxs-lookup"><span data-stu-id="fcf27-138">`kubectl get nodes` command result.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fcf27-139">[Zurück](orchestrate-high-scalability-availability.md)
>[Weiter](docker-apps-development-environment.md)</span><span class="sxs-lookup"><span data-stu-id="fcf27-139">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-development-environment.md)</span></span>
