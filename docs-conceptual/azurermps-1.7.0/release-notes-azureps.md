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
ms.sourcegitcommit: b256bf48e15ee98865de0fae50e7b81878b03a54
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2017
---
# <a name="release-notes"></a>Versionshinweise

Hierbei handelt es sich um eine Liste der Änderungen, die in dieser Version an Azure PowerShell vorgenommen wurden.

## <a name="version-170"></a>Version 1.7.0

* **Änderung des Verhaltens für die Parameter „-Force“, „–Confirm“ und „$ConfirmPreference“ für alle Cmdlets. Diese Implementierung wird den PowerShell-Richtlinien entsprechend geändert. Für die meisten Cmdlets bedeutet dies, dass der Force-Parameter entfernt und die ShouldProcess-Aufforderung übersprungen wird. Benutzer müssen künftig den Parameter „-Confirm:$false“ in PowerShell-Skripts einfügen.** Mit diesen Änderungen wurden Probleme behoben, um Folgendes zu ermöglichen:
  - Richtige Implementierung der –WhatIf-Funktion. Benutzer können dadurch die Auswirkungen eines Cmdlets oder Skripts bestimmen, ohne tatsächlich Änderungen vorzunehmen.
  - Steuerung der Aufforderung zur Verwendung eines sitzungsweiten $ConfirmPreference-Elements, sodass der Benutzer basierend auf der Auswirkung einer potenziellen Änderung eine Aufforderung erhält (wie in der ConfirmImpact-Einstellung im Cmdlet angegeben)
  - Cmdlet-spezifische Steuerung von Bestätigungsaufforderungen mit dem –Confirm-Parameter
  - Konsistente Verwendung von „ShouldContinue“ und des –Force-Parameters in allen Cmdlets nur für die Aktionen, für die aufgrund der speziellen Art der Änderungen eine Aufforderung vom Benutzer erforderlich wäre (Beispiel: Löschen ausgeblendeter Dateien)
  - Konsistenz mit anderen PowerShell-Cmdlets, damit PowerShell-Skriptinformationen von anderen Cmdlets sofort für die Azure PowerShell-Cmdlets übernommen werden

**Beachten Sie, dass Azure PowerShell-Cmdlets nun zum *automatischen Überspringen aller Aufforderungen unter allen Umständen* voraussetzen, dass der Benutzer zwei Parameter angibt:**
```powershell
My-CmdletWithConfirmation –Confirm:$false -Force
```
* Azure Compute
  - Set-AzureRmVMADDomainExtension
  - Get-AzureRmVMADDomainExtension
  - -Redeploy-Parameter für „Restart-AzureVM“
  - -Validate-Parameter für „Move-AzureService“, „Move-AzureStorageAccount“ und „Move-AzureVirtualNetwork“
  - Namens- und Versionsparameter für Erweiterungs-Cmdlets sind nach wie vor optional.
  - Mit „New-AzureVM“ kann ein Lizenztyp aus einem VM-Objekt abgerufen werden.
* Azure Storage
  - Der Tags-Parameter wurde in „Tag“ geändert, und der Parameteralias „Tags“ wurde hinzugefügt.
    + New-AzureRmStorageAccount
    + Set-AzureRmStorageAccount
* Azure-Netzwerk
  - Für Peering in virtuellen Netzwerken wurde ein neues Cmdlet hinzugefügt.
* Azure Redis Cache
  - Für „Reset-AzureRmRedisCache“ wurde ein neues Cmdlet hinzugefügt.
  - Für „Export-AzureRmRedisCache“ wurde ein neues Cmdlet hinzugefügt.
  - Für „Import-AzureRmRedisCache“ wurde ein neues Cmdlet hinzugefügt.
  - Das Cmdlet „New-AzureRmRedisCache“ wurde geändert und enthält jetzt eine Parameteränderung für VNET.
* Sicherung/Wiederherstellung von Azure SQL-Datenbanken
  - Cmdlets für die Funktion zur langfristigen Aufbewahrung
  - Get-AzureRmSqlServerBackupLongTermRetentionVault
  - Get-AzureRmSqlDatabaseBackupLongTermRetentionPolicy
  - Set-AzureRmSqlServerBackupLongTermRetentionVault
  - Set-AzureRmSqlDatabaseBackupLongTermRetentionPolicy
  - „Restore-AzureRmSqlDatabase“ unterstützt nun die Point-in-Time-Wiederherstellung einer gelöschten Datenbank.
  - „Restore-AzureRmSqlDatabase“ unterstützt nun die Wiederherstellung aus einer langfristig aufbewahrten Sicherung.
* Azure LogicApp
  - Cmdlets für LogicApp-Integrationskonten wurden hinzugefügt.
  - Get-AzureRmIntegrationAccountAgreement
  - Get-AzureRmIntegrationAccountCallbackUrl
  - Get-AzureRmIntegrationAccountCertificate
  - Get-AzureRmIntegrationAccount
  - Get-AzureRmIntegrationAccountMap
  - Get-AzureRmIntegrationAccountPartner
  - Get-AzureRmIntegrationAccountSchema
  - New-AzureRmIntegrationAccountAgreement
  - New-AzureRmIntegrationAccountCertificate
  - New-AzureRmIntegrationAccount
  - New-AzureRmIntegrationAccountMap
  - New-AzureRmIntegrationAccountPartner
  - New-AzureRmIntegrationAccountSchema
  - Remove-AzureRmIntegrationAccountAgreement
  - Remove-AzureRmIntegrationAccountCertificate
  - Remove-AzureRmIntegrationAccount
  - Remove-AzureRmIntegrationAccountMap
  - Remove-AzureRmIntegrationAccountPartner
  - Remove-AzureRmIntegrationAccountSchema
  - Set-AzureRmIntegrationAccountAgreement
  - Set-AzureRmIntegrationAccountCertificate
  - Set-AzureRmIntegrationAccount
  - Set-AzureRmIntegrationAccountMap
  - Set-AzureRmIntegrationAccountPartner
  - Set-AzureRmIntegrationAccountSchema
* Azure Data Lake Store
  - Die Leistung beim Upload und Download von Dateien und Ordnern wurde erheblich gesteigert.
  - Dies zog eine geringfügige Änderung der Parameternamen für den Download und die Aufnahme von zwei neuen Parameter für den Upload nach sich:
    + NumThreads -> PerFileThreadCount: Hiermit wird die Anzahl von in einer einzelnen Datei verwendeten Threads angegeben.
    + ConcurrentFileCount: Hiermit wird die Anzahl von Dateien angegeben, die beim Ordnerupload/-download gleichzeitig hoch- bzw. heruntergeladen werden sollen.
  - Standardthreadingwerte sollen nun einen höheren Gesamtdurchsatz für die meisten Dateigrößen ermöglichen. Falls nicht die gewünschte Leistung erzielt wird, können die oben genannten Werte angepasst werden, um die Anforderungen zu erfüllen.
* Azure Data Lake Analytics
  - „Get-AzureRMDataLakeAnalyticsDataSource“ gibt nun beim Aufruf ohne Argumente alle Datenquellen zurück.
  - Durch diese Änderung wird auch der Parameter für den Datenquelltyp aus dem Cmdlet entfernt.
  - Diese Änderung führt dazu, dass ein neues Objekt für den Auflistungsvorgang mit den folgenden Eigenschaften zurückgegeben wird:
    + Type: Der Typ der Datenquelle
    + Name: Der Name der Datenquelle
    + IsDefault: Ist auf TRUE festgelegt, wenn es sich um die Standarddatenquelle für das Konto handelt.
  - „Get-AzureRMDataLakeAnalyticsJob“ wurde für eine Liste mit bestimmten Werten für die Datums-/Uhrzeitabweichung korrigiert, wenn nach „submittedBefore“ und „submittedAfter“ gefiltert wird.
* Web-Apps
  - Das Cmdlet „Add Swap-AzureRmWebAppSlot“ wurde für reguläre Austauschvorgänge und Austauschvorgänge mit Vorschau hinzugefügt.
  - Das Cmdlet „Extend Set-AzureRmWebAppSlot“ wurde erweitert, um automatische Austauschvorgänge zu unterstützen.
* Azure API Management
  - Azure API Management-Bereitstellungs-Cmdlets für „AzureChinaCloud“ wurden korrigiert.
  - Das Cmdlet „Set-AzureRmApiManagementTenantGitAccess“ wurde entfernt, da Git-Zugriff standardmäßig aktiviert ist.
* Sicherung von Azure Recovery Services
  - Unterstützung für die Azure SQL-Workload wurde hinzugefügt.
  - Unterstützung für das Sichern und Wiederherstellen verschlüsselter virtueller Azure-Computer wurde hinzugefügt.
  - Backup-AzureRmRecoveryServicesBackupItem: Eine optionale Funktion für die Aufbewahrungsdauer für Wiederherstellungspunkte wurde hinzugefügt.
  - Kleinere filterbezogene Fehlerbehebungen in den Cmdlets „Get-AzureRmRecoveryServicesBackupContainer“ und „Get-AzureRmRecoveryServicesBackupItem“
* Azure-Automatisierung
  - „Get-AzureRmAutomationHybridWorkerGroup“ wurde hinzugefügt.
