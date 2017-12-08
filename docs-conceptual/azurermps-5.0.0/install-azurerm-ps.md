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
ms.date: 08/31/2017
ms.openlocfilehash: 0e560332c87fdcc8b7365f2271de24481003a4d6
ms.sourcegitcommit: 358d260a867c6ee2e8700b91f776ba4f1b0e24a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2017
---
# <a name="install-and-configure-azure-powershell"></a><span data-ttu-id="c327f-103">Installieren und Konfigurieren von Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="c327f-103">Install and configure Azure PowerShell</span></span>

<span data-ttu-id="c327f-104">Dieser Artikel beschreibt die Schritte zum Installieren der Azure PowerShell-Module in einer Windows-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="c327f-104">This article explains the steps to install the Azure PowerShell modules in a Windows environment.</span></span>
<span data-ttu-id="c327f-105">Wenn Sie Azure PowerShell unter macOS oder Linux verwenden möchten, lesen Sie den folgenden Artikel: [Installieren und Konfigurieren von Azure PowerShell unter macOS und Linux](install-azurermps-maclinux.md).</span><span class="sxs-lookup"><span data-stu-id="c327f-105">If you want to use Azure PowerShell on macOS or Linux, see the following article: [Install and configure Azure PowerShell on macOS and Linux](install-azurermps-maclinux.md).</span></span>

<span data-ttu-id="c327f-106">Die Installation von Azure PowerShell aus dem PowerShell-Katalog ist die bevorzugte Installationsmethode.</span><span class="sxs-lookup"><span data-stu-id="c327f-106">Installing Azure PowerShell from the PowerShell Gallery is the preferred method of installation.</span></span>

## <a name="step-1-install-powershellget"></a><span data-ttu-id="c327f-107">Schritt 1: Installieren von PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="c327f-107">Step 1: Install PowerShellGet</span></span>

<span data-ttu-id="c327f-108">Für die Installation von Komponenten aus dem PowerShell-Katalog ist das PowerShellGet-Modul erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c327f-108">Installing items from the PowerShell Gallery requires the PowerShellGet module.</span></span> <span data-ttu-id="c327f-109">Stellen Sie sicher, dass Sie über die entsprechende Version von PowerShellGet verfügen und alle anderen Systemanforderungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="c327f-109">Make sure you have the appropriate version of PowerShellGet and other system requirements.</span></span> <span data-ttu-id="c327f-110">Führen Sie den folgenden Befehl aus, um zu ermitteln, ob PowerShellGet auf Ihrem System installiert ist.</span><span class="sxs-lookup"><span data-stu-id="c327f-110">Run the following command to see if you have PowerShellGet installed on your system.</span></span>

```powershell
Get-Module PowerShellGet -list | Select-Object Name,Version,Path
```

<span data-ttu-id="c327f-111">Etwa folgende Ausgabe sollte angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="c327f-111">You should see something similar to the following output:</span></span>

```Output
Name          Version Path
----          ------- ----
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

<span data-ttu-id="c327f-112">Falls PowerShellGet nicht installiert ist, lesen Sie die Informationen im Abschnitt [Installieren von PowerShellGet](#how-to-get-powershellget) dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="c327f-112">If you do not have PowerShellGet installed, see the [How to get PowerShellGet](#how-to-get-powershellget) section of this article.</span></span>

> [!NOTE]
> <span data-ttu-id="c327f-113">Für die Verwendung von PowerShellGet ist eine Ausführungsrichtlinie erforderlich, die die Ausführung von Skripts ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c327f-113">Using PowerShellGet requires an Execution Policy that allows you to run scripts.</span></span> <span data-ttu-id="c327f-114">Weitere Informationen zur Ausführungsrichtlinie von PowerShell finden Sie unter [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies) (Informationen zu Ausführungsrichtlinien).</span><span class="sxs-lookup"><span data-stu-id="c327f-114">For more information about PowerShell's Execution Policy, see [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>

## <a name="step-2-install-azure-powershell"></a><span data-ttu-id="c327f-115">Schritt 2: Installieren von Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="c327f-115">Step 2: Install Azure PowerShell</span></span>

<span data-ttu-id="c327f-116">Für die Installation von Azure PowerShell aus dem PowerShell-Katalog sind erhöhte Rechte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c327f-116">Installing Azure PowerShell from the PowerShell Gallery requires elevated privileges.</span></span> <span data-ttu-id="c327f-117">Führen Sie den folgenden Befehl in einer PowerShell-Sitzung mit erhöhten Rechten aus:</span><span class="sxs-lookup"><span data-stu-id="c327f-117">Run the following command from an elevated PowerShell session:</span></span>

```powershell
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module AzureRM -AllowClobber
```

<span data-ttu-id="c327f-118">Standardmäßig ist der PowerShell-Katalog nicht als vertrauenswürdiges Repository für PowerShellGet konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c327f-118">By default, the PowerShell gallery is not configured as a Trusted repository for PowerShellGet.</span></span> <span data-ttu-id="c327f-119">Bei der ersten Verwendung des PowerShell-Katalogs wird die folgende Meldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c327f-119">The first time you use the PSGallery you see the following prompt:</span></span>

```Output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): Y
```

<span data-ttu-id="c327f-120">Antworten Sie mit „Ja“ oder „Ja zu allen“, um die Installation fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="c327f-120">Answer 'Yes' or 'Yes to All' to continue with the installation.</span></span>

> [!NOTE]
> <span data-ttu-id="c327f-121">Wenn Sie eine ältere NuGet-Version als 2.8.5.201 haben, werden Sie aufgefordert, die aktuelle NuGet-Version herunterzuladen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c327f-121">If you have a version older than 2.8.5.201 of NuGet, you are prompted to download and install the latest version of NuGet.</span></span>

<span data-ttu-id="c327f-122">Das AzureRM-Modul ist ein Rollupmodul für die Azure Resource Manager-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="c327f-122">The AzureRM module is a rollup module for the Azure Resource Manager cmdlets.</span></span> <span data-ttu-id="c327f-123">Bei der Installation des AzureRM-Moduls werden alle noch nicht installierten Azure PowerShell-Module aus dem PowerShell-Katalog heruntergeladen und installiert.</span><span class="sxs-lookup"><span data-stu-id="c327f-123">When you install the AzureRM module, any Azure PowerShell module not previously installed is downloaded and from the PowerShell Gallery.</span></span>

<span data-ttu-id="c327f-124">Wenn eine frühere Version von Azure PowerShell installiert ist, erhalten Sie möglicherweise eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="c327f-124">If you have a previous version of Azure PowerShell installed you may receive an error.</span></span> <span data-ttu-id="c327f-125">Informationen zum Beheben dieses Problem finden Sie im Abschnitt [Aktualisieren auf eine neue Version von Azure PowerShell](#update-azps) dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="c327f-125">To resolve this issue, see the [Updating to a new version of Azure PowerShell](#update-azps) section of this article.</span></span>

## <a name="step-3-load-the-azurerm-module"></a><span data-ttu-id="c327f-126">Schritt 3: Laden des AzureRM-Moduls</span><span class="sxs-lookup"><span data-stu-id="c327f-126">Step 3: Load the AzureRM module</span></span>
<span data-ttu-id="c327f-127">Nach der Installation des Moduls müssen Sie das Modul in der PowerShell-Sitzung laden.</span><span class="sxs-lookup"><span data-stu-id="c327f-127">Once the module is installed, you need to load the module into your PowerShell session.</span></span> <span data-ttu-id="c327f-128">Dies muss in einer normalen PowerShell-Sitzung (ohne erhöhte Rechte) erfolgen.</span><span class="sxs-lookup"><span data-stu-id="c327f-128">You should do this in a normal (non-elevated) PowerShell session.</span></span> <span data-ttu-id="c327f-129">Module werden wie folgt mit dem Cmdlet `Import-Module` geladen:</span><span class="sxs-lookup"><span data-stu-id="c327f-129">Modules are loaded using the `Import-Module` cmdlet, as follows:</span></span>

```powershell
Import-Module AzureRM
```

## <a name="next-steps"></a><span data-ttu-id="c327f-130">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c327f-130">Next Steps</span></span>

<span data-ttu-id="c327f-131">Weitere Informationen zur Verwendung von Azure PowerShell finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="c327f-131">For more information about using Azure PowerShell, see the following articles:</span></span>

* [<span data-ttu-id="c327f-132">Erste Schritte mit Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="c327f-132">Get started with Azure PowerShell</span></span>](get-started-azureps.md)

## <a name="reporting-issues-and-feedback"></a><span data-ttu-id="c327f-133">Melden von Problemen und Bereitstellen von Feedback</span><span class="sxs-lookup"><span data-stu-id="c327f-133">Reporting issues and feedback</span></span>

<span data-ttu-id="c327f-134">Wenn mit dem Tool Fehler auftreten, legen Sie einen Eintrag im Bereich [Probleme](https://github.com/Azure/azure-powershell/issues) unseres GitHub Repositorys an.</span><span class="sxs-lookup"><span data-stu-id="c327f-134">If you encounter any bugs with the tool, file an issue in the [Issues](https://github.com/Azure/azure-powershell/issues) section of our GitHub repo.</span></span> <span data-ttu-id="c327f-135">Zum Senden von Feedback zur Befehlszeile verwenden Sie das Cmdlet `Send-Feedback`.</span><span class="sxs-lookup"><span data-stu-id="c327f-135">To provide feedback from the command line, use the `Send-Feedback` cmdlet.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c327f-136">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="c327f-136">Frequently asked questions</span></span>

### <a name="how-to-get-powershellget"></a><span data-ttu-id="c327f-137">Installieren von PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="c327f-137">How to get PowerShellGet</span></span>

|<span data-ttu-id="c327f-138">Betriebssystemversion</span><span class="sxs-lookup"><span data-stu-id="c327f-138">OS Version</span></span>|<span data-ttu-id="c327f-139">Installationsanleitung</span><span class="sxs-lookup"><span data-stu-id="c327f-139">Install instructions</span></span>|
|---|---|
|<span data-ttu-id="c327f-140">Ich besitze Windows 10 oder Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="c327f-140">I have Windows 10 or Windows Server 2016</span></span>|<span data-ttu-id="c327f-141">In Windows Management Framework (WMF) 5.0 integriert (im Betriebssystem enthalten)</span><span class="sxs-lookup"><span data-stu-id="c327f-141">Built into Windows Management Framework (WMF) 5.0 included in the OS</span></span>|
|<span data-ttu-id="c327f-142">Ich möchte auf PowerShell 5 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c327f-142">I want to upgrade to PowerShell 5</span></span>|[<span data-ttu-id="c327f-143">Installieren Sie die aktuelle Version von WMF.</span><span class="sxs-lookup"><span data-stu-id="c327f-143">Install the latest version of WMF</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54616)|
|<span data-ttu-id="c327f-144">Ich nutze eine Windows-Version mit PowerShell 3 oder PowerShell 4.</span><span class="sxs-lookup"><span data-stu-id="c327f-144">I am running on a version of Windows with PowerShell 3 or PowerShell 4</span></span>|[<span data-ttu-id="c327f-145">Laden Sie die PackageManagement-Module herunter.</span><span class="sxs-lookup"><span data-stu-id="c327f-145">Get the PackageManagement modules</span></span>](http://go.microsoft.com/fwlink/?LinkID=746217)|

<a id="helpmechoose"></a>
### <a name="checking-the-version-of-azure-powershell"></a><span data-ttu-id="c327f-146">Überprüfen der Azure PowerShell-Version</span><span class="sxs-lookup"><span data-stu-id="c327f-146">Checking the version of Azure PowerShell</span></span>

<span data-ttu-id="c327f-147">Obwohl empfohlen wird, möglichst bald ein Upgrade auf die neueste Version auszuführen, werden verschiedene Azure PowerShell-Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c327f-147">Although we encourage you to upgrade to the latest version as early as possible, several versions of Azure PowerShell are supported.</span></span> <span data-ttu-id="c327f-148">Führen Sie zum Ermitteln der installierten Azure PowerShell-Version `Get-Module AzureRM` in der Befehlszeile aus:</span><span class="sxs-lookup"><span data-stu-id="c327f-148">To determine the version of Azure PowerShell you have installed, run `Get-Module AzureRM` from your command line.</span></span>

```powershell
Get-Module AzureRM -list | Select-Object Name,Version,Path
```

### <a name="support-for-classic-deployment-methods"></a><span data-ttu-id="c327f-149">Unterstützung für klassische Bereitstellungsmethoden</span><span class="sxs-lookup"><span data-stu-id="c327f-149">Support for classic deployment methods</span></span>

<span data-ttu-id="c327f-150">Bei Bereitstellungen mit dem klassischen Bereitstellungsmodell können Sie die Dienstverwaltungsversion von Azure PowerShell installieren.</span><span class="sxs-lookup"><span data-stu-id="c327f-150">If you have deployments that use the classic deployment model you can install the Service Management version of Azure PowerShell.</span></span> <span data-ttu-id="c327f-151">Weitere Informationen finden Sie unter [Installing the Azure PowerShell Service Management module](/powershell/azure/servicemanagement/install-azure-ps) (Installieren des Azure PowerShell-Dienstverwaltungsmoduls).</span><span class="sxs-lookup"><span data-stu-id="c327f-151">For more information, see [Install the Azure PowerShell Service Management module](/powershell/azure/servicemanagement/install-azure-ps).</span></span> <span data-ttu-id="c327f-152">Das Azure- und das AzureRM-Modul nutzen gemeinsame Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="c327f-152">The Azure and AzureRM modules share common dependencies.</span></span> <span data-ttu-id="c327f-153">Wenn Sie sowohl die Azure- als auch die AzureRM-Module verwenden, müssen Sie die gleiche Version der einzelnen Pakete installieren.</span><span class="sxs-lookup"><span data-stu-id="c327f-153">If you use both the Azure and AzureRM modules, you should install the same version of each package.</span></span>

### <a id="update-azps"></a><span data-ttu-id="c327f-154">Aktualisieren auf eine neue Version von Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="c327f-154">Updating to a new version of Azure PowerShell</span></span>

<span data-ttu-id="c327f-155">Wenn Sie eine frühere Version von Azure PowerShell installiert haben, die das Dienstverwaltungsmodul enthält, kann die folgende Fehlermeldung angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="c327f-155">If you have a previous version of Azure PowerShell installed that includes the Service Management module, you may receive the following error:</span></span>

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

<span data-ttu-id="c327f-156">Wie in der Fehlermeldung angegeben, müssen Sie den Parameter „-AllowClobber“ zum Installieren des Moduls verwenden.</span><span class="sxs-lookup"><span data-stu-id="c327f-156">As the error message states, you need to use the -AllowClobber parameter to install the module.</span></span> <span data-ttu-id="c327f-157">Verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="c327f-157">Use the following command:</span></span>

```powershell
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module AzureRM -AllowClobber
```

<span data-ttu-id="c327f-158">Weitere Informationen finden Sie im Hilfethema zu [Install-Module](https://msdn.microsoft.com/powershell/reference/5.1/PowerShellGet/install-module).</span><span class="sxs-lookup"><span data-stu-id="c327f-158">For more information, see the help topic for [Install-Module](https://msdn.microsoft.com/powershell/reference/5.1/PowerShellGet/install-module).</span></span>

### <a name="installing-module-versions-side-by-side"></a><span data-ttu-id="c327f-159">Parallele Installation von Modulversionen</span><span class="sxs-lookup"><span data-stu-id="c327f-159">Installing module versions side by side</span></span>

<span data-ttu-id="c327f-160">Die PowerShellGet-Installationsmethode ist die einzige Methode, die die Installation mehrerer Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c327f-160">The PowerShellGet method of installation is the only method that supports the installation of multiple versions.</span></span> <span data-ttu-id="c327f-161">Beispiel: Sie besitzen Skripts, die mit einer vorherigen Version von Azure PowerShell geschrieben wurden, für deren Aktualisierung keine Zeit ist bzw. keine Ressourcen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c327f-161">For example, you may have scripts written using a previous version of Azure PowerShell that you don't have the time or resources to updated.</span></span> <span data-ttu-id="c327f-162">Die folgenden Befehle veranschaulichen, wie mehrere Versionen von Azure PowerShell installiert werden:</span><span class="sxs-lookup"><span data-stu-id="c327f-162">The following commands illustrate how to install multiple versions of Azure PowerShell:</span></span>

```powershell
Install-Module -Name AzureRM -RequiredVersion 3.7.0
Install-Module -Name AzureRM -RequiredVersion 1.2.9
```

<span data-ttu-id="c327f-163">Nur eine Version des Moduls kann in einer PowerShell-Sitzung geladen werden.</span><span class="sxs-lookup"><span data-stu-id="c327f-163">Only one version of the module can be loaded in a PowerShell session.</span></span> <span data-ttu-id="c327f-164">Sie müssen ein neues PowerShell-Fenster öffnen und `Import-Module` verwenden, um eine bestimmte Version der AzureRM-Cmdlets zu importieren:</span><span class="sxs-lookup"><span data-stu-id="c327f-164">You must open a new PowerShell window and use `Import-Module` to import a specific version of the AzureRM cmdlets:</span></span>

```powershell
Import-Module AzureRM -RequiredVersion 1.2.9
```

> [!NOTE]
> <span data-ttu-id="c327f-165">Version 2.1.0 und Version 1.2.6 sind die ersten Modulversionen, die parallel installiert und genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="c327f-165">Version 2.1.0 and version 1.2.6 are the first module versions designed to be installed and used side by side.</span></span> <span data-ttu-id="c327f-166">Beim Laden einer früheren Version von Azure PowerShell werden inkompatible Versionen des **AzureRM.Profile**-Moduls geladen.</span><span class="sxs-lookup"><span data-stu-id="c327f-166">When loading an earlier version of the Azure PowerShell, incompatible versions of the **AzureRM.Profile** module are loaded.</span></span> <span data-ttu-id="c327f-167">Dies führt dazu, dass Sie, immer wenn Sie ein Cmdlet ausführen, zum Anmelden aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="c327f-167">This results in the cmdlets prompting you to log in whenever you execute a cmdlet.</span></span>

### <a name="other-installation-methods"></a><span data-ttu-id="c327f-168">Andere Installationsmethoden</span><span class="sxs-lookup"><span data-stu-id="c327f-168">Other installation methods</span></span>

<span data-ttu-id="c327f-169">Information zum Installieren des Webplattform-Installers oder des MSI-Pakets finden Sie unter [Other installation methods](other-install.md) (Andere Installationsmethoden).</span><span class="sxs-lookup"><span data-stu-id="c327f-169">For information about installing using the Web Platform Installer or the MSI Package, see [Other installation methods](other-install.md)</span></span>
