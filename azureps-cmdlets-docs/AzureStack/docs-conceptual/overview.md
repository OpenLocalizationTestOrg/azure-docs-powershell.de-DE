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
ms.openlocfilehash: 2a03697e0f3e80d63c48f2dc5615f6c99b9ef716
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2017
---
# <a name="azure-stack-powershell"></a>Azure Stack PowerShell 

Für Azure Stack sind die folgenden zwei PowerShell-Module erforderlich:  

1. Das mit Azure Stack kompatible **AzureRM**-Modul, das durch Installation des API-Versionsprofils **2017-03-09-profile** zur Verfügung gestellt wird. Die mithilfe dieses Profils installierten Cmdlets können von den Azure Stack-Cloudadministratoren und den Mandanten verwendet werden. Informationen zu den PowerShell-Cmdlets, die in diesem Profil verfügbar sind, finden Sie im PowerShell-Referenzinhalt für [Version 1.2.9 des AzureRM-Moduls](https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-1.2.9).  

2. Die Version **1.2.9** des **AzureStack**-Moduls. Die mithilfe dieses Moduls installierten Cmdlets können nur von den Azure Stack-Cloudadministratoren verwendet werden. Der Administrator kann Vorgänge (etwa die Verwaltung von Angeboten, Plänen, Diensten und Kontingenten) mithilfe der von diesem Modul bereitgestellten PowerShell-Cmdlets ausführen. Weitere Informationen zu den in diesem Modul verfügbaren PowerShell-Cmdlets finden Sie in den Referenzinhalten zu [AzureStackAdmin](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.9#azurerm.azurestackadmin) und [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.9#azurerm.azurestackstorage).

## <a name="next-steps"></a>Nächste Schritte

* [Installieren von PowerShell für Azure Stack](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-install?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
* [Konfigurieren von PowerShell für die Verwendung mit Azure Stack](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-configure?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)


