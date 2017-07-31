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
ms.date: 07/26/2017
ms.openlocfilehash: cc2fe75f498f9043e5a4b632c144877af0143173
ms.sourcegitcommit: 20bcef86db4e4869125bb63085fcffd009c19280
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2017
---
# <a name="release-notes"></a>Informacje o wersji

To jest lista zmian wprowadzonych w programie Azure PowerShell w tym wydaniu.

## <a name="20170717---version-421"></a>2017.07.17 — wersja 4.2.1
* Wystąpienia obliczeniowe
    - Rozwiązanie problemu z poleceniami cmdlet tworzenia oraz aktualizowania dysku maszyny wirtualnej i migawki dysku maszyny wirtualnej (link) [https://github.com/azure/azure-powershell/issues/4309]
      - New-AzureRmDisk
      - New-AzureRmSnapshot
      - Update-AzureRmDisk
      - Update-AzureRmSnapshot
* Profil
    - Rozwiązanie problemu z uwierzytelnianiem użytkowników nieinterakcyjnych we frontonie RedDog (link) [https://github.com/Azure/azure-powershell/issues/4299]
* ServiceManagement
    - Rozwiązanie problemu z uwierzytelnianiem użytkowników nieinterakcyjnych (link) [https://github.com/Azure/azure-powershell/issues/4299]

## <a name="2017711---version-420"></a>2017.7.11 — wersja 4.2.0
* AnalysisServices
    * Dodaj nowy interfejs API płaszczyzny danych
        - Wprowadzono interfejs API umożliwiający pobranie dziennika serwera usług AS, Export-AzureAnalysisServicesInstanceLog
* Automatyzacja
    * Odpowiednie ustawienie wartości strefy czasowej harmonogramu tygodniowego i miesięcznego dla polecenia New-AzureRmAutomationSchedule
        - Więcej informacji można znaleźć na stronie dotyczącej tego problemu: https://github.com/Azure/azure-powershell/issues/3043
* AzureBatch
    - Dodano nowe polecenie cmdlet Get-AzureBatchJobPreparationAndReleaseTaskStatu.
    - Dodano początek i koniec zakresu bajtów do parametrów polecenia Get-AzureBatchNodeFileContent.
* CognitiveServices
    * Integracja z zestawem SDK zarządzania usługami Cognitive Services w wersji 1.0.0.
    * Usunięto błąd związany ze sprawdzaniem długości nazwy konta.
* Wystąpienia obliczeniowe
    * Obsługa typu konta magazynu w przypadku dysku obrazu:
        - Dodano parametr „StorageAccountType” do poleceń Set-AzureRmImageOsDisk i Add-AzureRmImageDataDisk
    * Funkcja PrivateIP i PublicIP w konfiguracji adresu IP zestawu skalowania maszyn wirtualnych:
        - Dodano nazwy „PrivateIPAddressVersion”, „PublicIPAddressConfigurationName”, „PublicIPAddressConfigurationIdleTimeoutInMinutes” i „DnsSetting” do polecenia New-AzureRmVmssIpConfig
        - Do polecenia New-AzureRmVmssIpConfig dodano parametr „PrivateIPAddressVersion” umożliwiający określenie adresu IPv4 lub IPv6
    * Funkcja konserwacji w zakresie wydajności:
        - Dodano parametr przełącznika „PerformMaintenance” do polecenia Restart-AzureRmVM.
        - Użycie polecenia Get-AzureRmVM -Status powoduje wyświetlenie informacji o konserwacji w zakresie wydajności danej maszyny wirtualnej
    * Funkcja tożsamości maszyny wirtualnej:
        - Dodano parametr „IdentityType” do poleceń New-AzureRmVMConfig i UpdateAzureRmVM
        - Użycie polecenia Get-AzureRmVM powoduje wyświetlenie informacji o tożsamości danej maszyny wirtualnej
    * Funkcja tożsamości zestawu skalowania maszyn wirtualnych:
        - Dodano parametr „IdentityType” do polecenia New-AzureRmVmssConfig
        - Użycie polecenia Get-AzureRmVmss powoduje wyświetlenie informacji o tożsamości danego zestawu skalowania maszyn wirtualnych
    * Funkcja diagnostyki rozruchu zestawu skalowania maszyn wirtualnych:
        - Nowe polecenie cmdlet umożliwiające ustawienie diagnostyki rozruchu obiektu zestawu skalowania maszyny wirtualnej: Set-AzureRmVmssBootDiagnostics
        - Dodano parametr „BootDiagnostic” do polecenia New-AzureRmVmssConfig
    * Funkcja LicenseType zestawu skalowania maszyn wirtualnych:
        - Dodano parametr „LicenseType” do polecenia New-AzureRmVmssConfig
    * Obsługa parametru RecoveryPolicyMode:
        - Dodano parametr „RecoveryPolicyMode” do polecenia New-AzureRmVmssConfig
    * Funkcja obliczania jednostki SKU zasobu:
        - Nowe polecenie cmdlet „Get-AzureRmComputeResourceSku” umożliwiające wyświetlenie listy wszystkich obliczonych jednostek SKU zasobów
* DataFactories
    * Wycofanie polecenia New-AzureRmDataFactoryGatewayKey
    * Wprowadzenie funkcji klucza uwierzytelniania bramy przez dodanie poleceń New-AzureRmDataFactoryGatewayAuthKey i Get-AzureRmDataFactoryGatewayAuthKey
* DataLakeAnalytics
    * Dodanie obsługi operacji CRUD zasad obliczania przy użyciu następujących poleceń:
        - New-AzureRMDataLakeAnalyticsComputePolicy
        - Get-AzureRMDataLakeAnalyticsComputePolicy
        - Remove-AzureRMDataLakeAnalyticsComputePolicy
        - Update-AzureRMDataLakeAnalyticsComputePolicy
    * Dodanie obsługi metadanych relacji zadań w celu ułatwienia wykonywania zadań cyklicznych i potoków zadań. Zaktualizowano lub dodano następujące polecenia:
        - Submit-AzureRMDataLakeAnalyticsJob
        - Get-AzureRMDataLakeAnalyticsJob
        - Get-AzureRMDataLakeAnalyticsJobRecurrence
        - Get-AzureRMDataLakeAnalyticsJobPipeline
    * Zaktualizowano odbiorców tokenu interfejsów API zadań i wykazów w celu używania poprawnych odbiorców usługi Data Lake zamiast odbiorców zasobów platformy Azure.
* DataLakeStore
    * Dodano obsługę wymiany kluczy magazynu kluczy zarządzanych przez użytkowników w poleceniu cmdlet Set-AzureRMDataLakeStoreAccount
    * Dodano aktualizację ułatwiającą pracę, która powoduje automatyczne wyzwolenie elementu `enableKeyVault` w przypadku dodania klucza magazynu kluczy zarządzanego przez użytkownika lub wymiany klucza.
    * Zaktualizowano odbiorców tokenu interfejsów API zadań i wykazów w celu używania poprawnych odbiorców usługi Data Lake zamiast odbiorców zasobów platformy Azure.
    * Usunięto błąd ograniczający rozmiar plików tworzonych/dołączanych przy użyciu następujących poleceń cmdlet:
        - New-AzureRmDataLakeStoreItem
        - Add-AzureRmDataLakeStoreItemContent
* Dns
    * Usunięcie błędu w scenariuszu potoku dotyczącego polecenia Get-AzureRmDnsZone
        - Więcej informacji można znaleźć tutaj: https://github.com/Azure/azure-powershell/issues/4203
* HDInsight
    * Dodano obsługę włączania/wyłączania pakietu Operations Management Suite (OMS)
    * Nowe polecenia cmdlet
        - Enable-AzureRmHDInsightOperationsManagementSuite
        - Disable-AzureRmHDInsightOperationsManagementSuite
        - Get-AzureRmHDInsightOperationsManagementSuite
    * Dodanie do polecenia Add-AzureRmHDInsightConfigValues nowych parametrów umożliwiających ustawianie niestandardowych konfiguracji aparatu Spark
        - Parametry SparkDefaults i SparkThriftConf dla aparatu Spark 1.6
        - Parametry Spark2Defaults i Spark2ThriftConf dla aparatu Spark 2.0
* Insights
    * Problem 4215 (żądanie zmiany) powodujący usunięcie 15-dniowego limitu przedziału czasu polecenia cmdlet Get-AzureRmLog. Wprowadzono również drobne zmiany w nazwach testów jednostkowych.
    * Rozwiązano problem 3957 związany z poleceniem Get-AzureRmLog
        - Problem 1: zaplecze zwraca rekordy na stronach zawierających po 200 rekordów połączonych z następną stroną przez token kontynuacji. Polecenie cmdlet zwracało u klientów tylko 200 rekordów w sytuacji, gdy klienci wiedzieli, że istnieje więcej rekordów. Działo się tak niezależnie od ustawionej wartości elementu MaxEvents, gdy wartość nie była mniejsza niż 200.
        - Problem 2: dokumentacja zawierała niepoprawne dane dotyczące tego polecenia cmdlet, np. domyślny przedział czasu równy 1 godz.
        - Poprawka 1: polecenie cmdlet występuje teraz po tokenie kontynuacji zwróconym przez zaplecze do czasu osiągnięcia wartości elementu MaxEvents lub końca zestawu.<br>Wartość domyślna elementu MaxEvents to 1000, a wartość maksymalna to 100000. Każda wartość elementu MaxEvents mniejsza niż 1 jest ignorowana i zamiast niej jest używana wartość domyślna. Te wartości i zachowanie nie uległy zmianie. Są one teraz poprawnie udokumentowane.<br>Dodano alias elementu MaxEvents (MaxRecords), ponieważ nazwa polecenia cmdlet nie zawiera już informacji o zdarzeniach (zawiera tylko informacje o dziennikach).
        - Poprawka 2: dokumentacja zawiera poprawne i bardziej szczegółowe informacje — nowy alias, poprawny przedział czasu oraz poprawną wartość domyślną, minimalną i maksymalną.
* KeyVault
    * Usunięcie adresu e-mail z zapytania katalogu w przypadku określenia parametru -UserPrincipalName w poleceniach cmdlet Set-AzureRMKeyVaultAccessPolicy i Remove-AzureRMKeyVaultAccessPolicy.
      - Oba polecenia cmdlet zawierają już parametr -EmailAddress, którego może użyć zamiast parametru -UserPrincipalName podczas wykonywania zapytania dotyczącego adresu e-mail.  Jeśli w katalogu istnieje więcej niż jeden zgodny adres e-mail, polecenie cmdlet kończy się niepowodzeniem.
* Sieć
    * New-AzureRmIpsecPolicy: parametry SALifeTimeSeconds i SADataSizeKilobytes nie są już obowiązkowe
        - Wartość domyślna parametru SALifeTimeSeconds to 27000 sekund
        - Wartość domyślna parametru SADataSizeKilobytes to 102400000 KB
    * Dodano obsługę niestandardowej konfiguracji pakietu szyfrowania przy użyciu zasad SSL przez wyświetlenie listy wszystkich opcji interfejsu API protokołu SSL w usłudze Application Gateway
        - Dodano opcjonalne parametry -PolicyType, -PolicyName, -MinProtocolVersion i -Ciphersuite
            - Add-AzureRmApplicationGatewaySslPolicy
            - New-AzureRmApplicationGatewaySslPolicy
            - Set-AzureRmApplicationGatewaySslPolicy
        - Dodano polecenie Get-AzureRmApplicationGatewayAvailableSslOptions (alias: List-AzureRmApplicationGatewayAvailableSslOptions)
        - Dodano polecenie Get-AzureRmApplicationGatewaySslPredefinedPolicy (alias: List-AzureRmApplicationGatewaySslPredefinedPolicy)
    * Dodano obsługę przekierowywania w usłudze Application Gateway
        - Dodano polecenie Add-AzureRmApplicationGatewayRedirectConfiguration
        - Dodano polecenie Get-AzureRmApplicationGatewayRedirectConfiguration
        - Dodano polecenie New-AzureRmApplicationGatewayRedirectConfiguration
        - Dodano polecenie Remove-AzureRmApplicationGatewayRedirectConfiguration
        - Dodano polecenie Set-AzureRmApplicationGatewayRedirectConfiguration
        - Dodano opcjonalny parametr -RedirectConfiguration
            - Add-AzureRmApplicationGatewayRequestRoutingRule
            - New-AzureRmApplicationGatewayRequestRoutingRule
            - Set-AzureRmApplicationGatewayRequestRoutingRule
        - Dodano opcjonalny parametr -DefaultRedirectConfiguration
            - Add-AzureRmApplicationGatewayUrlPathMapConfig
            - New-AzureRmApplicationGatewayUrlPathMapConfig
            - Set-AzureRmApplicationGatewayUrlPathMapConfig
        - Dodano opcjonalny parametr -RedirectConfiguration
            - Add-AzureRmApplicationGatewayPathRuleConfig
            - New-AzureRmApplicationGatewayPathRuleConfig
            - Set-AzureRmApplicationGatewayPathRuleConfig
        - Dodano opcjonalny parametr -RedirectConfigurations
            - New-AzureRmApplicationGateway
            - Set-AzureRmApplicationGateway
    * Dodano obsługę witryn internetowych platformy Azure w usłudze Application Gateway
        - Dodano polecenie New-AzureRmApplicationGatewayProbeHealthResponseMatch
        - Dodano opcjonalne parametry -PickHostNameFromBackendHttpSettings, -MinServers i -Match
            - Add-AzureRmApplicationGatewayProbeConfig
            - New-AzureRmApplicationGatewayProbeConfig
            - Set-AzureRmApplicationGatewayProbeConfig
        - Dodano opcjonalne parametry -PickHostNameFromBackendAddress, -AffinityCookieName, -ProbeEnabled i -Path
            - Add-AzureRmApplicationGatewayBackendHttpSettings
            - New-AzureRmApplicationGatewayBackendHttpSettings
            - Set-AzureRmApplicationGatewayBackendHttpSettings
    * Aktualizacja polecenia Get-AzureRmPublicIPaddress w celu pobierania zasobów publicipaddress tworzonych przy użyciu zestawu skalowania maszyn wirtualnych
    * Dodano polecenie cmdlet umożliwiające pobranie bieżących danych użycia sieci wirtualnej
        - Get-AzureRmVirtualNetworkUsageList
* Profil
    * Usunięto błąd występujący w przypadku używania polecenia Import-AzureRmContext lub Save-AzureRmContext
        - Więcej informacji można znaleźć na stronie dotyczącej tego problemu: https://github.com/Azure/azure-powershell/issues/3954
* RecoveryServices.SiteRecovery
    * Wprowadzono nowy moduł operacji usługi Azure Site Recovery.
        - Wszystkie polecenia cmdlet rozpoczynają się od ciągu AzureRmRecoveryServicesAsr*
* Sql
    * Dodanie poleceń cmdlet programu PowerShell synchronizacji danych do elementu AzureRM.Sql
    * Zaktualizowano polecenia cmdlet AzureRmSqlServer w celu używania nowej wersji interfejsu API REST, która pozwala uniknąć przekroczeń limitu czasu podczas tworzenia serwera.
    * Wycofano polecenia cmdlet uaktualniania serwera, ponieważ stara wersja serwera (2.0) już nie istnieje.
    * Dodanie nowego opcjonalnego parametru przełącznika „AssignIdentity” do poleceń cmdlet New-AzureRmSqlServer i Set-AzureRmSqlServer w celu obsługi aprowizacji tożsamości zasobu serwera SQL
    * Parametr ResourceGroupName jest teraz opcjonalny w przypadku polecenia Get-AzureRmSqlServer
        - Więcej informacji można znaleźć na stronie dotyczącej następującego problemu: https://github.com/Azure/azure-powershell/issues/635
* ServiceManagement dla usługi ExpressRoute:
    * Zaktualizowano polecenie cmdlet New-AzureBgpPeering przez dodanie następujących nowych opcji:
        - PeerAddressType: można określić wartość „IPv4” lub „IPv6” w celu utworzenia komunikacji równorzędnej BGP odpowiedniego typu rodziny adresów
    * Zaktualizowano polecenie cmdlet Set-AzureBgpPeering przez dodanie następujących nowych opcji:
        - PeerAddressType: można określić wartość „IPv4” lub „IPv6” w celu zaktualizowania komunikacji równorzędnej BGP odpowiedniego typu rodziny adresów
    * Zaktualizowano polecenie cmdlet Remove-AzureBgpPeering przez dodanie następujących nowych opcji:
        - PeerAddressType: można określić wartość „IPv4”, „IPv6” lub „Wszystkie” w celu usunięcia komunikacji równorzędnej BGP odpowiedniego typu rodziny adresów albo wszystkich typów

## <a name="20170607---version-410"></a>2017.06.07 — wersja 4.1.0
* AnalysisServices
    * Dodano nowe jednostki SKU: B1, B2 i S0
    * Dodano obsługę skalowania w górę i w dół
* CognitiveServices
    * Aktualizacja szczegółów umów licencyjnych wyświetlanych podczas tworzenia zasobów usług Cognitive Services
* Wystąpienia obliczeniowe
    * Usunięcie błędu związanego z poleceniem Test-AzureRmVMAEMExtension w przypadku maszyn wirtualnych z wieloma dyskami Managed Disks
    * Zaktualizowano polecenie Set-AzureRmVMAEMExtension: dodanie informacji dotyczących buforowania w przypadku dysków Managed Disks w wersji Premium
    * Add-AzureRmVhd: zwiększono limit rozmiaru wirtualnego dysku twardego do 4 TB.
    * Stop-AzureRmVM: doprecyzowanie dokumentacji dotyczącej parametru STayProvisioned
    * New-AzureRmDiskUpdateConfig
      * Wycofano parametry CreateOption, StorageAccountId, ImageReference, SourceUri i SourceResourceId
    * Set-AzureRmDiskUpdateImageReference: wycofano polecenie cmdlet
    * New-AzureRmSnapshotUpdateConfig
      * Wycofano parametry CreateOption, StorageAccountId, ImageReference, SourceUri i SourceResourceId
    * Set-AzureRmSnapshotUpdateImageReference: wycofano polecenie cmdlet
* DataLakeStore
    * Enable-AzureRmDataLakeStoreKeyVault (Enable-AdlStoreKeyVault)
      * Włączenie szyfrowania zarządzanego przez magazyn kluczy w przypadku magazynu usługi DataLake
* DevTestLabs
    * Aktualizacja poleceń cmdlet w celu współdziałania z bieżącą i zaktualizowaną wersją interfejsu API usługi DevTest Labs.
* IotHub
    * Dodanie obsługi routingu w przypadku poleceń cmdlet usługi IoTHub
* KeyVault
  * Nowe polecenia cmdlet umożliwiające obsługę kluczy kont magazynu zarządzanych przez magazyn kluczy
    * Get-AzureKeyVaultManagedStorageAccount
    * Add-AzureKeyVaultManagedStorageAccount
    * Remove-AzureKeyVaultManagedStorageAccount
    * Update-AzureKeyVaultManagedStorageAccount
    * Update-AzureKeyVaultManagedStorageAccountKey
    * Get-AzureKeyVaultManagedStorageSasDefinition
    * Set-AzureKeyVaultManagedStorageSasDefinition
    * Remove-AzureKeyVaultManagedStorageSasDefinition
* Sieć
    * Get-AzureRmNetworkUsage: nowe polecenie cmdlet umożliwiające wyświetlenie szczegółowych informacji dotyczących użycia i pojemności
    * Dodano nowe opcje GatewaySku dla elementów VirtualNetworkGateway
        * VpnGw1, VpnGw2 i VpnGw3 to nowe jednostki SKU dodane do bram sieci VPN
    * Set-AzureRmNetworkWatcherConfigFlowLog
      * Przykłady pomocy w rozwiązaniu problemu
* NotificationHubs
    * Przezroczysta aktualizacja poleceń cmdlet usługi NotificationHubs pod kątem nowego interfejsu API
* Profil
    * Resolve-AzureRmError
      * Nowe polecenie cmdlet umożliwiające wyświetlenie szczegółów błędów i wyjątków zgłaszanych przez polecenia cmdlet, łącznie z danymi żądań/odpowiedzi serwera
    * Send-Feedback
      * Włączono wysyłanie opinii bez potrzeby logowania
    * Get-AzureRmSubscription
      * Usunięcie błędu występującego podczas pobierania subskrypcji dostawcy CSP
* Zasoby
    * Rozwiązano problem polegający na tym, że polecenie Get-AzureRMRoleAssignment powodowało wystąpienie nieprawidłowego żądania, gdy liczba przypisań ról była większa niż 1000
        * Użytkownicy mogą teraz używać polecenia Get-AzureRMRoleAssignment nawet wtedy, gdy zwrócona liczba przypisań ról jest większa niż 1000
* Sql
    * Restore-AzureRmSqlDatabase: aktualizacja przykładu dokumentacji
* Magazyn
    * Dodanie obsługi ustawienia AssignIdentity do poleceń cmdlet konta magazynu trybu zasobu
        * New-AzureRmStorageAccount
        * Set-AzureRmStorageAccount
    * Dodanie obsługi kluczy klientów do poleceń cmdlet konta magazynu trybu zasobu
        * Set-AzureRmStorageAccount
        * New-AzureRmStorageAccountEncryptionKeySource
* TrafficManager

    * Nowe ustawienia monitora „MonitorIntervalInSeconds”, „MonitorTimeoutInSeconds” i „MonitorToleratedNumberOfFailures”
    * Nowy protokół monitora „TCP”
* ServiceManagement
    * Add-AzureVhd: zwiększono limit rozmiaru wirtualnego dysku twardego do 4 TB.
    * New-AzureBGPPeering: obsługa elementu LegacyMode
* Azure.Storage
    * Aktualizacja pomocy dotyczącej parametrów, które akceptują symbole wieloznaczne i aktualizacja typu StorageContext

## <a name="20170523---version-402"></a>2017.05.23 — wersja 4.0.2
* Profil
    * Add-AzureRmAccount
      * Dodano alias parametru `-EnvironmentName` na potrzeby zachowania zgodności z poprzednimi wersjami 2.x elementu AzureRM.profile

## <a name="20170512---version-401"></a>2017.05.12 — wersja 4.0.1
 * Rozwiązanie problemu z poleceniem New-AzureStorageContext w scenariuszach w trybie offline: https://github.com/Azure/azure-powershell/issues/3939

## <a name="20170510---version-400"></a>2017.05.10 — wersja 4.0.0


* Niniejsza wersja zawiera istotne zmiany. Aby uzyskać szczegółowe informacje o zmianach i ich wpływie na istniejące skrypty, zobacz [przewodnik po migracji](https://aka.ms/azps-migration-guide).
* ApiManagement
  - Dodano obsługę konfigurowania grup zewnętrznych w poleceniu New-AzureRmApiManagementGroup.
* Rozliczenia
  - Nowe polecenie cmdlet Get-AzureRmBillingPeriod
    + Polecenie cmdlet do pobierania okresów rozliczeniowych subskrypcji platformy Azure.
  - Aktualizacja polecenia cmdlet Get-AzureRmBillingInvoice
  - Nowa właściwość BillingPeriodNames
  - Dane wyjściowe w widoku listy
* Wystąpienia obliczeniowe
  - Zaktualizowano polecenia cmdlet Set-AzureRmVMAEMExtension i Test-AzureRmVMAEMExtension o obsługę dysków zarządzanych w warstwie Premium
  - Ustawienia szyfrowania kopii zapasowych maszyn wirtualnych IaaS oraz przywracanie po awarii
  - Zmieniono nazwę opcji ChefServiceInterval na ChefDaemonInterval. Stara opcja będzie jednak nadal działać.
  - Usunięto zduplikowane właściwości DataDiskNames i NetworkInterfaceIDs z obiektu maszyny wirtualnej w programie PowerShell.
  - Zmieniono parametry DataDiskNames i NetworkInterfaceIDs odpowiednio w poleceniach Remove-AzureRmVMDataDisk i Remove-AzureRmVMNetworkInterface na opcjonalne.
  - Naprawiono problem z potokami poleceń cmdlet zawierających wartość Get, który występował, gdy polecenia cmdlet zwracały obiekt listy.
  - Zmieniono nazwy poleceń cmdlet powodujących konflikt z poleceniami cmdlet frontonu RedDog. Aby uzyskać szczegółowe informacje, zobacz opis problemu na stronie https://github.com/Azure/azure-powershell/issues/2917
    + Zmieniono nazwę polecenia `New-AzureVMSqlServerAutoBackupConfig` na `New-AzureRmVMSqlServerAutoBackupConfig`
    + Zmieniono nazwę polecenia `New-AzureVMSqlServerAutoPatchingConfig` na `New-AzureRmVMSqlServerAutoPatchingConfig`
    + Zmieniono nazwę polecenia `New-AzureVMSqlServerKeyVaultCredentialConfig` na `New-AzureRmVMSqlServerKeyVaultCredentialConfig`
* Zużycie
  - Dodano nowe polecenie cmdlet Get-AzureRmConsumptionUsageDetail
    + Polecenie cmdlet do pobierania szczegółów użycia w ramach subskrypcji.
* ContainerRegistry
  - Dodano polecenia cmdlet programu PowerShell dla usługi Azure Container Registry
    + New-AzureRmContainerRegistry
    + Get-AzureRmContainerRegistry
    + Update-AzureRmContainerRegistry
    + Remove-AzureRmContainerRegistry
    + Get-AzureRmContainerRegistryCredential
    + Update-AzureRmContainerRegistryCredential
    + Test-AzureRmContainerRegistryNameAvailability
* DataLakeAnalytics
  - Dodano obsługę pobierania i wyświetlania listy pakietu wykazu
  - Dodano obsługę wyświetlania listy poniższych elementów wykazu z głębszych elementów nadrzędnych:
    + Tabela
    + Funkcja TVF
    + Widok
    + Statystyki
* DataLakeStore
  - Dla poleceń `Import-AzureRMDataLakeStoreItem` i `Export-AzureRMDataLakeStoreItem` domyślnie wyłączono rejestrowanie śledzenia, aby poprawić wydajność. Aby włączyć rejestrowanie śledzenia, należy użyć parametrów `-DiagnosticLogLevel` i `-DiagnosticLogPath`
  - Naprawiono usterkę, która czasami powodowała awarię programu PowerShell podczas przekazywania wielu małych plików do usługi ADLS.
* EventHub
  - Poprawka usterki:
    + Poprawka błędu dotyczącego polecenia cmdlet Set-AzureRmEventHubNamespace: element „Tier” nie może mieć wartości null, gdy powinien mieć wartość „SkuName”
    + Set-AzureRmEventHub: poprawka dla błędu „Odwołanie do obiektu nie zostało ustawione na wystąpienie obiektu” wyświetlanego podczas aktualizowania usługi EventHub
* Insights
  - Add-AzureRm*AlertRule
    + Zwraca pojedynczy obiekt: newResource, statusCode, requestId
  - Get-AzureRmAlertRule
    + Dane wyjściowe są teraz wyliczane, a nie traktowane jako pojedynczy obiekt. Ich typ nie uległ zmianie. Nadal jest to lista.
  - Remove-AzureRmAlertRule
    + Po kodzie stanu zwróconym przez żądanie jest wyświetlana wartość „statusCode”. Wcześniej był to zawsze ciąg „OK”.
  - Add-AzureRmAutoscaleSetting
    + Zwraca teraz pojedynczy obiekt (a nie listę, jak wcześniej) zawierający wartości statusCode, requestId oraz nowo utworzony/zaktualizowany zasób.
    + Po stanie zwróconym przez żądanie jest wyświetlany kod stanu. Wcześniej był to zawsze ciąg „OK”.
  - New-AzureRmAutoscaleRule
    + Parametr ScaleActionType został rozszerzony. Otrzymuje teraz następujące wartości: ChangeCount, PercentChangeCount, ExactCount.
  - Remove-AzureRmAutoscaleSetting
    + W danych wyjściowych po wartości statusCode zwróconej przez żądanie jest wyświetlany ciąg statusCode. Wcześniej był to zawsze ciąg OK.
  - Get-AzureRMLogProfile
    + Dane wyjściowe są teraz wyliczane. Wcześniej były traktowane jako pojedynczy obiekt. Typ danych wyjściowych to nadal lista, tak jak wcześniej.
  - Remove-AzureRmLogProfile
    + Zaimplementowano parametr PassThru.
  - Interfejs API metryk
    + Zestaw SDK pobiera teraz metryki z usługi MDM.
  - Get-AzureRmMetricDefinition
    + Dane wyjściowe to nadal lista, ale struktura tej listy uległa zmianie.
  - Get-AzureRmMetric
    + Wywołanie uległo zmianie. Oto nowa składnia: Get-AzureRmMetric ResourceId [Nazwy_metryk [Ziarno_czasu] [Typ_agregacji] [Czas_rozpoczęcia] [Czas_zakończenia]] [Szczegółowe_dane_wyjściowe]
    + Dane wyjściowe to lista, a struktura jej elementów uległa zmianie.
* KeyVault
  - Dodano obsługę tworzenia/przywracania kopii zapasowych wpisów tajnych usługi KeyVault
    + Kopie zapasowe wpisów tajnych można tworzyć i przywracać, co zapewnia zgodność z funkcjami obecnie obsługiwanymi w przypadku kluczy

  - Polecenia cmdlet kopii zapasowych dla kluczy i wpisów tajnych akceptują teraz odpowiedni obiekt jako parametr wejściowy
    + Obiekt wywołujący może tworzyć łańcuchy operacji pobierania i tworzenia kopii zapasowych: Get-AzureKeyVaultKey -VaultName mójMagazyn -Name mójKlucz | Backup-AzureKeyVaultKey

  - Polecenia cmdlet kopii zapasowych obsługują teraz przełącznik -Force umożliwiający zastąpienie istniejącego pliku
    + Pamiętaj, że próba zastąpienia istniejącego pliku nie będzie już powodować zgłoszenia błędu. Zamiast tego będzie wyświetlany monit o wybranie działania.
* LogicApp
  - Nowe parametry poleceń cmdlet odzyskiwania po awarii numeru kontrolnego wymiany:
    + Opcjonalny parametr -AgreementType („X12” lub „Edifact”) umożliwiający określenie odpowiednich numerów kontrolnych
* MachineLearning
  - Korzystanie z nowej wersji zestawu .NET SDK usługi Azure Machine Learning i dodanie nowego polecenia cmdlet
    + Add-AzureRmMlWebServiceRegionalProperty
  - Niewielkie poprawki tekstu pomocy.
* Sieć
  - Dodano polecenie cmdlet Test-AzureRmNetworkWatcherConnectivity
    + Zwraca informacje o łączności dla określonej źródłowej maszyny wirtualnej i określonego miejsca docelowego
    + Jeśli nie można ustanowić łączności między miejscem źródłowym i docelowym, polecenie cmdlet zwraca szczegółowe informacje dotyczące problemu
* Profil
  - Dodano polecenie cmdlet „Send-Feedback”, które pozwala użytkownikowi na zainicjowanie zestawu monitów w celu wysłania opinii do zespołu programu Azure PowerShell.
  - Następujące aliasy zostały usunięte, ponieważ powodowały konflikty z istniejącymi nazwami poleceń cmdlet w module platformy Azure:
    + `Enable-AzureDataCollection` (obsługiwany przez `Enable-AzureRmDataCollection`)
    + `Disable-AzureDataCollection` (obsługiwany przez `Disable-AzureRmDataCollection`)
* Usługa Relay
  - Dodano polecenia cmdlet dla usługi Azure Relay umożliwiające użytkownikom tworzenie wszystkich zasobów usługi Azure Relay i zarządzanie nimi.
    + `New-AzureRmRelayNamespace`
    + `Get-AzureRmRelayNamespace`
    + `Set-AzureRmRelayNamespace`
    + `Remove-AzureRmRelayNamespace`
    + `New-AzureRmWcfRelay`
    + `Get-AzureRmWcfRelay`
    + `Set-AzureRmWcfRelay`
    + `Remove-AzureRmWcfRelay`
    + `New-AzureRmRelayHybridConnection`
    + `Get-AzureRmRelayHybridConnection`
    + `Set-AzureRmRelayHybridConnection`
    + `Remove-AzureRmRelayHybridConnection`
    + `Test-AzureRmRelayName`
    + `Get-AzureRmRelayOperation`
    + `New-AzureRmRelayKey`
    + `Get-AzureRmRelayKey`
    + `New-AzureRmRelayAuthorizationRule`
    + `Get-AzureRmRelayAuthorizationRule`
    + `Set-AzureRmRelayAuthorizationRule`
    + `Remove-AzureRmRelayAuthorizationRule`
* Zasoby
  - Obsługa wdrożeń między grupami zasobów w poleceniu cmdlet New-AzureRmResourceGroupDeployment
    + Użytkownicy mogą teraz używać zagnieżdżonych wdrożeń w celu wdrażania w różnych grupach zasobów.
* ServiceBus

  - Poprawka usterki: wartości właściwości obiektu kolejki ServiceBus zostały ustawione na null, obiekt jest używany jako parametr wejściowy w poleceniu cmdlet Set-AzureRmServiceBusQueue w celu zaktualizowania kolejki.
   - Właściwości, których to dotyczy, to: LockDuration, EntityAvailabilityStatus, DuplicateDetectionHistoryTimeWindow, MaxDeliveryCount i MessageCount
* ServiceFabric

  - Dodano polecenia cmdlet dla usługi Service Fabric
    + Add-AzureRmServiceFabricApplicationCertificate       Dodaj certyfikat, który będzie używany jako certyfikat aplikacji
    + Add-AzureRmServiceFabricClientCertificate       Dodaj nazwę pospolitą lub odcisk palca do ustawień klastra na potrzeby uwierzytelniania klienta
    + Add-AzureRmServiceFabricClusterCertificate       Dodaj pomocniczy certyfikat do klastra na potrzeby wymiany istniejącego certyfikatu
    + Add-AzureRmServiceFabricNodes       Dodaj węzły/maszyny wirtualne o określonym typie węzła do klastra
    + Add-AzureRmServiceFabricNodeType       Dodaj maszyny wirtualne/typ węzła do istniejącego klastra
    + Get-AzureRmServiceFabricCluster       Pobierz szczegóły zasobu klastra
    + New-AzureRmServiceFabricCluster Utwórz nowy klaster ServiceFabric. To polecenie ma wiele przeciążeń, aby obsłużyć różne scenariusze
    + Remove-AzureRmServiceFabricClientCertificate       Usuń certyfikat klienta, aby nie był już używany w celu uzyskiwania dostępu do klastra
    + Remove-AzureRmServiceFabricClusterCertificate       Usuń certyfikat klastra, aby nie był już używany do zabezpieczania klastra
    + Remove-AzureRmServiceFabricNodes       Usuń z klastra węzły o określonym typie
    + Remove-AzureRmServiceFabricNodeType       Usuń z klastra typ węzła
    + Remove-AzureRmServiceFabricSettings       Usuń z klastra co najmniej jedno ustawienie ServiceFabric
    + Set-AzureRmServiceFabricSettings       Dodaj lub zaktualizuj co najmniej jedno ustawienie ServiceFabric klastra
    + Set-AzureRmServiceFabricUpgradeType       Zmień typ uaktualnienia ServiceFabric klastra
    + Update-AzureRmServiceFabricDurability       Zmień warstwę trwałości klastra
    + Update-AzureRmServiceFabricReliability       Zmień warstwę niezawodności klastra
* Sql
  - Dodano parametr -SampleName do polecenia New-AzureRmSqlDatabase
  - Aktualizacje poleceń cmdlet grupy trybu failover
  - Usunięto parametry „Tag”
  - Usunięto parametry „PartnerResourceGroupName” i „PartnerServerName” z polecenia cmdlet Remove-AzureRmSqlDatabaseFailoverGroup
  - Dodano parametr „GracePeriodWithDataLossHours” do poleceń cmdlet New- i Set-, który w przyszłości zastąpi parametr „GracePeriodWithDataLossHour”
  - Dopracowano i zaktualizowano dokumentację
  - Zmieniono formatowanie zwracanych obiektów i usunięto usterki, z powodu których pola nie zawsze były wypełniane
  - Dodano właściwości „DatabaseNames” i „PartnerLocation” do obiektu grupy trybu failover
  - Naprawiono usterkę, z powodu której następował natychmiastowy powrót z polecenia cmdlet Switch-, zamiast poczekania na zakończenie operacji
  - Naprawiono usterkę powodującą przekroczenie zakresu liczb całkowitych w przypadku użycia dużych wartości okresu prolongaty
  - Okres prolongaty będzie zmieniany na wartość minimalną (1 godzina), jeśli podano krótszy
  - Usunięto wartość „Usage_Anomaly” z listy akceptowanych wartości parametru „ExcludedDetectionType” poleceń cmdlet Set-AzureRmSqlDatabaseThreatDetectionPolicy i Set-AzureRmSqlServerThreatDetectionPolicy.
* Magazyn
  - Uaktualniono zestaw SRP SDK do wersji 6.3.0
  - New/Set-AzureRmStorageAccount: dodano nowy parametr w celu obsługi atrybutu EnableHttpsTrafficOnly
  - New/Set/Get-AzureRmStorageAccount: zwracane konto magazynu zawiera nowy atrybut EnableHttpsTrafficOnly
* Azure.Storage
  - Uaktualniono bibliotekę klienta usługi Azure Storage do wersji 8.1.1 i bibliotekę przenoszenia danych usługi Azure Storage do wersji 0.5.1
  - Dodano nowe polecenie cmdlet w celu obsługi funkcji przyrostowej kopii obiektu blob
