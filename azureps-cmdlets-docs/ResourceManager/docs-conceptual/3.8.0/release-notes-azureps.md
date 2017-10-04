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
ms.openlocfilehash: 04f89e8d47d0825d46cb1b8817efbcc0cafa0acd
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2017
---
# <a name="release-notes"></a>Informacje o wersji

To jest lista zmian wprowadzonych w programie Azure PowerShell w tym wydaniu.

## <a name="version-380"></a>Wersja 3.8.0
* Compute
  - Naprawiono błąd w poleceniach cmdlet Get-*, aby zezwolić na pobieranie wielu stron danych (więcej niż 120 elementów)
* DataLakeAnalytics
  - Naprawiono pomoc dla niektórych poleceń tak, aby zawierała właściwe sformułowania i przykłady.
* DataLakeStore
  - Dodano obsługę rozpoczęcia i zakończenia polecenia cmdlet `Get-AzureRMDataLakeStoreItemContent`. Pozwala to zwracać N pierwszych lub N ostatnich wierszy tekstu rozdzielanych znakiem nowego wiersza, które mają być wyświetlone.
* HDInsight
  - Dodano obsługę typu klastra RServer
    + Rozmiar maszyny wirtualnej Edgenode można określić dla klastra oprogramowania RServer w poleceniu New-AzureRmHDInsightCluster lub New-AzureRmHDInsightClusterConfig
    + Program RServer jest teraz opcją konfiguracji w poleceniu Add-AzureRmHDInsightConfigValues. Umożliwia on ustawienie flagi RStudio w celu wskazania, że należy przeprowadzić instalację programu R Studio.
* LogicApp
  - Polecenia cmdlet Set-AzureRmIntegrationAccountSchema i Set-AzureRmIntegrationAccountMap zostały naprawione dla problemu z elementem contentlink (ustawienie elementów content i contentlink powodowało niepowodzenie aktualizacji).
* Network
  - Do bram Application Gateway dodano obsługę nowych funkcji zapory aplikacji sieci Web
    + Dodano polecenie New-AzureRmApplicationGatewayFirewallDisabledRuleGroupConfig
    + Dodano polecenie Get-AzureRmApplicationGatewayAvailableWafRuleSets (Alias: List-AzureRmApplicationGatewayAvailableWafRuleSets)
    + Zaktualizowano polecenie New-AzureRmApplicationGatewayWebApplicationFirewallConfiguration: dodano parametr -RuleSetType -RuleSetVersion i -DisabledRuleGroups
    + Zaktualizowano polecenie Set-AzureRmApplicationGatewayWebApplicationFirewallConfiguration: dodano parametr -RuleSetType -RuleSetVersion i -DisabledRuleGroups
  - Dodano obsługę zasad protokołu IPSec do połączeń bramy sieci wirtualnej
  - Dodano polecenie New-AzureRmIpsecPolicy
  - Zaktualizowano polecenie New-AzureRmVirtualNetworkGatewayConnection: dodano parametr -IpsecPolicies i -UsePolicyBasedTrafficSelectors
* Profil
  - *Przestarzałe*: Nazwa polecenia Save-AzureRmProfile została zmieniona na Save-AzureRmContext, przy czym istnieje alias dla starej nazwy polecenia cmdlet, który zostanie usunięty w następnej wersji.
  - *Przestarzałe*: Nazwa polecenia Select-AzureRmProfile została zmieniona na Import-AzureRmContext, przy czym istnieje alias dla starej nazwy polecenia cmdlet, który zostanie usunięty w następnej wersji.
  - Typy wyjściowe PSAzureContext i PSAzureProfile poleceń cmdlet profilu zostaną zmienione w następnej wersji.
  - Polecenie cmdlet Save-AzureRmContext nie będzie miało typu OutputType w następnej wersji.
  - Naprawiono błąd we wspólnym kodzie polecenia cmdlet dotyczący użycia zgodnego ze standardem FIPS algorytmu dla skrótów danych: https://github.com/Azure/azure-powershell/issues/3651
* Sql
  - Naprawiono błędy poleceń cmdlet grupy trybu failover platformy Azure
  - Poprawiono sondowanie operacji
  - Poprawiono wartość GracePeriodWithDataLossHour podczas ustawiania wartości właściwości FailoverPolicy na Manual
* TrafficManager
  - Obsługa metody geograficznego routingu ruchu
    + Nowa wartość „Geographic” dla parametru TrafficRoutingMethod polecenia New-AzureRmTrafficManagerProfile
    + Nowy parametr „GeoMapping” dla polecenia New-AzureRmTrafficManagerEndpoint i Add-AzureRmTrafficManagerEndpointConfig
    + Naprawiono przesyłanie potokowe dla polecenia Get-AzureRmTrafficManagerProfile, gdy zwraca ono kolekcję profilów
* ServiceManagement
  - Restart-AzureVM: dodano parametr InitiateMaintenance w celu przeprowadzania konserwacji podczas ponownego uruchamiania maszyny wirtualnej.
  - Get-AzureVM: dodano pole stanu konserwacji.
  - Dodano nowe polecenia cmdlet do obsługi uaktualnienia magazynu usługi Recovery Services
    + Test-AzureRecoveryServicesVaultUpgrade
    + Invoke-AzureRecoveryServicesVaultUpgrade