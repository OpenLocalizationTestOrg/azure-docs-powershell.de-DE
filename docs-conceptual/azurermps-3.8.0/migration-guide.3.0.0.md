# <a name="breaking-changes-for-microsoft-azure-powershell-300"></a><span data-ttu-id="330e9-101">Grundlegende Änderungen für Microsoft Azure PowerShell 3.0.0</span><span class="sxs-lookup"><span data-stu-id="330e9-101">Breaking changes for Microsoft Azure PowerShell 3.0.0.</span></span>

<span data-ttu-id="330e9-102">Dieses Dokument informiert über grundlegende Änderungen und fungiert als Migrationsleitfaden für Kunden mit Microsoft Azure PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="330e9-102">This document serves as both a breaking change notification and migration guide for consumers of the Microsoft Azure PowerShell cmdlets.</span></span>  <span data-ttu-id="330e9-103">In den einzelnen Abschnitten werden jeweils der Grund für die grundlegende Änderung und der Migrationspfad des geringsten Widerstands beschrieben.</span><span class="sxs-lookup"><span data-stu-id="330e9-103">Each section describes both the impetus for the breaking change and the migration path of least resistance.</span></span>  <span data-ttu-id="330e9-104">Ausführlichen Kontext finden Sie unter der Pull-Anforderung für die jeweilige Änderung.</span><span class="sxs-lookup"><span data-stu-id="330e9-104">For in-depth context, please refer to the pull request associated with each change.</span></span>

## <a name="table-of-contents"></a><span data-ttu-id="330e9-105">Inhaltsverzeichnis</span><span class="sxs-lookup"><span data-stu-id="330e9-105">Table of Contents</span></span>
1. [<span data-ttu-id="330e9-106">Grundlegende Änderungen für Data Lake Store-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="330e9-106">Breaking changes to Data Lake Store cmdlets</span></span>](#breaking-changes-to-data-lake-store-cmdlets)
2. [<span data-ttu-id="330e9-107">Grundlegende Änderungen für ApiManagement-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="330e9-107">Breaking changes to ApiManagement cmdlets</span></span>](#breaking-changes-to-apimanagement-cmdlets)
3. [<span data-ttu-id="330e9-108">Grundlegende Änderungen für Network-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="330e9-108">Breaking changes to Network cmdlets</span></span>](#breaking-changes-to-network-cmdlets)

## <a name="breaking-changes-to-data-lake-store-cmdlets"></a><span data-ttu-id="330e9-109">Grundlegende Änderungen für Data Lake Store-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="330e9-109">Breaking changes to Data Lake Store cmdlets</span></span>

<span data-ttu-id="330e9-110">Diese Version ([PR 2965](https://github.com/Azure/azure-powershell/pull/2965)) hat Auswirkungen auf folgende Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="330e9-110">The following cmdlets were affected this release ([PR 2965](https://github.com/Azure/azure-powershell/pull/2965)):</span></span>

<span data-ttu-id="330e9-111">**Get-AzureRmDataLakeStoreItemAcl (Get-AdlStoreItemAcl)**</span><span class="sxs-lookup"><span data-stu-id="330e9-111">**Get-AzureRmDataLakeStoreItemAcl (Get-AdlStoreItemAcl)**</span></span>
- <span data-ttu-id="330e9-112">Dieses Cmdlet wurde entfernt und durch ``Get-AzureRmDataLakeStoreItemAclEntry (Get-AdlStoreItemAclEntry)`` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="330e9-112">This cmdlet was removed and replaced with ``Get-AzureRmDataLakeStoreItemAclEntry (Get-AdlStoreItemAclEntry)``.</span></span>
- <span data-ttu-id="330e9-113">Das alte Cmdlet gab ein komplexes Objekt zurück, das die Zugriffssteuerungsliste (Access Control List, ACL) darstellte.</span><span class="sxs-lookup"><span data-stu-id="330e9-113">The old cmdlet returned a complex object representing the access control list (ACL).</span></span> <span data-ttu-id="330e9-114">Das neue Cmdlet gibt eine einfache Liste mit Einträgen in der ACL für den ausgewählten Pfad zurück.</span><span class="sxs-lookup"><span data-stu-id="330e9-114">The new cmdlet returns a simple list of entries in the chosen path's ACL.</span></span>

```powershell
# Old
Get-AdlStoreItemAcl -Account myadlsaccount -Path /foo

# New
Get-AdlStoreItemAclEntry -Account myadlsaccount -Path /foo
```

<span data-ttu-id="330e9-115">**Get-AzureRmDataLakeStoreItemAclEntry (Get-AdlStoreItemAclEntry)**</span><span class="sxs-lookup"><span data-stu-id="330e9-115">**Get-AzureRmDataLakeStoreItemAclEntry (Get-AdlStoreItemAclEntry)**</span></span>
- <span data-ttu-id="330e9-116">Dieses Cmdlet ersetzt das alte Cmdlet ``Get-AzureRmDataLakeStoreItemAcl (Get-AdlStoreItemAcl)``.</span><span class="sxs-lookup"><span data-stu-id="330e9-116">This cmdlet replaces the old cmdlet ``Get-AzureRmDataLakeStoreItemAcl (Get-AdlStoreItemAcl)``.</span></span>
- <span data-ttu-id="330e9-117">Das neue Cmdlet gibt eine einfache Liste mit Einträgen in der ACL für den ausgewählten Pfad (mit dem Typ ``DataLakeStoreItemAce[]``) zurück.</span><span class="sxs-lookup"><span data-stu-id="330e9-117">This new cmdlet returns a simple list of entries in the chosen path's ACL, with type ``DataLakeStoreItemAce[]``.</span></span>
- <span data-ttu-id="330e9-118">Die Ausgabe dieses Cmdlets kann an den Parameter ``-Acl`` folgender Cmdlets übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="330e9-118">The output of this cmdlet can be passed in to the ``-Acl`` parameter of the following cmdlets:</span></span>
   - ``Remove-AzureRmDataLakeStoreItemAcl``
   - ``Set-AzureRmDataLakeStoreItemAcl``
   - ``Set-AzureRmDataLakeStoreItemAclEntry``

```powershell
# Old
Get-AdlStoreItemAcl -Account myadlsaccount -Path /foo

# New
Get-AdlStoreItemAclEntry -Account myadlsaccount -Path /foo
```

<span data-ttu-id="330e9-119">**Remove-AzureRmDataLakeStoreItemAcl (Remove-AdlStoreItemAcl)**, **Set-AzureRmDataLakeStoreItemAcl (Set-AdlStoreItemAcl)**, **Set-AzureRmDataLakeStoreItemAclEntry (Set-AdlStoreItemAclEntry)**</span><span class="sxs-lookup"><span data-stu-id="330e9-119">**Remove-AzureRmDataLakeStoreItemAcl (Remove-AdlStoreItemAcl)**, **Set-AzureRmDataLakeStoreItemAcl (Set-AdlStoreItemAcl)**, **Set-AzureRmDataLakeStoreItemAclEntry (Set-AdlStoreItemAclEntry)**</span></span>
- <span data-ttu-id="330e9-120">Diese Cmdlets akzeptieren nun ``DataLakeStoreItemAce[]`` für den Parameter ``-Acl``.</span><span class="sxs-lookup"><span data-stu-id="330e9-120">These cmdlets now accept ``DataLakeStoreItemAce[]`` for the ``-Acl`` parameter.</span></span>
- <span data-ttu-id="330e9-121">``DataLakeStoreItemAce[]`` wird von ``Get-AzureRmDataLakeStoreItemAclEntry (Get-AdlStoreItemAclEntry)`` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="330e9-121">``DataLakeStoreItemAce[]`` is returned by ``Get-AzureRmDataLakeStoreItemAclEntry (Get-AdlStoreItemAclEntry)``.</span></span>

```powershell
# Old
$acl = Get-AdlStoreItemAcl -Account myadlsaccount -Path /foo
Set-AdlStoreItemAcl -Account myadlsaccount -Path /foo -Acl $acl

# New
$aclEntries = Get-AdlStoreItemAclEntry -Account myadlsaccount -Path /foo
Set-AdlStoreItemAcl -Account myadlsaccount -Path /foo -Acl $aclEntries
```

## <a name="breaking-changes-to-apimanagement-cmdlets"></a><span data-ttu-id="330e9-122">Grundlegende Änderungen für ApiManagement-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="330e9-122">Breaking changes to ApiManagement cmdlets</span></span>

<span data-ttu-id="330e9-123">Diese Version ([PR 2971](https://github.com/Azure/azure-powershell/pull/2971)) hat Auswirkungen auf folgende Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="330e9-123">The following cmdlets were affected this release ([PR 2971](https://github.com/Azure/azure-powershell/pull/2971)):</span></span>

<span data-ttu-id="330e9-124">**New-AzureRmApiManagementVirtualNetwork**</span><span class="sxs-lookup"><span data-stu-id="330e9-124">**New-AzureRmApiManagementVirtualNetwork**</span></span>
- <span data-ttu-id="330e9-125">Für den Verweis auf ein virtuelles Netzwerk wird nun „SubnetResourceId“ im Format ``/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ClassicNetwork/virtualNetworks/{virtualNetworkName}/subnets/{subnetName}`` benötigt (anstelle von „SubnetName“ und „VnetId“).</span><span class="sxs-lookup"><span data-stu-id="330e9-125">The required parameters to reference a virtual network changed from requiring SubnetName and VnetId to SubnetResourceId in format ``/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ClassicNetwork/virtualNetworks/{virtualNetworkName}/subnets/{subnetName}``</span></span>

```powershell
# Old
$virtualNetwork = New-AzureRmApiManagementVirtualNetwork -Location <String> -SubnetName <String> -VnetId <Guid>

# New
$virtualNetwork = New-AzureRmApiManagementVirtualNetwork -Location <String> -SubnetResourceId <String>

```

<span data-ttu-id="330e9-126">**Ausmusterung des Cmdlets „Set-AzureRmApiManagementVirtualNetworks“**</span><span class="sxs-lookup"><span data-stu-id="330e9-126">**Deprecating Cmdlet Set-AzureRmApiManagementVirtualNetworks**</span></span>
- <span data-ttu-id="330e9-127">Das Cmdlet wird ausgemustert, da es mehrere Möglichkeiten gab, um das virtuelle Netzwerk für die ApiManagement-Bereitstellung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="330e9-127">The Cmdlet is getting deprecated as there was more than one way to Set Virtual Network associated to ApiManagement deployment.</span></span>

```powershell
# Old
$networksList = @()
$networksList += New-AzureRmApiManagementVirtualNetwork -Location $vnetLocation -VnetId $vnetId -SubnetName $subnetName
Set-AzureRmApiManagementVirtualNetworks -ResourceGroupName "ContosoGroup" -Name "ContosoApi" -VirtualNetworks $networksList

# New
$masterRegionVirtualNetwork = New-AzureRmApiManagementVirtualNetwork -Location <String> -SubnetResourceId <String>
Update-AzureRmApiManagementDeployment -ResourceGroupName "ContosoGroup" -Name "ContosoApi" -VirtualNetwork $masterRegionVirtualNetwork
```

## <a name="breaking-changes-to-network-cmdlets"></a><span data-ttu-id="330e9-128">Grundlegende Änderungen für Network-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="330e9-128">Breaking changes to Network cmdlets</span></span>

<span data-ttu-id="330e9-129">Diese Version ([PR 2982](https://github.com/Azure/azure-powershell/pull/2982)) hat Auswirkungen auf folgende Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="330e9-129">The following cmdlets were affected this release ([PR 2982](https://github.com/Azure/azure-powershell/pull/2982)):</span></span>

<span data-ttu-id="330e9-130">**New-AzureRmVirtualNetworkGateway**</span><span class="sxs-lookup"><span data-stu-id="330e9-130">**New-AzureRmVirtualNetworkGateway**</span></span>
- <span data-ttu-id="330e9-131">Die Beschreibung der Änderung (``:- Bool parameter:-ActiveActive``) wird entfernt, und ``SwitchParameter:-EnableActiveActiveFeature`` wird zum Aktivieren des Aktiv/Aktiv-Features beim Erstellen eines neuen Gateways des virtuellen Netzwerks hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="330e9-131">Description of what has changed ``:- Bool parameter:-ActiveActive`` is removed and ``SwitchParameter:-EnableActiveActiveFeature`` is added for enabling Active-Active feature on newly creating virtual network gateway.</span></span>

```powershell
# Old 
# Sample of how the cmdlet was previously called
New-AzureRmVirtualNetworkGateway -ResourceGroupName $rgname -name $rname -Location $location -IpConfigurations $vnetIpConfig1,$vnetIpConfig2 -GatewayType Vpn -VpnType RouteBased -EnableBgp $false -GatewaySku HighPerformance -ActiveActive $true

# New
# Sample of how the cmdlet should now be called
New-AzureRmVirtualNetworkGateway -ResourceGroupName $rgname -name $rname -Location $location -IpConfigurations $vnetIpConfig1,$vnetIpConfig2 -GatewayType Vpn -VpnType RouteBased -EnableBgp $false -GatewaySku HighPerformance -EnableActiveActiveFeature
```

<span data-ttu-id="330e9-132">Set-AzureRmVirtualNetworkGateway</span><span class="sxs-lookup"><span data-stu-id="330e9-132">Set-AzureRmVirtualNetworkGateway</span></span>
- <span data-ttu-id="330e9-133">Die Beschreibung der Änderung (``:- Bool parameter:-ActiveActive``) wird entfernt, und ``SwitchParameters:-EnableActiveActiveFeature`` / ``DisableActiveActiveFeature`` wird zum Aktivieren/Deaktivieren des Aktiv/Aktiv-Features für das Gateway des virtuellen Netzwerks hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="330e9-133">Description of what has changed ``:- Bool parameter:-ActiveActive`` is removed and 2 ``SwitchParameters:-EnableActiveActiveFeature`` / ``DisableActiveActiveFeature`` are added for enabling and disabling Active-Active feature on virtual network gateway.</span></span>

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