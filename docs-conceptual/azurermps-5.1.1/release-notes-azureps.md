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
ms.date: 11/14/2017
ms.openlocfilehash: cf58789ba69fd2fc157e37d0b052827b361246e5
ms.sourcegitcommit: c42c7176276ec4e1cc3360a93e6b15d32083bf9f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2017
---
# <a name="release-notes"></a>Versionshinweise

Hierbei handelt es sich um eine Liste der Änderungen, die in dieser Version an Azure PowerShell vorgenommen wurden.

## <a name="20171208-version-511"></a>08.12.2017 Version 5.1.1
* AnalysisServices
    - Der Validierungssatz des Speicherorts für die dynamische Suche wurde geändert, sodass alle Clouds unterstützt werden.
* Automation
    - Aktualisierung von Import-AzureRMAutomationRunbook
        - Unterstützung wird jetzt für Python2-Runbooks bereitgestellt.
* Batch
    - Ein Fehler wurde behoben, bei dem das automatische Erkennen der Ressourcengruppe für Kontovorgänge ohne eine Ressourcengruppe fehlgeschlagen ist.
* Compute
    - Get-AzureRmComputeResourceSku zeigt Zoneninformationen an.
    - Disable-AzureRmVmssDiskEncryption wurde zur Fehlerkorrektur aktualisiert: https://github.com/Azure/azure-powershell/issues/5038
    - -AsJob-Unterstützung wurde für Compute-Cmdlets mit langer Ausführungsdauer hinzugefügt. Ausgewählte Cmdlets können im Hintergrund ausgeführt werden und einen Auftrag zum Nachverfolgen und Kontrollieren des Fortschritts zurückgeben.
        - Die betroffenen Cmdlets umfassen die Cmdlets New-, Update-, Set-, Remove-, Start-, Restart-, Stop- für virtuelle Computer und VM-Skalierungsgruppen.
    - Ein vereinfachter Parametersatz wurde zu New-AzureRmVM hinzugefügt, der einen virtuellen Computer und alle erforderlichen Ressourcen mithilfe intelligenter Standardwerte erstellt.
* ContainerInstance
    - Azure-Containerinstanz-SDK 2017-10-01 wird angewendet.
        - Unterstützung der Containerausführung bis zum Abschluss
        - Unterstützung für Azure-Dateivolumebindung
        - Unterstützung für das Öffnen mehrerer Ports für die öffentliche IP-Adresse
* ContainerRegistry
    - Neue Cmdlets für die Georeplikation und Webhooks
        - Get/New/Remove-AzureRmContainerRegistryReplication
        - Get/New/Remove/Test/Update-AzureRmContainerRegistryWebhook
* DataFactories
    - Die Funktion zum Verschlüsseln von Anmeldeinformationen funktioniert jetzt sowohl bei aktiviertem (über das Netzwerk) als auch bei deaktiviertem Remotezugriff (lokaler Computer).
* DataFactoryV2
    - Zwei neue Cmdlets wurden hinzugefügt: Update-AzureRmDataFactoryV2 und Stop-AzureRmDataFactoryV2PipelineRun.
* DataLakeAnalytics
    - Ein Parameter namens ScriptParameter wurde zu Submit-AzureRmDataLakeAnalyticsJob hinzugefügt.
        - Ausführliche Informationen zu ScriptParameter finden Sie mit Get-Help zu Submit-AzureRmDataLakeAnalyticsJob.
    - Für New-AzureRmDataLakeAnalyticsAccount wurde der Parameter MaxDegreeOfParallelism in MaxAnalyticsUnits geändert.
        - Ein Alias wurde für den Parameter MaxAnalyticsUnits hinzugefügt: MaxDegreeOfParallelism.
    - Für New-AzureRmDataLakeAnalyticsComputePolicy wurde der Parameter MaxDegreeOfParallelismPerJob in MaxAnalyticsUnitsPerJob geändert.
        - Ein Alias wurde für den Parameter MaxAnalyticsUnitsPerJob hinzugefügt: MaxDegreeOfParallelismPerJob.
    - Für Set-AzureRmDataLakeAnalyticsAccount wurde der Parameter MaxDegreeOfParallelism in MaxAnalyticsUnits geändert.
        - Ein Alias wurde für den Parameter MaxAnalyticsUnits hinzugefügt: MaxDegreeOfParallelism.
    - Für Submit-AzureRmDataLakeAnalyticsJob wurde der Parameter DegreeOfParallelism in AnalyticsUnits geändert.
        - Ein Alias wurde für den Parameter AnalyticsUnits hinzugefügt: DegreeOfParallelism.
    - Für Update-AzureRmDataLakeAnalyticsComputePolicy wurde der Parameter MaxDegreeOfParallelismPerJob in MaxAnalyticsUnitsPerJob geändert.
        - Ein Alias wurde für den Parameter MaxAnalyticsUnitsPerJob hinzugefügt: MaxDegreeOfParallelismPerJob.
* MachineLearningCompute
    - Set-AzureRmMlOpCluster wurde hinzugefügt.
        - Aktualisiert die Clusteragentanzahl oder SSL-Konfiguration.
    - Orchestratoreigenschaften sind optional.
        - Der Dienst erstellt einen Dienstprinzipal, sofern keiner angegeben ist, sodass die Orchestratoreigenschaften jetzt optional sind.
* PowerBIEmbedded
    - Unterstützung für Power BI Embedded-Kapazitäts-Cmdlets wurde hinzugefügt.
    - Neues Cmdlet Get-AzureRmPowerBIEmbeddedCapacity – ruft die Details einer PowerBI Embedded-Kapazität ab.
    - Neues Cmdlet New-AzureRmPowerBIEmbeddedCapacity – erstellt eine neue PowerBI Embedded-Kapazität.
    - Neues Cmdlet Remove-AzureRmPowerBIEmbeddedCapacity – löscht eine Instanz der PowerBI Embedded-Kapazität.
    - Neues Cmdlet Resume-AzureRmPowerBIEmbeddedCapacity – setzt eine Instanz der PowerBI Embedded-Kapazität fort.
    - Neues Cmdlet Suspend-AzureRmPowerBIEmbeddedCapacity – hält eine Instanz der PowerBI Embedded-Kapazität an.
    - Neues Cmdlet Test-AzureRmPowerBIEmbeddedCapacity – testet das Vorhandensein einer Instanz der PowerBI Embedded-Kapazität.
    - Neues Cmdlet Update-AzureRmPowerBIEmbeddedCapacity – verändert eine Instanz der PowerBI Embedded-Kapazität.
* Profil
    - USGovernmentActiveDirectoryEndpoint wurde aktualisiert auf https://login.microsoftonline.us/.
        - Weitere Informationen zu den Azure Government-Endpunktzuordnungen finden Sie hier: https://docs.microsoft.com/en-us/azure/azure-government/documentation-government-developer-guide#endpoint-mapping.
    - -AsJob-Unterstützung für Cmdlets wurde hinzugefügt, wodurch bestimmte Cmdlets im Hintergrund ausgeführt werden und einen Auftrag zum Nachverfolgen und Kontrollieren des Fortschritts zurückgeben können.
    - Der Parameter -AsJob wurde zum Cmdlet Get-AzureRmSubscription hinzugefügt.
* RecoveryServices.Backup
    - Ein Fehler wurde behoben – Get-AzureRmRecoveryServicesBackupItem muss einen Vergleich für den Containernamenfilter ausführen, bei dem die Groß- und Kleinschreibung nicht beachtet wird.
    - Ein Fehler wurde behoben  – AzureVmItem verfügt jetzt über eine Eigenschaft, die anzeigt, wann das letzte Mal ein Sicherungsvorgang ausgeführt wurde: LastBackupTime.
* Ressourcen
    - Ein Fehler wurde behoben, bei dem Get-AzureRMRoleAssignment zu einer Zuweisung ohne einen Rollendefinitionsnamen für benutzerdefinierte Rollen führt.
        - Benutzer können jetzt Get-AzureRMRoleAssignment mit Zuweisungen mit Rollendefinitionsnamen verwenden, unabhängig vom Typ der Rolle.
    - Ein Fehler wurde behoben, bei dem Set-AzureRMRoleRoleDefinition einen Fehler ausgegeben hat (RD nicht gefunden), wenn assignablescopes einen neuen Bereich enthielt.
        - Benutzer können jetzt Set-AzureRMRoleRoleDefinition mit zuweisbaren Bereichen, einschließlich neuer Bereiche, unabhängig von der Position des Bereichs verwenden.
    - Bereiche, die mit „/“ enden, sind zulässig.
        - Benutzer können jetzt die Commandlets RoleDefinition und RoleAssignment mit Bereichen verwenden, die mit „/“ enden, konsistent mit der API und CLI.
    - Benutzer dürfen RoleAssignment mithilfe des Delegierungsflags erstellen.
        - Benutzer können jetzt New-AzureRMRoleAssignment mit einer Option zum Hinzufügen des Delegierungsflags verwenden.
    - RoleAssignment wurde korrigiert, sodass die Bereichsparameter respektiert werden.
    - Ein Alias für ServicePrincipalName wurde im Cmdlet New-AzureRmRoleAssignment hinzugefügt.
        - Benutzer können jetzt ApplicationId anstelle von ServicePrincipalName verwenden, wenn sie das Commandlet New-AzureRmRoleAssignment verwenden.
* SiteRecovery
    - Warnungen für veraltete Befehle wurden für alle Cmdlets in diesem Modul hinzugefügt als Vorbereitung für die nächste Version mit grundlegenden Änderungen.
        - Im Leitfaden zu anstehenden grundlegenden Änderungen finden Sie weitere Informationen dazu, wie Sie Ihre Cmdlets aus AzureRM migrieren können.
* Sql
    - Die Möglichkeit zum Umbenennen einer Datenbank mithilfe von Set-AzureRmSqlDatabase wurde hinzugefügt.
    - Ein Fehler wurde behoben: https://github.com/Azure/azure-powershell/issues/4974
        - Das Angeben eines ungültigen AUDIT_CHANGED_GROUP-Werts für Cmdlets zur Überwachung führt zu keinem Fehler mehr, dies wird in der nächsten Version entfernt.
    - Ein Fehler wurde behoben: https://github.com/Azure/azure-powershell/issues/5046
        - Der AuditAction-Parameter in Cmdlets zur Überwachung wird nicht mehr ignoriert.
    - Ein Fehler wurde in Cmdlets zur Überwachung behoben, wenn der StorageKeyType „Secondary“ angegeben wird.
        - Beim Festlegen der BLOB-Überwachung wurde der primäre Speicherkontoschlüssel verwendet anstelle des sekundären Schlüssels unter Angabe des Werts „Secondary“ für den Parameter StorageKeyType.
    - Die Formulierung für die Bestätigungsmeldung von Set-AzureRmSqlServerTransparentDataEncryptionProtector wurde geändert.
* Azure (RDFE)
    - Alle RemoteApp-Cmdlets wurden entfernt.
* Azure.Storage
    - Ein Upgrade auf Azure Storage-Clientbibliothek 8.6.0 und Azure Storage DataMovement-Bibliothek 0.6.5 wurde durchgeführt.

Änderungen seit der letzten Version: Änderungen seit der letzten Version: https://github.com/azure/azure-powershell/compare/v5.0.1-November2017...v5.1.1-December2017

## <a name="20171110-version-501"></a>10.11.2017 – Version 5.0.1
* Problem beim Laden von Assemblys behoben, das dazu führte, dass einige Cmdlets in den folgenden Modulen nicht erfolgreich ausgeführt werden konnten:
    - AzureRM.ApiManagement
    - AzureRM.Backup
    - AzureRM.Batch
    - AzureRM.Compute
    - AzureRM.DataFactories
    - AzureRM.HDInsight
    - AzureRM.KeyVault
    - AzureRM.RecoveryServices
    - AzureRM.RecoveryServices.Backup
    - AzureRM.RecoveryServices.SiteRecovery
    - AzureRM.RedisCache
    - AzureRM.SiteRecovery
    - AzureRM.Sql
    - AzureRM.Storage
    - AzureRM.StreamAnalytics

## <a name="2017118---version-500"></a>08.11.2017 – Version 5.0.0
* HINWEIS: Hierbei handelt es sich um eine Version mit grundlegenden Änderungen. Eine vollständige Liste mit den grundlegenden Änderungen finden Sie im Migrationshandbuch (https://aka.ms/azps-migration-guide).
* Alle Cmdlets im AzureRM unterstützen jetzt die Onlinehilfe.
    - Führen Sie „Get-Help“ mit dem Parameter „-Online“ aus, um die Onlinehilfe in Ihrem Standardinternetbrowser zu öffnen.
* AnalysisServices
    * Der Befehl „Synchronize-AzureAsInstance“ wurde korrigiert und kann mit der neuen AsAzure-REST-API für die Synchronisierung verwendet werden.
* ApiManagement
    * Informationen zu grundlegenden Änderungen, die in dieser Version für „ApiManagement“ vorgenommen wurden, finden Sie im Migrationshandbuch.
    * Das Cmdlet „Get-AzureRmApiManagementUser“ wurde aktualisiert, um folgendes Problem zu beheben: https://github.com/Azure/azure-powershell/issues/4510
    * Das Cmdlet „New-AzureRmApiManagementApi“ wurde aktualisiert, um die API-Erstellung mit leerem Pfad zu ermöglichen: https://github.com/Azure/azure-powershell/issues/4069
* ApplicationInsights
    * Befehle zum Abrufen/Erstellen/Entfernen von Application Insights-Ressourcen hinzugefügt
        - Get-AzureRmApplicationInsights
        - New-AzureRmApplicationInsights
        - Remove-AzureRmApplicationInsights
    * Befehle zum Abrufen/Aktualisieren von Preisen/Tagesobergrenzen von Application Insights-Ressourcen hinzugefügt
        - Get-AzureRmApplicationInsights -IncludeDailyCap
        - Set-AzureRmApplicationInsightsPricingPlan
        - Set-AzureRmApplicationInsightsDailyCap
    * Befehle zum Abrufen/Erstellen/Aktualisieren/Entfernen des fortlaufenden Exports von Application Insights-Ressourcen hinzugefügt
        - Get-AzureRmApplicationInsightsContinuousExport
        - Set-AzureRmApplicationInsightsContinuousExport
        - New-AzureRmApplicationInsightsContinuousExport
        - Remove-AzureRmApplicationInsightsContinuousExport
    * Befehle zum Abrufen/Erstellen/Entfernen der API-Schlüssel von Application Insights-Ressourcen hinzugefügt
        - Get-AzureRmApplicationInsightsApiKey
        - New-AzureRmApplicationInsightsApiKey
        - Remove-AzureRmApplicationInsightsApiKey
* AzureBatch
    * Neue Parameter zu `New-AzureRmBatchAccount` hinzugefügt
        - `PoolAllocationMode`: Der Zuordnungsmodus, der beim Erstellen von Pools im Batch-Konto verwendet werden soll. Wenn Sie ein Batch-Konto erstellen möchten, das Poolknoten im Abonnement des Benutzers zuordnet, legen Sie diesen Modus auf `UserSubscription` fest.
        - `KeyVaultId`: Die Ressourcen-ID des Azure-Schlüsseltresors, der dem Batch-Konto zugeordnet ist.
        - `KeyVaultUrl`: Die URL des Azure-Schlüsseltresors, der dem Batch-Konto zugeordnet ist.
    * Parameter für `New-AzureBatchTask` aktualisiert
        - Der Switch `RunElevated` wurde entfernt. Der Parameter `UserIdentity` wurde hinzugefügt und ersetzt `RunElevated`. Das entsprechende Verhalten kann erreicht werden, indem `PSUserIdentity` wie folgt konstruiert wird:
            - $autoUser = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoUserSpecification -ArgumentList @("Task", "Admin")
            - $userIdentity = New-Object Microsoft.Azure.Commands.Batch.Models.PSUserIdentity $autoUser
        - Der Parameter `AuthenticationTokenSettings` wurde hinzugefügt. Mit diesem Parameter können Sie angeben, dass der Batch-Dienst ein Authentifizierungstoken für die Aufgabe bereitstellen soll, wenn sie ausgeführt wird. Dadurch müssen keine Batch-Kontoschlüssel an die Aufgabe übergeben werden, um Anforderungen an den Batch-Dienst auszugeben.
        - Parameter `ContainerSettings` hinzugefügt
            - Mit diesem Parameter können Sie angeben, dass der Batch-Dienst die Aufgabe innerhalb eines Containers ausführen soll.
        - Parameter `OutputFiles` hinzugefügt
            - Mit diesem Parameter können Sie die Aufgabe so konfigurieren, dass sie nach Abschluss der Ausführung Dateien in Azure Storage hochlädt.
    * Parameter für `New-AzureBatchPool` aktualisiert
        - Parameter `UserAccounts` hinzugefügt
            - Dieser Parameter definiert Benutzerkonten, die auf den einzelnen Knoten im Pool erstellt werden.
        - `TargetLowPriorityComputeNodes` hinzugefügt und `TargetDedicated` in `TargetDedicatedComputeNodes` umbenannt.
            - `TargetDedicated`-Alias für den Parameter `TargetDedicatedComputeNodes` erstellt.
        - Parameter `NetworkConfiguration` hinzugefügt
            - Mit diesem Parameter können Sie die Netzwerkeinstellungen des Pools konfigurieren.
    * Parameter für `New-AzureBatchCertificate` aktualisiert
        - Der Parameter `Password` ist nun eine Zeichenfolge vom Typ `SecureString`.
    * Parameter für `New-AzureBatchComputeNodeUser` aktualisiert
        - Der Parameter `Password` ist nun eine Zeichenfolge vom Typ `SecureString`.
    * Parameter für `Set-AzureBatchComputeNodeUser` aktualisiert
        - Der Parameter `Password` ist nun eine Zeichenfolge vom Typ `SecureString`.
    * Parameter `Name` für `Get-AzureBatchNodeFile`, `Get-AzureBatchNodeFileContent` und `Remove-AzureBatchNodeFile` in `Path` umbenannt
        - `Name`-Alias für den Parameter `Path` erstellt
    * Objektänderungen
        - Die vollständige Liste finden Sie im Änderungsprotokoll von Batch.
    * Unterstützung für die Azure Active Directory-basierte Authentifizierung hinzugefügt.
        - Rufen Sie zur Verwendung der Azure Active Directory-Authentifizierung mithilfe des Cmdlets `Get-AzureRmBatchAccount` ein `BatchAccountContext`-Objekt ab, und übergeben Sie `BatchAccountContext` an den Parameter `-BatchContext` eines Batch-Dienst-Cmdlets. Die Azure Active Directory-Authentifizierung ist für Konten mit `PoolAllocationMode = UserSubscription` obligatorisch.
        - Für bereits vorhandene Konten oder neue Konten, die mit `PoolAllocationMode = BatchService` erstellt werden, können Sie weiterhin die Authentifizierung mit gemeinsam verwendetem Schlüssel verwenden, indem Sie mithilfe des Cmdlets `Get-AzureRmBatchAccoutKeys` ein `BatchAccountContext`-Objekt abrufen.
* Compute
    * Befehle der Azure Disk Encryption-Erweiterung
        - Neuer Parameter für „Set-AzureRmVmDiskEncryptionExtension“: „-EncryptFormatAll“ zum Verschlüsseln/Formatieren von Datenträgern
        - Neue Parameter für „Set-AzureRmVmDiskEncryptionExtension“: „-ExtensionPublisherName“ und „-ExtensionType“ zum Wechseln zu anderen Versionen der Erweiterung
        - Neue Parameter für „Disable-AzureRmVmDiskEncryption“: „-ExtensionPublisherName“ und „-ExtensionType“ zum Wechseln zu anderen Versionen der Erweiterung
        - Neue Parameter für „Get-AzureRmVmDiskEncryptionStatus“: „-ExtensionPublisherName“ und „-ExtensionType“ zum Wechseln zu anderen Versionen der Erweiterung
* DataLakeAnalytics
    * Informationen zu grundlegenden Änderungen, die in dieser Version für „DataLakeAnalytics“ vorgenommen wurden, finden Sie im Migrationshandbuch.
    * Einer der beiden Ausgabetypen von „Get-AzureRmDataLakeAnalyticsAccount“ wurde geändert.
        - Von „List\<DataLakeAnalyticsAccount>“ in „List\<PSDataLakeAnalyticsAccountBasic>“
        - Bei den Eigenschaften von „PSDataLakeAnalyticsAccountBasic“ handelt es sich um eine echte Teilmenge der Eigenschaften von „DataLakeAnalyticsAccount“.
        - Die zusätzlichen Eigenschaften in „DataLakeAnalyticsAccount“ werden von dem Dienst nicht zurückgegeben.  Diese Änderung dient dazu, dies korrekt wiederzugeben. Die zusätzlichen Eigenschaften sind zwar weiterhin in „PSDataLakeAnalyticsAccountBasic“ enthalten, werden aber als veraltet gekennzeichnet.
    * Einer der beiden Ausgabetypen von „Get-AzureRmDataLakeAnalyticsJob“ wurde geändert.
        - Von „List\<JobInformation>“ in „List\<PSJobInformationBasic>“
        - Bei den Eigenschaften von „PSJobInformationBasic“ handelt es sich um eine echte Teilmenge der Eigenschaften von „JobInformation“.
        - Die zusätzlichen Eigenschaften in „JobInformation“ werden von dem Dienst nicht zurückgegeben.  Diese Änderung dient dazu, dies korrekt wiederzugeben. Die zusätzlichen Eigenschaften sind zwar weiterhin in „PSJobInformationBasic“ enthalten, werden aber als veraltet gekennzeichnet.
* DataLakeStore
    * Informationen zu grundlegenden Änderungen, die in dieser Version für „DataLakeStore“ vorgenommen wurden, finden Sie im Migrationshandbuch.
    * Einer der beiden Ausgabetypen von „Get-AzureRmDataLakeStoreAccount“ wurde geändert.
        - Von „List\<PSDataLakeStoreAccount>“ in „List\<PSDataLakeStoreAccountBasic>“
        - Bei den Eigenschaften von „PSDataLakeStoreAccountBasic“ handelt es sich um eine echte Teilmenge der Eigenschaften von „PSDataLakeStoreAccount“.
        - Die zusätzlichen Eigenschaften in „PSDataLakeStoreAccount“ werden von dem Dienst nicht zurückgegeben.  Diese Änderung dient dazu, dies korrekt wiederzugeben. Die zusätzlichen Eigenschaften sind zwar weiterhin in „PSDataLakeStoreAccountBasic“ enthalten, werden aber als veraltet gekennzeichnet.
* Dns
    * Unterstützung für CAA-Eintragstypen in Azure DNS
       - Unterstützt alle Vorgänge für CAA-Eintragstypen
* EventHub
    * Informationen zu grundlegenden Änderungen, die in dieser Version für „EventHub“ vorgenommen wurden, finden Sie im Migrationshandbuch.
* Erkenntnisse
    * Informationen zu grundlegenden Änderungen, die in dieser Version für „Insights“ vorgenommen wurden, finden Sie im Migrationshandbuch.
* Netzwerk
    * Informationen zu grundlegenden Änderungen, die in dieser Version für die Netzwerkkomponente vorgenommen wurden, finden Sie im Migrationshandbuch.
    * Cmdlet hinzugefügt, mit dem verfügbare Internetdienstanbieter für eine bestimmte Azure-Region aufgeführt werden können
        - Get-AzureRmNetworkWatcherReachabilityProvidersList
    * Cmdlet hinzugefügt, mit dem der relative Wartezeitwert für Internetdienstanbieter zwischen einem bestimmten Standort und Azure-Regionen abgerufen werden kann
        - Get-AzureRmNetworkWatcherReachabilityReport
* Profil
    - Set-AzureRmDefault
        - Verwenden Sie dieses Cmdlet, um eine Standardressourcengruppe festzulegen.  Dadurch wird der Parameter „-ResourceGroup“ für einige Cmdlets optional, und es wird der Standardwert verwendet, wenn keine Ressourcengruppe angegeben ist.
        - ```Set-AzureRmDefault -ResourceGroupName "ExampleResourceGroup"```
        - Wenn die angegebene Ressourcengruppe im Abonnement vorhanden ist, wird sie als Standard festgelegt.  Andernfalls wird die Ressourcengruppe erstellt und als Standard festgelegt.
    - Get-AzureRmDefault
        - Verwenden Sie dieses Cmdlet, um die aktuelle Standardressourcengruppe (und später auch andere Standardwerte) abzurufen.
        - ```Get-AzureRmDefault -ResourceGroup```
    - Clear-AzureRmDefault
        - Verwenden Sie dieses Cmdlet, um die aktuelle Standardressourcengruppe zu entfernen.
        - ```Clear-AzureRmDefault -ResourceGroup```
    - „Add-AzureRmEnvironment“ und „Set-AzureRmEnvironment“
        - Fügen Sie den Parameter „BatchAudience“ hinzu, um die Active Directory-Zielgruppe für Azure Batch anzugeben, die beim Abrufen von Authentifizierungstoken für den Batch-Dienst verwendet werden soll.
* RecoveryServices.Backup
    * Cmdlets für die sofortige Dateiwiederherstellung hinzugefügt
        - Get-AzureRmRecoveryServicesBackupRPMountScript
        - Disable-AzureRmRecoveryServicesBackupRPMountScript
    * SDK-Version für „RecoveryServices.Backup“ auf die neueste Version aktualisiert
    * Tests für die Workload virtueller Azure-Computer aktualisiert, sodass alle für Testläufe erforderlichen Einrichtungsschritte automatisch durchgeführt werden
    * Folgendes Problem behoben: https://github.com/Azure/azure-powershell/issues/3164
* RecoveryServices.SiteRecovery
    * Änderungen für ASR VMware zu Azure Site Recovery (Cmdlets unterstützen derzeit Vorgänge für Unternehmen zu Unternehmen, Unternehmen zu Azure und Hyper-V zu Azure)
        - New-AzureRmRecoveryServicesAsrPolicy
        - New-AzureRmRecoveryServicesAsrProtectedItem
        - Update-AzureRmRecoveryServicesAsrPolicy
        - Update-AzureRmRecoveryServicesAsrProtectionDirection
    * Unterstützung für AAD-basierten Tresor hinzugefügt
    * Cmdlets zum Verwalten von VCenter-Ressourcen hinzugefügt
        - Get-AzureRmRecoveryServicesAsrVCenter
        - New-AzureRmRecoveryServicesAsrVCenter
        - Remove-AzureRmRecoveryServicesAsrVCenter
        - Update-AzureRmRecoveryServicesAsrVCenter
    * Weitere Cmdlets hinzugefügt
        - Get-AzureRmRecoveryServicesAsrAlertSetting
        - Get-AzureRmRecoveryServicesAsrEvent
        - New-AzureRmRecoveryServicesAsrProtectableItem
        - Set-AzureRmRecoveryServicesAsrAlertSetting
        - Start-AzureRmRecoveryServicesAsrResynchronizeReplicationJob
        - Start-AzureRmRecoveryServicesAsrSwitchProcessServerJob
        - Start-AzureRmRecoveryServicesAsrTestFailoverCleanupJob
        - Update-AzureRmRecoveryServicesAsrMobilityService
* ServiceBus
    - Informationen zu grundlegenden Änderungen, die in dieser Version für „ServiceBus“ vorgenommen wurden, finden Sie im Migrationshandbuch.
* Sql
    * Unterstützung für das Auflisten und Abbrechen des asynchronen updateslo-Vorgangs für die Datenbank hinzugefügt
        - Vorhandenes Cmdlet „Get-AzureRmSqlDatabaseActivity“ aktualisiert, um den updateslo-Vorgangsstatus der Datenbank zurückgegeben
        - Neues Cmdlet „Stop-AzureRmSqlDatabaseActivity“ zum Abbrechen des asynchronen updateslo-Vorgangs für die Datenbank hinzugefügt
    * Unterstützung für Zonenredundanz für Datenbanken und Pools für elastische Datenbanken hinzugefügt
        - Switch-Parameter „ZoneRedundant“ zu „New-AzureRmSqlDatabase“ hinzugefügt
        - Switch-Parameter „ZoneRedundant“ zu „Set-AzureRmSqlDatabase“ hinzugefügt
        - Switch-Parameter „ZoneRedundant“ zu „New-AzureRmSqlElasticPool“ hinzugefügt
        - Switch-Parameter „ZoneRedundant“ zu „Set-AzureRmSqlElasticPool“ hinzugefügt
    * Unterstützung für Server-DNS-Aliase hinzugefügt
        - Cmdlet „Get-AzureRmSqlServerDnsAlias“ hinzugefügt, um Server-DNS-Aliase nach Server und Aliasname oder eine Liste mit Server-DNS-Aliasen für eine Azure SQL Server-Instanz abzurufen
        - Cmdlet „New-AzureRmSqlServerDnsAlias“ zum Erstellen eines neuen Server-DNS-Alias für eine bestimmte Azure SQL Server-Instanz hinzugefügt
        - Cmdlet „Set-AzurermSqlServerDnsAlias“ hinzugefügt, um die Aktualisierung einer Azure SQL Server-Instanz zu ermöglichen, auf die der Server-DNS-Alias verweist
        - Cmdlet „Remove-AzureRmSqlServerDnsAlias“ zum Entfernen eines Server-DNS-Alias für eine Azure SQL Server-Instanz hinzugefügt
* Azure.Storage
    * Upgrade auf Azure Storage-Clientbibliothek 8.5.0 und Azure Storage DataMovement-Bibliothek 0.6.3 durchgeführt
    * Supportfeature für Dateifreigabemomentaufnahmen hinzugefügt
        - Parameter „SnapshotTime“ zu „Get-AzureStorageShare“ hinzugefügt
        - Parameter „IncludeAllSnapshot“ zu „Remove-AzureStorageShare“ hinzugefügt
