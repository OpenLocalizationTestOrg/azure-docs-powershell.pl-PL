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
ms.openlocfilehash: 97a23180a1fc65d96fdc9dbdffcbe3501a4c4c2a
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2017
---
# <a name="release-notes"></a>Informacje o wersji

To jest lista zmian wprowadzonych w programie Azure PowerShell w tym wydaniu.

## <a name="version-400"></a>Wersja 4.0.0

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
