---
title: Instalowanie i konfigurowanie programu Azure PowerShell w systemach macOS i Linux | Microsoft Docs
description: "Jak zainstalować i skonfigurować program Azure PowerShell do pierwszego użycia w systemach macOS i Linux."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/06/2017
ms.openlocfilehash: 2357bb5d71c221a782a297c41e7a6d08cd3f2952
ms.sourcegitcommit: 4ebdeea3c472d94c1aedb10b9d85bf2e76826e83
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/06/2018
---
# <a name="install-and-configure-azure-powershell-on-macos-and-linux"></a>Instalowanie i konfigurowanie programu Azure PowerShell w systemach macOS i Linux

Teraz jest możliwa instalacja programów PowerShell 6 (beta) i Azure PowerShell na platformach innych niż Windows.
Proces instalowania programu Azure PowerShell w systemach macOS i Linux nie różni się zbytnio od instalowania w systemie Windows, należy jednak najpierw zainstalować program PowerShell 6 (beta).

> [!NOTE]

> W tej chwili oba programy, PowerShell 6 (beta) i Azure PowerShell for .NET Core, są wciąż w wersji beta.
> Wsparcie dla tych produktów jest ograniczone. Jeśli napotkasz problemy lub odkryjesz usterkę, zarejestruj problemy w witrynie GitHub.
>
> * [Problemy z programem PowerShell 6 (beta)](https://github.com/PowerShell/PowerShell/issues)
> * [Problemy z programem Azure PowerShell](https://github.com/azure/azure-docs-powershell/issues)

## <a name="step-1-install-powershell-6-beta"></a>Step 1. Instalowanie programu PowerShell 6 (beta)

Proces instalowania programu PowerShell 6 (beta) różni się zależnie od docelowego systemu operacyjnego.
Chociaż istnieje możliwość zainstalowania programu PowerShell 6 (beta) w systemie Windows, ten artykuł koncentruje się na systemach macOS i Linux. Jeśli chcesz korzystać z programu Azure PowerShell w systemie Windows, zobacz artykuł poświęcony [instalacji](./install-azurerm-ps.md) w systemie Windows.

Aby zainstalować program **PowerShell 6** (beta) w systemie Linux lub macOS, konieczne jest:

1. Uzyskanie programu PowerShell dla konkretnego systemu operacyjnego i jego wersji z witryny [GitHub](https://github.com/powershell/powershell#get-powershell)
2. Wykonanie instrukcji instalacji
   - [Linux](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md)
   - [macOS](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#macos-1012)

## <a name="step-2-install-azure-powershell-for-net-core"></a>Krok 2. Instalowanie programu Azure PowerShell dla platformy .NET Core

Program PowerShell 6 (beta) jest dostarczany z już zainstalowanym modułem PowerShellGet. Ułatwia to instalację modułów opublikowanych w galerii programu PowerShell. Aby zainstalować program Azure PowerShell, otwórz nową sesję programu PowerShell i uruchom następujące polecenie:

```powershell
Install-Module AzureRM.NetCore
```

## <a name="step-3-load-the-azurermnetcore-module"></a>Krok 3. Ładowanie modułu AzureRM.Netcore

Gdy moduł jest zainstalowany, musisz załadować moduł do swojej sesji programu PowerShell. Moduły są w następujący sposób ładowane przy użyciu polecenia cmdlet `Import-Module`:

```powershell
Import-Module AzureRM.Netcore
Import-Module AzureRM.Profile.Netcore
```

Po zakończeniu importowania można przetestować nowo zainstalowany moduł, próbując zalogować się do platformy Azure przy użyciu następującego polecenia:

```powershell
Login-AzureRMAccount
```

Powyższe polecenie powinno poprosić o przejście na stronę `https://aka.ms/devicelogin` i wprowadzenie udostępnionego kodu.

## <a name="available-cmdlets"></a>Dostępne polecenia cmdlet

Moduły programu Azure PowerShell dla platformy .NET Standard są ciągle w fazie opracowywania. Nie oferują one pełnego zestawu poleceń cmdlet dostępnych w modułach w wersji dla systemu Windows. Następujące funkcje są implementowane w modułach AzureRM.Netcore:

* Zarządzanie kontami
  - Logowanie się przy użyciu konta Microsoft, konta organizacji lub jednostki usługi za pośrednictwem usługi Microsoft Azure Active Directory
  - Zapisywanie poświadczeń na dysku poleceniem Save-AzureRmContext i ładowanie zapisanych poświadczeń poleceniem Import-AzureRmContext
* Środowisko
  - Pobieranie różnych gotowych środowisk platformy Microsoft Azure
  - Dodawanie/ustawianie/usuwanie dostosowanych środowisk (takich jak środowiska Azure Stack lub Windows Azure Pack)
* Polecenia cmdlet płaszczyzny zarządzania dla usług platformy Azure korzystających z interfejsów menedżera zasobów i zarządzania usługami.
  - Maszyna wirtualna
  - App Service (Websites)
  - SQL Database
  - Magazyn
  - Sieć

## <a name="next-steps"></a>Następne kroki

Aby uzyskać więcej informacji o korzystaniu z programu Azure PowerShell, zobacz artykuł [Rozpoczynanie pracy z programem Azure PowerShell](get-started-azureps.md).
