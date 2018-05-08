---
title: Installieren und Konfigurieren von Azure PowerShell | Microsoft-Dokumentation
description: Hier erfahren Sie, wie Sie Azure PowerShell für die erste Verwendung installieren und konfigurieren.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/27/2018
ms.openlocfilehash: 993c9570b7fe81e5be68b8d82943f2135aed2337
ms.sourcegitcommit: 8376e0bc5f862d382d7283ba72990e3707591e7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2018
---
# <a name="install-and-configure-azure-powershell"></a><span data-ttu-id="073ed-103">Installieren und Konfigurieren von Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="073ed-103">Install and configure Azure PowerShell</span></span>

<span data-ttu-id="073ed-104">Die Installation von Azure PowerShell aus dem PowerShell-Katalog ist die bevorzugte Installationsmethode.</span><span class="sxs-lookup"><span data-stu-id="073ed-104">Installing Azure PowerShell from the PowerShell Gallery is the preferred method of installation.</span></span>

## <a name="step-1-install-powershellget"></a><span data-ttu-id="073ed-105">Schritt 1: Installieren von PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="073ed-105">Step 1: Install PowerShellGet</span></span>

<span data-ttu-id="073ed-106">Für die Installation von Komponenten aus dem PowerShell-Katalog ist das PowerShellGet-Modul erforderlich.</span><span class="sxs-lookup"><span data-stu-id="073ed-106">Installing items from the PowerShell Gallery requires the PowerShellGet module.</span></span> <span data-ttu-id="073ed-107">Stellen Sie sicher, dass Sie über die entsprechende Version von PowerShellGet verfügen und alle anderen Systemanforderungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="073ed-107">Make sure you have the appropriate version of PowerShellGet and other system requirements.</span></span> <span data-ttu-id="073ed-108">Führen Sie den folgenden Befehl aus, um zu ermitteln, ob PowerShellGet auf Ihrem System installiert ist.</span><span class="sxs-lookup"><span data-stu-id="073ed-108">Run the following command to see if you have PowerShellGet installed on your system.</span></span>

```powershell
Get-Module -Name PowerShellGet -ListAvailable | Select-Object -Property Name,Version,Path
```

<span data-ttu-id="073ed-109">Etwa folgende Ausgabe sollte angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="073ed-109">You should see something similar to the following output:</span></span>

```Output
Name          Version Path
----          ------- ----
Name          Version Path
----          ------- ----
PowerShellGet 1.6.0   C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.6.0\PowerShellGet.psd1
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

<span data-ttu-id="073ed-110">Sie benötigen mindestens die PowerShellGet-Version 1.1.2.0.</span><span class="sxs-lookup"><span data-stu-id="073ed-110">You need PowerShellGet version 1.1.2.0 or higher.</span></span> <span data-ttu-id="073ed-111">Verwenden Sie zum Aktualisieren von PowerShellGet den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="073ed-111">To update PowerShellGet, use the following command:</span></span>

```powershell
Install-Module PowerShellGet -Force
```

<span data-ttu-id="073ed-112">Falls PowerShellGet nicht installiert ist, lesen Sie die Informationen im Abschnitt [Installieren von PowerShellGet](#how-to-get-powershellget) dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="073ed-112">If you do not have PowerShellGet installed, see the [How to get PowerShellGet](#how-to-get-powershellget) section of this article.</span></span>

> [!NOTE]
> <span data-ttu-id="073ed-113">Für die Verwendung von PowerShellGet ist eine Ausführungsrichtlinie erforderlich, die die Ausführung von Skripts ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="073ed-113">Using PowerShellGet requires an Execution Policy that allows you to run scripts.</span></span> <span data-ttu-id="073ed-114">Weitere Informationen zur Ausführungsrichtlinie von PowerShell finden Sie unter [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies) (Informationen zu Ausführungsrichtlinien).</span><span class="sxs-lookup"><span data-stu-id="073ed-114">For more information about PowerShell's Execution Policy, see [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>

## <a name="step-2-install-azure-powershell"></a><span data-ttu-id="073ed-115">Schritt 2: Installieren von Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="073ed-115">Step 2: Install Azure PowerShell</span></span>

<span data-ttu-id="073ed-116">Für die Installation von Azure PowerShell aus dem PowerShell-Katalog sind erhöhte Rechte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="073ed-116">Installing Azure PowerShell from the PowerShell Gallery requires elevated privileges.</span></span> <span data-ttu-id="073ed-117">Führen Sie den folgenden Befehl in einer PowerShell-Sitzung mit erhöhten Rechten aus:</span><span class="sxs-lookup"><span data-stu-id="073ed-117">Run the following command from an elevated PowerShell session:</span></span>

```powershell
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module -Name AzureRM -AllowClobber
```

<span data-ttu-id="073ed-118">Standardmäßig ist der PowerShell-Katalog nicht als vertrauenswürdiges Repository für PowerShellGet konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="073ed-118">By default, the PowerShell gallery is not configured as a Trusted repository for PowerShellGet.</span></span> <span data-ttu-id="073ed-119">Bei der ersten Verwendung des PowerShell-Katalogs wird die folgende Meldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="073ed-119">The first time you use the PSGallery you see the following prompt:</span></span>

```Output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): Y
```

<span data-ttu-id="073ed-120">Antworten Sie mit „Ja“ oder „Ja zu allen“, um die Installation fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="073ed-120">Answer 'Yes' or 'Yes to All' to continue with the installation.</span></span>

> [!NOTE]
> <span data-ttu-id="073ed-121">Wenn Sie eine ältere NuGet-Version als 2.8.5.201 haben, werden Sie aufgefordert, die aktuelle NuGet-Version herunterzuladen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="073ed-121">If you have a version older than 2.8.5.201 of NuGet, you are prompted to download and install the latest version of NuGet.</span></span>

<span data-ttu-id="073ed-122">Das AzureRM-Modul ist ein Rollupmodul für die Azure Resource Manager-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="073ed-122">The AzureRM module is a rollup module for the Azure Resource Manager cmdlets.</span></span> <span data-ttu-id="073ed-123">Bei der Installation des AzureRM-Moduls werden alle noch nicht installierten Azure PowerShell-Module aus dem PowerShell-Katalog heruntergeladen und installiert.</span><span class="sxs-lookup"><span data-stu-id="073ed-123">When you install the AzureRM module, any Azure PowerShell module not previously installed is downloaded and from the PowerShell Gallery.</span></span>

<span data-ttu-id="073ed-124">Wenn eine frühere Version von Azure PowerShell installiert ist, erhalten Sie möglicherweise eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="073ed-124">If you have a previous version of Azure PowerShell installed you may receive an error.</span></span> <span data-ttu-id="073ed-125">Informationen zum Beheben dieses Problem finden Sie im Abschnitt [Aktualisieren auf eine neue Version von Azure PowerShell](#update-azps) dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="073ed-125">To resolve this issue, see the [Updating to a new version of Azure PowerShell](#update-azps) section of this article.</span></span>

## <a name="step-3-load-the-azurerm-module"></a><span data-ttu-id="073ed-126">Schritt 3: Laden des AzureRM-Moduls</span><span class="sxs-lookup"><span data-stu-id="073ed-126">Step 3: Load the AzureRM module</span></span>
<span data-ttu-id="073ed-127">Nach der Installation des Moduls müssen Sie das Modul in der PowerShell-Sitzung laden.</span><span class="sxs-lookup"><span data-stu-id="073ed-127">Once the module is installed, you need to load the module into your PowerShell session.</span></span> <span data-ttu-id="073ed-128">Dies muss in einer normalen PowerShell-Sitzung (ohne erhöhte Rechte) erfolgen.</span><span class="sxs-lookup"><span data-stu-id="073ed-128">You should do this in a normal (non-elevated) PowerShell session.</span></span> <span data-ttu-id="073ed-129">Module werden wie folgt mit dem Cmdlet `Import-Module` geladen:</span><span class="sxs-lookup"><span data-stu-id="073ed-129">Modules are loaded using the `Import-Module` cmdlet, as follows:</span></span>

```powershell
Import-Module -Name AzureRM
```

## <a name="next-steps"></a><span data-ttu-id="073ed-130">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="073ed-130">Next Steps</span></span>

<span data-ttu-id="073ed-131">Weitere Informationen zur Verwendung von Azure PowerShell finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="073ed-131">For more information about using Azure PowerShell, see the following articles:</span></span>

* [<span data-ttu-id="073ed-132">Erste Schritte mit Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="073ed-132">Get started with Azure PowerShell</span></span>](get-started-azureps.md)

## <a name="frequently-asked-questions"></a><span data-ttu-id="073ed-133">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="073ed-133">Frequently asked questions</span></span>

### <a name="how-to-get-powershellget"></a><span data-ttu-id="073ed-134">Installieren von PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="073ed-134">How to get PowerShellGet</span></span>

|<span data-ttu-id="073ed-135">Betriebssystemversion</span><span class="sxs-lookup"><span data-stu-id="073ed-135">OS Version</span></span>|<span data-ttu-id="073ed-136">Installationsanleitung</span><span class="sxs-lookup"><span data-stu-id="073ed-136">Install instructions</span></span>|
|---|---|
|<span data-ttu-id="073ed-137">Ich besitze Windows 10 oder Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="073ed-137">I have Windows 10 or Windows Server 2016</span></span>|<span data-ttu-id="073ed-138">In Windows Management Framework (WMF) 5.0 integriert (im Betriebssystem enthalten)</span><span class="sxs-lookup"><span data-stu-id="073ed-138">Built into Windows Management Framework (WMF) 5.0 included in the OS</span></span>|
|<span data-ttu-id="073ed-139">Ich möchte auf PowerShell 5 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="073ed-139">I want to upgrade to PowerShell 5</span></span>|[<span data-ttu-id="073ed-140">Installieren Sie die aktuelle Version von WMF.</span><span class="sxs-lookup"><span data-stu-id="073ed-140">Install the latest version of WMF</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54616)|
|<span data-ttu-id="073ed-141">Ich nutze eine Windows-Version mit PowerShell 3 oder PowerShell 4.</span><span class="sxs-lookup"><span data-stu-id="073ed-141">I am running on a version of Windows with PowerShell 3 or PowerShell 4</span></span>|[<span data-ttu-id="073ed-142">Laden Sie die PackageManagement-Module herunter.</span><span class="sxs-lookup"><span data-stu-id="073ed-142">Get the PackageManagement modules</span></span>](http://go.microsoft.com/fwlink/?LinkID=746217)|

<a id="helpmechoose"></a>
### <a name="checking-the-version-of-azure-powershell"></a><span data-ttu-id="073ed-143">Überprüfen der Azure PowerShell-Version</span><span class="sxs-lookup"><span data-stu-id="073ed-143">Checking the version of Azure PowerShell</span></span>

<span data-ttu-id="073ed-144">Obwohl empfohlen wird, möglichst bald ein Upgrade auf die neueste Version auszuführen, werden verschiedene Azure PowerShell-Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="073ed-144">Although we encourage you to upgrade to the latest version as early as possible, several versions of Azure PowerShell are supported.</span></span> <span data-ttu-id="073ed-145">Führen Sie zum Ermitteln der installierten Azure PowerShell-Version `Get-Module AzureRM` in der Befehlszeile aus:</span><span class="sxs-lookup"><span data-stu-id="073ed-145">To determine the version of Azure PowerShell you have installed, run `Get-Module AzureRM` from your command line.</span></span>

```powershell
Get-Module AzureRM -ListAvailable | Select-Object -Property Name,Version,Path
```

### <a name="support-for-classic-deployment-methods"></a><span data-ttu-id="073ed-146">Unterstützung für klassische Bereitstellungsmethoden</span><span class="sxs-lookup"><span data-stu-id="073ed-146">Support for classic deployment methods</span></span>

<span data-ttu-id="073ed-147">Bei Bereitstellungen mit dem klassischen Bereitstellungsmodell können Sie die Dienstverwaltungsversion von Azure PowerShell installieren.</span><span class="sxs-lookup"><span data-stu-id="073ed-147">If you have deployments that use the classic deployment model you can install the Service Management version of Azure PowerShell.</span></span> <span data-ttu-id="073ed-148">Weitere Informationen finden Sie unter [Installing the Azure PowerShell Service Management module](/powershell/azure/servicemanagement/install-azure-ps) (Installieren des Azure PowerShell-Dienstverwaltungsmoduls).</span><span class="sxs-lookup"><span data-stu-id="073ed-148">For more information, see [Install the Azure PowerShell Service Management module](/powershell/azure/servicemanagement/install-azure-ps).</span></span> <span data-ttu-id="073ed-149">Das Azure- und das AzureRM-Modul nutzen gemeinsame Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="073ed-149">The Azure and AzureRM modules share common dependencies.</span></span> <span data-ttu-id="073ed-150">Wenn Sie sowohl die Azure- als auch die AzureRM-Module verwenden, müssen Sie die gleiche Version der einzelnen Pakete installieren.</span><span class="sxs-lookup"><span data-stu-id="073ed-150">If you use both the Azure and AzureRM modules, you should install the same version of each package.</span></span>

### <a id="update-azps"></a><span data-ttu-id="073ed-151">Aktualisieren auf eine neue Version von Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="073ed-151">Updating to a new version of Azure PowerShell</span></span>

<span data-ttu-id="073ed-152">Wenn Sie eine frühere Version von Azure PowerShell installiert haben, die das Dienstverwaltungsmodul enthält, kann die folgende Fehlermeldung angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="073ed-152">If you have a previous version of Azure PowerShell installed that includes the Service Management module, you may receive the following error:</span></span>

```Output
PackageManagement\Install-Package : A command with name 'Get-AzureStorageContainerAcl' is already
available on this system. This module 'Azure.Storage' may override the existing commands. If you
still want to install this module 'Azure.Storage', use -AllowClobber parameter.

At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PSModule.psm1:1772 char:21
+ ...          $null = PackageManagement\Install-Package @PSBoundParameters
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (Microsoft.Power....InstallPackage:InstallPackage) [Install-Package], Exception
    + FullyQualifiedErrorId : CommandAlreadyAvailable,Validate-ModuleCommandAlreadyAvailable,Microsoft.PowerShell.PackageManagement.Cmdlets.InstallPackage
```

<span data-ttu-id="073ed-153">Wie in der Fehlermeldung angegeben, müssen Sie den Parameter „-AllowClobber“ zum Installieren des Moduls verwenden.</span><span class="sxs-lookup"><span data-stu-id="073ed-153">As the error message states, you need to use the -AllowClobber parameter to install the module.</span></span> <span data-ttu-id="073ed-154">Verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="073ed-154">Use the following command:</span></span>

```powershell
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module -Name AzureRM -AllowClobber
```

<span data-ttu-id="073ed-155">Weitere Informationen finden Sie im Hilfethema zu [Install-Module](https://msdn.microsoft.com/powershell/reference/5.1/PowerShellGet/install-module).</span><span class="sxs-lookup"><span data-stu-id="073ed-155">For more information, see the help topic for [Install-Module](https://msdn.microsoft.com/powershell/reference/5.1/PowerShellGet/install-module).</span></span>

### <a name="installing-module-versions-side-by-side"></a><span data-ttu-id="073ed-156">Parallele Installation von Modulversionen</span><span class="sxs-lookup"><span data-stu-id="073ed-156">Installing module versions side by side</span></span>

<span data-ttu-id="073ed-157">Die PowerShellGet-Installationsmethode ist die einzige Methode, die die Installation mehrerer Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="073ed-157">The PowerShellGet method of installation is the only method that supports the installation of multiple versions.</span></span> <span data-ttu-id="073ed-158">Beispiel: Sie besitzen Skripts, die mit einer vorherigen Version von Azure PowerShell geschrieben wurden, für deren Aktualisierung keine Zeit ist bzw. keine Ressourcen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="073ed-158">For example, you may have scripts written using a previous version of Azure PowerShell that you don't have the time or resources to updated.</span></span> <span data-ttu-id="073ed-159">Die folgenden Befehle veranschaulichen, wie mehrere Versionen von Azure PowerShell installiert werden:</span><span class="sxs-lookup"><span data-stu-id="073ed-159">The following commands illustrate how to install multiple versions of Azure PowerShell:</span></span>

```powershell
Install-Module -Name AzureRM -RequiredVersion 3.7.0
Install-Module -Name AzureRM -RequiredVersion 1.2.9
```

<span data-ttu-id="073ed-160">Nur eine Version des Moduls kann in einer PowerShell-Sitzung geladen werden.</span><span class="sxs-lookup"><span data-stu-id="073ed-160">Only one version of the module can be loaded in a PowerShell session.</span></span> <span data-ttu-id="073ed-161">Sie müssen ein neues PowerShell-Fenster öffnen und `Import-Module` verwenden, um eine bestimmte Version der AzureRM-Cmdlets zu importieren:</span><span class="sxs-lookup"><span data-stu-id="073ed-161">You must open a new PowerShell window and use `Import-Module` to import a specific version of the AzureRM cmdlets:</span></span>

```powershell
Import-Module -Name AzureRM -RequiredVersion 1.2.9
```

> [!NOTE]
> <span data-ttu-id="073ed-162">Version 2.1.0 und Version 1.2.6 sind die ersten Modulversionen, die parallel installiert und genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="073ed-162">Version 2.1.0 and version 1.2.6 are the first module versions designed to be installed and used side by side.</span></span> <span data-ttu-id="073ed-163">Beim Laden einer früheren Version von Azure PowerShell werden inkompatible Versionen des **AzureRM.Profile**-Moduls geladen.</span><span class="sxs-lookup"><span data-stu-id="073ed-163">When loading an earlier version of the Azure PowerShell, incompatible versions of the **AzureRM.Profile** module are loaded.</span></span> <span data-ttu-id="073ed-164">Dies führt dazu, dass Sie, immer wenn Sie ein Cmdlet ausführen, zum Anmelden aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="073ed-164">This results in the cmdlets prompting you to log in whenever you execute a cmdlet.</span></span>

### <a name="other-installation-methods"></a><span data-ttu-id="073ed-165">Andere Installationsmethoden</span><span class="sxs-lookup"><span data-stu-id="073ed-165">Other installation methods</span></span>

<span data-ttu-id="073ed-166">Information zum Installieren des Webplattform-Installers oder des MSI-Pakets finden Sie unter [Other installation methods](other-install.md) (Andere Installationsmethoden).</span><span class="sxs-lookup"><span data-stu-id="073ed-166">For information about installing using the Web Platform Installer or the MSI Package, see [Other installation methods](other-install.md)</span></span>
