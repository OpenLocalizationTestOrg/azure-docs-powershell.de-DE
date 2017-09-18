---
title: Installieren und Konfigurieren von Azure PowerShell unter macOS und Linux | Microsoft-Dokumentation
description: "Hier erfahren Sie, wie Sie Azure PowerShell für die erste Verwendung unter macOS und Linux installieren und konfigurieren."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/06/2017
ms.openlocfilehash: 94b39c18acaca7a4b17b5207feed025442665acc
ms.sourcegitcommit: 202ec2df66c40a60f47ea06b30a6701ad444d229
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2017
---
# <a name="install-and-configure-azure-powershell-on-macos-and-linux"></a><span data-ttu-id="509b6-103">Installieren und Konfigurieren von Azure PowerShell unter macOS und Linux</span><span class="sxs-lookup"><span data-stu-id="509b6-103">Install and configure Azure PowerShell on macOS and Linux</span></span>

<span data-ttu-id="509b6-104">Es ist jetzt möglich, PowerShell 6 (Beta) und Azure PowerShell auf anderen Plattformen als Windows zu installieren.</span><span class="sxs-lookup"><span data-stu-id="509b6-104">It is now possible to install PowerShell 6 (beta) and Azure PowerShell on non-Windows platforms.</span></span>
<span data-ttu-id="509b6-105">Die Installation von Azure PowerShell unter macOS und Linux unterscheidet sich nicht sehr von der Installation unter Windows, allerdings müssen Sie zuerst PowerShell 6 (Beta) installieren.</span><span class="sxs-lookup"><span data-stu-id="509b6-105">The process of installing Azure PowerShell on macOS and Linux is not that different from Windows, however, you must first install PowerShell 6 (beta).</span></span>

> [!NOTE]

> <span data-ttu-id="509b6-106">Derzeit liegt sowohl PowerShell 6 (Beta) als auch Azure PowerShell für .NET Core noch in der Betaversion vor.</span><span class="sxs-lookup"><span data-stu-id="509b6-106">At this time, both PowerShell 6 (beta) and Azure PowerShell for .NET Core are still in beta.</span></span>
> <span data-ttu-id="509b6-107">Der Support für diese Produkte ist eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="509b6-107">Support for these products is limited.</span></span> <span data-ttu-id="509b6-108">Wenn Sie Probleme haben oder Fehler erkennen, melden Sie dies bitte in GitHub.</span><span class="sxs-lookup"><span data-stu-id="509b6-108">If you have problems or discover bugs, please file Issues in GitHub.</span></span>
>
> * [<span data-ttu-id="509b6-109">Probleme mit PowerShell 6 (Beta)</span><span class="sxs-lookup"><span data-stu-id="509b6-109">Issues for PowerShell 6 (beta)</span></span>](https://github.com/PowerShell/PowerShell/issues)
> * [<span data-ttu-id="509b6-110">Probleme mit Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="509b6-110">Issues for Azure PowerShell</span></span>](https://github.com/azure/azure-docs-powershell/issues)

## <a name="step-1-install-powershell-6-beta"></a><span data-ttu-id="509b6-111">Schritt 1: Installieren von PowerShell 6 (Beta)</span><span class="sxs-lookup"><span data-stu-id="509b6-111">Step 1: Install PowerShell 6 (beta)</span></span>

<span data-ttu-id="509b6-112">Die Installation von PowerShell 6 (Beta) variiert je nach Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="509b6-112">The process of installing PowerShell 6 (beta) on varies depending on the target operating system.</span></span>
<span data-ttu-id="509b6-113">Es ist zwar möglich, PowerShell 6 (Beta) unter Windows zu installieren, doch Thema dieses Artikels ist die Installation unter macOS und Linux.</span><span class="sxs-lookup"><span data-stu-id="509b6-113">While it is possible to install PowerShell 6 (beta) on Windows, this article focuses on macOS and Linux.</span></span> <span data-ttu-id="509b6-114">Wenn Sie Azure PowerShell unter Windows verwenden möchten, lesen Sie den Artikel [Installieren und Konfigurieren von Azure PowerShell](./install-azurerm-ps.md) für Windows.</span><span class="sxs-lookup"><span data-stu-id="509b6-114">If you want to use Azure PowerShell on Windows, see the [install](./install-azurerm-ps.md) article for Windows.</span></span>

<span data-ttu-id="509b6-115">Um **PowerShell 6** (Beta) unter Linux oder macOS zu installieren, müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="509b6-115">To install **PowerShell 6** (beta) on Linux or macOS, you need to:</span></span>

1. <span data-ttu-id="509b6-116">PowerShell für das jeweilige Betriebssystem und die Version von [GitHub](https://github.com/powershell/powershell#get-powershell) herunterladen</span><span class="sxs-lookup"><span data-stu-id="509b6-116">Get PowerShell for the specific OS and version, from [GitHub](https://github.com/powershell/powershell#get-powershell)</span></span>
2. <span data-ttu-id="509b6-117">Die Installationsanweisungen befolgen</span><span class="sxs-lookup"><span data-stu-id="509b6-117">Follow the installation instructions</span></span>
   - [<span data-ttu-id="509b6-118">Linux</span><span class="sxs-lookup"><span data-stu-id="509b6-118">Linux</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md)
   - [<span data-ttu-id="509b6-119">macOS</span><span class="sxs-lookup"><span data-stu-id="509b6-119">macOS</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#macos-1012)

## <a name="step-2-install-azure-powershell-for-net-core"></a><span data-ttu-id="509b6-120">Schritt 2: Installieren von Azure PowerShell für .NET Core</span><span class="sxs-lookup"><span data-stu-id="509b6-120">Step 2: Install Azure PowerShell for .NET Core</span></span>

<span data-ttu-id="509b6-121">In PowerShell 6 (Beta) ist das PowerShellGet-Modul bereits installiert.</span><span class="sxs-lookup"><span data-stu-id="509b6-121">PowerShell 6 (beta) comes with the PowerShellGet module already installed.</span></span> <span data-ttu-id="509b6-122">Dies vereinfacht die Installation eines beliebigen, im PowerShell-Katalog veröffentlichten Moduls.</span><span class="sxs-lookup"><span data-stu-id="509b6-122">This makes it easy to install any module that is published to the PowerShell Gallery.</span></span> <span data-ttu-id="509b6-123">Um Azure PowerShell zu installieren, öffnen Sie eine neue PowerShell-Sitzung, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="509b6-123">To install Azure PowerShell, open a new PowerShell session and run the following command:</span></span>

```powershell
Install-Module AzureRM.NetCore
```

## <a name="step-3-load-the-azurermnetcore-module"></a><span data-ttu-id="509b6-124">Schritt 3: Laden des AzureRM.Netcore-Moduls</span><span class="sxs-lookup"><span data-stu-id="509b6-124">Step 3: Load the AzureRM.Netcore module</span></span>

<span data-ttu-id="509b6-125">Nach der Installation des Moduls müssen Sie das Modul in der PowerShell-Sitzung laden.</span><span class="sxs-lookup"><span data-stu-id="509b6-125">Once the module is installed, you need to load the module into your PowerShell session.</span></span> <span data-ttu-id="509b6-126">Module werden wie folgt mit dem Cmdlet `Import-Module` geladen:</span><span class="sxs-lookup"><span data-stu-id="509b6-126">Modules are loaded using the `Import-Module` cmdlet, as follows:</span></span>

```powershell
Import-Module AzureRM.Netcore
```

<span data-ttu-id="509b6-127">Nach Abschluss des Imports können Sie das neu installierte Modul testen, indem Sie versuchen, sich mithilfe des folgenden Befehls bei Azure anzumelden:</span><span class="sxs-lookup"><span data-stu-id="509b6-127">After the import completes, you can test your newly installed and module by attempting to sign into Azure using the following command:</span></span>

```powershell
Login-AzureRMAccount
```

<span data-ttu-id="509b6-128">Der obige Befehl sollte Sie auffordern, zu `https://aka.ms/devicelogin` zu wechseln und den bereitgestellten Code einzugeben.</span><span class="sxs-lookup"><span data-stu-id="509b6-128">The above command should prompt you to go to `https://aka.ms/devicelogin` and enter the provided code.</span></span>

## <a name="available-cmdlets"></a><span data-ttu-id="509b6-129">Verfügbare Cmdlets</span><span class="sxs-lookup"><span data-stu-id="509b6-129">Available cmdlets</span></span>

<span data-ttu-id="509b6-130">Die Azure PowerShell-Module für .NET Standard sind immer noch in der Entwicklungsphase.</span><span class="sxs-lookup"><span data-stu-id="509b6-130">The Azure PowerShell modules for .NET Standard are still in development.</span></span> <span data-ttu-id="509b6-131">Diese Module bieten nicht den vollständigen Satz der Cmdlets, die für die Windows-Version der Module verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="509b6-131">These modules do not provide the full set of cmdlets that are available for the Windows version of the modules.</span></span> <span data-ttu-id="509b6-132">Die folgenden Funktionen werden in AzureRM.Netcore-Module implementiert:</span><span class="sxs-lookup"><span data-stu-id="509b6-132">The following functions are implemented in AzureRM.Netcore modules:</span></span>

* <span data-ttu-id="509b6-133">Kontoverwaltung</span><span class="sxs-lookup"><span data-stu-id="509b6-133">Account management</span></span>
  - <span data-ttu-id="509b6-134">Melden Sie sich mit dem Microsoft-Konto, Unternehmenskonto oder einem Dienstprinzipal über Microsoft Azure Active Directory an.</span><span class="sxs-lookup"><span data-stu-id="509b6-134">Login with Microsoft account, Organizational account, or Service Principal through Microsoft Azure Active Directory</span></span>
  - <span data-ttu-id="509b6-135">Speichern Sie die Anmeldeinformationen mit Save-AzureRmContext auf einem Datenträger, und laden Sie gespeicherte Anmeldeinformationen mit Import-AzureRmContext.</span><span class="sxs-lookup"><span data-stu-id="509b6-135">Save Credentials to disk with Save-AzureRmContext and load saved credentials using Import-AzureRmContext</span></span>
* <span data-ttu-id="509b6-136">Environment</span><span class="sxs-lookup"><span data-stu-id="509b6-136">Environment</span></span>
  - <span data-ttu-id="509b6-137">Abrufen der verschiedenen vorkonfigurierten Microsoft Azure-Umgebungen</span><span class="sxs-lookup"><span data-stu-id="509b6-137">Get the different out-of-box Microsoft Azure environments</span></span>
  - <span data-ttu-id="509b6-138">Hinzufügen/Einrichten/Entfernen angepasster Umgebungen (z.B. Ihrer Azure Stack- oder Windows Azure Pack-Umgebungen)</span><span class="sxs-lookup"><span data-stu-id="509b6-138">Add/Set/Remove customized environments (like your Azure Stack or Windows Azure Pack environments)</span></span>
* <span data-ttu-id="509b6-139">Cmdlets auf Verwaltungsebene für Azure-Dienste, die Resource Manager- und Service Management-Schnittstellen nutzen.</span><span class="sxs-lookup"><span data-stu-id="509b6-139">Management plane cmdlets for Azure services using Resource Manager and Service Management interfaces.</span></span>
  - <span data-ttu-id="509b6-140">Virtual Machine</span><span class="sxs-lookup"><span data-stu-id="509b6-140">Virtual Machine</span></span>
  - <span data-ttu-id="509b6-141">App Service (Websites)</span><span class="sxs-lookup"><span data-stu-id="509b6-141">App Service (Websites)</span></span>
  - <span data-ttu-id="509b6-142">SQL-Datenbank</span><span class="sxs-lookup"><span data-stu-id="509b6-142">SQL Database</span></span>
  - <span data-ttu-id="509b6-143">Speicher</span><span class="sxs-lookup"><span data-stu-id="509b6-143">Storage</span></span>
  - <span data-ttu-id="509b6-144">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="509b6-144">Network</span></span>

## <a name="next-steps"></a><span data-ttu-id="509b6-145">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="509b6-145">Next Steps</span></span>

<span data-ttu-id="509b6-146">Weitere Informationen zur Verwendung von Azure PowerShell finden Sie im Artikel [Erste Schritte mit Azure PowerShell](get-started-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="509b6-146">For more information about using Azure PowerShell, see the [Get started with Azure PowerShell](get-started-azureps.md) article.</span></span>
