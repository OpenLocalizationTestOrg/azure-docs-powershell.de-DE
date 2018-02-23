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
ms.date: 01/12/2018
ms.openlocfilehash: 64a86dfd4af7f3f0a91501e9a096ff190f7100cb
ms.sourcegitcommit: 7e77fe7ecd2112d6b4515517509c5c723e750e27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="install-and-configure-azure-powershell-on-macos-and-linux"></a><span data-ttu-id="1eade-103">Installieren und Konfigurieren von Azure PowerShell unter macOS und Linux</span><span class="sxs-lookup"><span data-stu-id="1eade-103">Install and configure Azure PowerShell on macOS and Linux</span></span>

<span data-ttu-id="1eade-104">PowerShell Core v6 und Azure PowerShell können jetzt auf Windows-fremden Plattformen installiert werden.</span><span class="sxs-lookup"><span data-stu-id="1eade-104">It is now possible to install PowerShell Core v6 and Azure PowerShell on non-Windows platforms.</span></span>
<span data-ttu-id="1eade-105">Die Installation von Azure PowerShell unter macOS und Linux unterscheidet sich nicht sehr von der Installation unter Windows, allerdings müssen Sie zuerst PowerShell Core v6 installieren.</span><span class="sxs-lookup"><span data-stu-id="1eade-105">The process of installing Azure PowerShell on macOS and Linux is not that different from Windows, however, you must first install PowerShell Core v6.</span></span>

> [!NOTE]

> <span data-ttu-id="1eade-106">PowerShell Core v6 und Azure PowerShell für .NET Core befinden sich derzeit noch in der Betaphase.</span><span class="sxs-lookup"><span data-stu-id="1eade-106">At this time, both PowerShell Core v6 and Azure PowerShell for .NET Core are still in beta.</span></span>
> <span data-ttu-id="1eade-107">Der Support für diese Produkte ist eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="1eade-107">Support for these products is limited.</span></span> <span data-ttu-id="1eade-108">Wenn Sie Probleme haben oder Fehler erkennen, melden Sie dies bitte in GitHub.</span><span class="sxs-lookup"><span data-stu-id="1eade-108">If you have problems or discover bugs, please file Issues in GitHub.</span></span>
>
> * [<span data-ttu-id="1eade-109">Probleme mit PowerShell Core v6</span><span class="sxs-lookup"><span data-stu-id="1eade-109">Issues for PowerShell Core v6</span></span>](https://github.com/PowerShell/PowerShell/issues)
> * [<span data-ttu-id="1eade-110">Probleme mit Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="1eade-110">Issues for Azure PowerShell</span></span>](https://github.com/azure/azure-docs-powershell/issues)

## <a name="step-1-install-powershell-core-v6"></a><span data-ttu-id="1eade-111">Schritt 1: Installieren von PowerShell Core v6</span><span class="sxs-lookup"><span data-stu-id="1eade-111">Step 1: Install PowerShell Core v6</span></span>

<span data-ttu-id="1eade-112">Die Installation von PowerShell Core v6 variiert je nach Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="1eade-112">The process of installing PowerShell Core v6 on varies depending on the target operating system.</span></span>
<span data-ttu-id="1eade-113">PowerShell Core v6 kann zwar auch unter Windows installiert werden, in diesem Artikel wird jedoch die Installation unter macOS und Linux behandelt.</span><span class="sxs-lookup"><span data-stu-id="1eade-113">While it is possible to install PowerShell Core v6 on Windows, this article focuses on macOS and Linux.</span></span> <span data-ttu-id="1eade-114">Wenn Sie Azure PowerShell unter Windows verwenden möchten, lesen Sie den Artikel [Installieren und Konfigurieren von Azure PowerShell](./install-azurerm-ps.md) für Windows.</span><span class="sxs-lookup"><span data-stu-id="1eade-114">If you want to use Azure PowerShell on Windows, see the [install](./install-azurerm-ps.md) article for Windows.</span></span>

<span data-ttu-id="1eade-115">Die Installation von **PowerShell Core v6** unter Linux oder macOS variiert je nach Linux-Distribution und Betriebssystemversion.</span><span class="sxs-lookup"><span data-stu-id="1eade-115">Installing **PowerShell Core v6** on Linux or macOS varies depending on the Linux distribution and OS version.</span></span>
<span data-ttu-id="1eade-116">Eine ausführliche Anleitung finden Sie im folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="1eade-116">Detailed instructions can be found in the following article:</span></span>

- [<span data-ttu-id="1eade-117">Installieren von PowerShell Core unter macOS und Linux</span><span class="sxs-lookup"><span data-stu-id="1eade-117">Installing PowerShell Core on macOS and Linux</span></span>](/powershell/scripting/setup/installing-powershell-core-on-macos-and-linux)

## <a name="step-2-install-azure-powershell-for-net-core"></a><span data-ttu-id="1eade-118">Schritt 2: Installieren von Azure PowerShell für .NET Core</span><span class="sxs-lookup"><span data-stu-id="1eade-118">Step 2: Install Azure PowerShell for .NET Core</span></span>

<span data-ttu-id="1eade-119">In PowerShell Core v6 ist das PowerShellGet-Modul bereits vorinstalliert.</span><span class="sxs-lookup"><span data-stu-id="1eade-119">PowerShell Core v6 comes with the PowerShellGet module already installed.</span></span> <span data-ttu-id="1eade-120">Dies vereinfacht die Installation eines beliebigen, im PowerShell-Katalog veröffentlichten Moduls.</span><span class="sxs-lookup"><span data-stu-id="1eade-120">This makes it easy to install any module that is published to the PowerShell Gallery.</span></span> <span data-ttu-id="1eade-121">Um Azure PowerShell zu installieren, öffnen Sie eine neue PowerShell-Sitzung, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="1eade-121">To install Azure PowerShell, open a new PowerShell session and run the following command:</span></span>

```powershell
Install-Module AzureRM.NetCore
```

## <a name="step-3-load-the-azurermnetcore-module"></a><span data-ttu-id="1eade-122">Schritt 3: Laden des AzureRM.Netcore-Moduls</span><span class="sxs-lookup"><span data-stu-id="1eade-122">Step 3: Load the AzureRM.Netcore module</span></span>

<span data-ttu-id="1eade-123">Nach der Installation des Moduls müssen Sie das Modul in der PowerShell-Sitzung laden.</span><span class="sxs-lookup"><span data-stu-id="1eade-123">Once the module is installed, you need to load the module into your PowerShell session.</span></span> <span data-ttu-id="1eade-124">Module werden wie folgt mit dem Cmdlet `Import-Module` geladen:</span><span class="sxs-lookup"><span data-stu-id="1eade-124">Modules are loaded using the `Import-Module` cmdlet, as follows:</span></span>

```powershell
Import-Module AzureRM.Netcore
Import-Module AzureRM.Profile.Netcore
```

<span data-ttu-id="1eade-125">Nach Abschluss des Imports können Sie das neu installierte Modul testen, indem Sie versuchen, sich mithilfe des folgenden Befehls bei Azure anzumelden:</span><span class="sxs-lookup"><span data-stu-id="1eade-125">After the import completes, you can test your newly installed and module by attempting to sign into Azure using the following command:</span></span>

```powershell
Login-AzureRMAccount
```

<span data-ttu-id="1eade-126">Der obige Befehl sollte Sie auffordern, zu `https://aka.ms/devicelogin` zu wechseln und den bereitgestellten Code einzugeben.</span><span class="sxs-lookup"><span data-stu-id="1eade-126">The above command should prompt you to go to `https://aka.ms/devicelogin` and enter the provided code.</span></span>

## <a name="available-cmdlets"></a><span data-ttu-id="1eade-127">Verfügbare Cmdlets</span><span class="sxs-lookup"><span data-stu-id="1eade-127">Available cmdlets</span></span>

<span data-ttu-id="1eade-128">Die Azure PowerShell-Module für .NET Standard sind immer noch in der Entwicklungsphase.</span><span class="sxs-lookup"><span data-stu-id="1eade-128">The Azure PowerShell modules for .NET Standard are still in development.</span></span> <span data-ttu-id="1eade-129">Diese Module bieten nicht den vollständigen Satz der Cmdlets, die für die Windows-Version der Module verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1eade-129">These modules do not provide the full set of cmdlets that are available for the Windows version of the modules.</span></span> <span data-ttu-id="1eade-130">Die folgenden Funktionen werden in AzureRM.Netcore-Module implementiert:</span><span class="sxs-lookup"><span data-stu-id="1eade-130">The following functions are implemented in AzureRM.Netcore modules:</span></span>

* <span data-ttu-id="1eade-131">Kontenverwaltung</span><span class="sxs-lookup"><span data-stu-id="1eade-131">Account management</span></span>
  - <span data-ttu-id="1eade-132">Melden Sie sich mit dem Microsoft-Konto, Unternehmenskonto oder einem Dienstprinzipal über Microsoft Azure Active Directory an.</span><span class="sxs-lookup"><span data-stu-id="1eade-132">Login with Microsoft account, Organizational account, or Service Principal through Microsoft Azure Active Directory</span></span>
  - <span data-ttu-id="1eade-133">Speichern Sie die Anmeldeinformationen mit Save-AzureRmContext auf einem Datenträger, und laden Sie gespeicherte Anmeldeinformationen mit Import-AzureRmContext.</span><span class="sxs-lookup"><span data-stu-id="1eade-133">Save Credentials to disk with Save-AzureRmContext and load saved credentials using Import-AzureRmContext</span></span>
* <span data-ttu-id="1eade-134">Environment</span><span class="sxs-lookup"><span data-stu-id="1eade-134">Environment</span></span>
  - <span data-ttu-id="1eade-135">Abrufen der verschiedenen vorkonfigurierten Microsoft Azure-Umgebungen</span><span class="sxs-lookup"><span data-stu-id="1eade-135">Get the different out-of-box Microsoft Azure environments</span></span>
  - <span data-ttu-id="1eade-136">Hinzufügen/Einrichten/Entfernen angepasster Umgebungen (z.B. Ihrer Azure Stack- oder Windows Azure Pack-Umgebungen)</span><span class="sxs-lookup"><span data-stu-id="1eade-136">Add/Set/Remove customized environments (like your Azure Stack or Windows Azure Pack environments)</span></span>
* <span data-ttu-id="1eade-137">Cmdlets auf Verwaltungsebene für Azure-Dienste, die Resource Manager- und Service Management-Schnittstellen nutzen.</span><span class="sxs-lookup"><span data-stu-id="1eade-137">Management plane cmdlets for Azure services using Resource Manager and Service Management interfaces.</span></span>
  - <span data-ttu-id="1eade-138">Virtual Machine</span><span class="sxs-lookup"><span data-stu-id="1eade-138">Virtual Machine</span></span>
  - <span data-ttu-id="1eade-139">App Service (Websites)</span><span class="sxs-lookup"><span data-stu-id="1eade-139">App Service (Websites)</span></span>
  - <span data-ttu-id="1eade-140">SQL-Datenbank</span><span class="sxs-lookup"><span data-stu-id="1eade-140">SQL Database</span></span>
  - <span data-ttu-id="1eade-141">Speicher</span><span class="sxs-lookup"><span data-stu-id="1eade-141">Storage</span></span>
  - <span data-ttu-id="1eade-142">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="1eade-142">Network</span></span>

## <a name="next-steps"></a><span data-ttu-id="1eade-143">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1eade-143">Next Steps</span></span>

<span data-ttu-id="1eade-144">Weitere Informationen zur Verwendung von Azure PowerShell finden Sie im Artikel [Erste Schritte mit Azure PowerShell](get-started-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="1eade-144">For more information about using Azure PowerShell, see the [Get started with Azure PowerShell](get-started-azureps.md) article.</span></span>
