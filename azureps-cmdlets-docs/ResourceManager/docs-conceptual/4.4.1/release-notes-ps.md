Instalator programu Azure PowerShell 4.3.1: [link](https://github.com/Azure/azure-powershell/releases/download/v4.3.1-August2017/azure-powershell.4.3.1.msi)

Moduł galerii dla poleceń cmdlet ARM: [link](https://www.powershellgallery.com/packages/AzureRM/4.3.1)

Moduł galerii dla starszych poleceń cmdlet do zarządzania usługami (RDFE): [link](https://www.powershellgallery.com/packages/Azure/4.3.1)

## <a name="changes-in-431"></a>Zmiany w wersji 4.3.1

- Rozwiązano problem polegający na tym, że określone zestawy nie były podpisane, co powodowało błąd `could not load file or assembly` przy importowaniu modułów

## <a name="changes-in-430"></a>Zmiany w wersji 4.3.0

* AnalysisServices
    * Usunięto usterkę w poleceniu Set-AzureRmAnalysisServciesServer
        - Jeśli administrator nie został podany, administrator zostanie usunięty.
    * Dodano parametr BackupBlobContainerUri w poleceniach New-AzureRmAnalysisServicesServer i Set-AzureRmAnalysisServicesServer
        - Należy go włączyć, aby ustawić/wyłączyć kontener obiektów blob kopii zapasowej na potrzeby kopii zapasowej i przywracania serwera usług Azure Analysis Services
    * Zaktualizowano wyszukiwanie jednostek SKU w poleceniach New-AzureRmAnalysisServicesServer i Set-AzureRmAnalysisServicesServer
        - Zamieniono zakodowaną jednostkę SKU na wyszukiwanie dynamiczne.
    * Polecenie Add-AzureAnalysisServicesAccount obsługuje logowanie za pomocą jednostki usługi
* Automatyzacja
    * Wprowadzono zmiany w poleceniach cmdlet AutomationDSC* w celu pobierania więcej niż 100 rekordów
    * Rozwiązano problem polegający na tym, że strumienie pełne przestawały działać po wywołaniu niektórych poleceń cmdlet usługi Automation (na przykład Get-AzureRmAutomationVariable, Get-AzureRmAutomationJob).
    * Dodano obsługę wersji kompilacji konfiguracji węzła w poleceniach StartAzureAutomationDscCompilationJob i ImportAzureAutomationDscNodeConfiguration.
    * Poprawki usterek dotyczące istniejących problemów — rozwiązano problem z aliasem (#3775), aliasem runOn oraz obsługą obiektów HybridWorker.
* Wystąpienia obliczeniowe
    * Set-AzureRmVMAEMExtension: dodano obsługę nowych rozmiarów dysków w warstwie Premium
    * Set-AzureRmVMAEMExtension: dodano obsługę serii M
    * Dodano parametr ForceUpdateTag do polecenia Add-AzureRmVmssExtension
    * Dodano parametr Primary do polecenia New-AzureRmVmssIpConfig
    * Dodano parametr EnableAcceleratedNetworking do polecenia Add-AzureRmVmssNetworkInterfaceConfig
    * Dodano parametr InstanceId do polecenia Set-AzureRmVmss
    * Udostępniono parametr MaintenanceRedeployStatus w danych wyjściowych polecenia Get-AzureRmVM -Status
    * Udostępniono parametry Restriction i Capability w formacie tabeli polecenia Get-AzureRmComputeResourceSku
* DataLakeStore
    * Rozwiązanie problemu: https://github.com/Azure/azure-powershell/issues/4323
* EventHub
    * Dodano właściwość ResourceGroup do parametru NamespaceAttributes
        - Do właściwości „ResourceGroup” jest pobierana nazwa grupy zasobów, w której znajduje się przestrzeń nazw
    * Zaktualizowano polecenia cmdlet przez dodanie nowych parametrów i aliasów parametrów
        - Zaktualizowano poniższe polecenia cmdlet przez dodanie zestawów parametrów dla przestrzeni nazw i centrów zdarzeń na potrzeby działania reguł autoryzacji
        - New-AzureRmEventHubAuthorizationRule
            + Dodaje nową regułę autoryzacji do istniejącej przestrzeni nazw lub centrum zdarzeń.
        - Get-AzureRmEventHubAuthorizationRule
            + Pobiera regułę autoryzacji albo listę reguł autoryzacji dla istniejącej przestrzeni nazw lub centrum zdarzeń.
        - Set-AzureRmEventHubAuthorizationRule
            + Aktualizuje właściwości istniejącej reguły autoryzacji dla przestrzeni nazw centrum zdarzeń.
        - Remove-AzureRmEventHubAuthorizationRule
            + Usuwa istniejącą regułę autoryzacji istniejącej przestrzeni nazw lub centrum zdarzeń.
        - New-AzureRmEventHubKey
            + Generuje nowy klucz podstawowy/pomocniczy dla reguły autoryzacji istniejącej przestrzeni nazw lub centrum zdarzeń.
        - Get-AzureRmEventHubKey
            + Pobiera klucz podstawowy/pomocniczy dla reguły autoryzacji istniejącej przestrzeni nazw lub centrum zdarzeń.
* Sieć
    * New-AzureRmExpressRouteCircuitPeeringConfig: dodano obsługę protokołu IPv6. Dodano nowy parametr opcjonalny
        - PeerAddressType
    * Set-AzureRmExpressRouteCircuitPeeringConfig: dodano obsługę protokołu IPv6. Dodano nowy parametr opcjonalny
        - PeerAddressType
    * Remove-AzureRmExpressRouteCircuitPeeringConfig: dodano obsługę protokołu IPv6. Dodano nowy parametr opcjonalny
        - PeerAddressType
    * Oznaczono parametr -ProbeEnabled jako przestarzały
        - Add-AzureRmApplicationGatewayBackendHttpSettings
        - New-AzureRmApplicationGatewayBackendHttpSettings
        - Set-AzureRmApplicationGatewayBackendHttpSettings
* Profil
    * Zbieranie danych zostało domyślnie włączone. Firma Microsoft zbiera dane użycia, aby ulepszyć środowisko użytkownika. Dane są anonimowe i nie zawierają wartości argumentów wiersza polecenia.
        - Do wyłączania tej funkcji służy polecenie cmdlet Disable-AzureRmDataCollection
        - Do włączania tej funkcji służy polecenie cmdlet Enable-AzureRmDataCollection
* Zasoby
    * Dodano obsługę weryfikacji zakresów dla następujących poleceń cmdlet definiowania ról i przypisywania ról przed wysłaniem żądania do usługi ARM
        - Get-AzureRMRoleAssignment
        - New-AzureRMRoleAssignment
        - Remove-AzureRMRoleAssignment
        - Get-AzureRMRoleDefinition
        - New-AzureRMRoleDefinition
        - Remove-AzureRMRoleDefinition
        - Set-AzureRMRoleDefinition
* ServiceBus
    * Dodano poniższe nowe polecenia cmdlet dotyczące reguł autoryzacji dla przestrzeni nazw, kolejki i tematu. Wykonywane są operacje reguł autoryzacji zgodnie z zestawem parametrów.
     - New-AzureRmServiceBusAuthorizationRule
       - Dodaje nową regułę autoryzacji do istniejącej przestrzeni nazw, kolejki lub tematu magistrali usług.
     - Get-AzureRmServiceBusAuthorizationRule
       - Pobiera regułę autoryzacji albo listę reguł autoryzacji dla istniejącej przestrzeni nazw, kolejki lub tematu magistrali usług.
     - Set-AzureRmServiceBusAuthorizationRule
       - Aktualizuje właściwości istniejącej reguły autoryzacji dla przestrzeni nazw, kolejki lub tematu magistrali usług.
     - New-AzureRmServiceBusKey
       - Generuje nowy klucz podstawowy/pomocniczy dla reguły autoryzacji istniejącej przestrzeni nazw, kolejki lub tematu magistrali usług.
     - Get-AzureRmServiceBusKey
       - Pobiera klucz podstawowy/pomocniczy dla reguły autoryzacji istniejącej przestrzeni nazw, kolejki lub tematu magistrali usług.
     - Remove-AzureRmServiceBusNamespaceAuthorizationRule
       - Usuwa istniejącą regułę autoryzacji dla przestrzeni nazw, kolejki lub tematu magistrali usług.
    * Dodano właściwość grupy zasobów do atrybutów obszaru nazw
* Sql
    * Zaktualizowano polecenie Set-AzureRmSqlServerTransparentDataEncryptionProtector w celu wyświetlania ostrzeżenia i wymagania potwierdzenia, jeśli jako typ funkcji ochrony szyfrowania zostanie ustawiona wartość AzureKeyVault
    * Dodano nowe/zaktualizowane polecenia cmdlet dla ustawień inspekcji
        - Dodano polecenie cmdlet Get-AzureRmSqlDatabaseAuditing, które pobiera ustawienia inspekcji bazy danych Azure SQL.
        - Dodano polecenie cmdlet Get-AzureRmSqlServerAuditing, które pobiera ustawienia inspekcji serwera Azure SQL.
        - Dodano polecenie cmdlet Set-AzureRmSqlDatabaseAuditing, które zmienia ustawienia inspekcji bazy danych Azure SQL.
        - Dodano polecenie cmdlet Set-AzureRmSqlServerAuditing, które zmienia ustawienia inspekcji serwera Azure SQL.
    * Wycofano istniejące polecenia cmdlet zasad inspekcji
        - Wycofano polecenie Get-AzureRmSqlDatabaseAuditingPolicy
        - Wycofano polecenie Get-AzureRmSqlServerAuditingPolicy
        - Wycofano polecenie Set-AzureRmSqlDatabaseAuditingPolicy
        - Wycofano polecenie Set-AzureRmSqlServerAuditingPolicy
        - Wycofano polecenie Use-AzureRmSqlServerAuditingPolicy
        - Wycofano polecenie Remove-AzureRmSqlDatabaseAuditing
        - Wycofano polecenie Remove-AzureRmSqlServerAuditing
    * Podczas analizowania plików schematu dla polecenia Update-AzureRmSqlSyncGroup jest teraz uwzględniana wielkość liter.
* Magazyn
    * Dodano obsługę reguł sieci do poleceń cmdlet konta magazynu trybu zasobu
        - New-AzureRmStorageAccount
        - Set-AzureRmStorageAccount
        - Get-AzureRmStorageAccountNetworkRuleSet
        - Update-AzureRmStorageAccountNetworkRuleSet
        - Add-AzureRmStorageAccountNetworkRule
        - Remove-AzureRmStorageAccountNetworkRule

Wyświetl [zmiany od ostatniego wydania](https://github.com/Azure/azure-powershell/compare/v4.2.1-July2017...v4.3.1-August2017)
