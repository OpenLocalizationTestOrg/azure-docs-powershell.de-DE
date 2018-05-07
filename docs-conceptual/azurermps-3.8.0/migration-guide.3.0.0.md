# <a name="breaking-changes-for-microsoft-azure-powershell-300"></a>Grundlegende Änderungen für Microsoft Azure PowerShell 3.0.0

Dieses Dokument informiert über grundlegende Änderungen und fungiert als Migrationsleitfaden für Kunden mit Microsoft Azure PowerShell-Cmdlets.  In den einzelnen Abschnitten werden jeweils der Grund für die grundlegende Änderung und der Migrationspfad des geringsten Widerstands beschrieben.  Ausführlichen Kontext finden Sie unter der Pull-Anforderung für die jeweilige Änderung.

## <a name="table-of-contents"></a>Inhaltsverzeichnis
1. [Grundlegende Änderungen für Data Lake Store-Cmdlets](#breaking-changes-to-data-lake-store-cmdlets)
2. [Grundlegende Änderungen für ApiManagement-Cmdlets](#breaking-changes-to-apimanagement-cmdlets)
3. [Grundlegende Änderungen für Network-Cmdlets](#breaking-changes-to-network-cmdlets)

## <a name="breaking-changes-to-data-lake-store-cmdlets"></a>Grundlegende Änderungen für Data Lake Store-Cmdlets

Diese Version ([PR 2965](https://github.com/Azure/azure-powershell/pull/2965)) hat Auswirkungen auf folgende Cmdlets:

**Get-AzureRmDataLakeStoreItemAcl (Get-AdlStoreItemAcl)**
- Dieses Cmdlet wurde entfernt und durch ``Get-AzureRmDataLakeStoreItemAclEntry (Get-AdlStoreItemAclEntry)`` ersetzt.
- Das alte Cmdlet gab ein komplexes Objekt zurück, das die Zugriffssteuerungsliste (Access Control List, ACL) darstellte. Das neue Cmdlet gibt eine einfache Liste mit Einträgen in der ACL für den ausgewählten Pfad zurück.

```powershell
# Old
Get-AdlStoreItemAcl -Account myadlsaccount -Path /foo

# New
Get-AdlStoreItemAclEntry -Account myadlsaccount -Path /foo
```

**Get-AzureRmDataLakeStoreItemAclEntry (Get-AdlStoreItemAclEntry)**
- Dieses Cmdlet ersetzt das alte Cmdlet ``Get-AzureRmDataLakeStoreItemAcl (Get-AdlStoreItemAcl)``.
- Das neue Cmdlet gibt eine einfache Liste mit Einträgen in der ACL für den ausgewählten Pfad (mit dem Typ ``DataLakeStoreItemAce[]``) zurück.
- Die Ausgabe dieses Cmdlets kann an den Parameter ``-Acl`` folgender Cmdlets übergeben werden:
   - ``Remove-AzureRmDataLakeStoreItemAcl``
   - ``Set-AzureRmDataLakeStoreItemAcl``
   - ``Set-AzureRmDataLakeStoreItemAclEntry``

```powershell
# Old
Get-AdlStoreItemAcl -Account myadlsaccount -Path /foo

# New
Get-AdlStoreItemAclEntry -Account myadlsaccount -Path /foo
```

**Remove-AzureRmDataLakeStoreItemAcl (Remove-AdlStoreItemAcl)**, **Set-AzureRmDataLakeStoreItemAcl (Set-AdlStoreItemAcl)**, **Set-AzureRmDataLakeStoreItemAclEntry (Set-AdlStoreItemAclEntry)**
- Diese Cmdlets akzeptieren nun ``DataLakeStoreItemAce[]`` für den Parameter ``-Acl``.
- ``DataLakeStoreItemAce[]`` wird von ``Get-AzureRmDataLakeStoreItemAclEntry (Get-AdlStoreItemAclEntry)`` zurückgegeben.

```powershell
# Old
$acl = Get-AdlStoreItemAcl -Account myadlsaccount -Path /foo
Set-AdlStoreItemAcl -Account myadlsaccount -Path /foo -Acl $acl

# New
$aclEntries = Get-AdlStoreItemAclEntry -Account myadlsaccount -Path /foo
Set-AdlStoreItemAcl -Account myadlsaccount -Path /foo -Acl $aclEntries
```

## <a name="breaking-changes-to-apimanagement-cmdlets"></a>Grundlegende Änderungen für ApiManagement-Cmdlets

Diese Version ([PR 2971](https://github.com/Azure/azure-powershell/pull/2971)) hat Auswirkungen auf folgende Cmdlets:

**New-AzureRmApiManagementVirtualNetwork**
- Für den Verweis auf ein virtuelles Netzwerk wird nun „SubnetResourceId“ im Format ``/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ClassicNetwork/virtualNetworks/{virtualNetworkName}/subnets/{subnetName}`` benötigt (anstelle von „SubnetName“ und „VnetId“).

```powershell
# Old
$virtualNetwork = New-AzureRmApiManagementVirtualNetwork -Location <String> -SubnetName <String> -VnetId <Guid>

# New
$virtualNetwork = New-AzureRmApiManagementVirtualNetwork -Location <String> -SubnetResourceId <String>

```

**Ausmusterung des Cmdlets „Set-AzureRmApiManagementVirtualNetworks“**
- Das Cmdlet wird ausgemustert, da es mehrere Möglichkeiten gab, um das virtuelle Netzwerk für die ApiManagement-Bereitstellung festzulegen.

```powershell
# Old
$networksList = @()
$networksList += New-AzureRmApiManagementVirtualNetwork -Location $vnetLocation -VnetId $vnetId -SubnetName $subnetName
Set-AzureRmApiManagementVirtualNetworks -ResourceGroupName "ContosoGroup" -Name "ContosoApi" -VirtualNetworks $networksList

# New
$masterRegionVirtualNetwork = New-AzureRmApiManagementVirtualNetwork -Location <String> -SubnetResourceId <String>
Update-AzureRmApiManagementDeployment -ResourceGroupName "ContosoGroup" -Name "ContosoApi" -VirtualNetwork $masterRegionVirtualNetwork
```

## <a name="breaking-changes-to-network-cmdlets"></a>Grundlegende Änderungen für Network-Cmdlets

Diese Version ([PR 2982](https://github.com/Azure/azure-powershell/pull/2982)) hat Auswirkungen auf folgende Cmdlets:

**New-AzureRmVirtualNetworkGateway**
- Die Beschreibung der Änderung (``:- Bool parameter:-ActiveActive``) wird entfernt, und ``SwitchParameter:-EnableActiveActiveFeature`` wird zum Aktivieren des Aktiv/Aktiv-Features beim Erstellen eines neuen Gateways des virtuellen Netzwerks hinzugefügt.

```powershell
# Old 
# Sample of how the cmdlet was previously called
New-AzureRmVirtualNetworkGateway -ResourceGroupName $rgname -name $rname -Location $location -IpConfigurations $vnetIpConfig1,$vnetIpConfig2 -GatewayType Vpn -VpnType RouteBased -EnableBgp $false -GatewaySku HighPerformance -ActiveActive $true

# New
# Sample of how the cmdlet should now be called
New-AzureRmVirtualNetworkGateway -ResourceGroupName $rgname -name $rname -Location $location -IpConfigurations $vnetIpConfig1,$vnetIpConfig2 -GatewayType Vpn -VpnType RouteBased -EnableBgp $false -GatewaySku HighPerformance -EnableActiveActiveFeature
```

Set-AzureRmVirtualNetworkGateway
- Die Beschreibung der Änderung (``:- Bool parameter:-ActiveActive``) wird entfernt, und ``SwitchParameters:-EnableActiveActiveFeature`` / ``DisableActiveActiveFeature`` wird zum Aktivieren/Deaktivieren des Aktiv/Aktiv-Features für das Gateway des virtuellen Netzwerks hinzugefügt.

```powershell
# Old
# Sample of how the cmdlet was previously called
Set-AzureRmVirtualNetworkGateway -VirtualNetworkGateway $gw -ActiveActive $true
Set-AzureRmVirtualNetworkGateway -VirtualNetworkGateway $gw -ActiveActive $false  

# New
# Sample of how the cmdlet should now be called
Set-AzureRmVirtualNetworkGateway -VirtualNetworkGateway $gw -EnableActiveActiveFeature
Set-AzureRmVirtualNetworkGateway -VirtualNetworkGateway $gw -DisableActiveActiveFeature
```