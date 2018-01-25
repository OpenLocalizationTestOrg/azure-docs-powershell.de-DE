# <a name="table-of-contents"></a>Inhaltsverzeichnis
1. [Entfernung von Force-Parametern](#removal-of-force-parameters)
2. [Änderung von Tag-Parametern](#change-of-tag-parameters)
3. [Grundlegende Änderungen für Storage-Cmdlets](#breaking-changes-to-storage-cmdlets)
4. [Grundlegende Änderungen für AD-Cmdlets](#breaking-changes-to-ad-cmdlets)

## <a name="removal-of-force-parameters"></a>Entfernung des Force-Parameters

In dieser Version haben wir sowohl alle veralteten `Force`-Parameter aus Cmdlets als auch die entsprechenden Warnungen mit dem Hinweis entfernt, dass der Parameter in einer zukünftigen Version entfernt wird.

Diese Änderung betrifft folgende Cmdlets:

**ApiManagement**
- Remove-AzureRmApiManagement
- Remove-AzureRmApiManagementApi
- Remove-AzureRmApiManagementGroup
- Remove-AzureRmApiManagementLogger
- Remove-AzureRmApiManagementOpenIdConnectProvider
- Remove-AzureRmApiManagementOperation
- Remove-AzureRmApiManagementPolicy
- Remove-AzureRmApiManagementProduct
- Remove-AzureRmApiManagementProperty
- Remove-AzureRmApiManagementSubscription
- Remove-AzureRmApiManagementUser

**Automation**
- Remove-AzureRmAutomationCertificate
- Remove-AzureRmAutomationCredential
- Remove-AzureRmAutomationVariable
- Remove-AzureRmAutomationWebhook

**Batch**
- Remove-AzureBatchCertificate
- Remove-AzureBatchComputeNode
- Remove-AzureBatchComputeNodeUser

**DataFactories**
- Resume-AzureRmDataFactoryPipeline
- Set-AzureRmDataFactoryPipelineActivePeriod
- Suspend-AzureRmDataFactoryPipeline

**DataLakeStore**
- Remove-AzureRmDataLakeStoreItemAclEntry
- Set-AzureRmDataLakeStoreItemAcl
- Set-AzureRmDataLakeStoreItemAclEntry
- Set-AzureRmDataLakeStoreItemOwner

**OperationalInsights**
- Remove-AzureRmOperationalInsightsSavedSearch

**Profil**
- Remove-AzureRmEnvironment

**RedisCache**
- Remove-AzureRmRedisCacheDiagnostics

**Ressourcen**
- Register-AzureRmProviderFeature
- Register-AzureRmResourceProvider
- Remove-AzureRmADServicePrincipal
- Remove-AzureRmPolicyAssignment
- Remove-AzureRmResourceGroupDeployment
- Remove-AzureRmRoleAssignment
- Stop-AzureRmResourceGroupDeployment
- Unregister-AzureRmResourceProvider

**Storage**
- Remove-AzureStorageContainerStoredAccessPolicy
- Remove-AzureStorageQueueStoredAccessPolicy
- Remove-AzureStorageShareStoredAccessPolicy
- Remove-AzureStorageTableStoredAccessPolicy

**StreamAnalytics**
- Remove-AzureRmStreamAnalyticsFunction
- Remove-AzureRmStreamAnalyticsInput
- Remove-AzureRmStreamAnalyticsJob
- Remove-AzureRmStreamAnalyticsOutput

**Tag**
- Remove-AzureRmTag

<br>

Wenn Sie über ein Skript verfügen, das eines der oben angegebenen Cmdlets verwendet, können Sie zur Behandlung der grundlegenden Änderungen einfach den `Force`-Parameter entfernen.

```powershell
# Old
New-AzureRmResourceGroup -Name $resourceGroupName -Location $location -Force

# New
New-AzureRmResourceGroup -Name $resourceGroupName -Location $location
```

<br>

## <a name="change-of-tag-parameters"></a>Änderung von Tag-Parametern

In dieser Version wurde der `Tags`-Parametername in `Tag` und der Typ von `Hashtable[]` in `Hashtable` geändert, wodurch sich das Format der Schlüssel-Wert-Paare ändert.

Bislang stand jeder Eintrag in `Hashtable[]` für ein einzelnes Schlüssel-Wert-Paar:

```powershell
$tags = @{ Name = "test1"; Value = "testval1" }, @{ Name = "test2", Value = "testval2" }
$tags[0].Name  # Key for the first entry, "test1"
$tags[0].Value # Value for the first entry, "testval1"
$tags[1].Name  # Key for the second entry, "test2"
$tags[1].Value # Value for the second entry, "testval2"
```

In Zukunft werden `Name` und `Value` nicht mehr benötigt, sodass Schlüssel-Wert-Paare nun durch Zuweisen von `Key = "Value"` in `Hashtable` erstellt werden können:

```powershell
$tag = @{ test1 = "testval1"; test2 = "testval2" }
$tag["test1"] # Gets the value associated with the key "test1"
$tag["test2"] # Gets the value associated with the key "test2"
```

Diese Änderung betrifft folgende Cmdlets:

**Batch**
- Get-AzureRmBatchAccount
- New-AzureRmBatchAccount
- Set-AzureRmBatchAccount

**Compute**
- New-AzureRmVM
- Update-AzureRmVM

**DataLakeAnalytics**
- New-AzureRmDataLakeAnalyticsAccount
- Set-AzureRmDataLakeAnalyticsAccount

**DataLakeStore**
- New-AzureRmDataLakeStoreAccount
- Set-AzureRmDataLakeStoreAccount

**Dns**
- New-AzureRmDnsZone
- Set-AzureRmDnsZone

**KeyVault**
- Get-AzureRmKeyVault
- New-AzureRmKeyVault

**Netzwerk**
- New-AzureRmApplicationGateway
- New-AzureRmExpressRouteCircuit
- New-AzureRmLoadBalancer
- New-AzureRmLocalNetworkGateway
- New-AzureRmNetworkInterface
- New-AzureRmNetworkSecurityGroup
- New-AzureRmPublicIpAddress
- New-AzureRmRouteTable
- New-AzureRmVirtualNetwork
- New-AzureRmVirtualNetworkGateway
- New-AzureRmVirtualNetworkGatewayConnection
- New-AzureRmVirtualNetworkPeering

**Ressourcen**
- Find-AzureRmResource
- Find-AzureRmResourceGroup
- New-AzureRmResource
- New-AzureRmResourceGroup
- Set-AzureRmResource
- Set-AzureRmResourceGroup

**SQL**
- New-AzureRmSqlDatabase
- New-AzureRmSqlDatabaseCopy
- New-AzureRmSqlDatabaseSecondary
- New-AzureRmSqlElasticPool
- New-AzureRmSqlServer
- Set-AzureRmSqlDatabase
- Set-AzureRmSqlElasticPool
- Set-AzureRmSqlServer

**Storage**
- New-AzureRmStorageAccount
- Set-AzureRmStorageAccount

**TrafficManager**
- New-AzureRmTrafficManagerProfile

<br>

Wenn Sie über ein Skript verfügen, das eines der oben angegebenen Cmdlets verwendet, können Sie zur Behandlung der grundlegenden Änderungen den `Tags`-Parameter in `Tag` umbenennen und `Tag` im neuen Format angeben.

```powershell
# Old
New-AzureRmResourceGroup -Name $resourceGroupName -Location -location -Tags @{ Name = "testtag"; Value = "testval" }

# New
New-AzureRmResourceGroup -Name $resourceGroupName -Location -location -Tag @{ testtag = "testval" }
```

<br>

## <a name="breaking-changes-to-storage-cmdlets"></a>Grundlegende Änderungen für Storage-Cmdlets

Diese Version hat Auswirkungen auf folgende Cmdlets:

**Get-AzureRmStorageAccountKey**
- Anstelle eines Objekts mit Eigenschaften für die einzelnen Schlüssel gibt das Cmdlet jetzt eine Liste mit Schlüsseln zurück.

```powershell
# Old
$key = (Get-AzureRmStorageAccountKey -ResourceGroupName $resourceGroupName -Name $accountName).Key1

# New
$key = (Get-AzureRmStorageAccountKey -ResourceGroupName $resourceGroupName -Name $accountName)[0].Value
```

**New-AzureRmStorageAccountKey**
- Das Feld `StorageAccountRegenerateKeyResponse` in der Ausgabe dieses Cmdlets wird in `StorageAccountListKeysResults` umbenannt und ist nun kein Objekt mit Eigenschaften für die einzelnen Schlüssel mehr, sondern eine Liste mit Schlüsseln.

```powershell
# Old
$key = (New-AzureRmStorageAccountKey -ResourceGroupName $resourceGroupName -Name $accountName).StorageAccountKeys.Key1

# New
$key = (New-AzureRmStorageAccountKey -ResourceGroupName $resourceGroupName -Name $accountName).Keys[0].Value
```

**New/Get/Set-AzureRmStorageAccount**
- Das Feld `AccountType` in der Ausgabe des Cmdlets wird in `Sku.Name` umbenannt.
- Der Ausgabetyp für primäre/sekundäre Endpunkte (Blob/Tabelle/Warteschlange/Datei) wird von `Uri` in `String` geändert.

```powershell
# Old
$accountType = (Get-AzureRmStorageAccount -ResourceGroupName $resourceGroupName -Name $accountName).AccountType

# New
$accountType = (Get-AzureRmStorageAccount -ResourceGroupName $resourceGroupName -Name $accountName).Sku.Name
```

```powershell
# Old 
$blobEndpoint = (Get-AzureRmStorageAccount -ResourceGroupName $resourceGroupName -Name $accountName).PrimaryEndpoints.Blob.ToString()
$blobEndpoint = (Get-AzureRmStorageAccount -ResourceGroupName $resourceGroupName -Name $accountName).PrimaryEndpoints.Blob.AbsolutePath

# New
$blobEndpoint = (Get-AzureRmStorageAccount -ResourceGroupName $resourceGroupName -Name $accountName).PrimaryEndpoints.Blob.ToString()
$blobEndpoint = (Get-AzureRmStorageAccount -ResourceGroupName $resourceGroupName -Name $accountName).PrimaryEndpoints.Blob
```

<br>

## <a name="breaking-changes-to-ad-cmdlets"></a>Grundlegende Änderungen für AD-Cmdlets

Diese Version hat Auswirkungen auf folgende Cmdlets:

**Get-AzureRMADServicePrincipal**
- Das Feld `ServicePrincipalName` in der Ausgabe des Cmdlets wird in `ServicePrincipalNames` umbenannt und ist nun eine Sammlung. Es zeigt nun `ApplicationId` auch als einen der Dienstprinzipalnamen an (zusammen mit dem Bezeichner-URI).

```powershell
# Old
$servicePrincipals = Get-AzureRmADServicePrincipal -SearchString $displayName
$spn = $servicePrincipals[0].ServicePrincipalName

# New
$servicePrincipals = Get-AzureRmADServicePrincipal -SearchString $displayName
$spn = $servicePrincipals[0].ServicePrincipalNames[0]
```

**Get-AzureRmADApplication**
- Der Parameter `ApplicationObjectId` wird in `ObjectId` umbenannt.
- In der Ausgabe des Cmdlets wird `ApplicationObjectId` in `ObjectId` umbenannt.

```powershell
# Old
$app = Get-AzureRmADApplication -ApplicationObjectId $applicationObjectId
$objectId = $app.ApplicationObjectId

# New
$app = Get-AzureRmADApplication -ObjectId $objectId
$objectId = $app.ObjectId
```

**Remove-AzureRmADApplication**
- Der Parameter `ApplicationObjectId` wird in `ObjectId` umbenannt.

```powershell
# Old
$app = Remove-AzureRmADApplication -ApplicationObjectId $applicationObjectId -Force

# New
$app = Remove-AzureRmADApplication -ObjectId $objectId -Force
```

**New-AzureRmADApplication**
- In der Ausgabe des Cmdlets wird `ApplicationObjectId` in `ObjectId` umbenannt.
- Die Parameter `KeyValue`, `KeyUsage` und `KeyType` werden entfernt.

```powershell
# Old
$app = New-AzureRmADApplication -DisplayName $displayName -HomePage $homePage -IdentifierUris $identifierUris -KeyValue $kv -KeyType $kt -KeyUsage $ku
$id = $app.ApplicationObjectId

# New
$app = New-AzureRmADApplication -DisplayName $displayName -HomePage $homePage -IdentifierUris $identifierUris
$id = $app.ObjectId
New-AzureRmADAppCredential -ObjectId $id -Password $kv
```

**Get-AzureRmADGroup**
- Das Feld `Mail` wird aus der Ausgabe entfernt.

**Get-AzureRmADUser**
- Das Feld `Mail` wird aus der Ausgabe entfernt.

**New-AzureRmADServicePrincipal**
- Der Parameter `DisableAccount` wurde entfernt.

```powershell
# Old
$servicePrincipal = New-AzureRmADServicePrincipal -DisplayName $displayName -Password $password -DisableAccount true

# New
$servicePrincipal = New-AzureRmADServicePrincipal -DisplayName $displayName -Password $password
Remove-AzureRmADServicePrincipal -ObjectId $servicePrincipal.ObjectId
```