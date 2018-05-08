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
# <a name="azure-stack-powershell"></a><span data-ttu-id="d984d-103">Azure Stack PowerShell</span><span class="sxs-lookup"><span data-stu-id="d984d-103">Azure Stack PowerShell</span></span>

<span data-ttu-id="d984d-104">Für Azure Stack sind die folgenden zwei PowerShell-Module erforderlich:</span><span class="sxs-lookup"><span data-stu-id="d984d-104">Azure Stack requires the following two PowerShell modules:</span></span>  

1. <span data-ttu-id="d984d-105">Das mit Azure Stack kompatible **AzureRM**-Modul, das durch Installation des API-Versionsprofils **2017-03-09-profile** zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d984d-105">The Azure Stack compatible **AzureRM** module which is available by installing the **2017-03-09-profile** API Version Profile.</span></span> <span data-ttu-id="d984d-106">Die mithilfe dieses Profils installierten Cmdlets können nur von den Azure Stack-Betreibern und -Benutzern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d984d-106">The cmdlets installed by using this profile can be used by Azure Stack operators and users.</span></span>

2. <span data-ttu-id="d984d-107">Die aktuelle Version ist **1.2.11** des **AzureStack**-Moduls.</span><span class="sxs-lookup"><span data-stu-id="d984d-107">The most current version is the **1.2.11** install of the **AzureStack** module.</span></span> <span data-ttu-id="d984d-108">Die mithilfe dieses Moduls installierten Cmdlets können nur von den Azure Stack-Betreibern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d984d-108">The cmdlets installed by using this module can be used by Azure Stack operators only.</span></span> <span data-ttu-id="d984d-109">Betreiber können Vorgänge (etwa die Verwaltung von Angeboten, Plänen, Diensten und Kontingenten) mithilfe der von diesem Modul bereitgestellten PowerShell-Cmdlets ausführen.</span><span class="sxs-lookup"><span data-stu-id="d984d-109">Operators can perform operations such as manage offers, plans, services, quotas, etc. by using the PowerShell cmdlets provided by this module.</span></span> <span data-ttu-id="d984d-110">Weitere Informationen zu den in diesem Modul verfügbaren PowerShell-Cmdlets finden Sie in den Referenzinhalten zu [AzureStackAdmin](https://docs.microsoft.com/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.11#azurerm.azurestackadmin) und [AzureStackStorage](https://docs.microsoft.com/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.11#azurerm.azurestackstorage).</span><span class="sxs-lookup"><span data-stu-id="d984d-110">To learn about the PowerShell cmdlets available in this module, see the [AzureStackAdmin](https://docs.microsoft.com/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.11#azurerm.azurestackadmin) and [AzureStackStorage](https://docs.microsoft.com/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.11#azurerm.azurestackstorage) Reference content.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d984d-111">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d984d-111">Next Steps</span></span>

* [<span data-ttu-id="d984d-112">Installieren von PowerShell für Azure Stack</span><span class="sxs-lookup"><span data-stu-id="d984d-112">Install PowerShell for Azure Stack</span></span>](https://docs.microsoft.com/azure/azure-stack/azure-stack-powershell-install?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
* [<span data-ttu-id="d984d-113">Konfigurieren von PowerShell für die Verwendung mit Azure Stack</span><span class="sxs-lookup"><span data-stu-id="d984d-113">Configure PowerShell for use with Azure Stack</span></span>](https://docs.microsoft.com/azure/azure-stack/azure-stack-powershell-configure?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
