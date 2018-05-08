# <a name="breaking-changes-for-microsoft-azure-powershell-400"></a><span data-ttu-id="64c98-101">Grundlegende Änderungen für Microsoft Azure PowerShell 4.0.0</span><span class="sxs-lookup"><span data-stu-id="64c98-101">Breaking changes for Microsoft Azure PowerShell 4.0.0</span></span>

<span data-ttu-id="64c98-102">Dieses Dokument informiert über grundlegende Änderungen und fungiert als Migrationsleitfaden für Kunden mit Microsoft Azure PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="64c98-102">This document serves as both a breaking change notification and migration guide for consumers of the Microsoft Azure PowerShell cmdlets.</span></span> <span data-ttu-id="64c98-103">In den einzelnen Abschnitten werden jeweils der Grund für die grundlegende Änderung und der Migrationspfad des geringsten Widerstands beschrieben.</span><span class="sxs-lookup"><span data-stu-id="64c98-103">Each section describes both the impetus for the breaking change and the migration path of least resistance.</span></span> <span data-ttu-id="64c98-104">Ausführlichen Kontext finden Sie unter der Pull-Anforderung für die jeweilige Änderung.</span><span class="sxs-lookup"><span data-stu-id="64c98-104">For in-depth context, please refer to the pull request associated with each change.</span></span>

## <a name="table-of-contents"></a><span data-ttu-id="64c98-105">Inhaltsverzeichnis</span><span class="sxs-lookup"><span data-stu-id="64c98-105">Table of Contents</span></span>

- [<span data-ttu-id="64c98-106">Grundlegende Änderungen für Compute-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64c98-106">Breaking changes to Compute cmdlets</span></span>](#breaking-changes-to-compute-cmdlets)
- [<span data-ttu-id="64c98-107">Grundlegende Änderungen für EventHub-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64c98-107">Breaking changes to EventHub cmdlets</span></span>](#breaking-changes-to-eventhub-cmdlets)
- [<span data-ttu-id="64c98-108">Grundlegende Änderungen für Insights-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64c98-108">Breaking changes to Insights cmdlets</span></span>](#breaking-changes-to-insights-cmdlets)
- [<span data-ttu-id="64c98-109">Grundlegende Änderungen für Network-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64c98-109">Breaking changes to Network cmdlets</span></span>](#breaking-changes-to-network-cmdlets)
- [<span data-ttu-id="64c98-110">Grundlegende Änderungen für ServiceBus-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64c98-110">Breaking changes to ServiceBus cmdlets</span></span>](#breaking-changes-to-servicebus-cmdlets)
- [<span data-ttu-id="64c98-111">Grundlegende Änderungen für Sql-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64c98-111">Breaking changes to Sql cmdlets</span></span>](#breaking-changes-to-sql-cmdlets)
- [<span data-ttu-id="64c98-112">Grundlegende Änderungen für Storage-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64c98-112">Breaking changes to Storage cmdlets</span></span>](#breaking-changes-to-storage-cmdlets)
- [<span data-ttu-id="64c98-113">Grundlegende Änderungen für Profile-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64c98-113">Breaking Changes to Profile Cmdlets</span></span>](#breaking-changes-to-profile-cmdlets)
## <a name="breaking-changes-to-compute-cmdlets"></a><span data-ttu-id="64c98-114">Grundlegende Änderungen für Compute-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64c98-114">Breaking changes to Compute cmdlets</span></span>

<span data-ttu-id="64c98-115">Diese Version hat Auswirkungen auf folgende Ausgabetypen:</span><span class="sxs-lookup"><span data-stu-id="64c98-115">The following output types were affected this release:</span></span>

### <a name="psvirtualmachine"></a><span data-ttu-id="64c98-116">PSVirtualMachine</span><span class="sxs-lookup"><span data-stu-id="64c98-116">PSVirtualMachine</span></span>
- <span data-ttu-id="64c98-117">Die übergeordneten Eigenschaften `DataDiskNames` und `NetworkInterfaceIDs` des Objekts `PSVirtualMachine` wurden aus dem Ausgabetyp entfernt.</span><span class="sxs-lookup"><span data-stu-id="64c98-117">Top level properties `DataDiskNames` and `NetworkInterfaceIDs` of nthe `PSVirtualMachine` object have been removed from the output type.</span></span> <span data-ttu-id="64c98-118">Diese Eigenschaften waren schon immer in den Eigenschaften `StorageProfile` und `NetworkProfile` des Objekts `PSVirtualMachine` verfügbar und müssen fortan für den Zugriff auf die Eigenschaften verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="64c98-118">These properties have always been available in the `StorageProfile` and `NetworkProfile` properties of the `PSVirtualMachine` object and will be the way they will need to be accessed going forward.</span></span>
- <span data-ttu-id="64c98-119">Diese Änderung wirkt sich auf folgende Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="64c98-119">This change affects the following cmdlets:</span></span>
    - `Add-AzureRmVMDataDisk`
    - `Add-AzureRmVMNetworkInterface`
    - `Get-AzureRmVM`
    - `Remove-AzureRmVMDataDisk`
    - `Remove-AzureRmVMNetworkInterface`
    - `Set-AzureRmVMDataDisk`

```powershell
# Old
$vm.DataDiskNames
$vm.NetworkInterfaceIDs

# New
$vm.StorageProfile.DataDisks | Select -Property Name
$vm.NetworkProfile.NetworkInterfaces | Select -Property Id
```

## <a name="breaking-changes-to-eventhub-cmdlets"></a><span data-ttu-id="64c98-120">Grundlegende Änderungen für EventHub-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64c98-120">Breaking changes to EventHub cmdlets</span></span>

<span data-ttu-id="64c98-121">Diese Version hat Auswirkungen auf folgende Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="64c98-121">The following cmdlets were affected this release:</span></span>

### <a name="get-azurermeventhubnamespace"></a><span data-ttu-id="64c98-122">Get-AzureRmEventHubNamespace</span><span class="sxs-lookup"><span data-stu-id="64c98-122">Get-AzureRmEventHubNamespace</span></span>
- <span data-ttu-id="64c98-123">Die Eigenschaft `ResourceGroupName` wurde aus dem Ausgabetyp `NamespaceAttributes` entfernt.</span><span class="sxs-lookup"><span data-stu-id="64c98-123">The property `ResourceGroupName` has been removed from the output type `NamespaceAttributes`</span></span>

### <a name="new-azurermeventhubnamespace"></a><span data-ttu-id="64c98-124">New-AzureRmEventHubNamespace</span><span class="sxs-lookup"><span data-stu-id="64c98-124">New-AzureRmEventHubNamespace</span></span>
- <span data-ttu-id="64c98-125">Die Eigenschaft `ResourceGroupName` wurde aus dem Ausgabetyp `NamespaceAttributes` entfernt.</span><span class="sxs-lookup"><span data-stu-id="64c98-125">The property `ResourceGroupName` has been removed from the output type `NamespaceAttributes`</span></span>

## <a name="breaking-changes-to-insights-cmdlets"></a><span data-ttu-id="64c98-126">Grundlegende Änderungen für Insights-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64c98-126">Breaking changes to Insights cmdlets</span></span>

<span data-ttu-id="64c98-127">Diese Version hat Auswirkungen auf folgende Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="64c98-127">The following cmdlets were affected this release:</span></span>
    
### <a name="get-azurermusage"></a><span data-ttu-id="64c98-128">Get-AzureRmUsage</span><span class="sxs-lookup"><span data-stu-id="64c98-128">Get-AzureRmUsage</span></span>
- <span data-ttu-id="64c98-129">Dieses Cmdlet ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="64c98-129">This cmdlet has been deprecated.</span></span>

### <a name="remove-azurermalertrule"></a><span data-ttu-id="64c98-130">Remove-AzureRmAlertRule</span><span class="sxs-lookup"><span data-stu-id="64c98-130">Remove-AzureRmAlertRule</span></span>
- <span data-ttu-id="64c98-131">Die Ausgabe dieses Cmdlets wurde von einer Liste mit einem einzelnen Objekt in ein einzelnes Objekt geändert, das die Anforderungs-ID und den Statuscode enthält.</span><span class="sxs-lookup"><span data-stu-id="64c98-131">The output of this cmdlet has changed from a list with a single object to a single object; this object includes the requestId, and status code.</span></span>
    
```powershell
# Old  
$s1 = Remove-AzureRmAlertRule -ResourceGroup $resourceGroup -name chiricutin
if ($s1 -ne $null)
{
    $r = $s1(0).RequestId
    $s = $s1(0).StatusCode
}

# New
$s1 = Remove-AzureRmAlertRule -ResourceGroup $resourceGroup -name chiricutin
$r = $s1.RequestId
$s = $s1.StatusCode
```
    
### <a name="add-azurermlogalertrule"></a><span data-ttu-id="64c98-132">Add-AzureRmLogAlertRule</span><span class="sxs-lookup"><span data-stu-id="64c98-132">Add-AzureRmLogAlertRule</span></span>
- <span data-ttu-id="64c98-133">Dieses Cmdlet ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="64c98-133">This cmdlet has been deprecated.</span></span>
    
### <a name="get-azurermalertrule"></a><span data-ttu-id="64c98-134">Get-AzureRmAlertRule</span><span class="sxs-lookup"><span data-stu-id="64c98-134">Get-AzureRmAlertRule</span></span>
- <span data-ttu-id="64c98-135">Jedes Element der Ausgabe dieses Cmdlets (eine Liste mit Objekten) wird vereinfacht. Anstelle von Objekten mit der Struktur `{ Id, Location, Name, Tags, Properties }` werden also Objekte mit der Struktur `{ Id, Location, Name, Tags, Type, Description, IsEnabled, Condition, Actions, LastUpdatedTime, ...}` zurückgegeben. Diese umfasst alle Attribute einer Azure-Ressource sowie alle Attribute eines AlertRuleResource-Objekts auf der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="64c98-135">Each element of the the output (a list of objects) of this cmdlet is flattened, i.e. instead of returning objects with the structure `{ Id, Location, Name, Tags, Properties }` it will return objects with the structure `{ Id, Location, Name, Tags, Type, Description, IsEnabled, Condition, Actions, LastUpdatedTime, ...}`, which is all of the attributes of an Azure Resource plus all of the attributes of an AlertRuleResource at the top level.</span></span>
    
```powershell
# Old
$rules = Get-AzureRmAlertRule -ResourceGroup $resourceGroup
if ($rules -and $rules.count -ge 1)
{
    Write-Host -fore red "Error updating alert rule"
      
    Write-Host $rules(0).Id
    Write-Host $rules(0).Properties.IsEnabled
    Write-Host $rules(0).Properties.Condition
}

# New
$rules = Get-AzureRmAlertRule -ResourceGroup $resourceGroup
if ($rules -and $rules.count -ge 1)
{
    Write-Host -fore red "Error updating alert rule"
 
    Write-Host $rules(0).Id
      
    # Properties will remain for a while
    Write-Host $rules(0).Properties.IsEnabled
      
    # But the properties will be at the top level too. Later Properties will be removed
    Write-Host $rules(0).IsEnabled
    Write-Host $rules(0).Condition
}
```
    
### <a name="get-azurermautoscalesetting"></a><span data-ttu-id="64c98-136">Get-AzureRmAutoscaleSetting</span><span class="sxs-lookup"><span data-stu-id="64c98-136">Get-AzureRmAutoscaleSetting</span></span>
- <span data-ttu-id="64c98-137">Das Feld `AutoscaleSettingResourceName` ist veraltet, da es immer denselben Wert besitzt wie das Feld `Name`.</span><span class="sxs-lookup"><span data-stu-id="64c98-137">The `AutoscaleSettingResourceName` field is deprecated since it always has the same value as the `Name` field.</span></span>

```powershell
# Old  
$s1 = Get-AzureRmAutoscaleSetting -ResourceGroup $resourceGroup -Name MySetting
if ($s1.AutoscaleSettingResourceName -ne $s1.Name)
{
    Write-Host "There is something wrong with the name"
}

# New
$s1 = Get-AzureRmAutoscaleSetting -ResourceGroup $resourceGroup -Name MySetting
    
# There won't be a AutoscaleSettingResourceName
Write-Host $s1.Name
```
    
### <a name="remove-azurermlogprofile"></a><span data-ttu-id="64c98-138">Remove-AzureRmLogProfile</span><span class="sxs-lookup"><span data-stu-id="64c98-138">Remove-AzureRmLogProfile</span></span>
- <span data-ttu-id="64c98-139">Die Ausgabe dieses Cmdlets ändert sich von `Boolean` in ein Objekt mit `RequestId` und `StatusCode`.</span><span class="sxs-lookup"><span data-stu-id="64c98-139">The output of this cmdlet will change from `Boolean` to and object containing `RequestId` and `StatusCode`</span></span>

```powershell
# Old  
$s1 = Remove-AzureRmLogProfile -Name myLogProfile
if ($s1 -eq $true)
{
    Write-Host "Removed"
}
else
{
    Write-Host "Failed"
}

# New
$s1 = Remove-AzureRmLogProfile -Name myLogProfile
$r = $s1.RequestId
$s = $s1.StatusCode
```
    
### <a name="add-azurermlogprofile"></a><span data-ttu-id="64c98-140">Add-AzureRmLogProfile</span><span class="sxs-lookup"><span data-stu-id="64c98-140">Add-AzureRmLogProfile</span></span>
- <span data-ttu-id="64c98-141">Die Ausgabe dieses Cmdlets ändert sich von einem Objekt mit Anforderungs-ID, Statuscode und aktualisierter oder neu erstellter Ressource.</span><span class="sxs-lookup"><span data-stu-id="64c98-141">The output of this cmdlet will change from an object that includes the requestId, status code, and the updated or newly created resource</span></span>
    
```powershell
# Old  
$s1 = Add-AzureRmLogProfile -Name default -StorageAccountId /subscriptions/df602c9c-7aa0-407d-a6fb-eb20c8bd1192/resourceGroups/JohnKemTest/providers/Microsoft.Storage/storageAccounts/johnkemtest8162 -Locations Global -categ Delete, Write, Action -retention 3
$r = $s1.ServiceBusRuleId

# New
$s1 = Add-AzureRmLogProfile -Name default -StorageAccountId /subscriptions/df602c9c-7aa0-407d-a6fb-eb20c8bd1192/resourceGroups/JohnKemTest/providers/Microsoft.Storage/storageAccounts/johnkemtest8162 -Locations Global -categ Delete, Write, Action -retention 3
$r = $s1.RequestId
$s = $s1.StatusCode
$a = $s1.NewResource.ServiceBusRuleId
    
```
    
### <a name="set-azurermdiagnosticsettings"></a><span data-ttu-id="64c98-142">Set-AzureRmDiagnosticSettings</span><span class="sxs-lookup"><span data-stu-id="64c98-142">Set-AzureRmDiagnosticSettings</span></span>
- <span data-ttu-id="64c98-143">Der Befehl wird in `Update-AzureRmDiagnsoticSettings` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="64c98-143">The command is going to be renamed to `Update-AzureRmDiagnsoticSettings`</span></span>

```powershell
# Old
Set-AzureRmDiagnosticSettings

# New
Update-AzureRmDiagnosticSettings
```

## <a name="breaking-changes-to-network-cmdlets"></a><span data-ttu-id="64c98-144">Grundlegende Änderungen für Network-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64c98-144">Breaking changes to Network cmdlets</span></span>

<span data-ttu-id="64c98-145">Diese Version hat Auswirkungen auf folgende Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="64c98-145">The following cmdlets were affected this release:</span></span>

### <a name="new-azurermvirtualnetworkgatewayconnection"></a><span data-ttu-id="64c98-146">New-AzureRmVirtualNetworkGatewayConnection</span><span class="sxs-lookup"><span data-stu-id="64c98-146">New-AzureRmVirtualNetworkGatewayConnection</span></span>
- <span data-ttu-id="64c98-147">Der Parameter `EnableBgp` wurde geändert und akzeptiert nun einen Wert vom Typ `boolean` anstelle eines Werts vom Typ `string`.</span><span class="sxs-lookup"><span data-stu-id="64c98-147">`EnableBgp` parameter has been changed to take a `boolean` instead of a `string`</span></span>

```powershell
# Old
New-AzureRmVirtualNetworkGatewayConnection -ResourceGroupName "RG" -name "conn1" -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localnetGateway -ConnectionType IPsec -SharedKey "key" -EnableBgp "true"

# New
New-AzureRmVirtualNetworkGatewayConnection -ResourceGroupName "RG" -name "conn1" -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localnetGateway -ConnectionType IPsec -SharedKey "key" -EnableBgp $true
```

## <a name="breaking-changes-to-servicebus-cmdlets"></a><span data-ttu-id="64c98-148">Grundlegende Änderungen für ServiceBus-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64c98-148">Breaking changes to ServiceBus cmdlets</span></span>

<span data-ttu-id="64c98-149">Diese Version hat Auswirkungen auf folgende Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="64c98-149">The following cmdlets were affected this release:</span></span>

### <a name="get-azurermservicebusnamespace"></a><span data-ttu-id="64c98-150">Get-AzureRmServiceBusNamespace</span><span class="sxs-lookup"><span data-stu-id="64c98-150">Get-AzureRmServiceBusNamespace</span></span>
- <span data-ttu-id="64c98-151">Die Eigenschaft `ResourceGroupName` wurde aus dem Ausgabetyp `NamespaceAttributes` entfernt.</span><span class="sxs-lookup"><span data-stu-id="64c98-151">The property `ResourceGroupName` has been removed from the output type `NamespaceAttributes`</span></span>

### <a name="new-azurermservicebusnamespace"></a><span data-ttu-id="64c98-152">New-AzureRmServiceBusNamespace</span><span class="sxs-lookup"><span data-stu-id="64c98-152">New-AzureRmServiceBusNamespace</span></span>

- <span data-ttu-id="64c98-153">Die Eigenschaft `ResourceGroupName` wurde aus dem Ausgabetyp `NamespaceAttributes` entfernt.</span><span class="sxs-lookup"><span data-stu-id="64c98-153">The property `ResourceGroupName` has been removed from the output type `NamespaceAttributes`</span></span>

## <a name="breaking-changes-to-sql-cmdlets"></a><span data-ttu-id="64c98-154">Grundlegende Änderungen für Sql-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64c98-154">Breaking changes to Sql cmdlets</span></span>

<span data-ttu-id="64c98-155">Diese Version hat Auswirkungen auf folgende Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="64c98-155">The following cmdlets were affected this release:</span></span>

### <a name="new-azurermsqldatabasefailovergroup"></a><span data-ttu-id="64c98-156">New-AzureRmSqlDatabaseFailoverGroup</span><span class="sxs-lookup"><span data-stu-id="64c98-156">New-AzureRmSqlDatabaseFailoverGroup</span></span>
- <span data-ttu-id="64c98-157">Der Parameter `Tag` wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="64c98-157">`Tag` parameter has been removed</span></span>
- <span data-ttu-id="64c98-158">Der Parameter `GracePeriodWithDataLossHour` wurde in `GracePeriodWithDataLossHours` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="64c98-158">`GracePeriodWithDataLossHour` parameter has been renamed to `GracePeriodWithDataLossHours`</span></span>

```powershell
# Old
New-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -PartnerServerName server2 -FailoverPolicy Automatic -GracePeriodWithDataLossHour 1 -Tag @{ Environment="Test" }

# New
New-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -PartnerServerName server2 -FailoverPolicy Automatic -GracePeriodWithDataLossHours 1
```

### <a name="set-azurermsqldatabasefailovergroup"></a><span data-ttu-id="64c98-159">Set-AzureRmSqlDatabaseFailoverGroup</span><span class="sxs-lookup"><span data-stu-id="64c98-159">Set-AzureRmSqlDatabaseFailoverGroup</span></span>
- <span data-ttu-id="64c98-160">Der Parameter `Tag` wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="64c98-160">`Tag` parameter has been removed</span></span>
- <span data-ttu-id="64c98-161">Der Parameter `GracePeriodWithDataLossHour` wurde in `GracePeriodWithDataLossHours` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="64c98-161">`GracePeriodWithDataLossHour` parameter has been renamed to `GracePeriodWithDataLossHours`</span></span>

```powershell
# Old
Set-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -FailoverPolicy Automatic -GracePeriodWithDataLossHour 1 -Tag @{ Environment="Test" }

# New
Set-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -FailoverPolicy Automatic -GracePeriodWithDataLossHours 1
```

### <a name="add-azurermsqldatabasetofailovergroup"></a><span data-ttu-id="64c98-162">Add-AzureRmSqlDatabaseToFailoverGroup</span><span class="sxs-lookup"><span data-stu-id="64c98-162">Add-AzureRmSqlDatabaseToFailoverGroup</span></span>
- <span data-ttu-id="64c98-163">Der Parameter `Tag` wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="64c98-163">`Tag` parameter has been removed</span></span>

```powershell
# Old
Add-AzureRmSqlDatabaseToFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -Database $db1 -Tag @{ Environment="Test" }

# New
Add-AzureRmSqlDatabaseToFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -Database $db1
```

###  <a name="remove-azurermsqldatabasefromfailovergroup"></a><span data-ttu-id="64c98-164">Remove-AzureRmSqlDatabaseFromFailoverGroup</span><span class="sxs-lookup"><span data-stu-id="64c98-164">Remove-AzureRmSqlDatabaseFromFailoverGroup</span></span>
- <span data-ttu-id="64c98-165">Der Parameter `Tag` wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="64c98-165">`Tag` parameter has been removed</span></span>

```powershell
# Old
Remove-AzureRmSqlDatabaseFromFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -Database $db1 -Tag @{ Environment="Test" }

# New
Remove-AzureRmSqlDatabaseFromFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -Database $db1
```

### <a name="remove-azurermsqldatabasefailovergroup"></a><span data-ttu-id="64c98-166">Remove-AzureRmSqlDatabaseFailoverGroup</span><span class="sxs-lookup"><span data-stu-id="64c98-166">Remove-AzureRmSqlDatabaseFailoverGroup</span></span>
- <span data-ttu-id="64c98-167">Der Parameter `PartnerResourceGroupName` wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="64c98-167">`PartnerResourceGroupName` parameter has been removed</span></span>
- <span data-ttu-id="64c98-168">Der Parameter `PartnerServerName` wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="64c98-168">`PartnerServerName` parameter has been removed</span></span>

```powershell
# Old
Remove-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -PartnerServerName server2 -PartnerResourceGroupName rg

# New
Remove-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg
```

### <a name="set-azurermsqldatabasethreatdetectionpolicy"></a><span data-ttu-id="64c98-169">Set-AzureRmSqlDatabaseThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="64c98-169">Set-AzureRmSqlDatabaseThreatDetectionPolicy</span></span>
- <span data-ttu-id="64c98-170">Der Wert `Usage_Anomaly` ist für den Parameter `ExcludedDetectionType` nicht mehr gültig.</span><span class="sxs-lookup"><span data-stu-id="64c98-170">The value `Usage_Anomaly` is no longer valid for the parameter `ExcludedDetectionType`</span></span>

### <a name="set-azurermsqlserverthreatdetectionpolicy"></a><span data-ttu-id="64c98-171">Set-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="64c98-171">Set-AzureRmSqlServerThreatDetectionPolicy</span></span>
- <span data-ttu-id="64c98-172">Der Wert `Usage_Anomaly` ist für den Parameter `ExcludedDetectionType` nicht mehr gültig.</span><span class="sxs-lookup"><span data-stu-id="64c98-172">The value `Usage_Anomaly` is no longer valid for the parameter `ExcludedDetectionType`</span></span>

## <a name="breaking-changes-to-storage-cmdlets"></a><span data-ttu-id="64c98-173">Grundlegende Änderungen für Storage-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64c98-173">Breaking changes to Storage cmdlets</span></span>

<span data-ttu-id="64c98-174">Diese Version hat Auswirkungen auf folgende Ausgabetypeigenschaften:</span><span class="sxs-lookup"><span data-stu-id="64c98-174">The following output type properties were affected this release:</span></span>

### <a name="azurestorageblobicloudblobserviceclient"></a><span data-ttu-id="64c98-175">AzureStorageBlob.ICloudBlob.ServiceClient</span><span class="sxs-lookup"><span data-stu-id="64c98-175">AzureStorageBlob.ICloudBlob.ServiceClient</span></span>
- <span data-ttu-id="64c98-176">Folgende Eigenschaften wurden aus diesem Typ entfernt. (_Hinweis:_ Sie stehen weiterhin in der Eigenschaft `DefaultRequestOptions` zur Verfügung.)</span><span class="sxs-lookup"><span data-stu-id="64c98-176">The following properties were removed from this type (_note_: they can still be found in `DefaultRequestOptions` property):</span></span>
    - `LocationMode`
    - `MaximumExecutionTime`
    - `ServerTimeout`
    - `ParallelOperationThreadCount`
    - `SingleBlobUploadThresholdInBytes`
- <span data-ttu-id="64c98-177">Diese Änderung wirkt sich auf folgende Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="64c98-177">This change affects the following cmdlets:</span></span>
    - `Get-AzureStorageBlob`
    - `Get-AzureStorageBlobContent`
    - `Get-AzureStorageBlobCopyState`
    - `Set-AzureStorageBlobContent`
    - `Start-AzureStorageBlobCopy`
    - `Stop-AzureStorageBlobCopy`
    
### <a name="azurestoragecontainercloudblobcontainerserviceclient"></a><span data-ttu-id="64c98-178">AzureStorageContainer.CloudBlobContainer.ServiceClient</span><span class="sxs-lookup"><span data-stu-id="64c98-178">AzureStorageContainer.CloudBlobContainer.ServiceClient</span></span>
- <span data-ttu-id="64c98-179">Folgende Eigenschaften wurden aus diesem Typ entfernt. (_Hinweis:_ Sie stehen weiterhin in der Eigenschaft `DefaultRequestOptions` zur Verfügung.)</span><span class="sxs-lookup"><span data-stu-id="64c98-179">The following properties were removed from this type (_note_: they can still be found in the `DefaultRequestOptions` property):</span></span>
    - `LocationMode`
    - `MaximumExecutionTime`
    - `ServerTimeout`
    - `ParallelOperationThreadCount`
    - `SingleBlobUploadThresholdInBytes`
- <span data-ttu-id="64c98-180">Diese Änderung wirkt sich auf folgende Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="64c98-180">This change affects the following cmdlets:</span></span>
    - `Get-AzureStorageContainer`
    - `New-AzureStorageContainer`
    - `Set-AzureStorageContainerAcl`
    
### <a name="azurestoragequeuecloudqueueserviceclient"></a><span data-ttu-id="64c98-181">AzureStorageQueue.CloudQueue.ServiceClient</span><span class="sxs-lookup"><span data-stu-id="64c98-181">AzureStorageQueue.CloudQueue.ServiceClient</span></span>
- <span data-ttu-id="64c98-182">Folgende Eigenschaften wurden aus diesem Typ entfernt. (_Hinweis:_ Sie stehen weiterhin in der Eigenschaft `DefaultRequestOptions` zur Verfügung.)</span><span class="sxs-lookup"><span data-stu-id="64c98-182">The following properties were removed from this type (_note_: they can still be found in the `DefaultRequestOptions` property):</span></span>
    - `LocationMode`
    - `MaximumExecutionTime`
    - `RetryPolicy`
    - `ServerTimeout`
- <span data-ttu-id="64c98-183">Diese Änderung wirkt sich auf folgende Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="64c98-183">This change affects the following cmdlets:</span></span>
    - `Get-AzureStorageQueue`
    - `New-AzureStorageQueue`
    
### <a name="azurestoragetablecloudtableserviceclient"></a><span data-ttu-id="64c98-184">AzureStorageTable.CloudTable.ServiceClient</span><span class="sxs-lookup"><span data-stu-id="64c98-184">AzureStorageTable.CloudTable.ServiceClient</span></span>
- <span data-ttu-id="64c98-185">Folgende Eigenschaften wurden aus diesem Typ entfernt. (_Hinweis:_ Sie stehen weiterhin in der Eigenschaft `DefaultRequestOptions` zur Verfügung.)</span><span class="sxs-lookup"><span data-stu-id="64c98-185">The following properties were removed from this type (_note_: they can still be found in the `DefaultRequestOptions` property):</span></span>
    - `LocationMode`
    - `MaximumExecutionTime`
    - `PayloadFormat`
    - `RetryPolicy`
    - `ServerTimeout`
- <span data-ttu-id="64c98-186">Diese Änderung wirkt sich auf folgende Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="64c98-186">This change affects the following cmdlets:</span></span>
    - `Get-AzureStorageTable`
    - `New-AzureStorageTable`
    
```powershell
# Old
$LocationMode = (Get-AzureStorageBlob -Container $containername)[0].ICloudBlob.ServiceClient.LocationMode       
$ParallelOperationThreadCount = (Get-AzureStorageContainer -Container $containername).CloudBlobContainer.ServiceClient.ParallelOperationThreadCount
$PayloadFormat = (Get-AzureStorageTable -Name $tablename).CloudTable.ServiceClient.PayloadFormat
$RetryPolicy = (Get-AzureStorageQueue -Name $queuename).CloudQueue.ServiceClient.RetryPolicy

# New
$LocationMode = (Get-AzureStorageBlob -Container $containername)[0].ICloudBlob.ServiceClient.DefaultRequestOptions.LocationMode     
$ParallelOperationThreadCount = (Get-AzureStorageContainer -Container $containername).CloudBlobContainer.ServiceClient.DefaultRequestOptions.ParallelOperationThreadCount
$PayloadFormat = (Get-AzureStorageTable -Name $tablename).CloudTable.ServiceClient.DefaultRequestOptions.PayloadFormat
$RetryPolicy = (Get-AzureStorageQueue -Name $queuename).CloudQueue.ServiceClient.DefaultRequestOptions.RetryPolicy
```

## <a name="breaking-changes-to-profile-cmdlets"></a><span data-ttu-id="64c98-187">Grundlegende Änderungen für Profile-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64c98-187">Breaking Changes to Profile Cmdlets</span></span>

<span data-ttu-id="64c98-188">In dieser Version wurden folgende Cmdlets und Cmdlet-Ausgabetypen geändert:</span><span class="sxs-lookup"><span data-stu-id="64c98-188">The following cmdlets and cmdlet output types were changed in this release.</span></span>

### <a name="add-azurermaccount-breaking-changes"></a><span data-ttu-id="64c98-189">Grundlegende Änderungen für „Add-AzureRmAccount“</span><span class="sxs-lookup"><span data-stu-id="64c98-189">Add-AzureRmAccount breaking changes</span></span>

- <span data-ttu-id="64c98-190">Der Parameter ```EnvironmentName``` wurde entfernt und durch ```Environment``` ersetzt. ```Environment``` akzeptiert nun eine Zeichenfolge anstelle eines Objekts vom Typ ```AzureEnvironment```.</span><span class="sxs-lookup"><span data-stu-id="64c98-190">```EnvironmentName``` parameter has been removed and replaced with ```Environment```, the ```Environment``` now takes a string and not an ```AzureEnvironment``` object</span></span>

```powershell
# Old
Add-AzureRmAccount -EnvironmentName AzureChinaCloud

# New
Add-AzureRmAccount -Environment AzureChinaCloud
```

### <a name="select-azurermprofile-was-renamed-to-import-azurermcontext"></a><span data-ttu-id="64c98-191">„Select-AzureRmProfile“ wurde in „Import-AzureRmContext“ umbenannt.</span><span class="sxs-lookup"><span data-stu-id="64c98-191">Select-AzureRmProfile was renamed to Import-AzureRmContext</span></span>

<span data-ttu-id="64c98-192">```Select-AzureRmProfile``` wurde in ```Import-AzureRmContext``` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="64c98-192">```Select-AzureRmProfile``` was renamed to ```Import-AzureRmContext```</span></span>

```powershell
# Old
Select-AzureRmProfile -Path c:\mydir\myprofile.json

# New
Import-AzureRmContext -Path c:\mydir\myprofile.json
```

### <a name="save-azurermprofile-was-renamed-to-save-azurermcontext"></a><span data-ttu-id="64c98-193">„Save-AzureRmProfile“ wurde in „Save-AzureRmContext“ umbenannt.</span><span class="sxs-lookup"><span data-stu-id="64c98-193">Save-AzureRmProfile was renamed to Save-AzureRmContext</span></span>

<span data-ttu-id="64c98-194">```Save-AzureRmProfile``` wurde in ```Save-AzureRmContext``` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="64c98-194">```Save-AzureRmProfile``` was renamed to ```Save-AzureRmContext```</span></span>

```powershell
# Old
Save-AzureRmProfile -Path c:\mydir\myprofile.json

# New
Save-AzureRmContext -Path c:\mydir\myprofile.json
```
### <a name="breaking-changes-to-output-psazurecontext-type"></a><span data-ttu-id="64c98-195">Grundlegende Änderungen für den Ausgabetyp „PSAzureContext“</span><span class="sxs-lookup"><span data-stu-id="64c98-195">Breaking Changes to output PSAzureContext Type</span></span>

- <span data-ttu-id="64c98-196">Die Eigenschaft ```TokenCache``` wurde in einen Typ geändert, der ```IAzureTokenCache``` (anstelle von ```byte[]```) implementiert.</span><span class="sxs-lookup"><span data-stu-id="64c98-196">The ```TokenCache``` property changed to a type that implements ```IAzureTokenCache``` instead of a ```byte[]```</span></span>

```powershell
# Old
$bytes = (Get-AzureRmContext).TokenCache
$bytes = (Set-AzureRmContext -SubscriptionId xxx-xxx-xxx-xxx).TokenCache
$bytes = (Add-AzureRmAccount).Context.TokenCache

# New
$bytes = (Get-AzureRmContext).TokenCache.CacheData
$bytes = (Set-AzureRmContext -SubscriptionId xxx-xxx-xxx-xxx).TokenCache.CacheData
$bytes = (Add-AzureRmAccount).Context.TokenCache.CacheData
```

### <a name="breaking-changes-to-the-output-psazureaccount-type"></a><span data-ttu-id="64c98-197">Grundlegende Änderungen für den Ausgabetyp „PSAzureAccount“</span><span class="sxs-lookup"><span data-stu-id="64c98-197">Breaking Changes to the output PSAzureAccount Type</span></span>

- <span data-ttu-id="64c98-198">Die Eigenschaft ```AccountType``` wurde in ```Type``` geändert.</span><span class="sxs-lookup"><span data-stu-id="64c98-198">The ```AccountType``` property was changed to ```Type```</span></span>

```powershell
# Old
$type = (Get-AzureRmContext).Account.AccountType
$type = (Set-AzureRmContext -SubscriptionId xxx-xxx-xxx-xxx).Account.AccountType
$type = (Add-AzureRmAccount).Context.Account.AccountType

# New 
$type = (Get-AzureRmContext).Account.Type
$type = (Set-AzureRmContext -SubscriptionId xxx-xxx-xxx-xxx).Account.Type
$type = (Add-AzureRmAccount).Context.Account.Type
```

### <a name="breaking-changes-to-the-output-psazuresubscription-type"></a><span data-ttu-id="64c98-199">Grundlegende Änderungen für den Ausgabetyp „PSAzureSubscription“</span><span class="sxs-lookup"><span data-stu-id="64c98-199">Breaking Changes to the output PSAzureSubscription Type</span></span>
- <span data-ttu-id="64c98-200">Die Eigenschaft ```SubscriptionId``` wurde in ```Id``` geändert.</span><span class="sxs-lookup"><span data-stu-id="64c98-200">The ```SubscriptionId``` property was changed to ```Id```</span></span>

```powershell
# Old
$id =(Get-AzureRmSubscription -SubscriptionId xxxx-xxxx-xxxx-xxxx).SubscriptionId
$id =(Add-AzureRmAccount -SubscriptionId xxxx-xxxx-xxxx-xxxx).Context.Subscription.SubscriptionId
$id =(Get-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Subscription.SubscriptionId
$id =(Set-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Subscription.SubscriptionId

# New
$id =(Get-AzureRmSubscription -SubscriptionId xxxx-xxxx-xxxx-xxxx).Id
$id =(Add-AzureRmAccount -SubscriptionId xxxx-xxxx-xxxx-xxxx).Context.Subscription.Id
$id =(Get-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Subscription.Id
$id =(Set-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Subscription.Id
```

- <span data-ttu-id="64c98-201">Die Eigenschaft ```SubscriptionName``` wurde in ```Name``` geändert.</span><span class="sxs-lookup"><span data-stu-id="64c98-201">The ```SubscriptionName``` property was changed to ```Name```</span></span>

```powershell
# Old
$name =(Get-AzureRmSubscription -SubscriptionId xxxx-xxxx-xxxx-xxxx).SubscriptionName
$name =(Add-AzureRmAccount -SubscriptionId xxxx-xxxx-xxxx-xxxx).Context.Subscription.SubscriptionName
$name =(Get-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Subscription.SubscriptionName
$name =(Set-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Subscription.SubscriptionName

# New
$name =(Get-AzureRmSubscription -SubscriptionId xxxx-xxxx-xxxx-xxxx).Name
$name =(Add-AzureRmAccount -SubscriptionId xxxx-xxxx-xxxx-xxxx).Context.Subscription.Name
$name =(Get-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Subscription.Name
$name =(Set-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Subscription.Name
```

### <a name="breaking-changes-to-the-output-psazuretenant-type"></a><span data-ttu-id="64c98-202">Grundlegende Änderungen für den Ausgabetyp „PSAzureTenant“</span><span class="sxs-lookup"><span data-stu-id="64c98-202">Breaking Changes to the output PSAzureTenant Type</span></span>

- <span data-ttu-id="64c98-203">Die Eigenschaft ```TenantId``` wurde in ```Id``` geändert.</span><span class="sxs-lookup"><span data-stu-id="64c98-203">The ```TenantId``` property was changed to ```Id```</span></span>

```powershell
# Old
$id =(Get-AzureRmTenant -TenantId xxxx-xxxx-xxxx-xxxx).TenantId
$id =(Add-AzureRmAccount -SubscriptionId xxxx-xxxx-xxxx-xxxx).Context.Tenant.TenantId
$id =(Get-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Tenant.TenantId
$id =(Set-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Tenant.TenantId

# New
$id =(Get-AzureRmTenant -TenantId xxxx-xxxx-xxxx-xxxx).Id
$id =(Add-AzureRmAccount -SubscriptionId xxxx-xxxx-xxxx-xxxx).Context.Tenant.Id
$id =(Get-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Tenant.Id
$id =(Set-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Tenant.Id
```

- <span data-ttu-id="64c98-204">Die Eigenschaft ```Domain``` wurde in ```Directory``` geändert.</span><span class="sxs-lookup"><span data-stu-id="64c98-204">The ```Domain``` property was changed to ```Directory```</span></span>

```powershell
# Old
$tenantName =(Get-AzureRmTenant -TenantId xxxx-xxxx-xxxx-xxxx).Domain

# New
$tenantName =(Get-AzureRmTenant -TenantId xxxx-xxxx-xxxx-xxxx).Directory
```
