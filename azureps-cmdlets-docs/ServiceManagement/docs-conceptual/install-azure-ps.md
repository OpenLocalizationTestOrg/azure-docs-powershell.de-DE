---
title: <span data-ttu-id="44cc6-101">Installieren und Konfigurieren des Azure PowerShell-Dienstverwaltungsmoduls | Microsoft-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="44cc6-101">Install and configure the Azure PowerShell Service Management module | Microsoft Docs</span></span>
description: "<span data-ttu-id=\"44cc6-102\">Hier erfahren Sie, wie Sie Azure PowerShell für die erste Verwendung installieren und konfigurieren.</span><span class=\"sxs-lookup\"><span data-stu-id=\"44cc6-102\">How to install and configure Azure PowerShell for first time use.</span></span>"
services: azure
author: sdwheeler
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/06/2017
ms.openlocfilehash: c51c727c1cb022eca59f819c7f24d8e058c677da
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="44cc6-103">Installieren des Azure PowerShell-Dienstverwaltungsmoduls</span><span class="sxs-lookup"><span data-stu-id="44cc6-103">Installing the Azure PowerShell Service Management module</span></span>
<a id="installing-the-azure-powershell-service-management-module" class="xliff"></a>

<span data-ttu-id="44cc6-104">Die Installation von Azure PowerShell aus dem [PowerShell-Katalog](https://www.powershellgallery.com/) ist die bevorzugte Installationsmethode.</span><span class="sxs-lookup"><span data-stu-id="44cc6-104">Installing Azure PowerShell from the [PowerShell Gallery](https://www.powershellgallery.com/) is the preferred method of installation.</span></span>

## <span data-ttu-id="44cc6-105">Schritt 1: Installieren von PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="44cc6-105">Step 1: Install PowerShellGet</span></span>
<a id="step-1-install-powershellget" class="xliff"></a>

<span data-ttu-id="44cc6-106">Für die Installation von Komponenten aus dem PowerShell-Katalog ist das PowerShellGet-Modul erforderlich.</span><span class="sxs-lookup"><span data-stu-id="44cc6-106">Installing items from the PowerShell Gallery requires the PowerShellGet module.</span></span> <span data-ttu-id="44cc6-107">Stellen Sie sicher, dass Sie über die entsprechende Version von PowerShellGet verfügen und alle anderen Systemanforderungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="44cc6-107">Make sure you have the appropriate version of PowerShellGet and other system requirements.</span></span> <span data-ttu-id="44cc6-108">Führen Sie den folgenden Befehl aus, um zu ermitteln, ob PowerShellGet auf Ihrem System installiert ist.</span><span class="sxs-lookup"><span data-stu-id="44cc6-108">Run the following command to see if you have PowerShellGet installed on your system.</span></span>

```powershell
Get-Module PowerShellGet -list | Select-Object Name,Version,Path
```

<span data-ttu-id="44cc6-109">Eine Ausgabe wie die folgende sollte angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="44cc6-109">You should see something similar to the following output:</span></span>

```
Name          Version Path
----          ------- ----
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

<span data-ttu-id="44cc6-110">Falls PowerShellGet nicht installiert ist, lesen Sie [Installieren von PowerShellGet](install-azurerm-ps.md#how-to-get-powershellget).</span><span class="sxs-lookup"><span data-stu-id="44cc6-110">If you do not have PowerShellGet installed, see the [How to get PowerShellGet](install-azurerm-ps.md#how-to-get-powershellget).</span></span>

## <span data-ttu-id="44cc6-111">Schritt 2: Installieren von Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="44cc6-111">Step 2: Install Azure PowerShell</span></span>
<a id="step-2-install-azure-powershell" class="xliff"></a>

<span data-ttu-id="44cc6-112">Führen Sie über die Windows PowerShell-Konsole den folgenden Befehl als Administrator aus:</span><span class="sxs-lookup"><span data-stu-id="44cc6-112">Run the following command from the Windows PowerShell console running as Administrator:</span></span>

```powershell
Install-Module Azure
```

<span data-ttu-id="44cc6-113">Das Azure-Modul ist ein Rollupmodul für die Azure Resource Manager-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="44cc6-113">The Azure module is a rollup module for the Azure Resource Manager cmdlets.</span></span> <span data-ttu-id="44cc6-114">Bei der Installation des AzureRM-Moduls werden alle noch nicht installierten Azure-Module aus dem PowerShell-Katalog heruntergeladen und installiert.</span><span class="sxs-lookup"><span data-stu-id="44cc6-114">When you install the AzureRM module, any other Azure modules that have not previously been installed will be downloaded and installed from the PowerShell Gallery.</span></span>

<span data-ttu-id="44cc6-115">Das Azure-Dienstverwaltungsmodul nutzt zum Teil die gleichen Abhängigkeiten wie die Azure PowerShell Resource Manager-Module.</span><span class="sxs-lookup"><span data-stu-id="44cc6-115">The Azure Service Management module shares dependencies with the Azure PowerShell Resource Manager modules.</span></span> <span data-ttu-id="44cc6-116">Wenn Sie die Azure PowerShell Resource Manager-Module installiert haben, müssen Sie dem Installationsbefehl den Parameter `-AllowClobber` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="44cc6-116">If you have installed the Azure PowerShell Resource Manager modules, you will need to add the `-AllowClobber` parameter to the install command.</span></span> <span data-ttu-id="44cc6-117">So können diese gemeinsam genutzten Abhängigkeiten aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="44cc6-117">This allows this existing shared dependencies to be updated.</span></span> <span data-ttu-id="44cc6-118">Ohne den Parameter ist die Installation des Moduls nicht erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="44cc6-118">Without this parameter, installation of the module fails.</span></span>

```powershell
Install-Module Azure -AllowClobber
```

<span data-ttu-id="44cc6-119">Nach der Installation können Sie das Modul mithilfe des folgenden Befehls importieren:</span><span class="sxs-lookup"><span data-stu-id="44cc6-119">After you install this module, you can import the module by running the following command:</span></span>

```powershell
Import-Module Azure
```

## <span data-ttu-id="44cc6-120">So verwenden Sie die Cmdlets</span><span class="sxs-lookup"><span data-stu-id="44cc6-120">To use the cmdlets</span></span>
<a id="to-use-the-cmdlets" class="xliff"></a>

<span data-ttu-id="44cc6-121">Melden Sie sich zunächst bei Ihrem Azure-Konto an, bevor Sie die Cmdlets der Azure-Dienstverwaltung verwenden.</span><span class="sxs-lookup"><span data-stu-id="44cc6-121">To start working with the Azure Service Management cmdlets, first log on to your Azure account.</span></span> <span data-ttu-id="44cc6-122">Führen Sie dazu den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="44cc6-122">To log on to your account, run the following command:</span></span>

```powershell
Add-AzureAccount
```

<span data-ttu-id="44cc6-123">Nach der Anmeldung bei Azure erstellt Azure PowerShell einen Kontext für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="44cc6-123">After logging into Azure, Azure PowerShell creates a context for the given session.</span></span> <span data-ttu-id="44cc6-124">Dieser Kontext enthält die Azure PowerShell-Umgebung, das Konto, den Mandanten und das Abonnement für alle Cmdlets innerhalb dieser Sitzung.</span><span class="sxs-lookup"><span data-stu-id="44cc6-124">That context contains the Azure PowerShell environment, account, tenant, and subscription that will be used for all cmdlets within that session.</span></span> <span data-ttu-id="44cc6-125">Nun können Sie die folgenden Module verwenden.</span><span class="sxs-lookup"><span data-stu-id="44cc6-125">Now you are ready to use the modules below.</span></span>

## <span data-ttu-id="44cc6-126">Cmdlets der Azure-Dienstverwaltung</span><span class="sxs-lookup"><span data-stu-id="44cc6-126">Azure Service Management cmdlets</span></span>
<a id="azure-service-management-cmdlets" class="xliff"></a>

<span data-ttu-id="44cc6-127">Azure PowerShell-Module werden regelmäßig aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="44cc6-127">Azure PowerShell modules are updated frequently.</span></span> <span data-ttu-id="44cc6-128">Sollten Sie feststellen, dass die Cmdlet-Onlinehilfe Cmdlets oder Parameter enthält, die in Ihrem Modul nicht vorhanden sind, laden Sie die neueste Version des Moduls herunter, und installieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="44cc6-128">If you notice that the online cmdlet help includes cmdlets or parameters that are not in your module, download and install the latest version of the module.</span></span> <span data-ttu-id="44cc6-129">Geben Sie Folgendes ein, um die Version Ihres Moduls zu ermitteln: `(Get-Module Azure).Version`.</span><span class="sxs-lookup"><span data-stu-id="44cc6-129">To find the version of your module, type: `(Get-Module Azure).Version`.</span></span>

<span data-ttu-id="44cc6-130">Beispielskripts zur Automatisierung einiger allgemeiner Aufgaben in Azure finden Sie im [Azure Script Center](http://www.windowsazure.com/documentation/scripts/).</span><span class="sxs-lookup"><span data-stu-id="44cc6-130">For sample scripts that can help you automate some of the common tasks in Azure, see the [Windows Azure Script Center](http://www.windowsazure.com/documentation/scripts/).</span></span>

<span data-ttu-id="44cc6-131">Allgemeine Informationen zum Installieren, Kennenlernen, Verwenden und Anpassen von Windows PowerShell finden Sie unter [Skripterstellung mit Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=320210).</span><span class="sxs-lookup"><span data-stu-id="44cc6-131">For general information about installing, learning, using, and customizing Windows PowerShell, see [Scripting with Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=320210).</span></span>
