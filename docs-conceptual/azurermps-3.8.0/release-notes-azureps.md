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
ms.openlocfilehash: 04f89e8d47d0825d46cb1b8817efbcc0cafa0acd
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2017
---
# <a name="release-notes"></a>Versionshinweise

Hierbei handelt es sich um eine Liste der Änderungen, die in dieser Version an Azure PowerShell vorgenommen wurden.

## <a name="version-380"></a>Version 3.8.0
* Compute
  - Korrektur eines Fehlers in Get-*-Cmdlets, um das Abrufen mehrerer Seiten mit Daten (mehr als 120 Elemente) zu ermöglichen
* DataLakeAnalytics
  - Korrektur der Hilfe für einige Befehle, sodass sie die richtige Sprache und die richtigen Beispiele enthalten.
* DataLakeStore
  - Zum `Get-AzureRMDataLakeStoreItemContent`-Cmdlet wurde Unterstützung für den Anfangs- und Endbereich hinzugefügt. Dies ermöglicht die Rückgabe der ersten n oder letzten n durch Zeilenumbrüche getrennten Zeilen für die Anzeige.
* HDInsight
  - Unterstützung für den RServer-Clustertyp wurde hinzugefügt.
    + Die Größe virtueller Edgeknotencomputer kann für RServer-Cluster in „New-AzureRmHDInsightCluster“ oder „New-AzureRmHDInsightClusterConfig“ angegeben werden.
    + „RServer“ ist jetzt eine Konfigurationsoption in „Add-AzureRmHDInsightConfigValues“. Sie ermöglicht das Festlegen des RStudio-Flags, um anzugeben, dass die R Studio-Installation ausgeführt werden sollte.
* LogicApp
  - Die Cmdlets „Set-AzureRmIntegrationAccountSchema“ und „Set-AzureRmIntegrationAccountMap“ wurden zur Behebung des contentlink-Problems korrigiert. („content“ und „contentlink“ führten zu einem Updatefehler.)
* Netzwerk
  - Anwendungsgateways wurde Unterstützung für neue Web Application Firewall-Features hinzugefügt.
    + „New-AzureRmApplicationGatewayFirewallDisabledRuleGroupConfig“ wurde hinzugefügt.
    + „Get-AzureRmApplicationGatewayAvailableWafRuleSets“ wurde hinzugefügt (Alias: List-AzureRmApplicationGatewayAvailableWafRuleSets).
    + „New-AzureRmApplicationGatewayWebApplicationFirewallConfiguration“ wurde aktualisiert: Die Parameter „-RuleSetType -RuleSetVersion“ und „-DisabledRuleGroups“ wurden hinzugefügt.
    + „Set-AzureRmApplicationGatewayWebApplicationFirewallConfiguration“ wurde aktualisiert: Die Parameter „-RuleSetType -RuleSetVersion“ und „-DisabledRuleGroups“ wurden hinzugefügt.
  - Für Verbindungen für das virtuelle Netzwerkgateway wurde Unterstützung für IPSec-Richtlinien hinzugefügt.
  - „New-AzureRmIpsecPolicy“ wurde hinzugefügt.
  - „New-AzureRmVirtualNetworkGatewayConnection“ wurde aktualisiert: Die Parameter „-IpsecPolicies“ und „-UsePolicyBasedTrafficSelectors“ wurden hinzugefügt.
* Profil
  - *Veraltet*: „Save-AzureRmProfile“ wurde in „Save-AzureRmContext“ umbenannt. Es gibt einen Alias für den alten Cmdlet-Namen. Der Alias wird in der nächsten Version entfernt.
  - *Veraltet*: „Select-AzureRmProfile“ wurde in „Import-AzureRmContext“ umbenannt. Es gibt einen Alias für den alten Cmdlet-Namen. Der Alias wird in der nächsten Version entfernt.
  - Die Ausgabetypen „PSAzureContext“ und „PSAzureProfile“ der Profil-Cmdlets werden in der nächsten Version geändert.
  - Das Cmdlet „Save-AzureRmContext“ enthält in der nächsten Version kein OutputType-Element.
  - Korrektur eines Fehlers im allgemeinen Cmdlet-Code, damit ein FIPS-kompatibler Algorithmus für Datenhashes verwendet werden kann: https://github.com/Azure/azure-powershell/issues/3651
* Sql
  - Fehlerbehebungen für Azure-Failovergruppen-Cmdlets
  - Korrektur für den Vorgangsabruf
  - Korrektur des GracePeriodWithDataLossHour-Werts, wenn für „FailoverPolicy“ die Option „Manuell“ festgelegt wird
* Traffic Manager
  - Unterstützung für die geografische Methode für das Datenverkehrsrouting
    + Neuer Wert „Geographic“ für den TrafficRoutingMethod-Parameter von „New-AzureRmTrafficManagerProfile“
    + Neuer Parameter „GeoMapping“ für „New-AzureRmTrafficManagerEndpoint“ und „Add-AzureRmTrafficManagerEndpointConfig“
    + Behebung eines Fehlers beim Übergeben für „Get-AzureRmTrafficManagerProfile“, wenn eine Sammlung mit Profilen zurückgegeben wird
* ServiceManagement
  - Restart-AzureVM: Der InitiateMaintenance-Parameter für die Ausführung einer Wartung während des VM-Neustarts wurde hinzugefügt.
  - Get-AzureVM: Das Feld für den Wartungsstatus wurde hinzugefügt.
  - Neue Cmdlets zur Unterstützung des Recovery Services-Tresorupgrades wurden hinzugefügt.
    + Test-AzureRecoveryServicesVaultUpgrade
    + Invoke-AzureRecoveryServicesVaultUpgrade
