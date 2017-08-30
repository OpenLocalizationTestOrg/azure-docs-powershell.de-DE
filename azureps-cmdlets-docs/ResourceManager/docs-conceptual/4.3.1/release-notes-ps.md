Azure PowerShell 4.3.1-Installationsprogramm: [Link](https://github.com/Azure/azure-powershell/releases/download/v4.3.1-August2017/azure-powershell.4.3.1.msi)

Katalog-Modul für ARM-Cmdlets: [Link](https://www.powershellgallery.com/packages/AzureRM/4.3.1)

Katalog-Modul für Legacy-Cmdlets für die Dienstverwaltung (RDFE): [Link](https://www.powershellgallery.com/packages/Azure/4.3.1)

## <a name="changes-in-431"></a>Änderungen in Version 4.3.1

- Problem behoben, bei dem bestimmte Assemblys nicht signiert werden und beim Modulimport einen `could not load file or assembly`-Fehler verursachen

## <a name="changes-in-430"></a>Änderungen in Version 4.3.0

* AnalysisServices
    * Fehler in „Set-AzureRmAnalysisServciesServer“ behoben
        - Wenn kein Administrator angegeben wurde, wird der Administrator entfernt.
    * „BackupBlobContainerUri“ zu „New-AzureRmAnalysisServicesServer“ und „Set-AzureRmAnalysisServicesServer“ hinzugefügt
        - Diese Option muss zum Festlegen bzw. Deaktivieren des Sicherungsblobcontainers für die Sicherung bzw. Wiederherstellung des Azure Analysis Services-Servers aktiviert werden.
    * SKU-Suche in „New-AzureRmAnalysisServicesServer“ und „Set-AzureRmAnalysisServicesServer“ aktualisiert
        - Die hartcodierte SKU in der dynamischen Suche wurde geändert.
    * „Add-AzureAnalysisServicesAccount“ zur Unterstützung der Anmeldung mit einem Dienstprinzipal
* Automation
    * Änderungen an AutomationDSC*-Cmdlets, damit mehr als 100 Datensätze abgerufen werden können
    * Das Problem, bei dem nach dem Aufrufen einiger Automation-Cmdlets (z.B. „Get-AzureRmAutomationVariable“, „Get-AzureRmAutomationJob“) die Verbose-Streams nicht mehr funktionieren, wurde behoben.
    * Unterstützung für die Verwaltung des Knotenkonfigurationsbuilds in StartAzureAutomationDscCompilationJob und ImportAzureAutomationDscNodeConfiguration wurde hinzugefügt.
    * Fehlerbehebungen für vorhandene Probleme – Korrektur des Problems mit Alias #3775 und runOn-Alias, Unterstützung für Hybrid Worker.
* Compute
    * Set-AzureRmVMAEMExtension: Unterstützung für neue Premium-Datenträgergrößen hinzugefügt
    * Set-AzureRmVMAEMExtension: Unterstützung für die M-Serie hinzugefügt
    * ForceUpdateTag-Parameter zu „Add-AzureRmVmssExtension“ hinzugefügt
    * Primary-Parameter zu „New-AzureRmVmssIpConfig“ hinzugefügt
    * „EnableAcceleratedNetworking-Parameter“ zu „Add-AzureRmVmssNetworkInterfaceConfig“ hinzugefügt
    * „InstanceId“ zu „Set-AzureRmVmss“ hinzugefügt
    * „MaintenanceRedeployStatus“ für die Ausgabe von „Get-AzureRmVM -Status“ verfügbar gemacht
    * Einschränkungen und Funktionen für das Tabellenformat von „Get-AzureRmComputeResourceSku“ verfügbar gemacht
* DataLakeStore
    * Behebung für das Problem: https://github.com/Azure/azure-powershell/issues/4323
* EventHub
    * ResourceGroup-Eigenschaft zu „NamespaceAttributes“ hinzugefügt
        - „ResourceGroup“ ruft den Namen der Ressourcengruppe ab, in der sich der Namespace befindet.
    * Cmdlets wurden mit neuen Parametern sowie Parameteraliasen aktualisiert.
        - Die folgenden Cmdlets wurden mit Parametersätzen für „NameSpace“ und „EventHub“ für AuthorizationRule aktualisiert.
        - New-AzureRmEventHubAuthorizationRule
            + Fügt eine neue AuthorizationRule zum vorhandenen Attribut „NameSpace“ oder „EventHub“ hinzu.
        - Get-AzureRmEventHubAuthorizationRule
            + Ruft AuthorizationRule bzw. eine Liste von AuthorizationRules für das vorhandene Attribut „NameSpace“ oder „EventHub“ ab.
        - Set-AzureRmEventHubAuthorizationRule
            + Aktualisiert die Eigenschaften einer vorhandenen AuthorizationRule des Attributs „EventHub“ und „NameSpace“.
        - Remove-AzureRmEventHubAuthorizationRule
            + Löscht die vorhandene AuthorizationRule des vorhandenen Attributs „NameSpace“ oder „EventHub“.
        - New-AzureRmEventHubKey
            + Generiert einen neuen primären/sekundären Schlüssel für die AuthorizationRule des vorhandenen Attributs „NameSpace“ oder „EventHub“.
        - Get-AzureRmEventHubKey
            + Ruft einen primären/sekundären Schlüssel für die AuthorizationRule des vorhandenen Attributs „NameSpace“ oder „EventHub“ ab.
* Netzwerk
    * New-AzureRmExpressRouteCircuitPeeringConfig: Unterstützung für IPv6 wurde hinzugefügt. Neuer optionaler Parameter hinzugefügt
        - PeerAddressType
    * Set-AzureRmExpressRouteCircuitPeeringConfig: Unterstützung für IPv6 hinzugefügt. Neuer optionaler Parameter hinzugefügt
        - PeerAddressType
    * Remove-AzureRmExpressRouteCircuitPeeringConfig: Unterstützung für IPv6 hinzugefügt. Neuer optionaler Parameter hinzugefügt
        - PeerAddressType
    * Parameter „-ProbeEnabled“ als veraltet markiert
        - Add-AzureRmApplicationGatewayBackendHttpSettings
        - New-AzureRmApplicationGatewayBackendHttpSettings
        - Set-AzureRmApplicationGatewayBackendHttpSettings
* Profil
    * Die Datensammlung wurde standardmäßig aktiviert. Zur Verbesserung der Benutzerfreundlichkeit werden Nutzungsdaten von Microsoft gesammelt. Die Daten sind anonymisiert und enthalten keine Befehlszeilenargument-Werte.
        - Verwenden Sie das Cmdlet „Disable-AzureRmDataCollection“, um die Funktion zu deaktivieren.
        - Verwenden Sie das Cmdlet „Enable-AzureRmDataCollection“, um diese Funktion zu aktivieren.
* Ressourcen
    * Unterstützung zum Überprüfen von Bereichen für die folgenden roledefinition- und roleassignment-Cmdlets vor dem Senden der Anforderung an ARM hinzugefügt
        - Get-AzureRMRoleAssignment
        - New-AzureRMRoleAssignment
        - Remove-AzureRMRoleAssignment
        - Get-AzureRMRoleDefinition
        - New-AzureRMRoleDefinition
        - Remove-AzureRMRoleDefinition
        - Set-AzureRMRoleDefinition
* ServiceBus
    * Es wurden die folgenden neuen Cmdlets für AuthorizationRules für „NameSpace“, „Queue“ und „Topic“ hinzugefügt. Die Autorisierungsregelvorgänge werden gemäß dem Parametersatz ausgeführt.
     - New-AzureRmServiceBusAuthorizationRule
       - Eine neue AuthorizationRule wurde zum vorhandenen ServiceBus-Attribut „NameSpace“, „Queue“ oder „Topic“ hinzugefügt.
     - Get-AzureRmServiceBusAuthorizationRule
       - Ruft die AuthorizationRule bzw. eine Liste von AuthorizationRules für das vorhandene ServiceBus-Attribut „NameSpace“, „Queue“ oder „Topic“ ab.
     - Set-AzureRmServiceBusAuthorizationRule
       - Aktualisiert die Eigenschaften einer vorhandenen AuthorizationRule des ServiceBus-Attributs „NameSpace“, „Queue“ oder „Topic“.
     - New-AzureRmServiceBusKey
       - Generiert einen neuen primären/sekundären Schlüssel für die AuthorizationRule des vorhandenen ServiceBus-Attributs „NameSpace“, „Queue“ oder „Topic“.
     - Get-AzureRmServiceBusKey
       - Ruft den primären/sekundären Schlüssel für die AuthorizationRule des vorhandenen ServiceBus-Attributs „NameSpace“, „Queue“ oder „Topic“ ab.
     - Remove-AzureRmServiceBusNamespaceAuthorizationRule
       - Löscht die vorhandene AuthorizationRule des ServiceBus-Attributs „NameSpace“, „Queue“ oder „Topic“.
    * ResourceGroup-Eigenschaft zu „NamespaceAttributes“ hinzugefügt
* SQL
    * „Set-AzureRmSqlServerTransparentDataEncryptionProtector“ aktualisiert, um Warnung anzuzeigen und die Bestätigung anzufordern, ob der Verschlüsselungsschutztyp auf „AzureKeyVault“ festgelegt werden soll
    * Neue aktualisierte Cmdlets für Überwachungseinstellungen hinzugefügt
        - Das Cmdlet „Get-AzureRmSqlDatabaseAuditing“ ruft die Überwachungseinstellungen einer Azure SQL-Datenbank ab.
        - Das Cmdlet „Get-AzureRmSqlServerAuditing“ ruft die Überwachungseinstellungen eines Azure SQL-Servers ab.
        - Das Cmdlet „Set-AzureRmSqlDatabaseAuditing“ ändert die Überwachungseinstellungen einer Azure SQL-Datenbank.
        - Das Cmdlet „Set-AzureRmSqlServerAuditing“ ändert die Überwachungseinstellungen eines Azure SQL-Servers.
    * Vorhandene Cmdlets für die Überwachungsrichtlinie als veraltet markiert
        - „Get-AzureRmSqlDatabaseAuditingPolicy“ als veraltet markiert
        - „Get-AzureRmSqlServerAuditingPolicy“ als veraltet markiert
        - „Set-AzureRmSqlDatabaseAuditingPolicy“ als veraltet markiert
        - „Set-AzureRmSqlServerAuditingPolicy“ als veraltet markiert
        - „Use-AzureRmSqlServerAuditingPolicy“ als veraltet markiert
        - „Remove-AzureRmSqlDatabaseAuditing“ als veraltet markiert
        - „Remove-AzureRmSqlServerAuditing“ als veraltet markiert
    * Bei der Analyse von Schemadateien für „Update-AzureRmSqlSyncGroup“ gilt nun die Groß-/Kleinschreibung.
* Speicher
    * Unterstützung für „NeworkRule“ zu Cmdlets für Speicherkonten mit Ressourcenmodus hinzugefügt
        - New-AzureRmStorageAccount
        - Set-AzureRmStorageAccount
        - Get-AzureRmStorageAccountNetworkRuleSet
        - Update-AzureRmStorageAccountNetworkRuleSet
        - Add-AzureRmStorageAccountNetworkRule
        - Remove-AzureRmStorageAccountNetworkRule

Sehen Sie sich die [Änderungen seit der letzten Version](https://github.com/Azure/azure-powershell/compare/v4.2.1-July2017...v4.3.1-August2017) an.
