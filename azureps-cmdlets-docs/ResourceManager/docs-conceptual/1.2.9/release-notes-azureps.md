---
title: "Azure PowerShell-Änderungsprotokoll | Microsoft-Dokumentation"
description: "Hierbei handelt es sich um einen Verlauf der Änderungen, die in der neuesten Version an Azure PowerShell vorgenommen wurden."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.service: azure-powershell
ms.product: azure
ms.devlang: powershell
ms.topic: conceptual
ms.workload: 
ms.date: 05/18/2017
ms.openlocfilehash: 5fe7591855577e083aad5923aed37b18d0b2a40c
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2017
---
# <a name="release-notes"></a><span data-ttu-id="b8f8a-103">Versionshinweise</span><span class="sxs-lookup"><span data-stu-id="b8f8a-103">Release notes</span></span>

<span data-ttu-id="b8f8a-104">Hierbei handelt es sich um eine Liste der Änderungen, die in dieser Version an Azure PowerShell vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="b8f8a-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <a name="version-129"></a><span data-ttu-id="b8f8a-105">Version 1.2.9</span><span class="sxs-lookup"><span data-stu-id="b8f8a-105">Version 1.2.9</span></span>

<span data-ttu-id="b8f8a-106">Änderungen in dieser Version</span><span class="sxs-lookup"><span data-stu-id="b8f8a-106">Changes This Release</span></span>

* <span data-ttu-id="b8f8a-107">AzureRm.AzureStackAdmin-Modul</span><span class="sxs-lookup"><span data-stu-id="b8f8a-107">AzureRm.AzureStackAdmin Module</span></span>
    + <span data-ttu-id="b8f8a-108">Am Cmdlet „Add-AzureRmResourceProviderRegistration“ wurden Änderungen vorgenommen, um Teilungsvorgänge für Azure Resource Manager-Administratoren und Azure Resource Manager-Mandanten zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b8f8a-108">Changes in the Add-AzureRmResourceProviderRegistration cmdlet for the support of Admin Azure resource manager and tenant azure resource manager split.</span></span> <span data-ttu-id="b8f8a-109">Der neue Parameter „-ResourceManagerType“ wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b8f8a-109">A new parameter -ResourceManagerType has been added.</span></span>
    + <span data-ttu-id="b8f8a-110">Die Parameter „-AdminUri“, „-ApiVersion“, „-SubscriptionId“ und „-Token“ wurden aus den einzelnen Cmdlets entfernt.</span><span class="sxs-lookup"><span data-stu-id="b8f8a-110">Removal of the parameters -AdminUri, -ApiVersion, -SubscriptionId and -Token from each cmdlets.</span></span> <span data-ttu-id="b8f8a-111">Wir haben mithilfe von Warnungen darauf hingewiesen, dass diese Parameter ausgemustert werden. Nun wurden sie entfernt.</span><span class="sxs-lookup"><span data-stu-id="b8f8a-111">We have been printing warnings that these parameters will be deprecated and now they got removed.</span></span>
* <span data-ttu-id="b8f8a-112">AzureStackStorage-Modul</span><span class="sxs-lookup"><span data-stu-id="b8f8a-112">AzureStackStorage module</span></span>
    + <span data-ttu-id="b8f8a-113">Zur Unterstützung von Containermigrationsszenarien wurden neue Cmdlets hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b8f8a-113">Added new cmdlets to support container migration scenarios.</span></span>
    + <span data-ttu-id="b8f8a-114">Cmdlets, die auf interne Komponenten und zugrunde liegende Features verweisen, wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="b8f8a-114">Removed cmdlets referring to internal components and underlying features.</span></span>
* <span data-ttu-id="b8f8a-115">AzureRM.BootStrapper</span><span class="sxs-lookup"><span data-stu-id="b8f8a-115">AzureRM.BootStrapper</span></span>
    + <span data-ttu-id="b8f8a-116">Ein neues Modul wurde erstellt, das zum Verwalten der Versionen von Azure PowerShell-Cmdlets mithilfe von Versionsprofilen dient.</span><span class="sxs-lookup"><span data-stu-id="b8f8a-116">Created new module to manage versions of Azure PowerShell cmdlets through the use of version profiles</span></span>