---
title: Threadingprobleme bei der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, threading issues
- threading issues with UI Automation
ms.assetid: 0ab8d42c-5b8b-481b-b788-2caecc2f0191
ms.openlocfilehash: 83b8ec67cff7006e736e0f65a7339b340b20d458
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678591"
---
# <a name="ui-automation-threading-issues"></a>Threadingprobleme bei der Benutzeroberflächenautomatisierung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Aufgrund der Art und Weise, wie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Windows-Meldungen verwendet, können Konflikte auftreten, wenn eine Clientanwendung versucht, mit der eigenen [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] über den [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] zu interagieren. Diese Konflikte können dazu führen, dass die Leistung erheblich beeinträchtigt wird, oder sogar dazu, dass die Anwendung gar nicht mehr reagiert.  
  
 Wenn die Clientanwendung mit allen Elementen auf dem Desktop interagieren soll, einschließlich der eigenen [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], sollten alle Aufrufe von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] in einem getrennten Thread ausgeführt werden. Dies schließt das Suchen von Elementen (z. B. durch Verwenden der <xref:System.Windows.Automation.TreeWalker> -Methode oder der <xref:System.Windows.Automation.AutomationElement.FindAll%2A> -Methode) sowie die Verwendung von Steuerelementmustern ein.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Aufrufe können problemlos innerhalb eines [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignishandlers ausgeführt werden, da der Ereignishandler stets in einem anderen als dem[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Thread aufgerufen wird. Beim Abonnieren von Ereignissen, die aus der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]der Clientanwendung stammen können, muss der Aufruf von <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>bzw. einer verwandten Methode jedoch in einem anderen als dem[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Thread ausgeführt werden. Entfernen Sie Ereignishandler im gleichen Thread.
