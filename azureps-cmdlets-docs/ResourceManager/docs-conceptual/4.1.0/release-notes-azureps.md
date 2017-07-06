---
title: "Azure PowerShell-Änderungsprotokoll | Microsoft-Dokumentation"
description: "Hierbei handelt es sich um einen Verlauf der Änderungen, die in der neuesten Version an Azure PowerShell vorgenommen wurden."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.service: azure-resource-manager
ms.product: azure
ms.devlang: powershell
ms.topic: conceptual
ms.workload: 
ms.date: 05/18/2017
ms.openlocfilehash: 5c8fa2a5a8f94cd24b66f42c237749a7b89af3b3
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2017
---
# <a name="release-notes"></a>Versionshinweise

Hierbei handelt es sich um eine Liste der Änderungen, die in dieser Version an Azure PowerShell vorgenommen wurden.

## <a name="version-400"></a>Version 4.0.0

* Diese Version enthält wichtige Änderungen. Im [Migrationshandbuch](https://aka.ms/azps-migration-guide) finden Sie Änderungsdetails sowie die Auswirkung auf vorhandene Skripts.
* ApiManagement
  - Unterstützung für das Konfigurieren externer Gruppen in „New-AzureRmApiManagementGroup“ hinzugefügt.
* Abrechnung
  - Neues Cmdlet „Get-AzureRmBillingPeriod“
    + Cmdlet zum Abrufen von Azure-Abrechnungszeiträumen im Abonnement.
  - Cmdlet „Get-AzureRmBillingInvoice“ aktualisiert
  - Neue Eigenschaft „BillingPeriodNames“
  - Ausgabe in Listenansicht
* Compute
  - Cmdlets „Set-AzureRmVMAEMExtension“ und „Test-AzureRmVMAEMExtension“ für die Unterstützung von Premium Managed Disks aktualisiert
  - Sichern von Verschlüsselungseinstellungen für IaaS-VMs und Wiederherstellen bei einem Fehler
  - Die Option „ChefServiceInterval“ wurde in „ChefDaemonInterval“ umbenannt. Die alte Bezeichnung funktioniert jedoch weiterhin.
  - Die duplizierten Eigenschaften „DataDiskNames“ und „NetworkInterfaceIDs“ wurden aus dem PowerShell-Objekt „VM“ entfernt.
  - Die Parameter „DataDiskNames“ und „NetworkInterfaceIDs“ wurden in „Remove-AzureRmVMDataDisk“ bzw. „Remove-AzureRmVMNetworkInterface“ in optional geändert.
  - Das Weiterleitungsproblem von „Get“-Cmdlets, wenn diese ein Listenobjekt zurückgeben, wurde behoben.
  - Cmdlets, die in Konflikt mit RDFE-Cmdlets stehen, wurden umbenannt. Weitere Details zum Problem finden Sie unter „https://github.com/Azure/azure-powershell/issues/2917“
    + `New-AzureVMSqlServerAutoBackupConfig` wurde in `New-AzureRmVMSqlServerAutoBackupConfig` umbenannt.
    + `New-AzureVMSqlServerAutoPatchingConfig` wurde in `New-AzureRmVMSqlServerAutoPatchingConfig` umbenannt.
    + `New-AzureVMSqlServerKeyVaultCredentialConfig` wurde in `New-AzureRmVMSqlServerKeyVaultCredentialConfig` umbenannt.
* Nutzung
  - Neues Cmdlet „Get-AzureRmConsumptionUsageDetail“
    + Cmdlet zum Abrufen der Nutzungsdetails des Abonnements.
* ContainerRegistry
  - PowerShell-Cmdlets für Azure-Containerregistrierung hinzugefügt
    + New-AzureRmContainerRegistry
    + Get-AzureRmContainerRegistry
    + Update-AzureRmContainerRegistry
    + Remove-AzureRmContainerRegistry
    + Get-AzureRmContainerRegistryCredential
    + Update-AzureRmContainerRegistryCredential
    + Test-AzureRmContainerRegistryNameAvailability
* DataLakeAnalytics
  - Unterstützung für „get“ und „list“ für Katalogpaket hinzugefügt
  - Unterstützung für das Auflisten der folgenden Katalogelemente aus tieferen Vorgängern hinzugefügt:
    + Table
    + Tabellenwertfunktion (TVF)
    + Sicht
    + Statistiken
* DataLakeStore
  - Für `Import-AzureRMDataLakeStoreItem` und `Export-AzureRMDataLakeStoreItem` wurde die Ablaufverfolgungsprotokollierung zur Verbesserung der Leistung standardmäßig deaktiviert. Wenn die Ablaufprotokollierung gewünscht ist, verwenden Sie die Parameter `-DiagnosticLogLevel` und `-DiagnosticLogPath`
  - Fehler korrigiert, der mitunter den Absturz von PowerShell verursachte, wenn viele kleine Dateien in AD LS hochgeladen wurden.
* EventHub
  - Fehlerbehebung:
    + Korrektur für Fehler im Cmdlet „Set-AzureRmEventHubNamespace“: 'Tarif' darf nicht NULL sein, wenn es 'SKU-Name' sein sollte
    + Set-AzureRmEventHub: Korrektur für den Fehler „Der Objektverweis ist nicht auf eine Objektinstanz festgelegt“ beim Aktualisieren von EventHub
* Einblicke
  - Add-AzureRm*AlertRule
    + Gibt ein einzelnes Objekt zurück: newResource, statusCode, requestId
  - Get-AzureRmAlertRule
    + Die Ausgabe wird jetzt aufgezählt und nicht mehr als einzelnes Objekt betrachtet. Der Typ wurde nicht geändert, es ist immer noch eine Liste.
  - Remove-AzureRmAlertRule
    + Auf den Statuscode folgt der von der Anforderung zurückgegebene Statuscode. Vorher war dieser stets „OK“.
  - Add-AzureRmAutoscaleSetting
    + Gibt jetzt ein einzelnes Objekt (keine Liste wie zuvor) mit „statusCode“, „requestId“ und der neu erstellten/aktualisierten Ressource zurück.
    + Auf den Statuscode folgt der von der Anforderung zurückgegebene Status. Vorher war dieser stets „OK“.
  - New-AzureRmAutoscaleRule
    + Der Parameter „ScaleActionType“ wurde erweitert und empfängt nun die folgenden Werte: ChangeCount, PercentChangeCount, ExactCount.
  - Remove-AzureRmAutoscaleSetting
    + Auf den Statuscode in der Ausgabe folgt der von der Anforderung zurückgegebene Statuscode. Vorher war dieser stets „OK“.
  - Get-AzureRmLogProfile
    + Die Ausgabe wird jetzt aufgezählt. Zuvor wurde sie als einzelnes Objekt betrachtet. Der Typ der Ausgabe bleibt wie zuvor eine Liste.
  - Remove-AzureRmLogProfile
    + Der Parameter „PassThru“ wurde implementiert.
  - Metrik-API
    + Das SDK ruft nun Metriken aus der Masterdatenverwaltung (MDM) ab.
  - Get-AzureRmMetricDefinition
    + Die Ausgabe ist weiterhin eine Liste, aber die Struktur der Liste hat sich geändert.
  - Get-AzureRmMetric
    + Der Aufruf wurde geändert. Die neue Syntax lautet: Get-AzureRmMetric ResourceId [MetricNames [TimeGrain] [AggregationType] [StartTime] [EndTime]] [DetailedOutput]
    + Die Ausgabe ist eine Liste, und die Struktur der Elemente hat sich geändert.
* KeyVault
  - Unterstützung für die Sicherung/Wiederherstellung von KeyVault-Geheimnissen hinzugefügt
    + Geheimnisse können entsprechend der derzeit für Schlüssel unterstützten Funktionen gesichert und wiederhergestellt werden

  - Cmdlets für die Sicherung von Schlüsseln und Geheimnissen akzeptieren nun ein entsprechendes Objekt als Eingabeparameter
    + Der Aufrufer kann Abruf- und Sicherungsvorgänge verketten: Get-AzureKeyVaultKey -VaultName myVault -Name myKey | Backup-AzureKeyVaultKey

  - Cmdlets für die Sicherung unterstützen nun den Schalter „-Force“, um eine vorhandene Datei zu überschreiben
    + Beachten Sie, dass beim Versuch des Überschreibens einer vorhandenen Datei keine Ausnahme mehr ausgelöst wird, sondern der Benutzer zur Entscheidung aufgefordert wird, wie fortgefahren werden soll.
* LogicApp
  - Neue Parameter für Cmdlets für die Notfallwiederherstellung von Austauschkontrollnummern:
    + Optionaler Parameter „-AgreementType“ (X12 oder Edifact) zum Angeben der relevanten Kontrollnummern
* MachineLearning
  - Neue Version des Azure Machine Learning .NET SDK wird genutzt, und ein neues Cmdlet wurde hinzugefügt
    + Add-AzureRmMlWebServiceRegionalProperty
  - Kleinere Formulierungskorrekturen im Hilfetext.
* Netzwerk
  - Cmdlet „Test-AzureRmNetworkWatcherConnectivity“ hinzugefügt
    + Gibt Verbindungsinformationen für eine angegebene Quell-VM und ein Ziel zurück
    + Wenn die Verbindung zwischen Quelle und Ziel nicht hergestellt werden kann, gibt das Cmdlet Einzelheiten zum Problem zurück
* Profil
  - Cmdlet „Send-Feedback“ hinzugefügt: Ermöglicht einem Benutzer das Auslösen einer Reihe von Aufforderungen zum Senden von Feedback an das Azure PowerShell-Team.
  - Die folgenden Aliase wurden entfernt, da sie mit vorhandenen Cmdlet-Namen im Azure-Modul in Konflikt stehen:
    + `Enable-AzureDataCollection` (unterstützt von `Enable-AzureRmDataCollection`)
    + `Disable-AzureDataCollection` (unterstützt von `Disable-AzureRmDataCollection`)
* Relay
  - Cmdlets für Azure Relay hinzugefügt, die Benutzern das Erstellen und Verwalten sämtlicher Azure Relay-Ressourcen erlauben.
    + `New-AzureRmRelayNamespace`
    + `Get-AzureRmRelayNamespace`
    + `Set-AzureRmRelayNamespace`
    + `Remove-AzureRmRelayNamespace`
    + `New-AzureRmWcfRelay`
    + `Get-AzureRmWcfRelay`
    + `Set-AzureRmWcfRelay`
    + `Remove-AzureRmWcfRelay`
    + `New-AzureRmRelayHybridConnection`
    + `Get-AzureRmRelayHybridConnection`
    + `Set-AzureRmRelayHybridConnection`
    + `Remove-AzureRmRelayHybridConnection`
    + `Test-AzureRmRelayName`
    + `Get-AzureRmRelayOperation`
    + `New-AzureRmRelayKey`
    + `Get-AzureRmRelayKey`
    + `New-AzureRmRelayAuthorizationRule`
    + `Get-AzureRmRelayAuthorizationRule`
    + `Set-AzureRmRelayAuthorizationRule`
    + `Remove-AzureRmRelayAuthorizationRule`
* Ressourcen
  - Unterstützung für ressourcengruppenübergreifende Bereitstellungen für „New-AzureRmResourceGroupDeployment“
    + Benutzer können jetzt geschachtelte Bereitstellungen verwenden, um verschiedene Ressourcengruppen bereitzustellen.
* ServiceBus

  - Fehlerbehebung: Eigenschaftswerte des ServiceBus-Warteschlangenobjekts wurden auf NULL festgelegt. Das Objekt wird als Eingabeparameter im Cmdlet „AzureRmServiceBusQueue“ verwendet, um die Warteschlange zu aktualisieren.
   - Betroffene Eigenschaften: LockDuration, EntityAvailabilityStatus, DuplicateDetectionHistoryTimeWindow, MaxDeliveryCount und MessageCount
* ServiceFabric

  - Cmdlets für Service Fabric hinzugefügt
    + Add-AzureRmServiceFabricApplicationCertificate: Fügt ein Zertifikat hinzu, das als Anwendungszertifikat verwendet wird
    + Add-AzureRmServiceFabricClientCertificate: Fügt den Clustereinstellungen einen allgemeinen Namen oder Fingerabdruck für die Clientauthentifizierung hinzu
    + Add-AzureRmServiceFabricClusterCertificate: Fügt dem Cluster ein sekundäres Clusterzertifikat hinzu, um das vorhandene Zertifikat zu verlängern
    + Add-AzureRmServiceFabricNodes: Fügt einem Cluster Knoten/VMs eines bestimmten Knotentyps hinzu
    + Add-AzureRmServiceFabricNodeType: Fügt einem vorhandenen Cluster einen Knotentyp bzw. VMs hinzu
    + Get-AzureRmServiceFabricCluster: Ruft die Details der Clusterressource ab
    + New-AzureRmServiceFabricCluster: Erstellt einen neuen ServiceFabric-Cluster. Dieser Befehl hat viele Überladungen, um verschiedene Szenarien abzudecken
    + Remove-AzureRmServiceFabricClientCertificate: Entfernt ein Clientzertifikat, damit es nicht für den Zugriff auf einen Cluster verwendet wird
    + Remove-AzureRmServiceFabricClusterCertificate: Entfernt ein Clusterzertifikat, damit es nicht für die Clustersicherheit verwendet wird
    + Remove-AzureRmServiceFabricNodes: Entfernt Knoten eines bestimmten Knotentyps aus einem Cluster
    + Remove-AzureRmServiceFabricNodeType: Entfernt einen Knotentyp aus einem Cluster
    + Remove-AzureRmServiceFabricSettings: Entfernt eine oder mehrere ServiceFabric-Einstellungen aus einem Cluster
    + Set-AzureRmServiceFabricSettings: Dient zum Hinzufügen oder Aktualisieren einer oder mehrerer ServiceFabric-Einstellungen eines Clusters
    + Set-AzureRmServiceFabricUpgradeType: Ändert den ServiceFabric-Upgradetyp eines Clusters
    + Update-AzureRmServiceFabricDurability: Ändert die Dauerhaftigkeitsstufe eines Clusters
    + Update-AzureRmServiceFabricReliability: Ändert die Zuverlässigkeitsstufe eines Clusters
* Sql
  - „New-AzureRmSqlDatabase“ wurde der Parameter „-SampleName“ hinzugefügt
  - Updates für Failovergruppen-Cmdlets
  - „Tag“-Parameter entfernt
  - Aus dem Cmdlet „Remove-AzureRmSqlDatabaseFailoverGroup“ wurden die Parameter „PartnerResourceGroupName“ und „PartnerServerName“ entfernt
  - Den Cmdlets „New-“ und „Set-“ wurde der Parameter „GracePeriodWithDataLossHours“ hinzugefügt, durch den „GracePeriodWithDataLossHour“ letztendlich ersetzt wird
  - Dokumentation wurde konkretisiert und aktualisiert
  - Die Formatierung zurückgegebener Objekte wurde geändert, und einige Fehler wurden behoben, bei denen Felder nicht immer aufgefüllt wurden
  - Dem Objekt „FailoverGroup“ wurden die Eigenschaften „DatabaseNames“ und „PartnerLocation“ hinzugefügt
  - Korrektur eines Fehlers, der bewirkte, dass das Cmdlet „Switch-“ sofort eine Rückgabe lieferte, anstatt auf den Abschluss des Vorgangs zu warten
  - Überlauffehler bei ganzen Zahlen behoben, wenn hohe Werte für die Toleranzperiode verwendet werden
  - Die Toleranzperiode wird auf mindestens 1 Stunde angepasst, wenn eine kürzere angegeben wird
  - „Usage_Anomaly“ aus den akzeptierten Werten für den Parameter „ExcludedDetectionType“ für die Cmdlets „Set-AzureRmSqlDatabaseThreatDetectionPolicy“ und „Set-AzureRmSqlServerThreatDetectionPolicy“ entfernt.
* Speicher
  - Aktualisierung des SRP SDK auf 6.3.0
  - New/Set-AzureRmStorageAccount: Neuen Parameter zur Unterstützung von „EnableHttpsTrafficOnly“ hinzugefügt
  - New/Set/Get-AzureRmStorageAccount: Zurückgegebenes Speicherkonto enthält das neue Attribut „EnableHttpsTrafficOnly“
* Azure.Storage
  - Upgrade auf Azure Storage-Clientbibliothek 8.1.1 und Azure Storage DataMovement-Bibliothek 0.5.1
  - Neues Cmdlet zum Unterstützen der Blobfunktion „Inkrementelles Kopieren“
