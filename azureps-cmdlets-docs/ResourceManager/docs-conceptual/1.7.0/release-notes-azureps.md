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
ms.openlocfilehash: 0a3f152751fee569d3ac5fba6bcff8c1737f7b8c
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="43ee3-103">Versionshinweise</span><span class="sxs-lookup"><span data-stu-id="43ee3-103">Release notes</span></span>
<a id="release-notes" class="xliff"></a>

<span data-ttu-id="43ee3-104">Hierbei handelt es sich um eine Liste der Änderungen, die in dieser Version an Azure PowerShell vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="43ee3-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <span data-ttu-id="43ee3-105">Version 1.7.0</span><span class="sxs-lookup"><span data-stu-id="43ee3-105">Version 1.7.0</span></span>
<a id="version-170" class="xliff"></a>

* <span data-ttu-id="43ee3-106">**Änderung des Verhaltens für die Parameter „-Force“, „–Confirm“ und „$ConfirmPreference“ für alle Cmdlets. Diese Implementierung wird den PowerShell-Richtlinien entsprechend geändert. Für die meisten Cmdlets bedeutet dies, dass der Force-Parameter entfernt und die ShouldProcess-Aufforderung übersprungen wird. Benutzer müssen künftig den Parameter „-Confirm:$false“ in PowerShell-Skripts einfügen.**</span><span class="sxs-lookup"><span data-stu-id="43ee3-106">**Behavioral change for -Force, –Confirm and $ConfirmPreference parameters for all cmdlets. We are changing this implementation to be in line with PowerShell guidelines. For most cmdlets, this means removing the Force parameter and to skip the ShouldProcess prompt, users will need to include the parameter: ‘-Confirm:$false’ in their PowerShell scripts.**</span></span> <span data-ttu-id="43ee3-107">Mit diesen Änderungen wurden Probleme behoben, um Folgendes zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="43ee3-107">This changes are addressing following issues:</span></span>
  - <span data-ttu-id="43ee3-108">Richtige Implementierung der –WhatIf-Funktion. Benutzer können dadurch die Auswirkungen eines Cmdlets oder Skripts bestimmen, ohne tatsächlich Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="43ee3-108">Correct implementation of –WhatIf functionality, allowing a user to determine the effects of a cmdlet or script without making any actual changes</span></span>
  - <span data-ttu-id="43ee3-109">Steuerung der Aufforderung zur Verwendung eines sitzungsweiten $ConfirmPreference-Elements, sodass der Benutzer basierend auf der Auswirkung einer potenziellen Änderung eine Aufforderung erhält (wie in der ConfirmImpact-Einstellung im Cmdlet angegeben)</span><span class="sxs-lookup"><span data-stu-id="43ee3-109">Control over prompting using a session-wide $ConfirmPreference, so that the user is prompted based on the impact of a prospective change (as reported in the ConfirmImpact setting in the cmdlet)</span></span>
  - <span data-ttu-id="43ee3-110">Cmdlet-spezifische Steuerung von Bestätigungsaufforderungen mit dem –Confirm-Parameter</span><span class="sxs-lookup"><span data-stu-id="43ee3-110">Cmdlet-specific control over confirmation prompts using the –Confirm parameter</span></span>
  - <span data-ttu-id="43ee3-111">Konsistente Verwendung von „ShouldContinue“ und des –Force-Parameters in allen Cmdlets nur für die Aktionen, für die aufgrund der speziellen Art der Änderungen eine Aufforderung vom Benutzer erforderlich wäre (Beispiel: Löschen ausgeblendeter Dateien)</span><span class="sxs-lookup"><span data-stu-id="43ee3-111">Consistent use of ShouldContinue and the –Force parameter across cmdlets, for only those actions that would require prompting from the user due to the special nature of the changes (for example, deleting hidden files)</span></span>
  - <span data-ttu-id="43ee3-112">Konsistenz mit anderen PowerShell-Cmdlets, damit PowerShell-Skriptinformationen von anderen Cmdlets sofort für die Azure PowerShell-Cmdlets übernommen werden</span><span class="sxs-lookup"><span data-stu-id="43ee3-112">Consistency with other PowerShell cmdlets, so that PowerShell scripting knowledge from other cmdlets is immediately applicable to the Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="43ee3-113">**Beachten Sie, dass Azure PowerShell-Cmdlets nun zum *automatischen Überspringen aller Aufforderungen unter allen Umständen* voraussetzen, dass der Benutzer zwei Parameter angibt:**</span><span class="sxs-lookup"><span data-stu-id="43ee3-113">**Notice that now to *automatically skip all Prompts in all Circumstances* Azure PowerShell cmdlets require the user to supply two parameters:**</span></span>
```powershell
My-CmdletWithConfirmation –Confirm:$false -Force
```
* <span data-ttu-id="43ee3-114">Azure Compute</span><span class="sxs-lookup"><span data-stu-id="43ee3-114">Azure Compute</span></span>
  - <span data-ttu-id="43ee3-115">Set-AzureRmVMADDomainExtension</span><span class="sxs-lookup"><span data-stu-id="43ee3-115">Set-AzureRmVMADDomainExtension</span></span>
  - <span data-ttu-id="43ee3-116">Get-AzureRmVMADDomainExtension</span><span class="sxs-lookup"><span data-stu-id="43ee3-116">Get-AzureRmVMADDomainExtension</span></span>
  - <span data-ttu-id="43ee3-117">-Redeploy-Parameter für „Restart-AzureVM“</span><span class="sxs-lookup"><span data-stu-id="43ee3-117">-Redeploy parameter for Restart-AzureVM</span></span>
  - <span data-ttu-id="43ee3-118">-Validate-Parameter für „Move-AzureService“, „Move-AzureStorageAccount“ und „Move-AzureVirtualNetwork“</span><span class="sxs-lookup"><span data-stu-id="43ee3-118">-Validate parameter for Move-AzureService, Move-AzureStorageAccount, and Move-AzureVirtualNetwork</span></span>
  - <span data-ttu-id="43ee3-119">Namens- und Versionsparameter für Erweiterungs-Cmdlets sind nach wie vor optional.</span><span class="sxs-lookup"><span data-stu-id="43ee3-119">Name and version parameters for extension cmdlets are optional as before.</span></span>
  - <span data-ttu-id="43ee3-120">Mit „New-AzureVM“ kann ein Lizenztyp aus einem VM-Objekt abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="43ee3-120">New-AzureVM can get a license type from VM object.</span></span>
* <span data-ttu-id="43ee3-121">Azure Storage</span><span class="sxs-lookup"><span data-stu-id="43ee3-121">Azure Storage</span></span>
  - <span data-ttu-id="43ee3-122">Der Tags-Parameter wurde in „Tag“ geändert, und der Parameteralias „Tags“ wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="43ee3-122">Change Tags Parameter to Tag, and add parameter alias Tags</span></span>
    + <span data-ttu-id="43ee3-123">New-AzureRmStorageAccount</span><span class="sxs-lookup"><span data-stu-id="43ee3-123">New-AzureRmStorageAccount</span></span>
    + <span data-ttu-id="43ee3-124">Set-AzureRmStorageAccount</span><span class="sxs-lookup"><span data-stu-id="43ee3-124">Set-AzureRmStorageAccount</span></span>
* <span data-ttu-id="43ee3-125">Azure-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="43ee3-125">Azure Network</span></span>
  - <span data-ttu-id="43ee3-126">Für Peering in virtuellen Netzwerken wurde ein neues Cmdlet hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="43ee3-126">New cmdlet added for Virtual Network Peering</span></span>
* <span data-ttu-id="43ee3-127">Azure Redis Cache</span><span class="sxs-lookup"><span data-stu-id="43ee3-127">Azure Redis Cache</span></span>
  - <span data-ttu-id="43ee3-128">Für „Reset-AzureRmRedisCache“ wurde ein neues Cmdlet hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="43ee3-128">New cmdlet added for Reset-AzureRmRedisCache</span></span>
  - <span data-ttu-id="43ee3-129">Für „Export-AzureRmRedisCache“ wurde ein neues Cmdlet hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="43ee3-129">New cmdlet added for Export-AzureRmRedisCache</span></span>
  - <span data-ttu-id="43ee3-130">Für „Import-AzureRmRedisCache“ wurde ein neues Cmdlet hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="43ee3-130">New cmdlet added for Import-AzureRmRedisCache</span></span>
  - <span data-ttu-id="43ee3-131">Das Cmdlet „New-AzureRmRedisCache“ wurde geändert und enthält jetzt eine Parameteränderung für VNET.</span><span class="sxs-lookup"><span data-stu-id="43ee3-131">Modified cmdlet New-AzureRmRedisCache to include parameter change for vNet</span></span>
* <span data-ttu-id="43ee3-132">Sicherung/Wiederherstellung von Azure SQL-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="43ee3-132">Azure SQL DB Backup/Restore</span></span>
  - <span data-ttu-id="43ee3-133">Cmdlets für die Funktion zur langfristigen Aufbewahrung</span><span class="sxs-lookup"><span data-stu-id="43ee3-133">Cmdlets for LTR (Long Term Retention) backup feature</span></span>
  - <span data-ttu-id="43ee3-134">Get-AzureRmSqlServerBackupLongTermRetentionVault</span><span class="sxs-lookup"><span data-stu-id="43ee3-134">Get-AzureRmSqlServerBackupLongTermRetentionVault</span></span>
  - <span data-ttu-id="43ee3-135">Get-AzureRmSqlDatabaseBackupLongTermRetentionPolicy</span><span class="sxs-lookup"><span data-stu-id="43ee3-135">Get-AzureRmSqlDatabaseBackupLongTermRetentionPolicy</span></span>
  - <span data-ttu-id="43ee3-136">Set-AzureRmSqlServerBackupLongTermRetentionVault</span><span class="sxs-lookup"><span data-stu-id="43ee3-136">Set-AzureRmSqlServerBackupLongTermRetentionVault</span></span>
  - <span data-ttu-id="43ee3-137">Set-AzureRmSqlDatabaseBackupLongTermRetentionPolicy</span><span class="sxs-lookup"><span data-stu-id="43ee3-137">Set-AzureRmSqlDatabaseBackupLongTermRetentionPolicy</span></span>
  - <span data-ttu-id="43ee3-138">„Restore-AzureRmSqlDatabase“ unterstützt nun die Point-in-Time-Wiederherstellung einer gelöschten Datenbank.</span><span class="sxs-lookup"><span data-stu-id="43ee3-138">Restore-AzureRmSqlDatabase now supports point-in-time restore of a deleted database</span></span>
  - <span data-ttu-id="43ee3-139">„Restore-AzureRmSqlDatabase“ unterstützt nun die Wiederherstellung aus einer langfristig aufbewahrten Sicherung.</span><span class="sxs-lookup"><span data-stu-id="43ee3-139">Restore-AzureRmSqlDatabase now supports restoring from a Long Term Retention backup</span></span>
* <span data-ttu-id="43ee3-140">Azure LogicApp</span><span class="sxs-lookup"><span data-stu-id="43ee3-140">Azure LogicApp</span></span>
  - <span data-ttu-id="43ee3-141">Cmdlets für LogicApp-Integrationskonten wurden hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="43ee3-141">Added LogicApp Integration accounts cmdlets.</span></span>
  - <span data-ttu-id="43ee3-142">Get-AzureRmIntegrationAccountAgreement</span><span class="sxs-lookup"><span data-stu-id="43ee3-142">Get-AzureRmIntegrationAccountAgreement</span></span>
  - <span data-ttu-id="43ee3-143">Get-AzureRmIntegrationAccountCallbackUrl</span><span class="sxs-lookup"><span data-stu-id="43ee3-143">Get-AzureRmIntegrationAccountCallbackUrl</span></span>
  - <span data-ttu-id="43ee3-144">Get-AzureRmIntegrationAccountCertificate</span><span class="sxs-lookup"><span data-stu-id="43ee3-144">Get-AzureRmIntegrationAccountCertificate</span></span>
  - <span data-ttu-id="43ee3-145">Get-AzureRmIntegrationAccount</span><span class="sxs-lookup"><span data-stu-id="43ee3-145">Get-AzureRmIntegrationAccount</span></span>
  - <span data-ttu-id="43ee3-146">Get-AzureRmIntegrationAccountMap</span><span class="sxs-lookup"><span data-stu-id="43ee3-146">Get-AzureRmIntegrationAccountMap</span></span>
  - <span data-ttu-id="43ee3-147">Get-AzureRmIntegrationAccountPartner</span><span class="sxs-lookup"><span data-stu-id="43ee3-147">Get-AzureRmIntegrationAccountPartner</span></span>
  - <span data-ttu-id="43ee3-148">Get-AzureRmIntegrationAccountSchema</span><span class="sxs-lookup"><span data-stu-id="43ee3-148">Get-AzureRmIntegrationAccountSchema</span></span>
  - <span data-ttu-id="43ee3-149">New-AzureRmIntegrationAccountAgreement</span><span class="sxs-lookup"><span data-stu-id="43ee3-149">New-AzureRmIntegrationAccountAgreement</span></span>
  - <span data-ttu-id="43ee3-150">New-AzureRmIntegrationAccountCertificate</span><span class="sxs-lookup"><span data-stu-id="43ee3-150">New-AzureRmIntegrationAccountCertificate</span></span>
  - <span data-ttu-id="43ee3-151">New-AzureRmIntegrationAccount</span><span class="sxs-lookup"><span data-stu-id="43ee3-151">New-AzureRmIntegrationAccount</span></span>
  - <span data-ttu-id="43ee3-152">New-AzureRmIntegrationAccountMap</span><span class="sxs-lookup"><span data-stu-id="43ee3-152">New-AzureRmIntegrationAccountMap</span></span>
  - <span data-ttu-id="43ee3-153">New-AzureRmIntegrationAccountPartner</span><span class="sxs-lookup"><span data-stu-id="43ee3-153">New-AzureRmIntegrationAccountPartner</span></span>
  - <span data-ttu-id="43ee3-154">New-AzureRmIntegrationAccountSchema</span><span class="sxs-lookup"><span data-stu-id="43ee3-154">New-AzureRmIntegrationAccountSchema</span></span>
  - <span data-ttu-id="43ee3-155">Remove-AzureRmIntegrationAccountAgreement</span><span class="sxs-lookup"><span data-stu-id="43ee3-155">Remove-AzureRmIntegrationAccountAgreement</span></span>
  - <span data-ttu-id="43ee3-156">Remove-AzureRmIntegrationAccountCertificate</span><span class="sxs-lookup"><span data-stu-id="43ee3-156">Remove-AzureRmIntegrationAccountCertificate</span></span>
  - <span data-ttu-id="43ee3-157">Remove-AzureRmIntegrationAccount</span><span class="sxs-lookup"><span data-stu-id="43ee3-157">Remove-AzureRmIntegrationAccount</span></span>
  - <span data-ttu-id="43ee3-158">Remove-AzureRmIntegrationAccountMap</span><span class="sxs-lookup"><span data-stu-id="43ee3-158">Remove-AzureRmIntegrationAccountMap</span></span>
  - <span data-ttu-id="43ee3-159">Remove-AzureRmIntegrationAccountPartner</span><span class="sxs-lookup"><span data-stu-id="43ee3-159">Remove-AzureRmIntegrationAccountPartner</span></span>
  - <span data-ttu-id="43ee3-160">Remove-AzureRmIntegrationAccountSchema</span><span class="sxs-lookup"><span data-stu-id="43ee3-160">Remove-AzureRmIntegrationAccountSchema</span></span>
  - <span data-ttu-id="43ee3-161">Set-AzureRmIntegrationAccountAgreement</span><span class="sxs-lookup"><span data-stu-id="43ee3-161">Set-AzureRmIntegrationAccountAgreement</span></span>
  - <span data-ttu-id="43ee3-162">Set-AzureRmIntegrationAccountCertificate</span><span class="sxs-lookup"><span data-stu-id="43ee3-162">Set-AzureRmIntegrationAccountCertificate</span></span>
  - <span data-ttu-id="43ee3-163">Set-AzureRmIntegrationAccount</span><span class="sxs-lookup"><span data-stu-id="43ee3-163">Set-AzureRmIntegrationAccount</span></span>
  - <span data-ttu-id="43ee3-164">Set-AzureRmIntegrationAccountMap</span><span class="sxs-lookup"><span data-stu-id="43ee3-164">Set-AzureRmIntegrationAccountMap</span></span>
  - <span data-ttu-id="43ee3-165">Set-AzureRmIntegrationAccountPartner</span><span class="sxs-lookup"><span data-stu-id="43ee3-165">Set-AzureRmIntegrationAccountPartner</span></span>
  - <span data-ttu-id="43ee3-166">Set-AzureRmIntegrationAccountSchema</span><span class="sxs-lookup"><span data-stu-id="43ee3-166">Set-AzureRmIntegrationAccountSchema</span></span>
* <span data-ttu-id="43ee3-167">Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="43ee3-167">Azure Data Lake Store</span></span>
  - <span data-ttu-id="43ee3-168">Die Leistung beim Upload und Download von Dateien und Ordnern wurde erheblich gesteigert.</span><span class="sxs-lookup"><span data-stu-id="43ee3-168">Drastically improve performance of file and folder upload and download.</span></span>
  - <span data-ttu-id="43ee3-169">Dies zog eine geringfügige Änderung der Parameternamen für den Download und die Aufnahme von zwei neuen Parameter für den Upload nach sich:</span><span class="sxs-lookup"><span data-stu-id="43ee3-169">This includes a slight change to the parameter names for download and inclusion of two new parameters for upload:</span></span>
    + <span data-ttu-id="43ee3-170">NumThreads -> PerFileThreadCount: Hiermit wird die Anzahl von in einer einzelnen Datei verwendeten Threads angegeben.</span><span class="sxs-lookup"><span data-stu-id="43ee3-170">NumThreads -> PerFileThreadCount, used to indicate the number of threads to use in a single file</span></span>
    + <span data-ttu-id="43ee3-171">ConcurrentFileCount: Hiermit wird die Anzahl von Dateien angegeben, die beim Ordnerupload/-download gleichzeitig hoch- bzw. heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="43ee3-171">ConcurrentFileCount, used to indicate the number of files to upload/download in parallel for folder upload/download.</span></span>
  - <span data-ttu-id="43ee3-172">Standardthreadingwerte sollen nun einen höheren Gesamtdurchsatz für die meisten Dateigrößen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="43ee3-172">Default threading values are now designed to give a better all around throughput for most file sizes.</span></span> <span data-ttu-id="43ee3-173">Falls nicht die gewünschte Leistung erzielt wird, können die oben genannten Werte angepasst werden, um die Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="43ee3-173">If performance is not as desired, the values above can be modified to meet requirements.</span></span>
* <span data-ttu-id="43ee3-174">Azure Data Lake Analytics</span><span class="sxs-lookup"><span data-stu-id="43ee3-174">Azure Data Lake Analytics</span></span>
  - <span data-ttu-id="43ee3-175">„Get-AzureRMDataLakeAnalyticsDataSource“ gibt nun beim Aufruf ohne Argumente alle Datenquellen zurück.</span><span class="sxs-lookup"><span data-stu-id="43ee3-175">Get-AzureRMDataLakeAnalyticsDataSource now returns all data sources when called with no arguments.</span></span>
  - <span data-ttu-id="43ee3-176">Durch diese Änderung wird auch der Parameter für den Datenquelltyp aus dem Cmdlet entfernt.</span><span class="sxs-lookup"><span data-stu-id="43ee3-176">This change also removes the data source type parameter from the cmdlet.</span></span>
  - <span data-ttu-id="43ee3-177">Diese Änderung führt dazu, dass ein neues Objekt für den Auflistungsvorgang mit den folgenden Eigenschaften zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="43ee3-177">This change results in a new object being returned for the list operation with the following properties:</span></span>
    + <span data-ttu-id="43ee3-178">Type: Der Typ der Datenquelle</span><span class="sxs-lookup"><span data-stu-id="43ee3-178">Type, the type of data source</span></span>
    + <span data-ttu-id="43ee3-179">Name: Der Name der Datenquelle</span><span class="sxs-lookup"><span data-stu-id="43ee3-179">Name, the name of the data source</span></span>
    + <span data-ttu-id="43ee3-180">IsDefault: Ist auf TRUE festgelegt, wenn es sich um die Standarddatenquelle für das Konto handelt.</span><span class="sxs-lookup"><span data-stu-id="43ee3-180">IsDefault, set to true if this is the default data source for the account</span></span>
  - <span data-ttu-id="43ee3-181">„Get-AzureRMDataLakeAnalyticsJob“ wurde für eine Liste mit bestimmten Werten für die Datums-/Uhrzeitabweichung korrigiert, wenn nach „submittedBefore“ und „submittedAfter“ gefiltert wird.</span><span class="sxs-lookup"><span data-stu-id="43ee3-181">Get-AzureRMDataLakeAnalyticsJob fixed for list for certain date time offset values when filtering on submittedBefore and submittedAfter.</span></span>
* <span data-ttu-id="43ee3-182">Web-Apps</span><span class="sxs-lookup"><span data-stu-id="43ee3-182">Web Apps</span></span>
  - <span data-ttu-id="43ee3-183">Das Cmdlet „Add Swap-AzureRmWebAppSlot“ wurde für reguläre Austauschvorgänge und Austauschvorgänge mit Vorschau hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="43ee3-183">Add Swap-AzureRmWebAppSlot cmdlet for regular swap and swap with preview</span></span>
  - <span data-ttu-id="43ee3-184">Das Cmdlet „Extend Set-AzureRmWebAppSlot“ wurde erweitert, um automatische Austauschvorgänge zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="43ee3-184">Extend Set-AzureRmWebAppSlot cmdlet to support auto swap</span></span>
* <span data-ttu-id="43ee3-185">Azure API Management</span><span class="sxs-lookup"><span data-stu-id="43ee3-185">Azure API Management</span></span>
  - <span data-ttu-id="43ee3-186">Azure API Management-Bereitstellungs-Cmdlets für „AzureChinaCloud“ wurden korrigiert.</span><span class="sxs-lookup"><span data-stu-id="43ee3-186">Fixed Azure Api Management Deployment cmdlets for AzureChinaCloud.</span></span>
  - <span data-ttu-id="43ee3-187">Das Cmdlet „Set-AzureRmApiManagementTenantGitAccess“ wurde entfernt, da Git-Zugriff standardmäßig aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="43ee3-187">Removed cmdlet Set-AzureRmApiManagementTenantGitAccess as Git Access is enabled by Default.</span></span>
* <span data-ttu-id="43ee3-188">Sicherung von Azure Recovery Services</span><span class="sxs-lookup"><span data-stu-id="43ee3-188">Azure Recovery Services Backup</span></span>
  - <span data-ttu-id="43ee3-189">Unterstützung für die Azure SQL-Workload wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="43ee3-189">Added support for the Azure SQL workload</span></span>
  - <span data-ttu-id="43ee3-190">Unterstützung für das Sichern und Wiederherstellen verschlüsselter virtueller Azure-Computer wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="43ee3-190">Added support for backing up and restoring encrypted Azure VMs</span></span>
  - <span data-ttu-id="43ee3-191">Backup-AzureRmRecoveryServicesBackupItem: Eine optionale Funktion für die Aufbewahrungsdauer für Wiederherstellungspunkte wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="43ee3-191">Backup-AzureRmRecoveryServicesBackupItem - Added optional retention time feature for recovery points</span></span>
  - <span data-ttu-id="43ee3-192">Kleinere filterbezogene Fehlerbehebungen in den Cmdlets „Get-AzureRmRecoveryServicesBackupContainer“ und „Get-AzureRmRecoveryServicesBackupItem“</span><span class="sxs-lookup"><span data-stu-id="43ee3-192">Minor filter-related bug fixes in Get-AzureRmRecoveryServicesBackupContainer and Get-AzureRmRecoveryServicesBackupItem cmdlets</span></span>
* <span data-ttu-id="43ee3-193">Azure-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="43ee3-193">Azure Automation</span></span>
  - <span data-ttu-id="43ee3-194">„Get-AzureRmAutomationHybridWorkerGroup“ wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="43ee3-194">Added Get-AzureRmAutomationHybridWorkerGroup</span></span>
