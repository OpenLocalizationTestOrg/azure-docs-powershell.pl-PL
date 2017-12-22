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
ms.date: 11/14/2017
ms.openlocfilehash: cf58789ba69fd2fc157e37d0b052827b361246e5
ms.sourcegitcommit: c42c7176276ec4e1cc3360a93e6b15d32083bf9f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/14/2017
---
# <a name="release-notes"></a>Informacje o wersji

To jest lista zmian wprowadzonych w programie Azure PowerShell w tym wydaniu.

## <a name="20171208-version-511"></a>2017.12.08, wersja 5.1.1
* AnalysisServices
    - Zmieniono weryfikację zestawu lokalizacji na wyszukiwanie dynamiczne, aby zapewnić obsługę wszystkich chmur.
* Automatyzacja
    - Aktualizacja polecenia Import-AzureRMAutomationRunbook
        - Teraz są obsługiwane elementy runbook programu Python2
* Batch
    - Usunięto usterkę uniemożliwiającą automatyczne wykrywanie grupy zasobów przez operacje na koncie bez grupy zasobów
* Wystąpienia obliczeniowe
    - Polecenie Get-AzureRmComputeResourceSku umożliwia wyświetlanie informacji o strefach.
    - Zaktualizowano polecenie cmdlet Disable-AzureRmVmssDiskEncryption, aby rozwiązać problem https://github.com/Azure/azure-powershell/issues/5038
    - Dodano obsługę parametru -AsJob dla długotrwałych poleceń cmdlet obliczeń. Umożliwia on działanie wybranych poleceń cmdlet w tle i zwrócenie zadania w celu śledzenia i kontrolowania postępu.
        - Dotyczy to m.in. następujących poleceń cmdlet usług Virtual Machines i Virtual Machine Scale Sets: New-, Update-, Set-, Remove-, Start-, Restart-, Stop-
    - Dodano uproszczony zestaw parametrów do polecenia New-AzureRmVM, który umożliwia utworzenie maszyny wirtualnej i wszystkich wymaganych zasobów przy użyciu inteligentnych wartości domyślnych
* ContainerInstance
    - Zastosowano zestaw SDK wystąpienia kontenera platformy Azure (2017-10-01)
        - Obsługa kończenia działania kontenera
        - Obsługa instalacji woluminów plików platformy Azure
        - Obsługa otwierania wielu portów dla publicznego adresu IP
* ContainerRegistry
    - Nowe polecenia cmdlet dotyczące replikacji geograficznej i elementów webhook
        - Get/New/Remove-AzureRmContainerRegistryReplication
        - Get/New/Remove/Test/Update-AzureRmContainerRegistryWebhook
* DataFactories
    - Teraz funkcja szyfrowania poświadczeń działa, gdy dostęp zdalny jest włączony (przez sieć) i wyłączony (maszyna lokalna).
* DataFactoryV2
    - Dodano dwa nowe polecenia cmdlet: Update-AzureRmDataFactoryV2 i Stop-AzureRmDataFactoryV2PipelineRun
* DataLakeAnalytics
    - Dodano parametr o nazwie ScriptParameter do polecenia Submit-AzureRmDataLakeAnalyticsJob
        - Szczegółowe informacje o parametrze ScriptParameter można uzyskać, używając polecenia Get-Help dla polecenia Submit-AzureRmDataLakeAnalyticsJob
    - W przypadku polecenia New-AzureRmDataLakeAnalyticsAccount zmieniono parametr MaxDegreeOfParallelism na parametr MaxAnalyticsUnits
        - Dodano alias parametru MaxAnalyticsUnits: MaxDegreeOfParallelism
    - W przypadku polecenia New-AzureRmDataLakeAnalyticsComputePolicy zmieniono parametr MaxDegreeOfParallelismPerJob na parametr MaxAnalyticsUnitsPerJob
        - Dodano alias parametru MaxAnalyticsUnitsPerJob: MaxDegreeOfParallelismPerJob
    - W przypadku polecenia Set-AzureRmDataLakeAnalyticsAccount zmieniono parametr MaxDegreeOfParallelism na parametr MaxAnalyticsUnits
        - Dodano alias parametru MaxAnalyticsUnits: MaxDegreeOfParallelism
    - W przypadku polecenia Submit-AzureRmDataLakeAnalyticsJob zmieniono parametr DegreeOfParallelism na parametr AnalyticsUnits
        - Dodano alias parametru AnalyticsUnits: DegreeOfParallelism
    - W przypadku polecenia Update-AzureRmDataLakeAnalyticsComputePolicy zmieniono parametr MaxDegreeOfParallelismPerJob na parametr MaxAnalyticsUnitsPerJob
        - Dodano alias parametru MaxAnalyticsUnitsPerJob: MaxDegreeOfParallelismPerJob
* MachineLearningCompute
    - Dodano polecenie Set-AzureRmMlOpCluster
        - Zaktualizowano liczbę agentów klastra lub konfigurację protokołu SSL
    - Właściwości programu Orchestrator są opcjonalne
        - Usługa utworzy jednostkę usługi, jeśli jej nie podano, więc właściwości programu Orchestrator są teraz opcjonalne
* PowerBIEmbedded
    - Dodano obsługę poleceń cmdlet dotyczących pojemności usługi Power BI Embedded
    - Nowe polecenie cmdlet Get-AzureRmPowerBIEmbeddedCapacity — pobiera szczegóły pojemności usługi PowerBI Embedded.
    - Nowe polecenie cmdlet New-AzureRmPowerBIEmbeddedCapacity — tworzy nową pojemność usługi PowerBI Embedded
    - Nowe polecenie cmdlet Remove-AzureRmPowerBIEmbeddedCapacity — usuwa wystąpienie pojemności usługi PowerBI Embedded
    - Nowe polecenie cmdlet Resume-AzureRmPowerBIEmbeddedCapacity — wznawia wystąpienie pojemności usługi PowerBI Embedded
    - Nowe polecenie cmdlet Suspend-AzureRmPowerBIEmbeddedCapacity — wstrzymuje wystąpienie pojemności usługi PowerBI Embedded
    - Nowe polecenie cmdlet Test-AzureRmPowerBIEmbeddedCapacity — sprawdza obecność wystąpienia pojemności usługi PowerBI Embedded
    - Nowe polecenie cmdlet Update-AzureRmPowerBIEmbeddedCapacity — modyfikuje wystąpienie pojemności usługi PowerBI Embedded
* Profil
    - Zaktualizowano element USGovernmentActiveDirectoryEndpoint przy użyciu adresu https://login.microsoftonline.us/
        - Aby uzyskać więcej informacji na temat mapowań punktu końcowego usługi Azure Government, zobacz https://docs.microsoft.com/pl-pl/azure/azure-government/documentation-government-developer-guide#endpoint-mapping
    - Dodano obsługę parametru -AsJob w poleceniach cmdlet, aby umożliwić wykonywanie wybranych poleceń cmdlet w tle i zwrócenie zadania śledzenia i kontrolowania postępu
    - Dodano parametr -AsJob do polecenia cmdlet Get-AzureRmSubscription
* RecoveryServices.Backup
    - Usunięto usterkę — polecenie Get-AzureRmRecoveryServicesBackupItem powinno uwzględniać wielkość liter podczas porównywania za pomocą filtru nazwy kontenera.
    - Usunięto usterkę — element AzureVmItem ma teraz właściwość, która umożliwia pokazanie czasu ostatniej operacji wykonywania kopii zapasowej (LastBackupTime).
* Zasoby
    - Rozwiązano problem, w wyniku którego użycie polecenia Get-AzureRMRoleAssignment powodowało tworzenie przypisań ról niestandardowych bez nazwy definicji roli
        - Użytkownicy mogą teraz korzystać z polecenia Get-AzureRMRoleAssignment z przypisaniami mającymi nazwy definicji roli niezależnie od typu roli
    - Rozwiązano problem, w wyniku którego polecenie Set-AzureRMRoleRoleDefinition zgłaszało błąd (nie znaleziono definicji roli) w przypadku nowego zakresu we właściwości assignablescopes
        - Użytkownicy mogą teraz korzystać z polecenia Set-AzureRMRoleRoleDefinition z zakresami możliwymi do przypisania, w tym nowymi zakresami, niezależnie od położenia zakresu
    - Umożliwiono używanie znaku „/” na końcu zakresu
        - Użytkownicy mogą teraz korzystać z poleceń cmdlet definicji ról i przypisań ról z zakresami kończącymi się znakiem „/” zgodnie z interfejsem API i interfejsem wiersza polecenia
    - Umożliwiono użytkownikom tworzenie przypisań ról za pomocą flagi delegowania
        - Użytkownicy mogą teraz dodawać flagę delegowania do polecenia New-AzureRMRoleAssignment
    - Naprawiono polecenie pobierania przypisania roli w celu uwzględniania parametru zakresu
    - Dodano alias dla elementu ServicePrincipalName w poleceniu cmdlet New-AzureRmRoleAssignment
        - Użytkownicy mogą teraz korzystać z elementu ApplicationId zamiast elementu ServicePrincipalName w przypadku używania polecenia cmdlet New-AzureRmRoleAssignment
* SiteRecovery
    - Dodano ostrzeżenia dotyczące zakończenia obsługi dla wszystkich poleceń cmdlet w tym module w ramach przygotowania do następnej wersji zawierającej istotne zmiany.
        - Więcej informacji na temat migracji poleceń cmdlet z usługi AzureRM można znaleźć w przewodniku dotyczącym istotnych zmian.
* Sql
    - Dodano możliwość zmiany nazwy bazy danych przy użyciu polecenia Set-AzureRmSqlDatabase
    - Rozwiązano problem https://github.com/Azure/azure-powershell/issues/4974
        - Podanie nieprawidłowej wartości AUDIT_CHANGED_GROUP dla poleceń cmdlet inspekcji nie powoduje już zgłoszenia błędu i zostanie to usunięte w następnej wersji.
    - Rozwiązano problem https://github.com/Azure/azure-powershell/issues/5046
        - Parametr AuditAction nie jest już ignorowany w poleceniach cmdlet inspekcji
    - Rozwiązano problem z poleceniami cmdlet inspekcji występujący w przypadku podania wartości „Secondary” dla elementu StorageKeyType
        - W przypadku ustawiania inspekcji obiektów blob zamiast klucza pomocniczego jako wartość „Secondary” parametru StorageKeyType był używany podstawowy klucz konta magazynu.
    - Zmieniono treść komunikatu potwierdzenia z polecenia Set-AzureRmSqlServerTransparentDataEncryptionProtector
* Azure (fronton RedDog)
    - Usunięto wszystkie polecenia cmdlet usługi RemoteApp
* Azure.Storage
    - Uaktualniono bibliotekę klienta usługi Azure Storage do wersji 8.6.0 i bibliotekę przenoszenia danych usługi Azure Storage do wersji 0.6.5

Zmiany od ostatniego wydania: https://github.com/azure/azure-powershell/compare/v5.0.1-November2017...v5.1.1-December2017

## <a name="20171110-version-501"></a>2017.11.10 — wersja 5.0.1
* Rozwiązano problem z ładowaniem zestawu, który powodował, że niektóre polecenia cmdlet powodowały błąd podczas wykonywania w następujących modułach:
    - AzureRM.ApiManagement
    - AzureRM.Backup
    - AzureRM.Batch
    - AzureRM.Compute
    - AzureRM.DataFactories
    - AzureRM.HDInsight
    - AzureRM.KeyVault
    - AzureRM.RecoveryServices
    - AzureRM.RecoveryServices.Backup
    - AzureRM.RecoveryServices.SiteRecovery
    - AzureRM.RedisCache
    - AzureRM.SiteRecovery
    - AzureRM.Sql
    - AzureRM.Storage
    - AzureRM.StreamAnalytics

## <a name="2017118---version-500"></a>2017.11.08 — wersja 5.0.0
* UWAGA: To jest wersja zawierająca przełomowe zmiany. Aby uzyskać pełną listę przełomowych zmian, które zostały wprowadzone, zobacz przewodnik migracji (https://aka.ms/azps-migration-guide).
* Wszystkie polecenia cmdlet w usłudze AzureRM obsługują teraz pomoc online
    - Uruchom polecenie Get-Help z parametrem -Online, aby otworzyć pomoc online w domyślnej przeglądarce internetowej
* AnalysisServices
    * Rozwiązano problem z poleceniem Synchronize-AzureAsInstance, aby umożliwić jego współpracę z nowym interfejsem API REST AsAzure dla celów synchronizacji
* ApiManagement
    * Aby uzyskać informacje na temat przełomowych zmian wprowadzonych w tej wersji usługi ApiManagement, zobacz przewodnik migracji
    * Zaktualizowano polecenie cmdlet Get-AzureRmApiManagementUser, aby rozwiązać problem https://github.com/Azure/azure-powershell/issues/4510
    * Zaktualizowano polecenie cmdlet New-AzureRmApiManagementApi, aby utworzyć interfejs API z pustą ścieżką https://github.com/Azure/azure-powershell/issues/4069
* ApplicationInsights
    * Dodano polecenia umożliwiające pobieranie/tworzenie/usuwanie zasobu usługi Application Insights
        - Get-AzureRmApplicationInsights
        - New-AzureRmApplicationInsights
        - Remove-AzureRmApplicationInsights
    * Dodano polecenia umożliwiające pobieranie/aktualizowanie cen/dziennego limitu zasobu usługi Applicaiton Insights
        - Get-AzureRmApplicationInsights -IncludeDailyCap
        - Set-AzureRmApplicationInsightsPricingPlan
        - Set-AzureRmApplicationInsightsDailyCap
    * Dodano polecenia umożliwiające pobieranie/tworzenie/aktualizowanie/usuwanie ciągłego eksportu zasobu usługi Application Insights
        - Get-AzureRmApplicationInsightsContinuousExport
        - Set-AzureRmApplicationInsightsContinuousExport
        - New-AzureRmApplicationInsightsContinuousExport
        - Remove-AzureRmApplicationInsightsContinuousExport
    * Dodano polecenia umożliwiające pobieranie/tworzenie/usuwanie kluczy interfejsu API zasobu usługi Application Insights
        - Get-AzureRmApplicationInsightsApiKey
        - New-AzureRmApplicationInsightsApiKey
        - Remove-AzureRmApplicationInsightsApiKey
* AzureBatch
    * Dodano nowe parametry do polecenia `New-AzureRmBatchAccount`.
        - `PoolAllocationMode`: Tryb alokacji na potrzeby tworzenia pul w ramach konta usługi Batch. Aby utworzyć konto usługi Batch, które przydziela węzły pul w subskrypcji użytkownika, ustaw tę wartość na `UserSubscription`.
        - `KeyVaultId`: Identyfikator zasobu magazynu kluczy Azure skojarzonego z kontem usługi Batch.
        - `KeyVaultUrl`: Adres URL magazynu kluczy Azure skojarzonego z kontem usługi Batch.
    * Zaktualizowano parametry polecenia `New-AzureBatchTask`.
        - Usunięto przełącznik `RunElevated`. Dodano parametr `UserIdentity` w celu zastąpienia przełącznika `RunElevated`, a równoważne zachowanie można uzyskać, konstruując parametr `PSUserIdentity` w sposób pokazany poniżej:
            - $autoUser = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoUserSpecification -ArgumentList @("Zadanie", "Administrator")
            - $userIdentity = New-Object Microsoft.Azure.Commands.Batch.Models.PSUserIdentity $autoUser
        - Dodano parametr `AuthenticationTokenSettings`. Ten parametr umożliwia żądanie, aby usługa Batch podawała token uwierzytelniania dla zadania po jego uruchomieniu, unikając w ten sposób konieczności przekazywania kluczy konta usługi Batch do zadania w celu wysyłania żądań do usługi Batch.
        - Dodano parametr `ContainerSettings`.
            - Ten parametr pozwala zażądać, aby usługa Batch uruchamiała zadanie wewnątrz kontenera.
        - Dodano parametr `OutputFiles`.
            - Ten parametr umożliwia skonfigurowanie zadania tak, aby po zakończeniu pracy pliki były przekazywane do usługi Azure Storage.
    * Zaktualizowano parametry polecenia `New-AzureBatchPool`.
        - Dodano parametr `UserAccounts`.
            - Ten parametr określa konta użytkowników utworzone na każdym węźle w puli.
        - Dodano parametr `TargetLowPriorityComputeNodes` i zmieniono nazwę parametru `TargetDedicated` na `TargetDedicatedComputeNodes`.
            - Utworzono alias `TargetDedicated` dla parametru `TargetDedicatedComputeNodes`.
        - Dodano parametr `NetworkConfiguration`.
            - Ten parametr umożliwia skonfigurowanie ustawień sieciowych pul.
    * Zaktualizowano parametry polecenia `New-AzureBatchCertificate`.
        - Parametr `Password` nosi teraz nazwę `SecureString`.
    * Zaktualizowano parametry polecenia `New-AzureBatchComputeNodeUser`.
        - Parametr `Password` nosi teraz nazwę `SecureString`.
    * Zaktualizowano parametry polecenia `Set-AzureBatchComputeNodeUser`.
        - Parametr `Password` nosi teraz nazwę `SecureString`.
    * Zmieniono nazwę parametru `Name` na `Path` w poleceniach `Get-AzureBatchNodeFile`, `Get-AzureBatchNodeFileContent` i `Remove-AzureBatchNodeFile`.
        - Utworzono alias `Name` dla parametru `Path`.
    * Zmiany obiektów
        - Aby uzyskać pełną listę, zobacz dziennik zmian usługi Batch
    * Dodano obsługę uwierzytelniania w oparciu o usługę Azure Active Directory.
        - Aby używać uwierzytelniania za pomocą usługi Azure Active Directory, pobierz obiekt `BatchAccountContext` przy użyciu polecenia cmdlet `Get-AzureRmBatchAccount` i podaj tę wartość `BatchAccountContext` dla parametru `-BatchContext` polecenia cmdlet usługi Batch. Uwierzytelnianie za pomocą usługi Azure Active Directory jest obowiązkowe w przypadku kont w trybie `PoolAllocationMode = UserSubscription`.
        - W przypadku istniejących kont lub nowych kont utworzonych przy użyciu trybu `PoolAllocationMode = BatchService` możesz nadal używać uwierzytelniania za pomocą klucza współużytkowanego, pobierając obiekt `BatchAccountContext` za pomocą polecenia cmdlet `Get-AzureRmBatchAccoutKeys`.
* Wystąpienia obliczeniowe
    * Polecenia rozszerzenia Azure Disk Encryption
        - Nowy parametr polecenia „Set-AzureRmVmDiskEncryptionExtension”: „-EncryptFormatAll” szyfruje formaty dysków z danymi
        - Nowe parametry polecenia „Set-AzureRmVmDiskEncryptionExtension”: „-ExtensionPublisherName” i „-ExtensionType” zezwalają na przełączanie na inne wersje rozszerzenia
        - Nowe parametry polecenia „Disable-AzureRmVmDiskEncryption”: „-ExtensionPublisherName” i „-ExtensionType” zezwalają na przełączanie na inne wersje rozszerzenia
        - Nowe parametry polecenia „Get-AzureRmVmDiskEncryptionStatus”: „-ExtensionPublisherName” i „-ExtensionType” zezwalają na przełączanie na inne wersje rozszerzenia
* DataLakeAnalytics
    * Aby uzyskać informacje na temat przełomowych zmian wprowadzonych w tej wersji usługi DataLakeAnalytics, zobacz przewodnik migracji
    * Zmieniono jeden z dwóch typów OutputType polecenia Get-AzureRmDataLakeAnalyticsAccount
        - List\<DataLakeAnalyticsAccount> na List\<PSDataLakeAnalyticsAccountBasic>
        - Właściwości typu PSDataLakeAnalyticsAccountBasic to ściśle określony podzbiór właściwości typu DataLakeAnalyticsAccount
        - Typ DataLakeAnalyticsAccount nie zwraca zawartych w nim właściwości dodatkowych.  W związku z tym ta zmiana ma na celu precyzyjne odzwierciedlenie tej sytuacji. Właściwości dodatkowe wciąż znajdują się w typie PSDataLakeAnalyticsAccountBasic, ale są oznaczone jako Obsolete.
    * Zmieniono jeden z dwóch typów OutputType polecenia Get-AzureRmDataLakeAnalyticsJob
        - List\<JobInformation> na List\<PSJobInformationBasic>
        - Właściwości typu PSJobInformationBasic to ściśle określony podzbiór właściwości typu JobInformation
        - Typ JobInformation nie zwraca zawartych w nim właściwości dodatkowych.  W związku z tym ta zmiana ma na celu precyzyjne odzwierciedlenie tej sytuacji. Właściwości dodatkowe wciąż znajdują się w typie PSJobInformationBasic, ale są oznaczone jako Obsolete.
* DataLakeStore
    * Aby uzyskać informacje na temat przełomowych zmian wprowadzonych w tej wersji usługi DataLakeStore, zobacz przewodnik migracji
    * Zmieniono jeden z dwóch typów OutputType polecenia Get-AzureRmDataLakeStoreAccount
        - List\<PSDataLakeStoreAccount> na List\<PSDataLakeStoreAccountBasic>
        - Właściwości typu PSDataLakeStoreAccountBasic to ściśle określony podzbiór właściwości typu PSDataLakeStoreAccount
        - Typ PSDataLakeStoreAccount nie zwraca zawartych w nim właściwości dodatkowych.  W związku z tym ta zmiana ma na celu precyzyjne odzwierciedlenie tej sytuacji. Właściwości dodatkowe wciąż znajdują się w typie PSDataLakeStoreAccountBasic, ale są oznaczone jako Obsolete.
* Dns
    * Obsługa typów rekordów CAA w usłudze Azure DNS
       - Obsługa wszystkich operacji na typie rekordu CAA
* EventHub
    * Aby uzyskać informacje na temat przełomowych zmian wprowadzonych w tej wersji usługi EventHub, zobacz przewodnik migracji
* Insights
    * Aby uzyskać informacje na temat przełomowych zmian wprowadzonych w tej wersji usługi Insights, zobacz przewodnik migracji
* Sieć
    * Aby uzyskać informacje na temat przełomowych zmian wprowadzonych w tej wersji usługi Network, zobacz przewodnik migracji
    * Dodano polecenie cmdlet umożliwiające wyświetlanie listy dostępnych usługodawców internetowych dla określonego regionu Azure
        - Get-AzureRmNetworkWatcherReachabilityProvidersList
    * Dodano polecenie cmdlet umożliwiające uzyskanie oceny opóźnienia względnego dla usługodawców internetowych z określonej lokalizacji do regionów Azure
        - Get-AzureRmNetworkWatcherReachabilityReport
* Profil
    - Set-AzureRmDefault
        - Użyj tego polecenia cmdlet, aby określić domyślną grupę zasobów.  Dzięki temu parametr -ResourceGroup stanie się opcjonalny dla niektórych poleceń cmdlet, a gdy grupa zasobów nie zostanie określona, będzie używana grupa domyślna
        - ```Set-AzureRmDefault -ResourceGroupName "ExampleResourceGroup"```
        - Jeśli określona grupa zasobów istnieje w subskrypcji, zostanie ona ustawiona jako domyślna.  W przeciwnym razie grupa zasobów zostanie utworzona, a następnie ustawiona jako domyślna.
    - Get-AzureRmDefault
        - Użyj tego polecenia cmdlet, aby uzyskać bieżącą domyślną grupę zasobów (oraz inne wartości domyślne w przyszłości).
        - ```Get-AzureRmDefault -ResourceGroup```
    - Clear-AzureRmDefault
        - Użyj tego polecenia cmdlet, aby usunąć bieżącą domyślną grupę zasobów
        - ```Clear-AzureRmDefault -ResourceGroup```
    - Add-AzureRmEnvironment i Set-AzureRmEnvironment
        - Dodaj parametr BatchAudience umożliwiający określenie odbiorców usługi Azure Batch Active Directory, którzy będą używani podczas uzyskiwania tokenów uwierzytelniania dla usługi Batch.
* RecoveryServices.Backup
    * Dodano polecenia cmdlet umożliwiające wykonywanie błyskawicznego odzyskiwania plików.
        - Get-AzureRmRecoveryServicesBackupRPMountScript
        - Disable-AzureRmRecoveryServicesBackupRPMountScript
    * Zaktualizowano wersję zestawu SDK RecoveryServices.Backup do najnowszej wersji
    * Zaktualizowano testy obciążenia maszyny wirtualnej platformy Azure VM, aby wszystkie konfiguracje niezbędne do uruchamiania testów były przeprowadzane przez same testy.
    * Rozwiązano problem https://github.com/Azure/azure-powershell/issues/3164
* RecoveryServices.SiteRecovery
    * Zmiany dotyczące operacji między usługami ASR VMware i Azure Site Recovery (polecenia cmdlet obsługują obecnie operacje Enterprise-Enterprise, Enterprise-Azure, HyperV-Azure)
        - New-AzureRmRecoveryServicesAsrPolicy
        - New-AzureRmRecoveryServicesAsrProtectedItem
        - Update-AzureRmRecoveryServicesAsrPolicy
        - Update-AzureRmRecoveryServicesAsrProtectionDirection
    * Dodano obsługę magazynu opartego na usłudze AAD
    * Dodano polecenia cmdlet umożliwiające zarządzanie zasobami VCenter
        - Get-AzureRmRecoveryServicesAsrVCenter
        - New-AzureRmRecoveryServicesAsrVCenter
        - Remove-AzureRmRecoveryServicesAsrVCenter
        - Update-AzureRmRecoveryServicesAsrVCenter
    * Dodano inne polecenia cmdlet
        - Get-AzureRmRecoveryServicesAsrAlertSetting
        - Get-AzureRmRecoveryServicesAsrEvent
        - New-AzureRmRecoveryServicesAsrProtectableItem
        - Set-AzureRmRecoveryServicesAsrAlertSetting
        - Start-AzureRmRecoveryServicesAsrResynchronizeReplicationJob
        - Start-AzureRmRecoveryServicesAsrSwitchProcessServerJob
        - Start-AzureRmRecoveryServicesAsrTestFailoverCleanupJob
        - Update-AzureRmRecoveryServicesAsrMobilityService
* ServiceBus
    - Aby uzyskać informacje na temat przełomowych zmian wprowadzonych w tej wersji usługi ServiceBus, zobacz przewodnik migracji
* Sql
    * Dodanie obsługi listy i anulowanie operacji asynchronicznej updateslo na bazie danych
        - Aktualizacja istniejącego polecenia cmdlet Get-AzureRmSqlDatabaseActivity tak, aby zwracało stan operacji updateslo bazy danych.
        - Dodanie nowego polecenia cmdlet Stop-AzureRmSqlDatabaseActivity umożliwiającego anulowanie operacji asynchronicznej updateslo na bazie danych.
    * Dodanie obsługi nadmiarowości strefy dla baz danych i pul elastycznych
        - Dodanie parametru przełącznika ZoneRedundant do polecenia New-AzureRmSqlDatabase
        - Dodanie parametru przełącznika ZoneRedundant do polecenia Set-AzureRmSqlDatabase
        - Dodanie parametru przełącznika ZoneRedundant do polecenia New-AzureRmSqlElasticPool
        - Dodanie parametru przełącznika ZoneRedundant do polecenia Set-AzureRmSqlElasticPool
    * Dodanie obsługi aliasów DNS serwera
        - Dodanie polecenia cmdlet Get-AzureRmSqlServerDnsAlias pobierającego aliasy DNS według serwerów oraz nazwę aliasu lub listę aliasów DNS serwera dla serwera SQL Azure.
        - Dodanie polecenia cmdlet New-AzureRmSqlServerDnsAlias tworzącego nowy alias DNS serwera dla danego serwera SQL Azure
        - Dodanie polecenia cmdlet Set-AzurermSqlServerDnsAlias umożliwiającego zaktualizowanie serwera SQL Azure, na który wskazuje alias DNS serwera
        - Dodanie polecenia cmdlet Remove-AzureRmSqlServerDnsAlias usuwającego alias DNS serwera dla danego serwera SQL Azure
* Azure.Storage
    * Uaktualniono bibliotekę klienta usługi Azure Storage do wersji 8.5.0 i bibliotekę przenoszenia danych usługi Azure Storage do wersji 0.6.3
    * Dodano funkcję obsługi migawki udziału plików
        - Dodano parametr „SnapshotTime” do polecenia Get-AzureStorageShare
        - Dodano parametr „IncludeAllSnapshot” do polecenia Remove-AzureStorageShare