# <a name="table-of-contents"></a><span data-ttu-id="aa7c0-101">Inhaltsverzeichnis</span><span class="sxs-lookup"><span data-stu-id="aa7c0-101">Table of Contents</span></span>
1. [<span data-ttu-id="aa7c0-102">Entfernung von Force-Parametern</span><span class="sxs-lookup"><span data-stu-id="aa7c0-102">Removal of Force parameters</span></span>](#removal-of-force-parameters)
2. [<span data-ttu-id="aa7c0-103">Änderung von Tag-Parametern</span><span class="sxs-lookup"><span data-stu-id="aa7c0-103">Change of Tag parameters</span></span>](#change-of-tag-parameters)
3. [<span data-ttu-id="aa7c0-104">Grundlegende Änderungen für Storage-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="aa7c0-104">Breaking changes to Storage cmdlets</span></span>](#breaking-changes-to-storage-cmdlets)
4. [<span data-ttu-id="aa7c0-105">Grundlegende Änderungen für AD-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="aa7c0-105">Breaking changes to AD cmdlets</span></span>](#breaking-changes-to-ad-cmdlets)

## <a name="removal-of-force-parameters"></a><span data-ttu-id="aa7c0-106">Entfernung des Force-Parameters</span><span class="sxs-lookup"><span data-stu-id="aa7c0-106">Removal of Force parameters</span></span>

<span data-ttu-id="aa7c0-107">In dieser Version haben wir sowohl alle veralteten `Force`-Parameter aus Cmdlets als auch die entsprechenden Warnungen mit dem Hinweis entfernt, dass der Parameter in einer zukünftigen Version entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-107">This release, we removed all Obsolete `Force` parameters from cmdlets and the corresponding warnings that the parameter would be removed in a future release.</span></span>

<span data-ttu-id="aa7c0-108">Diese Änderung betrifft folgende Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="aa7c0-108">The following cmdlets are affected by this change:</span></span>

<span data-ttu-id="aa7c0-109">**ApiManagement**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-109">**ApiManagement**</span></span>
- <span data-ttu-id="aa7c0-110">Remove-AzureRmApiManagement</span><span class="sxs-lookup"><span data-stu-id="aa7c0-110">Remove-AzureRmApiManagement</span></span>
- <span data-ttu-id="aa7c0-111">Remove-AzureRmApiManagementApi</span><span class="sxs-lookup"><span data-stu-id="aa7c0-111">Remove-AzureRmApiManagementApi</span></span>
- <span data-ttu-id="aa7c0-112">Remove-AzureRmApiManagementGroup</span><span class="sxs-lookup"><span data-stu-id="aa7c0-112">Remove-AzureRmApiManagementGroup</span></span>
- <span data-ttu-id="aa7c0-113">Remove-AzureRmApiManagementLogger</span><span class="sxs-lookup"><span data-stu-id="aa7c0-113">Remove-AzureRmApiManagementLogger</span></span>
- <span data-ttu-id="aa7c0-114">Remove-AzureRmApiManagementOpenIdConnectProvider</span><span class="sxs-lookup"><span data-stu-id="aa7c0-114">Remove-AzureRmApiManagementOpenIdConnectProvider</span></span>
- <span data-ttu-id="aa7c0-115">Remove-AzureRmApiManagementOperation</span><span class="sxs-lookup"><span data-stu-id="aa7c0-115">Remove-AzureRmApiManagementOperation</span></span>
- <span data-ttu-id="aa7c0-116">Remove-AzureRmApiManagementPolicy</span><span class="sxs-lookup"><span data-stu-id="aa7c0-116">Remove-AzureRmApiManagementPolicy</span></span>
- <span data-ttu-id="aa7c0-117">Remove-AzureRmApiManagementProduct</span><span class="sxs-lookup"><span data-stu-id="aa7c0-117">Remove-AzureRmApiManagementProduct</span></span>
- <span data-ttu-id="aa7c0-118">Remove-AzureRmApiManagementProperty</span><span class="sxs-lookup"><span data-stu-id="aa7c0-118">Remove-AzureRmApiManagementProperty</span></span>
- <span data-ttu-id="aa7c0-119">Remove-AzureRmApiManagementSubscription</span><span class="sxs-lookup"><span data-stu-id="aa7c0-119">Remove-AzureRmApiManagementSubscription</span></span>
- <span data-ttu-id="aa7c0-120">Remove-AzureRmApiManagementUser</span><span class="sxs-lookup"><span data-stu-id="aa7c0-120">Remove-AzureRmApiManagementUser</span></span>

<span data-ttu-id="aa7c0-121">**Automation**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-121">**Automation**</span></span>
- <span data-ttu-id="aa7c0-122">Remove-AzureRmAutomationCertificate</span><span class="sxs-lookup"><span data-stu-id="aa7c0-122">Remove-AzureRmAutomationCertificate</span></span>
- <span data-ttu-id="aa7c0-123">Remove-AzureRmAutomationCredential</span><span class="sxs-lookup"><span data-stu-id="aa7c0-123">Remove-AzureRmAutomationCredential</span></span>
- <span data-ttu-id="aa7c0-124">Remove-AzureRmAutomationVariable</span><span class="sxs-lookup"><span data-stu-id="aa7c0-124">Remove-AzureRmAutomationVariable</span></span>
- <span data-ttu-id="aa7c0-125">Remove-AzureRmAutomationWebhook</span><span class="sxs-lookup"><span data-stu-id="aa7c0-125">Remove-AzureRmAutomationWebhook</span></span>

<span data-ttu-id="aa7c0-126">**Batch**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-126">**Batch**</span></span>
- <span data-ttu-id="aa7c0-127">Remove-AzureBatchCertificate</span><span class="sxs-lookup"><span data-stu-id="aa7c0-127">Remove-AzureBatchCertificate</span></span>
- <span data-ttu-id="aa7c0-128">Remove-AzureBatchComputeNode</span><span class="sxs-lookup"><span data-stu-id="aa7c0-128">Remove-AzureBatchComputeNode</span></span>
- <span data-ttu-id="aa7c0-129">Remove-AzureBatchComputeNodeUser</span><span class="sxs-lookup"><span data-stu-id="aa7c0-129">Remove-AzureBatchComputeNodeUser</span></span>

<span data-ttu-id="aa7c0-130">**DataFactories**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-130">**DataFactories**</span></span>
- <span data-ttu-id="aa7c0-131">Resume-AzureRmDataFactoryPipeline</span><span class="sxs-lookup"><span data-stu-id="aa7c0-131">Resume-AzureRmDataFactoryPipeline</span></span>
- <span data-ttu-id="aa7c0-132">Set-AzureRmDataFactoryPipelineActivePeriod</span><span class="sxs-lookup"><span data-stu-id="aa7c0-132">Set-AzureRmDataFactoryPipelineActivePeriod</span></span>
- <span data-ttu-id="aa7c0-133">Suspend-AzureRmDataFactoryPipeline</span><span class="sxs-lookup"><span data-stu-id="aa7c0-133">Suspend-AzureRmDataFactoryPipeline</span></span>

<span data-ttu-id="aa7c0-134">**DataLakeStore**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-134">**DataLakeStore**</span></span>
- <span data-ttu-id="aa7c0-135">Remove-AzureRmDataLakeStoreItemAclEntry</span><span class="sxs-lookup"><span data-stu-id="aa7c0-135">Remove-AzureRmDataLakeStoreItemAclEntry</span></span>
- <span data-ttu-id="aa7c0-136">Set-AzureRmDataLakeStoreItemAcl</span><span class="sxs-lookup"><span data-stu-id="aa7c0-136">Set-AzureRmDataLakeStoreItemAcl</span></span>
- <span data-ttu-id="aa7c0-137">Set-AzureRmDataLakeStoreItemAclEntry</span><span class="sxs-lookup"><span data-stu-id="aa7c0-137">Set-AzureRmDataLakeStoreItemAclEntry</span></span>
- <span data-ttu-id="aa7c0-138">Set-AzureRmDataLakeStoreItemOwner</span><span class="sxs-lookup"><span data-stu-id="aa7c0-138">Set-AzureRmDataLakeStoreItemOwner</span></span>

<span data-ttu-id="aa7c0-139">**OperationalInsights**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-139">**OperationalInsights**</span></span>
- <span data-ttu-id="aa7c0-140">Remove-AzureRmOperationalInsightsSavedSearch</span><span class="sxs-lookup"><span data-stu-id="aa7c0-140">Remove-AzureRmOperationalInsightsSavedSearch</span></span>

<span data-ttu-id="aa7c0-141">**Profil**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-141">**Profile**</span></span>
- <span data-ttu-id="aa7c0-142">Remove-AzureRmEnvironment</span><span class="sxs-lookup"><span data-stu-id="aa7c0-142">Remove-AzureRmEnvironment</span></span>

<span data-ttu-id="aa7c0-143">**RedisCache**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-143">**RedisCache**</span></span>
- <span data-ttu-id="aa7c0-144">Remove-AzureRmRedisCacheDiagnostics</span><span class="sxs-lookup"><span data-stu-id="aa7c0-144">Remove-AzureRmRedisCacheDiagnostics</span></span>

<span data-ttu-id="aa7c0-145">**Ressourcen**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-145">**Resources**</span></span>
- <span data-ttu-id="aa7c0-146">Register-AzureRmProviderFeature</span><span class="sxs-lookup"><span data-stu-id="aa7c0-146">Register-AzureRmProviderFeature</span></span>
- <span data-ttu-id="aa7c0-147">Register-AzureRmResourceProvider</span><span class="sxs-lookup"><span data-stu-id="aa7c0-147">Register-AzureRmResourceProvider</span></span>
- <span data-ttu-id="aa7c0-148">Remove-AzureRmADServicePrincipal</span><span class="sxs-lookup"><span data-stu-id="aa7c0-148">Remove-AzureRmADServicePrincipal</span></span>
- <span data-ttu-id="aa7c0-149">Remove-AzureRmPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="aa7c0-149">Remove-AzureRmPolicyAssignment</span></span>
- <span data-ttu-id="aa7c0-150">Remove-AzureRmResourceGroupDeployment</span><span class="sxs-lookup"><span data-stu-id="aa7c0-150">Remove-AzureRmResourceGroupDeployment</span></span>
- <span data-ttu-id="aa7c0-151">Remove-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="aa7c0-151">Remove-AzureRmRoleAssignment</span></span>
- <span data-ttu-id="aa7c0-152">Stop-AzureRmResourceGroupDeployment</span><span class="sxs-lookup"><span data-stu-id="aa7c0-152">Stop-AzureRmResourceGroupDeployment</span></span>
- <span data-ttu-id="aa7c0-153">Unregister-AzureRmResourceProvider</span><span class="sxs-lookup"><span data-stu-id="aa7c0-153">Unregister-AzureRmResourceProvider</span></span>

<span data-ttu-id="aa7c0-154">**Storage**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-154">**Storage**</span></span>
- <span data-ttu-id="aa7c0-155">Remove-AzureStorageContainerStoredAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="aa7c0-155">Remove-AzureStorageContainerStoredAccessPolicy</span></span>
- <span data-ttu-id="aa7c0-156">Remove-AzureStorageQueueStoredAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="aa7c0-156">Remove-AzureStorageQueueStoredAccessPolicy</span></span>
- <span data-ttu-id="aa7c0-157">Remove-AzureStorageShareStoredAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="aa7c0-157">Remove-AzureStorageShareStoredAccessPolicy</span></span>
- <span data-ttu-id="aa7c0-158">Remove-AzureStorageTableStoredAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="aa7c0-158">Remove-AzureStorageTableStoredAccessPolicy</span></span>

<span data-ttu-id="aa7c0-159">**StreamAnalytics**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-159">**StreamAnalytics**</span></span>
- <span data-ttu-id="aa7c0-160">Remove-AzureRmStreamAnalyticsFunction</span><span class="sxs-lookup"><span data-stu-id="aa7c0-160">Remove-AzureRmStreamAnalyticsFunction</span></span>
- <span data-ttu-id="aa7c0-161">Remove-AzureRmStreamAnalyticsInput</span><span class="sxs-lookup"><span data-stu-id="aa7c0-161">Remove-AzureRmStreamAnalyticsInput</span></span>
- <span data-ttu-id="aa7c0-162">Remove-AzureRmStreamAnalyticsJob</span><span class="sxs-lookup"><span data-stu-id="aa7c0-162">Remove-AzureRmStreamAnalyticsJob</span></span>
- <span data-ttu-id="aa7c0-163">Remove-AzureRmStreamAnalyticsOutput</span><span class="sxs-lookup"><span data-stu-id="aa7c0-163">Remove-AzureRmStreamAnalyticsOutput</span></span>

<span data-ttu-id="aa7c0-164">**Tag**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-164">**Tag**</span></span>
- <span data-ttu-id="aa7c0-165">Remove-AzureRmTag</span><span class="sxs-lookup"><span data-stu-id="aa7c0-165">Remove-AzureRmTag</span></span>

<br>

<span data-ttu-id="aa7c0-166">Wenn Sie über ein Skript verfügen, das eines der oben angegebenen Cmdlets verwendet, können Sie zur Behandlung der grundlegenden Änderungen einfach den `Force`-Parameter entfernen.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-166">If you have a script that uses any of the above cmdlets, the breaking change can be fixed by simply removing the `Force` parameter.</span></span>

```powershell
# Old
New-AzureRmResourceGroup -Name $resourceGroupName -Location $location -Force

# New
New-AzureRmResourceGroup -Name $resourceGroupName -Location $location
```

<br>

## <a name="change-of-tag-parameters"></a><span data-ttu-id="aa7c0-167">Änderung von Tag-Parametern</span><span class="sxs-lookup"><span data-stu-id="aa7c0-167">Change of Tag parameters</span></span>

<span data-ttu-id="aa7c0-168">In dieser Version wurde der `Tags`-Parametername in `Tag` und der Typ von `Hashtable[]` in `Hashtable` geändert, wodurch sich das Format der Schlüssel-Wert-Paare ändert.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-168">This release, the `Tags` parameter name was changed to `Tag`, and the type was changed from `Hashtable[]` to `Hashtable`, changing the format of the key-value pairings.</span></span>

<span data-ttu-id="aa7c0-169">Bislang stand jeder Eintrag in `Hashtable[]` für ein einzelnes Schlüssel-Wert-Paar:</span><span class="sxs-lookup"><span data-stu-id="aa7c0-169">Previously, each entry in the `Hashtable[]` represented a single key-value pairing:</span></span>

```powershell
$tags = @{ Name = "test1"; Value = "testval1" }, @{ Name = "test2", Value = "testval2" }
$tags[0].Name  # Key for the first entry, "test1"
$tags[0].Value # Value for the first entry, "testval1"
$tags[1].Name  # Key for the second entry, "test2"
$tags[1].Value # Value for the second entry, "testval2"
```

<span data-ttu-id="aa7c0-170">In Zukunft werden `Name` und `Value` nicht mehr benötigt, sodass Schlüssel-Wert-Paare nun durch Zuweisen von `Key = "Value"` in `Hashtable` erstellt werden können:</span><span class="sxs-lookup"><span data-stu-id="aa7c0-170">Now, `Name` and `Value` are no longer necessary, allowing for key-value pairings to be created by assigning `Key = "Value"` in the `Hashtable`:</span></span>

```powershell
$tag = @{ test1 = "testval1"; test2 = "testval2" }
$tag["test1"] # Gets the value associated with the key "test1"
$tag["test2"] # Gets the value associated with the key "test2"
```

<span data-ttu-id="aa7c0-171">Diese Änderung betrifft folgende Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="aa7c0-171">The following cmdlets are affected by this change:</span></span>

<span data-ttu-id="aa7c0-172">**Batch**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-172">**Batch**</span></span>
- <span data-ttu-id="aa7c0-173">Get-AzureRmBatchAccount</span><span class="sxs-lookup"><span data-stu-id="aa7c0-173">Get-AzureRmBatchAccount</span></span>
- <span data-ttu-id="aa7c0-174">New-AzureRmBatchAccount</span><span class="sxs-lookup"><span data-stu-id="aa7c0-174">New-AzureRmBatchAccount</span></span>
- <span data-ttu-id="aa7c0-175">Set-AzureRmBatchAccount</span><span class="sxs-lookup"><span data-stu-id="aa7c0-175">Set-AzureRmBatchAccount</span></span>

<span data-ttu-id="aa7c0-176">**Compute**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-176">**Compute**</span></span>
- <span data-ttu-id="aa7c0-177">New-AzureRmVM</span><span class="sxs-lookup"><span data-stu-id="aa7c0-177">New-AzureRmVM</span></span>
- <span data-ttu-id="aa7c0-178">Update-AzureRmVM</span><span class="sxs-lookup"><span data-stu-id="aa7c0-178">Update-AzureRmVM</span></span>

<span data-ttu-id="aa7c0-179">**DataLakeAnalytics**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-179">**DataLakeAnalytics**</span></span>
- <span data-ttu-id="aa7c0-180">New-AzureRmDataLakeAnalyticsAccount</span><span class="sxs-lookup"><span data-stu-id="aa7c0-180">New-AzureRmDataLakeAnalyticsAccount</span></span>
- <span data-ttu-id="aa7c0-181">Set-AzureRmDataLakeAnalyticsAccount</span><span class="sxs-lookup"><span data-stu-id="aa7c0-181">Set-AzureRmDataLakeAnalyticsAccount</span></span>

<span data-ttu-id="aa7c0-182">**DataLakeStore**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-182">**DataLakeStore**</span></span>
- <span data-ttu-id="aa7c0-183">New-AzureRmDataLakeStoreAccount</span><span class="sxs-lookup"><span data-stu-id="aa7c0-183">New-AzureRmDataLakeStoreAccount</span></span>
- <span data-ttu-id="aa7c0-184">Set-AzureRmDataLakeStoreAccount</span><span class="sxs-lookup"><span data-stu-id="aa7c0-184">Set-AzureRmDataLakeStoreAccount</span></span>

<span data-ttu-id="aa7c0-185">**Dns**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-185">**Dns**</span></span>
- <span data-ttu-id="aa7c0-186">New-AzureRmDnsZone</span><span class="sxs-lookup"><span data-stu-id="aa7c0-186">New-AzureRmDnsZone</span></span>
- <span data-ttu-id="aa7c0-187">Set-AzureRmDnsZone</span><span class="sxs-lookup"><span data-stu-id="aa7c0-187">Set-AzureRmDnsZone</span></span>

<span data-ttu-id="aa7c0-188">**KeyVault**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-188">**KeyVault**</span></span>
- <span data-ttu-id="aa7c0-189">Get-AzureRmKeyVault</span><span class="sxs-lookup"><span data-stu-id="aa7c0-189">Get-AzureRmKeyVault</span></span>
- <span data-ttu-id="aa7c0-190">New-AzureRmKeyVault</span><span class="sxs-lookup"><span data-stu-id="aa7c0-190">New-AzureRmKeyVault</span></span>

<span data-ttu-id="aa7c0-191">**Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-191">**Network**</span></span>
- <span data-ttu-id="aa7c0-192">New-AzureRmApplicationGateway</span><span class="sxs-lookup"><span data-stu-id="aa7c0-192">New-AzureRmApplicationGateway</span></span>
- <span data-ttu-id="aa7c0-193">New-AzureRmExpressRouteCircuit</span><span class="sxs-lookup"><span data-stu-id="aa7c0-193">New-AzureRmExpressRouteCircuit</span></span>
- <span data-ttu-id="aa7c0-194">New-AzureRmLoadBalancer</span><span class="sxs-lookup"><span data-stu-id="aa7c0-194">New-AzureRmLoadBalancer</span></span>
- <span data-ttu-id="aa7c0-195">New-AzureRmLocalNetworkGateway</span><span class="sxs-lookup"><span data-stu-id="aa7c0-195">New-AzureRmLocalNetworkGateway</span></span>
- <span data-ttu-id="aa7c0-196">New-AzureRmNetworkInterface</span><span class="sxs-lookup"><span data-stu-id="aa7c0-196">New-AzureRmNetworkInterface</span></span>
- <span data-ttu-id="aa7c0-197">New-AzureRmNetworkSecurityGroup</span><span class="sxs-lookup"><span data-stu-id="aa7c0-197">New-AzureRmNetworkSecurityGroup</span></span>
- <span data-ttu-id="aa7c0-198">New-AzureRmPublicIpAddress</span><span class="sxs-lookup"><span data-stu-id="aa7c0-198">New-AzureRmPublicIpAddress</span></span>
- <span data-ttu-id="aa7c0-199">New-AzureRmRouteTable</span><span class="sxs-lookup"><span data-stu-id="aa7c0-199">New-AzureRmRouteTable</span></span>
- <span data-ttu-id="aa7c0-200">New-AzureRmVirtualNetwork</span><span class="sxs-lookup"><span data-stu-id="aa7c0-200">New-AzureRmVirtualNetwork</span></span>
- <span data-ttu-id="aa7c0-201">New-AzureRmVirtualNetworkGateway</span><span class="sxs-lookup"><span data-stu-id="aa7c0-201">New-AzureRmVirtualNetworkGateway</span></span>
- <span data-ttu-id="aa7c0-202">New-AzureRmVirtualNetworkGatewayConnection</span><span class="sxs-lookup"><span data-stu-id="aa7c0-202">New-AzureRmVirtualNetworkGatewayConnection</span></span>
- <span data-ttu-id="aa7c0-203">New-AzureRmVirtualNetworkPeering</span><span class="sxs-lookup"><span data-stu-id="aa7c0-203">New-AzureRmVirtualNetworkPeering</span></span>

<span data-ttu-id="aa7c0-204">**Ressourcen**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-204">**Resources**</span></span>
- <span data-ttu-id="aa7c0-205">Find-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="aa7c0-205">Find-AzureRmResource</span></span>
- <span data-ttu-id="aa7c0-206">Find-AzureRmResourceGroup</span><span class="sxs-lookup"><span data-stu-id="aa7c0-206">Find-AzureRmResourceGroup</span></span>
- <span data-ttu-id="aa7c0-207">New-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="aa7c0-207">New-AzureRmResource</span></span>
- <span data-ttu-id="aa7c0-208">New-AzureRmResourceGroup</span><span class="sxs-lookup"><span data-stu-id="aa7c0-208">New-AzureRmResourceGroup</span></span>
- <span data-ttu-id="aa7c0-209">Set-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="aa7c0-209">Set-AzureRmResource</span></span>
- <span data-ttu-id="aa7c0-210">Set-AzureRmResourceGroup</span><span class="sxs-lookup"><span data-stu-id="aa7c0-210">Set-AzureRmResourceGroup</span></span>

<span data-ttu-id="aa7c0-211">**SQL**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-211">**SQL**</span></span>
- <span data-ttu-id="aa7c0-212">New-AzureRmSqlDatabase</span><span class="sxs-lookup"><span data-stu-id="aa7c0-212">New-AzureRmSqlDatabase</span></span>
- <span data-ttu-id="aa7c0-213">New-AzureRmSqlDatabaseCopy</span><span class="sxs-lookup"><span data-stu-id="aa7c0-213">New-AzureRmSqlDatabaseCopy</span></span>
- <span data-ttu-id="aa7c0-214">New-AzureRmSqlDatabaseSecondary</span><span class="sxs-lookup"><span data-stu-id="aa7c0-214">New-AzureRmSqlDatabaseSecondary</span></span>
- <span data-ttu-id="aa7c0-215">New-AzureRmSqlElasticPool</span><span class="sxs-lookup"><span data-stu-id="aa7c0-215">New-AzureRmSqlElasticPool</span></span>
- <span data-ttu-id="aa7c0-216">New-AzureRmSqlServer</span><span class="sxs-lookup"><span data-stu-id="aa7c0-216">New-AzureRmSqlServer</span></span>
- <span data-ttu-id="aa7c0-217">Set-AzureRmSqlDatabase</span><span class="sxs-lookup"><span data-stu-id="aa7c0-217">Set-AzureRmSqlDatabase</span></span>
- <span data-ttu-id="aa7c0-218">Set-AzureRmSqlElasticPool</span><span class="sxs-lookup"><span data-stu-id="aa7c0-218">Set-AzureRmSqlElasticPool</span></span>
- <span data-ttu-id="aa7c0-219">Set-AzureRmSqlServer</span><span class="sxs-lookup"><span data-stu-id="aa7c0-219">Set-AzureRmSqlServer</span></span>

<span data-ttu-id="aa7c0-220">**Storage**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-220">**Storage**</span></span>
- <span data-ttu-id="aa7c0-221">New-AzureRmStorageAccount</span><span class="sxs-lookup"><span data-stu-id="aa7c0-221">New-AzureRmStorageAccount</span></span>
- <span data-ttu-id="aa7c0-222">Set-AzureRmStorageAccount</span><span class="sxs-lookup"><span data-stu-id="aa7c0-222">Set-AzureRmStorageAccount</span></span>

<span data-ttu-id="aa7c0-223">**TrafficManager**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-223">**TrafficManager**</span></span>
- <span data-ttu-id="aa7c0-224">New-AzureRmTrafficManagerProfile</span><span class="sxs-lookup"><span data-stu-id="aa7c0-224">New-AzureRmTrafficManagerProfile</span></span>

<br>

<span data-ttu-id="aa7c0-225">Wenn Sie über ein Skript verfügen, das eines der oben angegebenen Cmdlets verwendet, können Sie zur Behandlung der grundlegenden Änderungen den `Tags`-Parameter in `Tag` umbenennen und `Tag` im neuen Format angeben.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-225">If you have a script that uses any of the above cmdlets, the breaking change can be fixed by changing the `Tags` parameter to `Tag`, as well as changing the `Tag` to the new format.</span></span>

```powershell
# Old
New-AzureRmResourceGroup -Name $resourceGroupName -Location -location -Tags @{ Name = "testtag"; Value = "testval" }

# New
New-AzureRmResourceGroup -Name $resourceGroupName -Location -location -Tag @{ testtag = "testval" }
```

<br>

## <a name="breaking-changes-to-storage-cmdlets"></a><span data-ttu-id="aa7c0-226">Grundlegende Änderungen für Storage-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="aa7c0-226">Breaking changes to Storage cmdlets</span></span>

<span data-ttu-id="aa7c0-227">Diese Version hat Auswirkungen auf folgende Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="aa7c0-227">The following cmdlets were affected this release:</span></span>

<span data-ttu-id="aa7c0-228">**Get-AzureRmStorageAccountKey**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-228">**Get-AzureRmStorageAccountKey**</span></span>
- <span data-ttu-id="aa7c0-229">Anstelle eines Objekts mit Eigenschaften für die einzelnen Schlüssel gibt das Cmdlet jetzt eine Liste mit Schlüsseln zurück.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-229">The cmdlet now returns a list of keys, rather than an object with properties for each key</span></span>

```powershell
# Old
$key = (Get-AzureRmStorageAccountKey -ResourceGroupName $resourceGroupName -Name $accountName).Key1

# New
$key = (Get-AzureRmStorageAccountKey -ResourceGroupName $resourceGroupName -Name $accountName)[0].Value
```

<span data-ttu-id="aa7c0-230">**New-AzureRmStorageAccountKey**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-230">**New-AzureRmStorageAccountKey**</span></span>
- <span data-ttu-id="aa7c0-231">Das Feld `StorageAccountRegenerateKeyResponse` in der Ausgabe dieses Cmdlets wird in `StorageAccountListKeysResults` umbenannt und ist nun kein Objekt mit Eigenschaften für die einzelnen Schlüssel mehr, sondern eine Liste mit Schlüsseln.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-231">`StorageAccountRegenerateKeyResponse` field in output of this cmdlet is renamed to `StorageAccountListKeysResults`, which is now a list of keys rather than an object with properties for each key</span></span>

```powershell
# Old
$key = (New-AzureRmStorageAccountKey -ResourceGroupName $resourceGroupName -Name $accountName).StorageAccountKeys.Key1

# New
$key = (New-AzureRmStorageAccountKey -ResourceGroupName $resourceGroupName -Name $accountName).Keys[0].Value
```

<span data-ttu-id="aa7c0-232">**New/Get/Set-AzureRmStorageAccount**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-232">**New/Get/Set-AzureRmStorageAccount**</span></span>
- <span data-ttu-id="aa7c0-233">Das Feld `AccountType` in der Ausgabe des Cmdlets wird in `Sku.Name` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-233">`AccountType` field in output of this cmdlet is renamed to `Sku.Name`</span></span>
- <span data-ttu-id="aa7c0-234">Der Ausgabetyp für primäre/sekundäre Endpunkte (Blob/Tabelle/Warteschlange/Datei) wird von `Uri` in `String` geändert.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-234">Output type for PrimaryEndpoints/Secondary endpoints blob/table/queue/file changed from `Uri` to `String`</span></span>

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

## <a name="breaking-changes-to-ad-cmdlets"></a><span data-ttu-id="aa7c0-235">Grundlegende Änderungen für AD-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="aa7c0-235">Breaking changes to AD cmdlets</span></span>

<span data-ttu-id="aa7c0-236">Diese Version hat Auswirkungen auf folgende Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="aa7c0-236">The following cmdlets were affected this release:</span></span>

<span data-ttu-id="aa7c0-237">**Get-AzureRMADServicePrincipal**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-237">**Get-AzureRMADServicePrincipal**</span></span>
- <span data-ttu-id="aa7c0-238">Das Feld `ServicePrincipalName` in der Ausgabe des Cmdlets wird in `ServicePrincipalNames` umbenannt und ist nun eine Sammlung.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-238">`ServicePrincipalName` field in output of this cmdlet is renamed to `ServicePrincipalNames` and is now a collection.</span></span> <span data-ttu-id="aa7c0-239">Es zeigt nun `ApplicationId` auch als einen der Dienstprinzipalnamen an (zusammen mit dem Bezeichner-URI).</span><span class="sxs-lookup"><span data-stu-id="aa7c0-239">It now displays `ApplicationId` also as one of the SPN, along with the identifierUri.</span></span>

```powershell
# Old
$servicePrincipals = Get-AzureRmADServicePrincipal -SearchString $displayName
$spn = $servicePrincipals[0].ServicePrincipalName

# New
$servicePrincipals = Get-AzureRmADServicePrincipal -SearchString $displayName
$spn = $servicePrincipals[0].ServicePrincipalNames[0]
```

<span data-ttu-id="aa7c0-240">**Get-AzureRmADApplication**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-240">**Get-AzureRmADApplication**</span></span>
- <span data-ttu-id="aa7c0-241">Der Parameter `ApplicationObjectId` wird in `ObjectId` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-241">Parameter `ApplicationObjectId` is renamed to `ObjectId`.</span></span>
- <span data-ttu-id="aa7c0-242">In der Ausgabe des Cmdlets wird `ApplicationObjectId` in `ObjectId` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-242">In output of this cmdlet, `ApplicationObjectId` is renamed to `ObjectId`.</span></span>

```powershell
# Old
$app = Get-AzureRmADApplication -ApplicationObjectId $applicationObjectId
$objectId = $app.ApplicationObjectId

# New
$app = Get-AzureRmADApplication -ObjectId $objectId
$objectId = $app.ObjectId
```

<span data-ttu-id="aa7c0-243">**Remove-AzureRmADApplication**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-243">**Remove-AzureRmADApplication**</span></span>
- <span data-ttu-id="aa7c0-244">Der Parameter `ApplicationObjectId` wird in `ObjectId` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-244">Parameter `ApplicationObjectId` is renamed to `ObjectId`.</span></span>

```powershell
# Old
$app = Remove-AzureRmADApplication -ApplicationObjectId $applicationObjectId -Force

# New
$app = Remove-AzureRmADApplication -ObjectId $objectId -Force
```

<span data-ttu-id="aa7c0-245">**New-AzureRmADApplication**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-245">**New-AzureRmADApplication**</span></span>
- <span data-ttu-id="aa7c0-246">In der Ausgabe des Cmdlets wird `ApplicationObjectId` in `ObjectId` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-246">In output of this cmdlet, `ApplicationObjectId` is renamed to `ObjectId`.</span></span>
- <span data-ttu-id="aa7c0-247">Die Parameter `KeyValue`, `KeyUsage` und `KeyType` werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-247">`KeyValue`, `KeyUsage`, `KeyType` parameters are removed.</span></span>

```powershell
# Old
$app = New-AzureRmADApplication -DisplayName $displayName -HomePage $homePage -IdentifierUris $identifierUris -KeyValue $kv -KeyType $kt -KeyUsage $ku
$id = $app.ApplicationObjectId

# New
$app = New-AzureRmADApplication -DisplayName $displayName -HomePage $homePage -IdentifierUris $identifierUris
$id = $app.ObjectId
New-AzureRmADAppCredential -ObjectId $id -Password $kv
```

<span data-ttu-id="aa7c0-248">**Get-AzureRmADGroup**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-248">**Get-AzureRmADGroup**</span></span>
- <span data-ttu-id="aa7c0-249">Das Feld `Mail` wird aus der Ausgabe entfernt.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-249">`Mail` field is removed from the output.</span></span>

<span data-ttu-id="aa7c0-250">**Get-AzureRmADUser**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-250">**Get-AzureRmADUser**</span></span>
- <span data-ttu-id="aa7c0-251">Das Feld `Mail` wird aus der Ausgabe entfernt.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-251">`Mail` field is removed from the output.</span></span>

<span data-ttu-id="aa7c0-252">**New-AzureRmADServicePrincipal**</span><span class="sxs-lookup"><span data-stu-id="aa7c0-252">**New-AzureRmADServicePrincipal**</span></span>
- <span data-ttu-id="aa7c0-253">Der Parameter `DisableAccount` wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="aa7c0-253">Removed `DisableAccount` parameter.</span></span>

```powershell
# Old
$servicePrincipal = New-AzureRmADServicePrincipal -DisplayName $displayName -Password $password -DisableAccount true

# New
$servicePrincipal = New-AzureRmADServicePrincipal -DisplayName $displayName -Password $password
Remove-AzureRmADServicePrincipal -ObjectId $servicePrincipal.ObjectId
```