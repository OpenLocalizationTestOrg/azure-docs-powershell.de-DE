---
title: "Übersicht über Azure Stack PowerShell | Microsoft-Dokumentation"
description: "Übersicht über die Azure Stack PowerShell-Installation und -Konfiguration."
author: SnehaGunda
manager: Byronr
ms.product: azure-stack
ms.service: powershell
ms.devlang: powershell
ms.topic: reference
ms.author: sngun
ms.manager: byronr
ms.openlocfilehash: f895992b4200f260189b3dbc541452e73a377b00
ms.sourcegitcommit: 8446ae373ac6928871ec8f10d3a4918b4601d5b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2018
---
# <a name="azure-stack-powershell"></a>Azure Stack PowerShell

Für Azure Stack sind die folgenden zwei PowerShell-Module erforderlich:  

1. Das mit Azure Stack kompatible **AzureRM**-Modul, das durch Installation des API-Versionsprofils **2017-03-09-profile** zur Verfügung gestellt wird. Die mithilfe dieses Profils installierten Cmdlets können nur von den Azure Stack-Betreibern und -Benutzern verwendet werden.

2. Die aktuelle Version ist **1.2.11** des **AzureStack**-Moduls. Die mithilfe dieses Moduls installierten Cmdlets können nur von den Azure Stack-Betreibern verwendet werden. Betreiber können Vorgänge (etwa die Verwaltung von Angeboten, Plänen, Diensten und Kontingenten) mithilfe der von diesem Modul bereitgestellten PowerShell-Cmdlets ausführen. Weitere Informationen zu den in diesem Modul verfügbaren PowerShell-Cmdlets finden Sie in den Referenzinhalten zu [AzureStackAdmin](https://docs.microsoft.com/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.11#azurerm.azurestackadmin) und [AzureStackStorage](https://docs.microsoft.com/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.11#azurerm.azurestackstorage).

## <a name="next-steps"></a>Nächste Schritte

* [Installieren von PowerShell für Azure Stack](https://docs.microsoft.com/azure/azure-stack/azure-stack-powershell-install?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
* [Konfigurieren von PowerShell für die Verwendung mit Azure Stack](https://docs.microsoft.com/azure/azure-stack/azure-stack-powershell-configure?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
