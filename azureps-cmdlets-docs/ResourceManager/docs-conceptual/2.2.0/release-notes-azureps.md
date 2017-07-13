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
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="57587-103">Informacje o wersji</span><span class="sxs-lookup"><span data-stu-id="57587-103">Release notes</span></span>
<a id="release-notes" class="xliff"></a>

<span data-ttu-id="57587-104">To jest lista zmian wprowadzonych w programie Azure PowerShell w tym wydaniu.</span><span class="sxs-lookup"><span data-stu-id="57587-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <span data-ttu-id="57587-105">Wersja 2.2.0</span><span class="sxs-lookup"><span data-stu-id="57587-105">Version 2.2.0</span></span>
<a id="version-220" class="xliff"></a>
* <span data-ttu-id="57587-106">Compute</span><span class="sxs-lookup"><span data-stu-id="57587-106">Compute</span></span>
  - <span data-ttu-id="57587-107">Dodano obsługę pytania o stan szyfrowania z rozszerzenia AzureDiskEncryptionForLinux</span><span class="sxs-lookup"><span data-stu-id="57587-107">Add support for querying encryption status from the AzureDiskEncryptionForLinux extension</span></span>
* <span data-ttu-id="57587-108">DataFactory</span><span class="sxs-lookup"><span data-stu-id="57587-108">DataFactory</span></span>
  - <span data-ttu-id="57587-109">Dodano nowe polecenie cmdlet do wyświetlania listy okien działania</span><span class="sxs-lookup"><span data-stu-id="57587-109">Added new cmdlet for listing activity windows</span></span>
    + <span data-ttu-id="57587-110">Get-AzureRmDataFactoryActivityWindow</span><span class="sxs-lookup"><span data-stu-id="57587-110">Get-AzureRmDataFactoryActivityWindow</span></span>
* <span data-ttu-id="57587-111">DataLake</span><span class="sxs-lookup"><span data-stu-id="57587-111">DataLake</span></span>
  - <span data-ttu-id="57587-112">Zmieniono parametr `Host` na `DatabaseHost` i dodano alias do `Host`</span><span class="sxs-lookup"><span data-stu-id="57587-112">Changed parameter `Host` to `DatabaseHost` and added alias to `Host`</span></span>
    + <span data-ttu-id="57587-113">New-AzureRmDataLakeAnalyticsCatalogSecret</span><span class="sxs-lookup"><span data-stu-id="57587-113">New-AzureRmDataLakeAnalyticsCatalogSecret</span></span>
    + <span data-ttu-id="57587-114">Set-AzureRmDataLakeAnalyticsCatalogSecret</span><span class="sxs-lookup"><span data-stu-id="57587-114">Set-AzureRmDataLakeAnalyticsCatalogSecret</span></span>
  - <span data-ttu-id="57587-115">Dodano obsługę usuwania listy ACL i domyślnej listy ACL</span><span class="sxs-lookup"><span data-stu-id="57587-115">Add support for ACL and Default ACL removal</span></span>
  - <span data-ttu-id="57587-116">Dodano obsługę pobierania i ustawiania nienazwanych uprawnień do plików i folderów</span><span class="sxs-lookup"><span data-stu-id="57587-116">Add support for getting and setting unnamed permissions on files and folders</span></span>
* <span data-ttu-id="57587-117">KeyVault</span><span class="sxs-lookup"><span data-stu-id="57587-117">KeyVault</span></span>
  - <span data-ttu-id="57587-118">Dodano obsługę certyfikatów</span><span class="sxs-lookup"><span data-stu-id="57587-118">Add support for certificates</span></span>
    + <span data-ttu-id="57587-119">Add-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="57587-119">Add-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="57587-120">Add-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="57587-120">Add-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="57587-121">Get-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="57587-121">Get-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="57587-122">Get-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="57587-122">Get-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="57587-123">Get-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="57587-123">Get-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="57587-124">Get-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="57587-124">Get-AzureKeyVaultCertificateOperation</span></span>
    + <span data-ttu-id="57587-125">Get-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="57587-125">Get-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="57587-126">Import-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="57587-126">Import-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="57587-127">New-AzureKeyVaultCertificateAdministratorDetails</span><span class="sxs-lookup"><span data-stu-id="57587-127">New-AzureKeyVaultCertificateAdministratorDetails</span></span>
    + <span data-ttu-id="57587-128">New-AzureKeyVaultCertificateOrganizationDetails</span><span class="sxs-lookup"><span data-stu-id="57587-128">New-AzureKeyVaultCertificateOrganizationDetails</span></span>
    + <span data-ttu-id="57587-129">New-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="57587-129">New-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="57587-130">Remove-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="57587-130">Remove-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="57587-131">Remove-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="57587-131">Remove-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="57587-132">Remove-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="57587-132">Remove-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="57587-133">Remove-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="57587-133">Remove-AzureKeyVaultCertificateOperation</span></span>
    + <span data-ttu-id="57587-134">Set-AzureKeyVaultCertificateAttribute</span><span class="sxs-lookup"><span data-stu-id="57587-134">Set-AzureKeyVaultCertificateAttribute</span></span>
    + <span data-ttu-id="57587-135">Set-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="57587-135">Set-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="57587-136">Set-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="57587-136">Set-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="57587-137">Stop-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="57587-137">Stop-AzureKeyVaultCertificateOperation</span></span>
* <span data-ttu-id="57587-138">Sieć</span><span class="sxs-lookup"><span data-stu-id="57587-138">Network</span></span>

  - <span data-ttu-id="57587-139">Dodano nowy parametr przełącznika interfejsu sieciowego, aby włączyć/wyłączyć wydajniejsze sieci +New-AzureRmNetworkInterface -EnableAcceleratedNetworking</span><span class="sxs-lookup"><span data-stu-id="57587-139">New switch parameter added for network interface to enable/disable accelerated networking +New-AzureRmNetworkInterface -EnableAcceleratedNetworking</span></span>
  - <span data-ttu-id="57587-140">Włączono polecenia cmdlet programu PowerShell funkcji bramy Active-Active</span><span class="sxs-lookup"><span data-stu-id="57587-140">Enable Active-Active gateway feature PowerShell cmdlets</span></span>
    + <span data-ttu-id="57587-141">Add-AzureRmVirtualNetworkGatewayIpConfig</span><span class="sxs-lookup"><span data-stu-id="57587-141">Add-AzureRmVirtualNetworkGatewayIpConfig</span></span>
    + <span data-ttu-id="57587-142">Remove-AzureRmVirtualNetworkGatewayIpConfig</span><span class="sxs-lookup"><span data-stu-id="57587-142">Remove-AzureRmVirtualNetworkGatewayIpConfig</span></span>
  - <span data-ttu-id="57587-143">Dodano nowe polecenie cmdlet</span><span class="sxs-lookup"><span data-stu-id="57587-143">Added new cmdlet</span></span>
    + <span data-ttu-id="57587-144">Test-AzureRmPrivateIpAddressAvailability</span><span class="sxs-lookup"><span data-stu-id="57587-144">Test-AzureRmPrivateIpAddressAvailability</span></span>
* <span data-ttu-id="57587-145">Zasoby</span><span class="sxs-lookup"><span data-stu-id="57587-145">Resources</span></span>
  - <span data-ttu-id="57587-146">Obsługa stref w poleceniach cmdlet dostawcy i zasobów</span><span class="sxs-lookup"><span data-stu-id="57587-146">Support zones in provider and resource cmdlets</span></span>
    + <span data-ttu-id="57587-147">Get-AzureRmProvider</span><span class="sxs-lookup"><span data-stu-id="57587-147">Get-AzureRmProvider</span></span>
    + <span data-ttu-id="57587-148">New-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="57587-148">New-AzureRmResource</span></span>
    + <span data-ttu-id="57587-149">Set-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="57587-149">Set-AzureRmResource</span></span>
* <span data-ttu-id="57587-150">Sql</span><span class="sxs-lookup"><span data-stu-id="57587-150">Sql</span></span>
  - <span data-ttu-id="57587-151">Dodano nowe polecenia cmdlet do zarządzania zasadami wykrywania zagrożeń usług Azure SQL na poziomie serwera</span><span class="sxs-lookup"><span data-stu-id="57587-151">Added new cmdlets for Azure SQL threat detection policy management at server level</span></span>
    + <span data-ttu-id="57587-152">Get-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="57587-152">Get-AzureRmSqlServerThreatDetectionPolicy</span></span>
    + <span data-ttu-id="57587-153">Remove-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="57587-153">Remove-AzureRmSqlServerThreatDetectionPolicy</span></span>
    + <span data-ttu-id="57587-154">Set-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="57587-154">Set-AzureRmSqlServerThreatDetectionPolicy</span></span>
  - <span data-ttu-id="57587-155">Dodano nowe polecenia cmdlet do obsługi włączania/wyłączania zasad GeoBackupPolicy dla usług Azure SQL DataWarehouse</span><span class="sxs-lookup"><span data-stu-id="57587-155">Added new cmdlets to support enabling/disabling GeoBackupPolicy for Sql Azure DataWarehouses</span></span>
    + <span data-ttu-id="57587-156">Get-AzureRmSqlDatabaseGeoBackupPolicy</span><span class="sxs-lookup"><span data-stu-id="57587-156">Get-AzureRmSqlDatabaseGeoBackupPolicy</span></span>
    + <span data-ttu-id="57587-157">Set-AzureRmSqlDatabaseGeoBackupPolicy</span><span class="sxs-lookup"><span data-stu-id="57587-157">Set-AzureRmSqlDatabaseGeoBackupPolicy</span></span>
  - <span data-ttu-id="57587-158">Dodano nowe polecenia cmdlet dla interfejsów API usług Azure SQL Advisor i zalecanych akcji</span><span class="sxs-lookup"><span data-stu-id="57587-158">Added new cmdlets for Azure Sql Advisors and Recommended Actions APIs</span></span>
    + <span data-ttu-id="57587-159">Get-AzureRmSqlDatabaseAdvisor</span><span class="sxs-lookup"><span data-stu-id="57587-159">Get-AzureRmSqlDatabaseAdvisor</span></span>
    + <span data-ttu-id="57587-160">Get-AzureRmSqlElasticPoolAdvisor</span><span class="sxs-lookup"><span data-stu-id="57587-160">Get-AzureRmSqlElasticPoolAdvisor</span></span>
    + <span data-ttu-id="57587-161">Get-AzureRmSqlServerAdvisor</span><span class="sxs-lookup"><span data-stu-id="57587-161">Get-AzureRmSqlServerAdvisor</span></span>
    + <span data-ttu-id="57587-162">Get-AzureRmSqlDatabaseRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="57587-162">Get-AzureRmSqlDatabaseRecommendedActions</span></span>
    + <span data-ttu-id="57587-163">Get-AzureRmSqlElasticPoolRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="57587-163">Get-AzureRmSqlElasticPoolRecommendedActions</span></span>
    + <span data-ttu-id="57587-164">Get-AzureRmSqlServerRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="57587-164">Get-AzureRmSqlServerRecommendedActions</span></span>
    + <span data-ttu-id="57587-165">Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="57587-165">Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="57587-166">Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="57587-166">Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="57587-167">Set-AzureRmSqlServerAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="57587-167">Set-AzureRmSqlServerAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="57587-168">Set-AzureRmSqlDatabaseRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="57587-168">Set-AzureRmSqlDatabaseRecommendedActionState</span></span>
    + <span data-ttu-id="57587-169">Set-AzureRmSqlElasticPoolRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="57587-169">Set-AzureRmSqlElasticPoolRecommendedActionState</span></span>
    + <span data-ttu-id="57587-170">Set-AzureRmSqlServerRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="57587-170">Set-AzureRmSqlServerRecommendedActionState</span></span>
