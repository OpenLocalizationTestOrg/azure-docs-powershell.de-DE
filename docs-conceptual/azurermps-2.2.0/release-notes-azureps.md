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
ms.openlocfilehash: 143d92384fd270711378f6741ba59e88c12833d1
ms.sourcegitcommit: b256bf48e15ee98865de0fae50e7b81878b03a54
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2017
---
# <a name="release-notes"></a><span data-ttu-id="6ecf4-103">Versionshinweise</span><span class="sxs-lookup"><span data-stu-id="6ecf4-103">Release notes</span></span>

<span data-ttu-id="6ecf4-104">Hierbei handelt es sich um eine Liste der Änderungen, die in dieser Version an Azure PowerShell vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="6ecf4-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <a name="version-220"></a><span data-ttu-id="6ecf4-105">Version 2.2.0</span><span class="sxs-lookup"><span data-stu-id="6ecf4-105">Version 2.2.0</span></span>
* <span data-ttu-id="6ecf4-106">Compute</span><span class="sxs-lookup"><span data-stu-id="6ecf4-106">Compute</span></span>
  - <span data-ttu-id="6ecf4-107">Unterstützung zum Abfragen des Verschlüsselungsstatus aus der AzureDiskEncryptionForLinux-Erweiterung wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6ecf4-107">Add support for querying encryption status from the AzureDiskEncryptionForLinux extension</span></span>
* <span data-ttu-id="6ecf4-108">DataFactory</span><span class="sxs-lookup"><span data-stu-id="6ecf4-108">DataFactory</span></span>
  - <span data-ttu-id="6ecf4-109">Ein neues Cmdlet zum Auflisten der Aktivitätsfenster wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6ecf4-109">Added new cmdlet for listing activity windows</span></span>
    + <span data-ttu-id="6ecf4-110">Get-AzureRmDataFactoryActivityWindow</span><span class="sxs-lookup"><span data-stu-id="6ecf4-110">Get-AzureRmDataFactoryActivityWindow</span></span>
* <span data-ttu-id="6ecf4-111">DataLake</span><span class="sxs-lookup"><span data-stu-id="6ecf4-111">DataLake</span></span>
  - <span data-ttu-id="6ecf4-112">Der Parameter `Host` wurde in `DatabaseHost` geändert. Außerdem wurde `Host` ein Alias hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6ecf4-112">Changed parameter `Host` to `DatabaseHost` and added alias to `Host`</span></span>
    + <span data-ttu-id="6ecf4-113">New-AzureRmDataLakeAnalyticsCatalogSecret</span><span class="sxs-lookup"><span data-stu-id="6ecf4-113">New-AzureRmDataLakeAnalyticsCatalogSecret</span></span>
    + <span data-ttu-id="6ecf4-114">Set-AzureRmDataLakeAnalyticsCatalogSecret</span><span class="sxs-lookup"><span data-stu-id="6ecf4-114">Set-AzureRmDataLakeAnalyticsCatalogSecret</span></span>
  - <span data-ttu-id="6ecf4-115">Hinzufügen von Unterstützung für die Entfernung der ACL und Standard-ACL</span><span class="sxs-lookup"><span data-stu-id="6ecf4-115">Add support for ACL and Default ACL removal</span></span>
  - <span data-ttu-id="6ecf4-116">Unterstützung für das Abrufen und Festlegen unbenannter Berechtigungen für Dateien und Ordner wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6ecf4-116">Add support for getting and setting unnamed permissions on files and folders</span></span>
* <span data-ttu-id="6ecf4-117">KeyVault</span><span class="sxs-lookup"><span data-stu-id="6ecf4-117">KeyVault</span></span>
  - <span data-ttu-id="6ecf4-118">Unterstützung für Zertifikate wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6ecf4-118">Add support for certificates</span></span>
    + <span data-ttu-id="6ecf4-119">Add-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="6ecf4-119">Add-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="6ecf4-120">Add-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="6ecf4-120">Add-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="6ecf4-121">Get-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="6ecf4-121">Get-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="6ecf4-122">Get-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="6ecf4-122">Get-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="6ecf4-123">Get-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="6ecf4-123">Get-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="6ecf4-124">Get-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="6ecf4-124">Get-AzureKeyVaultCertificateOperation</span></span>
    + <span data-ttu-id="6ecf4-125">Get-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="6ecf4-125">Get-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="6ecf4-126">Import-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="6ecf4-126">Import-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="6ecf4-127">New-AzureKeyVaultCertificateAdministratorDetails</span><span class="sxs-lookup"><span data-stu-id="6ecf4-127">New-AzureKeyVaultCertificateAdministratorDetails</span></span>
    + <span data-ttu-id="6ecf4-128">New-AzureKeyVaultCertificateOrganizationDetails</span><span class="sxs-lookup"><span data-stu-id="6ecf4-128">New-AzureKeyVaultCertificateOrganizationDetails</span></span>
    + <span data-ttu-id="6ecf4-129">New-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="6ecf4-129">New-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="6ecf4-130">Remove-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="6ecf4-130">Remove-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="6ecf4-131">Remove-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="6ecf4-131">Remove-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="6ecf4-132">Remove-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="6ecf4-132">Remove-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="6ecf4-133">Remove-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="6ecf4-133">Remove-AzureKeyVaultCertificateOperation</span></span>
    + <span data-ttu-id="6ecf4-134">Set-AzureKeyVaultCertificateAttribute</span><span class="sxs-lookup"><span data-stu-id="6ecf4-134">Set-AzureKeyVaultCertificateAttribute</span></span>
    + <span data-ttu-id="6ecf4-135">Set-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="6ecf4-135">Set-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="6ecf4-136">Set-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="6ecf4-136">Set-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="6ecf4-137">Stop-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="6ecf4-137">Stop-AzureKeyVaultCertificateOperation</span></span>
* <span data-ttu-id="6ecf4-138">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="6ecf4-138">Network</span></span>

  - <span data-ttu-id="6ecf4-139">Ein neuer Switch-Parameter wurde für die Netzwerkschnittstelle hinzugefügt, um beschleunigte Netzwerke zu aktivieren/deaktivieren. +New-AzureRmNetworkInterface -EnableAcceleratedNetworking</span><span class="sxs-lookup"><span data-stu-id="6ecf4-139">New switch parameter added for network interface to enable/disable accelerated networking +New-AzureRmNetworkInterface -EnableAcceleratedNetworking</span></span>
  - <span data-ttu-id="6ecf4-140">Die Funktion für Aktiv/Aktiv-Gateways für PowerShell-Cmdlets wurde aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6ecf4-140">Enable Active-Active gateway feature PowerShell cmdlets</span></span>
    + <span data-ttu-id="6ecf4-141">Add-AzureRmVirtualNetworkGatewayIpConfig</span><span class="sxs-lookup"><span data-stu-id="6ecf4-141">Add-AzureRmVirtualNetworkGatewayIpConfig</span></span>
    + <span data-ttu-id="6ecf4-142">Remove-AzureRmVirtualNetworkGatewayIpConfig</span><span class="sxs-lookup"><span data-stu-id="6ecf4-142">Remove-AzureRmVirtualNetworkGatewayIpConfig</span></span>
  - <span data-ttu-id="6ecf4-143">Ein neues Cmdlet wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6ecf4-143">Added new cmdlet</span></span>
    + <span data-ttu-id="6ecf4-144">Test-AzureRmPrivateIpAddressAvailability</span><span class="sxs-lookup"><span data-stu-id="6ecf4-144">Test-AzureRmPrivateIpAddressAvailability</span></span>
* <span data-ttu-id="6ecf4-145">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="6ecf4-145">Resources</span></span>
  - <span data-ttu-id="6ecf4-146">Zonen in Anbieter- und Ressourcen-Cmdlets werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6ecf4-146">Support zones in provider and resource cmdlets</span></span>
    + <span data-ttu-id="6ecf4-147">Get-AzureRmProvider</span><span class="sxs-lookup"><span data-stu-id="6ecf4-147">Get-AzureRmProvider</span></span>
    + <span data-ttu-id="6ecf4-148">New-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="6ecf4-148">New-AzureRmResource</span></span>
    + <span data-ttu-id="6ecf4-149">Set-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="6ecf4-149">Set-AzureRmResource</span></span>
* <span data-ttu-id="6ecf4-150">Sql</span><span class="sxs-lookup"><span data-stu-id="6ecf4-150">Sql</span></span>
  - <span data-ttu-id="6ecf4-151">Neue Cmdlets für die Richtlinienverwaltung der Azure SQL-Bedrohungserkennung auf Serverebene wurden hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6ecf4-151">Added new cmdlets for Azure SQL threat detection policy management at server level</span></span>
    + <span data-ttu-id="6ecf4-152">Get-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="6ecf4-152">Get-AzureRmSqlServerThreatDetectionPolicy</span></span>
    + <span data-ttu-id="6ecf4-153">Remove-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="6ecf4-153">Remove-AzureRmSqlServerThreatDetectionPolicy</span></span>
    + <span data-ttu-id="6ecf4-154">Set-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="6ecf4-154">Set-AzureRmSqlServerThreatDetectionPolicy</span></span>
  - <span data-ttu-id="6ecf4-155">Neue Cmdlets wurden hinzugefügt, um die Aktivierung/Deaktivierung von „GeoBackupPolicy“ für SQL Azure Data Warehouses zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6ecf4-155">Added new cmdlets to support enabling/disabling GeoBackupPolicy for Sql Azure DataWarehouses</span></span>
    + <span data-ttu-id="6ecf4-156">Get-AzureRmSqlDatabaseGeoBackupPolicy</span><span class="sxs-lookup"><span data-stu-id="6ecf4-156">Get-AzureRmSqlDatabaseGeoBackupPolicy</span></span>
    + <span data-ttu-id="6ecf4-157">Set-AzureRmSqlDatabaseGeoBackupPolicy</span><span class="sxs-lookup"><span data-stu-id="6ecf4-157">Set-AzureRmSqlDatabaseGeoBackupPolicy</span></span>
  - <span data-ttu-id="6ecf4-158">Neue Cmdlets für Azure SQL-Ratgeber und empfohlene Aktions-APIs wurden hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6ecf4-158">Added new cmdlets for Azure Sql Advisors and Recommended Actions APIs</span></span>
    + <span data-ttu-id="6ecf4-159">Get-AzureRmSqlDatabaseAdvisor</span><span class="sxs-lookup"><span data-stu-id="6ecf4-159">Get-AzureRmSqlDatabaseAdvisor</span></span>
    + <span data-ttu-id="6ecf4-160">Get-AzureRmSqlElasticPoolAdvisor</span><span class="sxs-lookup"><span data-stu-id="6ecf4-160">Get-AzureRmSqlElasticPoolAdvisor</span></span>
    + <span data-ttu-id="6ecf4-161">Get-AzureRmSqlServerAdvisor</span><span class="sxs-lookup"><span data-stu-id="6ecf4-161">Get-AzureRmSqlServerAdvisor</span></span>
    + <span data-ttu-id="6ecf4-162">Get-AzureRmSqlDatabaseRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="6ecf4-162">Get-AzureRmSqlDatabaseRecommendedActions</span></span>
    + <span data-ttu-id="6ecf4-163">Get-AzureRmSqlElasticPoolRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="6ecf4-163">Get-AzureRmSqlElasticPoolRecommendedActions</span></span>
    + <span data-ttu-id="6ecf4-164">Get-AzureRmSqlServerRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="6ecf4-164">Get-AzureRmSqlServerRecommendedActions</span></span>
    + <span data-ttu-id="6ecf4-165">Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="6ecf4-165">Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="6ecf4-166">Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="6ecf4-166">Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="6ecf4-167">Set-AzureRmSqlServerAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="6ecf4-167">Set-AzureRmSqlServerAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="6ecf4-168">Set-AzureRmSqlDatabaseRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="6ecf4-168">Set-AzureRmSqlDatabaseRecommendedActionState</span></span>
    + <span data-ttu-id="6ecf4-169">Set-AzureRmSqlElasticPoolRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="6ecf4-169">Set-AzureRmSqlElasticPoolRecommendedActionState</span></span>
    + <span data-ttu-id="6ecf4-170">Set-AzureRmSqlServerRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="6ecf4-170">Set-AzureRmSqlServerRecommendedActionState</span></span>
