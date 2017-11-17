---
title: "Andere Installationsmöglichkeiten für Azure PowerShell | Microsoft-Dokumentation"
description: Hier erfahren Sie, wie Sie Azure PowerShell mithilfe des MSI-Pakets oder des Webplattform-Installers installieren.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/06/2017
ms.openlocfilehash: 73c099375cecc8abdd5d6179109513946e7e793b
ms.sourcegitcommit: b256bf48e15ee98865de0fae50e7b81878b03a54
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2017
---
# <a name="other-installation-methods"></a><span data-ttu-id="71da9-103">Andere Installationsmethoden</span><span class="sxs-lookup"><span data-stu-id="71da9-103">Other installation methods</span></span>

<span data-ttu-id="71da9-104">Für Azure PowerShell stehen unterschiedliche Installationsmethoden zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="71da9-104">Azure PowerShell has multiple installation methods.</span></span> <span data-ttu-id="71da9-105">Bevorzugt wird die Kombination aus „PowerShellGet“ und PowerShell-Katalog.</span><span class="sxs-lookup"><span data-stu-id="71da9-105">Using PowerShellGet with the PowerShell Gallery is the preferred method.</span></span> <span data-ttu-id="71da9-106">Azure PowerShell kann mithilfe des Webplattform-Installers (WebPI) oder unter Verwendung der bei GitHub verfügbaren MSI-Datei unter Windows installiert werden.</span><span class="sxs-lookup"><span data-stu-id="71da9-106">Azure PowerShell can be installed on Windows using the Web Platform Installer (WebPI) or by using the MSI file available from GitHub.</span></span> <span data-ttu-id="71da9-107">Azure PowerShell kann auch in einem Docker-Container installiert werden.</span><span class="sxs-lookup"><span data-stu-id="71da9-107">Azure PowerShell can also be installed in a Docker container.</span></span>

## <a name="install-on-windows-using-the-web-platform-installer"></a><span data-ttu-id="71da9-108">Installieren unter Windows mit dem Webplattform-Installer</span><span class="sxs-lookup"><span data-stu-id="71da9-108">Install on Windows using the Web Platform Installer</span></span>

<span data-ttu-id="71da9-109">Die Vorgehensweise zum Installieren der neuesten Azure PowerShell-Version über WebPI hat sich im Vergleich zu früheren Versionen nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="71da9-109">Installing the latest Azure PowerShell from WebPI is the same as it was for previous versions.</span></span>
<span data-ttu-id="71da9-110">Laden Sie das [Azure PowerShell-WebPI-Paket](http://aka.ms/webpi-azps) herunter, und starten Sie die Installation.</span><span class="sxs-lookup"><span data-stu-id="71da9-110">Download the [Azure PowerShell WebPI package](http://aka.ms/webpi-azps) and start the install.</span></span>

> [!NOTE]
> <span data-ttu-id="71da9-111">Wenn Sie bereits Azure-Module aus dem PowerShell-Katalog installiert haben, entfernt das Installationsprogramm diese automatisch.</span><span class="sxs-lookup"><span data-stu-id="71da9-111">If you have previously installed Azure modules from the PowerShell Gallery, the installer automatically removes them.</span></span> <span data-ttu-id="71da9-112">Dadurch wird sichergestellt, dass nur eine einzelne Version von Azure PowerShell installiert ist, was Ihre Umgebung vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="71da9-112">This simplifies your environment by ensuring that only one version of Azure PowerShell is installed.</span></span> <span data-ttu-id="71da9-113">Es gibt jedoch Szenarien, in denen mehrere gleichzeitig installierte Versionen benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="71da9-113">However, there are scenarios where you may need multiple versions installed at the same time.</span></span>
>
> <span data-ttu-id="71da9-114">PowerShell-Katalogmodule werden unter `$env:ProgramFiles\WindowsPowerShell\Modules` installiert.</span><span class="sxs-lookup"><span data-stu-id="71da9-114">PowerShell Gallery modules install modules in `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span> <span data-ttu-id="71da9-115">Der WebPI-Installer installiert Azure-Module dagegen unter `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.</span><span class="sxs-lookup"><span data-stu-id="71da9-115">In contrast, the WebPI installer installs the Azure modules in `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.</span></span>
>
> <span data-ttu-id="71da9-116">Im Falle eines Installationsfehlers können Sie die Azure*-Ordner aus dem Ordner `$env:ProgramFiles\WindowsPowerShell\Modules` entfernen und die Installation wiederholen.</span><span class="sxs-lookup"><span data-stu-id="71da9-116">If an error occurs during install, you can manually remove the Azure* folders in your `$env:ProgramFiles\WindowsPowerShell\Modules` folder, and try the installation again.</span></span>

<span data-ttu-id="71da9-117">Nach Abschluss der Installation sollte Ihre `$env:PSModulePath` -Einstellung die Verzeichnisse mit den Azure PowerShell-Cmdlets enthalten.</span><span class="sxs-lookup"><span data-stu-id="71da9-117">Once the installation completes, your `$env:PSModulePath` setting should include the directories containing the Azure PowerShell cmdlets.</span></span> <span data-ttu-id="71da9-118">Mit dem folgenden Befehl können Sie überprüfen, ob Azure PowerShell ordnungsgemäß installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="71da9-118">The following command can be used to verify that the Azure PowerShell is installed properly.</span></span>

```powershell
# To make sure the Azure PowerShell module is available after you install
Get-Module -ListAvailable Azure* | Select-Object Name, Version, Path
```

> [!NOTE]
> <span data-ttu-id="71da9-119">Es gibt ein bekanntes Problem, das bei der Installation per WebPI auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="71da9-119">There is a known issue that can occur when installing from WebPI.</span></span> <span data-ttu-id="71da9-120">Wenn Ihr Computer aufgrund von Systemupdates oder anderen Installationen neu gestartet werden muss, wird bei Updates für `$env:PSModulePath` unter Umständen der Installationspfad von Azure PowerShell nicht einbezogen.</span><span class="sxs-lookup"><span data-stu-id="71da9-120">If your computer requires a restart due to system updates or other installations, it may cause updates to `$env:PSModulePath` to fail to include the path where Azure PowerShell is installed.</span></span>

<span data-ttu-id="71da9-121">Nach der Installation wird beim Ladevorgang oder beim Ausführen von Cmdlets möglicherweise folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="71da9-121">When attempting to load or execute cmdlets after installation, you can receive the following error message:</span></span>

```
PS C:\> Login-AzureRmAccount
Login-AzureRmAccount : The term 'Login-AzureRmAccount' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:1
+ Login-AzureRmAccount
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Login-AzureRmAccount:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="71da9-122">Starten Sie zum Beheben dieses Fehlers den Computer neu, oder importieren Sie das Modul unter Verwendung des vollqualifizierten Pfads.</span><span class="sxs-lookup"><span data-stu-id="71da9-122">This error can be corrected by restarting the machine or importing the module using the fully qualified path.</span></span> <span data-ttu-id="71da9-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="71da9-123">For example:</span></span>

```powershell
Import-Module "$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\AzureRM.psd1"
```

## <a name="install-on-windows-using-the-msi-package"></a><span data-ttu-id="71da9-124">Installieren unter Windows mithilfe des MSI-Pakets</span><span class="sxs-lookup"><span data-stu-id="71da9-124">Install on Windows using the MSI Package</span></span>

<span data-ttu-id="71da9-125">Azure PowerShell kann mithilfe der bei [GitHub](https://github.com/Azure/azure-powershell/releases/latest) verfügbaren MSI-Datei installiert werden.</span><span class="sxs-lookup"><span data-stu-id="71da9-125">Azure PowerShell can be installed using the MSI file available from [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span></span> <span data-ttu-id="71da9-126">Ältere installierte Versionen von Azure-Modulen werden vom Installationsprogramm automatisch entfernt.</span><span class="sxs-lookup"><span data-stu-id="71da9-126">If you have installed previous versions of Azure modules, the installer automatically removes them.</span></span> <span data-ttu-id="71da9-127">Das MSI-Paket installiert Module unter `$env:ProgramFiles\WindowsPowerShell\Modules`, erstellt aber keine versionsspezifischen Ordner.</span><span class="sxs-lookup"><span data-stu-id="71da9-127">The MSI package installs modules in `$env:ProgramFiles\WindowsPowerShell\Modules` but does not create version-specific folders.</span></span>

## <a name="install-in-a-docker-container"></a><span data-ttu-id="71da9-128">Installieren in einem Docker-Container</span><span class="sxs-lookup"><span data-stu-id="71da9-128">Install in a Docker container</span></span>

<span data-ttu-id="71da9-129">Wir behalten ein mit Azure PowerShell vorkonfiguriertes Docker-Image bei.</span><span class="sxs-lookup"><span data-stu-id="71da9-129">We maintain a Docker image preconfigured with Azure PowerShell.</span></span>

<span data-ttu-id="71da9-130">Führen Sie den Container mit `docker run` aus.</span><span class="sxs-lookup"><span data-stu-id="71da9-130">Run the container with `docker run`.</span></span>

```powershell
docker run azuresdk/azure-powershell
```

<span data-ttu-id="71da9-131">Darüber hinaus behalten wir eine Teilmenge der Cmdlets als PowerShell Core-Container bei.</span><span class="sxs-lookup"><span data-stu-id="71da9-131">In addition, we maintain a subset of cmdlets as a PowerShell Core container.</span></span>

<span data-ttu-id="71da9-132">Verwenden Sie für Mac/Linux das `latest`-Image.</span><span class="sxs-lookup"><span data-stu-id="71da9-132">For Mac/Linux, use the `latest` image.</span></span>

```bash
docker run azuresdk/azure-powershell-core:latest
```

<span data-ttu-id="71da9-133">Verwenden Sie für Windows das `nanoserver`-Image.</span><span class="sxs-lookup"><span data-stu-id="71da9-133">For Windows, use the `nanoserver` image.</span></span>

```powershell
docker run azuresdk/azure-powershell-core:nanoserver
```

<span data-ttu-id="71da9-134">Azure PowerShell wurde über `Install-Module` aus dem [PowerShell-Katalog](https://www.powershellgallery.com/) installiert.</span><span class="sxs-lookup"><span data-stu-id="71da9-134">Azure PowerShell is installed on the image via `Install-Module` from the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>