---
title: Dziennik zmian w programie Azure PowerShell | Microsoft Docs
description: Jest to historia zmian wprowadzonych w programie Azure PowerShell w jego najnowszej wersji.
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
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2017
---
# <a name="release-notes"></a><span data-ttu-id="bdf35-103">Informacje o wersji</span><span class="sxs-lookup"><span data-stu-id="bdf35-103">Release notes</span></span>

<span data-ttu-id="bdf35-104">To jest lista zmian wprowadzonych w programie Azure PowerShell w tym wydaniu.</span><span class="sxs-lookup"><span data-stu-id="bdf35-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <a name="version-220"></a><span data-ttu-id="bdf35-105">Wersja 2.2.0</span><span class="sxs-lookup"><span data-stu-id="bdf35-105">Version 2.2.0</span></span>
* <span data-ttu-id="bdf35-106">Compute</span><span class="sxs-lookup"><span data-stu-id="bdf35-106">Compute</span></span>
  - <span data-ttu-id="bdf35-107">Dodano obsługę pytania o stan szyfrowania z rozszerzenia AzureDiskEncryptionForLinux</span><span class="sxs-lookup"><span data-stu-id="bdf35-107">Add support for querying encryption status from the AzureDiskEncryptionForLinux extension</span></span>
* <span data-ttu-id="bdf35-108">DataFactory</span><span class="sxs-lookup"><span data-stu-id="bdf35-108">DataFactory</span></span>
  - <span data-ttu-id="bdf35-109">Dodano nowe polecenie cmdlet do wyświetlania listy okien działania</span><span class="sxs-lookup"><span data-stu-id="bdf35-109">Added new cmdlet for listing activity windows</span></span>
    + <span data-ttu-id="bdf35-110">Get-AzureRmDataFactoryActivityWindow</span><span class="sxs-lookup"><span data-stu-id="bdf35-110">Get-AzureRmDataFactoryActivityWindow</span></span>
* <span data-ttu-id="bdf35-111">DataLake</span><span class="sxs-lookup"><span data-stu-id="bdf35-111">DataLake</span></span>
  - <span data-ttu-id="bdf35-112">Zmieniono parametr `Host` na `DatabaseHost` i dodano alias do `Host`</span><span class="sxs-lookup"><span data-stu-id="bdf35-112">Changed parameter `Host` to `DatabaseHost` and added alias to `Host`</span></span>
    + <span data-ttu-id="bdf35-113">New-AzureRmDataLakeAnalyticsCatalogSecret</span><span class="sxs-lookup"><span data-stu-id="bdf35-113">New-AzureRmDataLakeAnalyticsCatalogSecret</span></span>
    + <span data-ttu-id="bdf35-114">Set-AzureRmDataLakeAnalyticsCatalogSecret</span><span class="sxs-lookup"><span data-stu-id="bdf35-114">Set-AzureRmDataLakeAnalyticsCatalogSecret</span></span>
  - <span data-ttu-id="bdf35-115">Dodano obsługę usuwania listy ACL i domyślnej listy ACL</span><span class="sxs-lookup"><span data-stu-id="bdf35-115">Add support for ACL and Default ACL removal</span></span>
  - <span data-ttu-id="bdf35-116">Dodano obsługę pobierania i ustawiania nienazwanych uprawnień do plików i folderów</span><span class="sxs-lookup"><span data-stu-id="bdf35-116">Add support for getting and setting unnamed permissions on files and folders</span></span>
* <span data-ttu-id="bdf35-117">KeyVault</span><span class="sxs-lookup"><span data-stu-id="bdf35-117">KeyVault</span></span>
  - <span data-ttu-id="bdf35-118">Dodano obsługę certyfikatów</span><span class="sxs-lookup"><span data-stu-id="bdf35-118">Add support for certificates</span></span>
    + <span data-ttu-id="bdf35-119">Add-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="bdf35-119">Add-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="bdf35-120">Add-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="bdf35-120">Add-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="bdf35-121">Get-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="bdf35-121">Get-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="bdf35-122">Get-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="bdf35-122">Get-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="bdf35-123">Get-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="bdf35-123">Get-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="bdf35-124">Get-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="bdf35-124">Get-AzureKeyVaultCertificateOperation</span></span>
    + <span data-ttu-id="bdf35-125">Get-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="bdf35-125">Get-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="bdf35-126">Import-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="bdf35-126">Import-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="bdf35-127">New-AzureKeyVaultCertificateAdministratorDetails</span><span class="sxs-lookup"><span data-stu-id="bdf35-127">New-AzureKeyVaultCertificateAdministratorDetails</span></span>
    + <span data-ttu-id="bdf35-128">New-AzureKeyVaultCertificateOrganizationDetails</span><span class="sxs-lookup"><span data-stu-id="bdf35-128">New-AzureKeyVaultCertificateOrganizationDetails</span></span>
    + <span data-ttu-id="bdf35-129">New-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="bdf35-129">New-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="bdf35-130">Remove-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="bdf35-130">Remove-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="bdf35-131">Remove-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="bdf35-131">Remove-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="bdf35-132">Remove-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="bdf35-132">Remove-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="bdf35-133">Remove-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="bdf35-133">Remove-AzureKeyVaultCertificateOperation</span></span>
    + <span data-ttu-id="bdf35-134">Set-AzureKeyVaultCertificateAttribute</span><span class="sxs-lookup"><span data-stu-id="bdf35-134">Set-AzureKeyVaultCertificateAttribute</span></span>
    + <span data-ttu-id="bdf35-135">Set-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="bdf35-135">Set-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="bdf35-136">Set-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="bdf35-136">Set-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="bdf35-137">Stop-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="bdf35-137">Stop-AzureKeyVaultCertificateOperation</span></span>
* <span data-ttu-id="bdf35-138">Sieć</span><span class="sxs-lookup"><span data-stu-id="bdf35-138">Network</span></span>

  - <span data-ttu-id="bdf35-139">Dodano nowy parametr przełącznika interfejsu sieciowego, aby włączyć/wyłączyć wydajniejsze sieci +New-AzureRmNetworkInterface -EnableAcceleratedNetworking</span><span class="sxs-lookup"><span data-stu-id="bdf35-139">New switch parameter added for network interface to enable/disable accelerated networking +New-AzureRmNetworkInterface -EnableAcceleratedNetworking</span></span>
  - <span data-ttu-id="bdf35-140">Włączono polecenia cmdlet programu PowerShell funkcji bramy Active-Active</span><span class="sxs-lookup"><span data-stu-id="bdf35-140">Enable Active-Active gateway feature PowerShell cmdlets</span></span>
    + <span data-ttu-id="bdf35-141">Add-AzureRmVirtualNetworkGatewayIpConfig</span><span class="sxs-lookup"><span data-stu-id="bdf35-141">Add-AzureRmVirtualNetworkGatewayIpConfig</span></span>
    + <span data-ttu-id="bdf35-142">Remove-AzureRmVirtualNetworkGatewayIpConfig</span><span class="sxs-lookup"><span data-stu-id="bdf35-142">Remove-AzureRmVirtualNetworkGatewayIpConfig</span></span>
  - <span data-ttu-id="bdf35-143">Dodano nowe polecenie cmdlet</span><span class="sxs-lookup"><span data-stu-id="bdf35-143">Added new cmdlet</span></span>
    + <span data-ttu-id="bdf35-144">Test-AzureRmPrivateIpAddressAvailability</span><span class="sxs-lookup"><span data-stu-id="bdf35-144">Test-AzureRmPrivateIpAddressAvailability</span></span>
* <span data-ttu-id="bdf35-145">Zasoby</span><span class="sxs-lookup"><span data-stu-id="bdf35-145">Resources</span></span>
  - <span data-ttu-id="bdf35-146">Obsługa stref w poleceniach cmdlet dostawcy i zasobów</span><span class="sxs-lookup"><span data-stu-id="bdf35-146">Support zones in provider and resource cmdlets</span></span>
    + <span data-ttu-id="bdf35-147">Get-AzureRmProvider</span><span class="sxs-lookup"><span data-stu-id="bdf35-147">Get-AzureRmProvider</span></span>
    + <span data-ttu-id="bdf35-148">New-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="bdf35-148">New-AzureRmResource</span></span>
    + <span data-ttu-id="bdf35-149">Set-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="bdf35-149">Set-AzureRmResource</span></span>
* <span data-ttu-id="bdf35-150">Sql</span><span class="sxs-lookup"><span data-stu-id="bdf35-150">Sql</span></span>
  - <span data-ttu-id="bdf35-151">Dodano nowe polecenia cmdlet do zarządzania zasadami wykrywania zagrożeń usług Azure SQL na poziomie serwera</span><span class="sxs-lookup"><span data-stu-id="bdf35-151">Added new cmdlets for Azure SQL threat detection policy management at server level</span></span>
    + <span data-ttu-id="bdf35-152">Get-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="bdf35-152">Get-AzureRmSqlServerThreatDetectionPolicy</span></span>
    + <span data-ttu-id="bdf35-153">Remove-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="bdf35-153">Remove-AzureRmSqlServerThreatDetectionPolicy</span></span>
    + <span data-ttu-id="bdf35-154">Set-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="bdf35-154">Set-AzureRmSqlServerThreatDetectionPolicy</span></span>
  - <span data-ttu-id="bdf35-155">Dodano nowe polecenia cmdlet do obsługi włączania/wyłączania zasad GeoBackupPolicy dla usług Azure SQL DataWarehouse</span><span class="sxs-lookup"><span data-stu-id="bdf35-155">Added new cmdlets to support enabling/disabling GeoBackupPolicy for Sql Azure DataWarehouses</span></span>
    + <span data-ttu-id="bdf35-156">Get-AzureRmSqlDatabaseGeoBackupPolicy</span><span class="sxs-lookup"><span data-stu-id="bdf35-156">Get-AzureRmSqlDatabaseGeoBackupPolicy</span></span>
    + <span data-ttu-id="bdf35-157">Set-AzureRmSqlDatabaseGeoBackupPolicy</span><span class="sxs-lookup"><span data-stu-id="bdf35-157">Set-AzureRmSqlDatabaseGeoBackupPolicy</span></span>
  - <span data-ttu-id="bdf35-158">Dodano nowe polecenia cmdlet dla interfejsów API usług Azure SQL Advisor i zalecanych akcji</span><span class="sxs-lookup"><span data-stu-id="bdf35-158">Added new cmdlets for Azure Sql Advisors and Recommended Actions APIs</span></span>
    + <span data-ttu-id="bdf35-159">Get-AzureRmSqlDatabaseAdvisor</span><span class="sxs-lookup"><span data-stu-id="bdf35-159">Get-AzureRmSqlDatabaseAdvisor</span></span>
    + <span data-ttu-id="bdf35-160">Get-AzureRmSqlElasticPoolAdvisor</span><span class="sxs-lookup"><span data-stu-id="bdf35-160">Get-AzureRmSqlElasticPoolAdvisor</span></span>
    + <span data-ttu-id="bdf35-161">Get-AzureRmSqlServerAdvisor</span><span class="sxs-lookup"><span data-stu-id="bdf35-161">Get-AzureRmSqlServerAdvisor</span></span>
    + <span data-ttu-id="bdf35-162">Get-AzureRmSqlDatabaseRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="bdf35-162">Get-AzureRmSqlDatabaseRecommendedActions</span></span>
    + <span data-ttu-id="bdf35-163">Get-AzureRmSqlElasticPoolRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="bdf35-163">Get-AzureRmSqlElasticPoolRecommendedActions</span></span>
    + <span data-ttu-id="bdf35-164">Get-AzureRmSqlServerRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="bdf35-164">Get-AzureRmSqlServerRecommendedActions</span></span>
    + <span data-ttu-id="bdf35-165">Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="bdf35-165">Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="bdf35-166">Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="bdf35-166">Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="bdf35-167">Set-AzureRmSqlServerAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="bdf35-167">Set-AzureRmSqlServerAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="bdf35-168">Set-AzureRmSqlDatabaseRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="bdf35-168">Set-AzureRmSqlDatabaseRecommendedActionState</span></span>
    + <span data-ttu-id="bdf35-169">Set-AzureRmSqlElasticPoolRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="bdf35-169">Set-AzureRmSqlElasticPoolRecommendedActionState</span></span>
    + <span data-ttu-id="bdf35-170">Set-AzureRmSqlServerRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="bdf35-170">Set-AzureRmSqlServerRecommendedActionState</span></span>
