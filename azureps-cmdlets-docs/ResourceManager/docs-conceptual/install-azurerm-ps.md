---
title: Installieren und Konfigurieren von Azure PowerShell | Microsoft-Dokumentation
description: "Hier erfahren Sie, wie Sie Azure PowerShell für die erste Verwendung installieren und konfigurieren."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/17/2017
ms.openlocfilehash: 62572780a2e713ea0a53a670cfd548a7badd2d98
ms.sourcegitcommit: 020066d68d4ab68da162a4ae0cb4e239241f950f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2017
---
# <a name="install-and-configure-azure-powershell"></a><span data-ttu-id="7f6e9-103">Installieren und Konfigurieren von Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f6e9-103">Install and configure Azure PowerShell</span></span>

<span data-ttu-id="7f6e9-104">Die Installation von Azure PowerShell aus dem PowerShell-Katalog ist die bevorzugte Installationsmethode.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-104">Installing Azure PowerShell from the PowerShell Gallery is the preferred method of installation.</span></span>

## <a name="step-1-install-powershellget"></a><span data-ttu-id="7f6e9-105">Schritt 1: Installieren von PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="7f6e9-105">Step 1: Install PowerShellGet</span></span>

<span data-ttu-id="7f6e9-106">Für die Installation von Komponenten aus dem PowerShell-Katalog ist das PowerShellGet-Modul erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-106">Installing items from the PowerShell Gallery requires the PowerShellGet module.</span></span> <span data-ttu-id="7f6e9-107">Stellen Sie sicher, dass Sie über die entsprechende Version von PowerShellGet verfügen und alle anderen Systemanforderungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-107">Make sure you have the appropriate version of PowerShellGet and other system requirements.</span></span> <span data-ttu-id="7f6e9-108">Führen Sie den folgenden Befehl aus, um zu ermitteln, ob PowerShellGet auf Ihrem System installiert ist.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-108">Run the following command to see if you have PowerShellGet installed on your system.</span></span>

```powershell
Get-Module PowerShellGet -list | Select-Object Name,Version,Path
```

<span data-ttu-id="7f6e9-109">Etwa folgende Ausgabe sollte angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="7f6e9-109">You should see something similar to the following output:</span></span>

```
Name          Version Path
----          ------- ----
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

<span data-ttu-id="7f6e9-110">Falls PowerShellGet nicht installiert ist, lesen Sie die Informationen im Abschnitt [Installieren von PowerShellGet](#how-to-get-powershellget) dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-110">If you do not have PowerShellGet installed, see the [How to get PowerShellGet](#how-to-get-powershellget) section of this article.</span></span>

> [!NOTE]
> <span data-ttu-id="7f6e9-111">Für die Verwendung von PowerShellGet ist eine Ausführungsrichtlinie erforderlich, die die Ausführung von Skripts ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-111">Using PowerShellGet requires an Execution Policy that allows you to run scripts.</span></span> <span data-ttu-id="7f6e9-112">Weitere Informationen zur Ausführungsrichtlinie von PowerShell finden Sie unter [About Execution Policies](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/about/about_execution_policies) (Informationen zu Ausführungsrichtlinien).</span><span class="sxs-lookup"><span data-stu-id="7f6e9-112">For more information about PowerShell's Execution Policy, see [About Execution Policies](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/about/about_execution_policies).</span></span>

## <a name="step-2-install-azure-powershell"></a><span data-ttu-id="7f6e9-113">Schritt 2: Installieren von Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f6e9-113">Step 2: Install Azure PowerShell</span></span>

<span data-ttu-id="7f6e9-114">Für die Installation von Azure PowerShell aus dem PowerShell-Katalog sind erhöhte Rechte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-114">Installing Azure PowerShell from the PowerShell Gallery requires elevated privileges.</span></span> <span data-ttu-id="7f6e9-115">Führen Sie den folgenden Befehl in einer PowerShell-Sitzung mit erhöhten Rechten aus:</span><span class="sxs-lookup"><span data-stu-id="7f6e9-115">Run the following command from an elevated PowerShell session:</span></span>

```powershell
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module AzureRM
```

<span data-ttu-id="7f6e9-116">Standardmäßig ist der PowerShell-Katalog nicht als vertrauenswürdiges Repository für PowerShellGet konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-116">By default, the PowerShell gallery is not configured as a Trusted repository for PowerShellGet.</span></span> <span data-ttu-id="7f6e9-117">Bei der ersten Verwendung des PowerShell-Katalogs wird die folgende Meldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7f6e9-117">The first time you use the PSGallery you see the following prompt:</span></span>

```
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): Y
```

<span data-ttu-id="7f6e9-118">Antworten Sie mit „Ja“ oder „Ja zu allen“, um die Installation fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-118">Answer 'Yes' or 'Yes to All' to continue with the installation.</span></span>

> [!NOTE]
> <span data-ttu-id="7f6e9-119">Wenn Sie eine ältere NuGet-Version als 2.8.5.201 haben, werden Sie aufgefordert, die aktuelle NuGet-Version herunterzuladen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-119">If you have a version older than 2.8.5.201 of NuGet, you are prompted to download and install the latest version of NuGet.</span></span>

<span data-ttu-id="7f6e9-120">Das AzureRM-Modul ist ein Rollupmodul für die Azure Resource Manager-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-120">The AzureRM module is a rollup module for the Azure Resource Manager cmdlets.</span></span> <span data-ttu-id="7f6e9-121">Bei der Installation des AzureRM-Moduls werden alle noch nicht installierten Azure PowerShell-Module aus dem PowerShell-Katalog heruntergeladen und installiert.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-121">When you install the AzureRM module, any Azure PowerShell module not previously installed is downloaded and from the PowerShell Gallery.</span></span>

<span data-ttu-id="7f6e9-122">Wenn eine frühere Version von Azure PowerShell installiert ist, erhalten Sie möglicherweise eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-122">If you have a previous version of Azure PowerShell installed you may receive an error.</span></span> <span data-ttu-id="7f6e9-123">Informationen zum Beheben dieses Problem finden Sie im Abschnitt [Aktualisieren auf eine neue Version von Azure PowerShell](#update-azps) dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-123">To resolve this issue, see the [Updating to a new version of Azure PowerShell](#update-azps) section of this article.</span></span>

## <a name="step-3-load-the-azurerm-module"></a><span data-ttu-id="7f6e9-124">Schritt 3: Laden des AzureRM-Moduls</span><span class="sxs-lookup"><span data-stu-id="7f6e9-124">Step 3: Load the AzureRM module</span></span>
<span data-ttu-id="7f6e9-125">Nach der Installation des Moduls müssen Sie das Modul in der PowerShell-Sitzung laden.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-125">Once the module is installed, you need to load the module into your PowerShell session.</span></span> <span data-ttu-id="7f6e9-126">Dies muss in einer normalen PowerShell-Sitzung (ohne erhöhte Rechte) erfolgen.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-126">You should do this in a normal (non-elevated) PowerShell session.</span></span> <span data-ttu-id="7f6e9-127">Module werden wie folgt mit dem Cmdlet `Import-Module` geladen:</span><span class="sxs-lookup"><span data-stu-id="7f6e9-127">Modules are loaded using the `Import-Module` cmdlet, as follows:</span></span>

```powershell
Import-Module AzureRM
```

## <a name="next-steps"></a><span data-ttu-id="7f6e9-128">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7f6e9-128">Next Steps</span></span>

<span data-ttu-id="7f6e9-129">Weitere Informationen zur Verwendung von Azure PowerShell finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="7f6e9-129">For more information about using Azure PowerShell, see the following articles:</span></span>

* [<span data-ttu-id="7f6e9-130">Erste Schritte mit Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f6e9-130">Get started with Azure PowerShell</span></span>](get-started-azureps.md)

## <a name="reporting-issues-and-feedback"></a><span data-ttu-id="7f6e9-131">Melden von Problemen und Bereitstellen von Feedback</span><span class="sxs-lookup"><span data-stu-id="7f6e9-131">Reporting issues and feedback</span></span>

<span data-ttu-id="7f6e9-132">Wenn mit dem Tool Fehler auftreten, legen Sie einen Eintrag im Bereich [Probleme](https://github.com/Azure/azure-powershell/issues) unseres GitHub Repositorys an.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-132">If you encounter any bugs with the tool, file an issue in the [Issues](https://github.com/Azure/azure-powershell/issues) section of our GitHub repo.</span></span> <span data-ttu-id="7f6e9-133">Zum Senden von Feedback zur Befehlszeile verwenden Sie das Cmdlet `Send-Feedback`.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-133">To provide feedback from the command line, use the `Send-Feedback` cmdlet.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="7f6e9-134">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="7f6e9-134">Frequently asked questions</span></span>

### <a name="how-to-get-powershellget"></a><span data-ttu-id="7f6e9-135">Installieren von PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="7f6e9-135">How to get PowerShellGet</span></span>

|<span data-ttu-id="7f6e9-136">Betriebssystemversion</span><span class="sxs-lookup"><span data-stu-id="7f6e9-136">OS Version</span></span>|<span data-ttu-id="7f6e9-137">Installationsanleitung</span><span class="sxs-lookup"><span data-stu-id="7f6e9-137">Install instructions</span></span>|
|---|---|
|<span data-ttu-id="7f6e9-138">Ich besitze Windows 10 oder Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-138">I have Windows 10 or Windows Server 2016</span></span>|<span data-ttu-id="7f6e9-139">In Windows Management Framework (WMF) 5.0 integriert (im Betriebssystem enthalten)</span><span class="sxs-lookup"><span data-stu-id="7f6e9-139">Built into Windows Management Framework (WMF) 5.0 included in the OS</span></span>|
|<span data-ttu-id="7f6e9-140">Ich möchte auf PowerShell 5 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-140">I want to upgrade to PowerShell 5</span></span>|[<span data-ttu-id="7f6e9-141">Installieren Sie die aktuelle Version von WMF.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-141">Install the latest version of WMF</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54616)|
|<span data-ttu-id="7f6e9-142">Ich nutze eine Windows-Version mit PowerShell 3 oder PowerShell 4.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-142">I am running on a version of Windows with PowerShell 3 or PowerShell 4</span></span>|[<span data-ttu-id="7f6e9-143">Laden Sie die PackageManagement-Module herunter.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-143">Get the PackageManagement modules</span></span>](http://go.microsoft.com/fwlink/?LinkID=746217)|

<a id="helpmechoose"></a>
### <a name="checking-the-version-of-azure-powershell"></a><span data-ttu-id="7f6e9-144">Überprüfen der Azure PowerShell-Version</span><span class="sxs-lookup"><span data-stu-id="7f6e9-144">Checking the version of Azure PowerShell</span></span>

<span data-ttu-id="7f6e9-145">Obwohl empfohlen wird, möglichst bald ein Upgrade auf die neueste Version auszuführen, werden verschiedene Azure PowerShell-Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-145">Although we encourage you to upgrade to the latest version as early as possible, several versions of Azure PowerShell are supported.</span></span> <span data-ttu-id="7f6e9-146">Führen Sie zum Ermitteln der installierten Azure PowerShell-Version `Get-Module AzureRM` in der Befehlszeile aus:</span><span class="sxs-lookup"><span data-stu-id="7f6e9-146">To determine the version of Azure PowerShell you have installed, run `Get-Module AzureRM` from your command line.</span></span>

```powershell
Get-Module AzureRM -list | Select-Object Name,Version,Path
```

### <a name="support-for-classic-deployment-methods"></a><span data-ttu-id="7f6e9-147">Unterstützung für klassische Bereitstellungsmethoden</span><span class="sxs-lookup"><span data-stu-id="7f6e9-147">Support for classic deployment methods</span></span>

<span data-ttu-id="7f6e9-148">Bei Bereitstellungen mit dem klassischen Bereitstellungsmodell können Sie die Dienstverwaltungsversion von Azure PowerShell installieren.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-148">If you have deployments that use the classic deployment model you can install the Service Management version of Azure PowerShell.</span></span> <span data-ttu-id="7f6e9-149">Weitere Informationen finden Sie unter [Installing the Azure PowerShell Service Management module](/powershell/azure/servicemanagement/install-azure-ps) (Installieren des Azure PowerShell-Dienstverwaltungsmoduls).</span><span class="sxs-lookup"><span data-stu-id="7f6e9-149">For more information, see [Install the Azure PowerShell Service Management module](/powershell/azure/servicemanagement/install-azure-ps).</span></span> <span data-ttu-id="7f6e9-150">Das Azure- und das AzureRM-Modul nutzen gemeinsame Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-150">The Azure and AzureRM modules share common dependencies.</span></span> <span data-ttu-id="7f6e9-151">Wenn Sie sowohl die Azure- als auch die AzureRM-Module verwenden, müssen Sie die gleiche Version der einzelnen Pakete installieren.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-151">If you use both the Azure and AzureRM modules, you should install the same version of each package.</span></span>

### <span data-ttu-id="7f6e9-152"><a id="update-azps"></a>Aktualisieren auf eine neue Version von Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f6e9-152"><a id="update-azps"></a>Updating to a new version of Azure PowerShell</span></span>

<span data-ttu-id="7f6e9-153">Wenn Sie eine frühere Version von Azure PowerShell installiert haben, die das Dienstverwaltungsmodul enthält, kann die folgende Fehlermeldung angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="7f6e9-153">If you have a previous version of Azure PowerShell installed that includes the Service Management module, you may receive the following error:</span></span>

```
PackageManagement\Install-Package : A command with name 'Get-AzureStorageContainerAcl' is already
available on this system. This module 'Azure.Storage' may override the existing commands. If you
still want to install this module 'Azure.Storage', use -AllowClobber parameter.

At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PSModule.psm1:1772 char:21
+ ...          $null = PackageManagement\Install-Package @PSBoundParameters
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (Microsoft.Power....InstallPackage:InstallPackage) [Install-Package], Exception
    + FullyQualifiedErrorId : CommandAlreadyAvailable,Validate-ModuleCommandAlreadyAvailable,Microsoft.PowerShell.PackageManagement.Cmdlets.InstallPackage
```

<span data-ttu-id="7f6e9-154">Wie in der Fehlermeldung angegeben, müssen Sie den Parameter „-AllowClobber“ zum Installieren des Moduls verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-154">As the error message states, you need to use the -AllowClobber parameter to install the module.</span></span> <span data-ttu-id="7f6e9-155">Verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="7f6e9-155">Use the following command:</span></span>

```powershell
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module AzureRM -AllowClobber
```

<span data-ttu-id="7f6e9-156">Weitere Informationen finden Sie im Hilfethema zu [Install-Module](https://msdn.microsoft.com/powershell/reference/5.1/PowerShellGet/install-module).</span><span class="sxs-lookup"><span data-stu-id="7f6e9-156">For more information, see the help topic for [Install-Module](https://msdn.microsoft.com/powershell/reference/5.1/PowerShellGet/install-module).</span></span>

### <a name="installing-module-versions-side-by-side"></a><span data-ttu-id="7f6e9-157">Parallele Installation von Modulversionen</span><span class="sxs-lookup"><span data-stu-id="7f6e9-157">Installing module versions side by side</span></span>

<span data-ttu-id="7f6e9-158">Die PowerShellGet-Installationsmethode ist die einzige Methode, die die Installation mehrerer Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-158">The PowerShellGet method of installation is the only method that supports the installation of multiple versions.</span></span> <span data-ttu-id="7f6e9-159">Beispiel: Sie besitzen Skripts, die mit einer vorherigen Version von Azure PowerShell geschrieben wurden, für deren Aktualisierung keine Zeit ist bzw. keine Ressourcen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-159">For example, you may have scripts written using a previous version of Azure PowerShell that you don't have the time or resources to updated.</span></span> <span data-ttu-id="7f6e9-160">Die folgenden Befehle veranschaulichen, wie mehrere Versionen von Azure PowerShell installiert werden:</span><span class="sxs-lookup"><span data-stu-id="7f6e9-160">The following commands illustrate how to install multiple versions of Azure PowerShell:</span></span>

```powershell
Install-Module -Name AzureRM -RequiredVersion 3.7.0
Install-Module -Name AzureRM -RequiredVersion 1.2.9
```

<span data-ttu-id="7f6e9-161">Nur eine Version des Moduls kann in einer PowerShell-Sitzung geladen werden.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-161">Only one version of the module can be loaded in a PowerShell session.</span></span> <span data-ttu-id="7f6e9-162">Sie müssen ein neues PowerShell-Fenster öffnen und `Import-Module` verwenden, um eine bestimmte Version der AzureRM-Cmdlets zu importieren:</span><span class="sxs-lookup"><span data-stu-id="7f6e9-162">You must open a new PowerShell window and use `Import-Module` to import a specific version of the AzureRM cmdlets:</span></span>

```powershell
Import-Module AzureRM -RequiredVersion 1.2.9
```

> [!NOTE]
> <span data-ttu-id="7f6e9-163">Version 2.1.0 und Version 1.2.6 sind die ersten Modulversionen, die parallel installiert und genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-163">Version 2.1.0 and version 1.2.6 are the first module versions designed to be installed and used side by side.</span></span> <span data-ttu-id="7f6e9-164">Beim Laden einer früheren Version von Azure PowerShell werden inkompatible Versionen des **AzureRM.Profile**-Moduls geladen.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-164">When loading an earlier version of the Azure PowerShell, incompatible versions of the **AzureRM.Profile** module are loaded.</span></span> <span data-ttu-id="7f6e9-165">Dies führt dazu, dass Sie, immer wenn Sie ein Cmdlet ausführen, zum Anmelden aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-165">This results in the cmdlets prompting you to log in whenever you execute a cmdlet.</span></span>

### <a name="other-installation-methods"></a><span data-ttu-id="7f6e9-166">Andere Installationsmethoden</span><span class="sxs-lookup"><span data-stu-id="7f6e9-166">Other installation methods</span></span>

<span data-ttu-id="7f6e9-167">Information zum Installieren des Webplattform-Installers oder des MSI-Pakets finden Sie unter [Other installation methods](other-install.md) (Andere Installationsmethoden).</span><span class="sxs-lookup"><span data-stu-id="7f6e9-167">For information about installing using the Web Platform Installer or the MSI Package, see [Other installation methods](other-install.md)</span></span>
