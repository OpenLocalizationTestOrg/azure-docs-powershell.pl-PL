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
# <a name="install-and-configure-azure-powershell-on-macos-and-linux"></a><span data-ttu-id="87121-103">Instalowanie i konfigurowanie programu Azure PowerShell w systemach macOS i Linux</span><span class="sxs-lookup"><span data-stu-id="87121-103">Install and configure Azure PowerShell on macOS and Linux</span></span>

<span data-ttu-id="87121-104">Teraz jest możliwa instalacja programów PowerShell 6 (beta) i Azure PowerShell na platformach innych niż Windows.</span><span class="sxs-lookup"><span data-stu-id="87121-104">It is now possible to install PowerShell 6 (beta) and Azure PowerShell on non-Windows platforms.</span></span>
<span data-ttu-id="87121-105">Proces instalowania programu Azure PowerShell w systemach macOS i Linux nie różni się zbytnio od instalowania w systemie Windows, należy jednak najpierw zainstalować program PowerShell 6 (beta).</span><span class="sxs-lookup"><span data-stu-id="87121-105">The process of installing Azure PowerShell on macOS and Linux is not that different from Windows, however, you must first install PowerShell 6 (beta).</span></span>

> [!NOTE]

> <span data-ttu-id="87121-106">W tej chwili oba programy, PowerShell 6 (beta) i Azure PowerShell for .NET Core, są wciąż w wersji beta.</span><span class="sxs-lookup"><span data-stu-id="87121-106">At this time, both PowerShell 6 (beta) and Azure PowerShell for .NET Core are still in beta.</span></span>
> <span data-ttu-id="87121-107">Wsparcie dla tych produktów jest ograniczone.</span><span class="sxs-lookup"><span data-stu-id="87121-107">Support for these products is limited.</span></span> <span data-ttu-id="87121-108">Jeśli napotkasz problemy lub odkryjesz usterkę, zarejestruj problemy w witrynie GitHub.</span><span class="sxs-lookup"><span data-stu-id="87121-108">If you have problems or discover bugs, please file Issues in GitHub.</span></span>
>
> * [<span data-ttu-id="87121-109">Problemy z programem PowerShell 6 (beta)</span><span class="sxs-lookup"><span data-stu-id="87121-109">Issues for PowerShell 6 (beta)</span></span>](https://github.com/PowerShell/PowerShell/issues)
> * [<span data-ttu-id="87121-110">Problemy z programem Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="87121-110">Issues for Azure PowerShell</span></span>](https://github.com/azure/azure-docs-powershell/issues)

## <a name="step-1-install-powershell-6-beta"></a><span data-ttu-id="87121-111">Step 1. Instalowanie programu PowerShell 6 (beta)</span><span class="sxs-lookup"><span data-stu-id="87121-111">Step 1: Install PowerShell 6 (beta)</span></span>

<span data-ttu-id="87121-112">Proces instalowania programu PowerShell 6 (beta) różni się zależnie od docelowego systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="87121-112">The process of installing PowerShell 6 (beta) on varies depending on the target operating system.</span></span>
<span data-ttu-id="87121-113">Chociaż istnieje możliwość zainstalowania programu PowerShell 6 (beta) w systemie Windows, ten artykuł koncentruje się na systemach macOS i Linux.</span><span class="sxs-lookup"><span data-stu-id="87121-113">While it is possible to install PowerShell 6 (beta) on Windows, this article focuses on macOS and Linux.</span></span> <span data-ttu-id="87121-114">Jeśli chcesz korzystać z programu Azure PowerShell w systemie Windows, zobacz artykuł poświęcony [instalacji](./install-azurerm-ps.md) w systemie Windows.</span><span class="sxs-lookup"><span data-stu-id="87121-114">If you want to use Azure PowerShell on Windows, see the [install](./install-azurerm-ps.md) article for Windows.</span></span>

<span data-ttu-id="87121-115">Aby zainstalować program **PowerShell 6** (beta) w systemie Linux lub macOS, konieczne jest:</span><span class="sxs-lookup"><span data-stu-id="87121-115">To install **PowerShell 6** (beta) on Linux or macOS, you need to:</span></span>

1. <span data-ttu-id="87121-116">Uzyskanie programu PowerShell dla konkretnego systemu operacyjnego i jego wersji z witryny [GitHub](https://github.com/powershell/powershell#get-powershell)</span><span class="sxs-lookup"><span data-stu-id="87121-116">Get PowerShell for the specific OS and version, from [GitHub](https://github.com/powershell/powershell#get-powershell)</span></span>
2. <span data-ttu-id="87121-117">Wykonanie instrukcji instalacji</span><span class="sxs-lookup"><span data-stu-id="87121-117">Follow the installation instructions</span></span>
   - [<span data-ttu-id="87121-118">Linux</span><span class="sxs-lookup"><span data-stu-id="87121-118">Linux</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md)
   - [<span data-ttu-id="87121-119">macOS</span><span class="sxs-lookup"><span data-stu-id="87121-119">macOS</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#macos-1012)

## <a name="step-2-install-azure-powershell-for-net-core"></a><span data-ttu-id="87121-120">Krok 2. Instalowanie programu Azure PowerShell dla platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="87121-120">Step 2: Install Azure PowerShell for .NET Core</span></span>

<span data-ttu-id="87121-121">Program PowerShell 6 (beta) jest dostarczany z już zainstalowanym modułem PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="87121-121">PowerShell 6 (beta) comes with the PowerShellGet module already installed.</span></span> <span data-ttu-id="87121-122">Ułatwia to instalację modułów opublikowanych w galerii programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="87121-122">This makes it easy to install any module that is published to the PowerShell Gallery.</span></span> <span data-ttu-id="87121-123">Aby zainstalować program Azure PowerShell, otwórz nową sesję programu PowerShell i uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="87121-123">To install Azure PowerShell, open a new PowerShell session and run the following command:</span></span>

```powershell
Install-Module AzureRM.NetCore
```

## <a name="step-3-load-the-azurermnetcore-module"></a><span data-ttu-id="87121-124">Krok 3. Ładowanie modułu AzureRM.Netcore</span><span class="sxs-lookup"><span data-stu-id="87121-124">Step 3: Load the AzureRM.Netcore module</span></span>

<span data-ttu-id="87121-125">Gdy moduł jest zainstalowany, musisz załadować moduł do swojej sesji programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="87121-125">Once the module is installed, you need to load the module into your PowerShell session.</span></span> <span data-ttu-id="87121-126">Moduły są w następujący sposób ładowane przy użyciu polecenia cmdlet `Import-Module`:</span><span class="sxs-lookup"><span data-stu-id="87121-126">Modules are loaded using the `Import-Module` cmdlet, as follows:</span></span>

```powershell
Import-Module AzureRM.Netcore
Import-Module AzureRM.Profile.Netcore
```

<span data-ttu-id="87121-127">Po zakończeniu importowania można przetestować nowo zainstalowany moduł, próbując zalogować się do platformy Azure przy użyciu następującego polecenia:</span><span class="sxs-lookup"><span data-stu-id="87121-127">After the import completes, you can test your newly installed and module by attempting to sign into Azure using the following command:</span></span>

```powershell
Login-AzureRMAccount
```

<span data-ttu-id="87121-128">Powyższe polecenie powinno poprosić o przejście na stronę `https://aka.ms/devicelogin` i wprowadzenie udostępnionego kodu.</span><span class="sxs-lookup"><span data-stu-id="87121-128">The above command should prompt you to go to `https://aka.ms/devicelogin` and enter the provided code.</span></span>

## <a name="available-cmdlets"></a><span data-ttu-id="87121-129">Dostępne polecenia cmdlet</span><span class="sxs-lookup"><span data-stu-id="87121-129">Available cmdlets</span></span>

<span data-ttu-id="87121-130">Moduły programu Azure PowerShell dla platformy .NET Standard są ciągle w fazie opracowywania.</span><span class="sxs-lookup"><span data-stu-id="87121-130">The Azure PowerShell modules for .NET Standard are still in development.</span></span> <span data-ttu-id="87121-131">Nie oferują one pełnego zestawu poleceń cmdlet dostępnych w modułach w wersji dla systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="87121-131">These modules do not provide the full set of cmdlets that are available for the Windows version of the modules.</span></span> <span data-ttu-id="87121-132">Następujące funkcje są implementowane w modułach AzureRM.Netcore:</span><span class="sxs-lookup"><span data-stu-id="87121-132">The following functions are implemented in AzureRM.Netcore modules:</span></span>

* <span data-ttu-id="87121-133">Zarządzanie kontami</span><span class="sxs-lookup"><span data-stu-id="87121-133">Account management</span></span>
  - <span data-ttu-id="87121-134">Logowanie się przy użyciu konta Microsoft, konta organizacji lub jednostki usługi za pośrednictwem usługi Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="87121-134">Login with Microsoft account, Organizational account, or Service Principal through Microsoft Azure Active Directory</span></span>
  - <span data-ttu-id="87121-135">Zapisywanie poświadczeń na dysku poleceniem Save-AzureRmContext i ładowanie zapisanych poświadczeń poleceniem Import-AzureRmContext</span><span class="sxs-lookup"><span data-stu-id="87121-135">Save Credentials to disk with Save-AzureRmContext and load saved credentials using Import-AzureRmContext</span></span>
* <span data-ttu-id="87121-136">Środowisko</span><span class="sxs-lookup"><span data-stu-id="87121-136">Environment</span></span>
  - <span data-ttu-id="87121-137">Pobieranie różnych gotowych środowisk platformy Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="87121-137">Get the different out-of-box Microsoft Azure environments</span></span>
  - <span data-ttu-id="87121-138">Dodawanie/ustawianie/usuwanie dostosowanych środowisk (takich jak środowiska Azure Stack lub Windows Azure Pack)</span><span class="sxs-lookup"><span data-stu-id="87121-138">Add/Set/Remove customized environments (like your Azure Stack or Windows Azure Pack environments)</span></span>
* <span data-ttu-id="87121-139">Polecenia cmdlet płaszczyzny zarządzania dla usług platformy Azure korzystających z interfejsów menedżera zasobów i zarządzania usługami.</span><span class="sxs-lookup"><span data-stu-id="87121-139">Management plane cmdlets for Azure services using Resource Manager and Service Management interfaces.</span></span>
  - <span data-ttu-id="87121-140">Maszyna wirtualna</span><span class="sxs-lookup"><span data-stu-id="87121-140">Virtual Machine</span></span>
  - <span data-ttu-id="87121-141">App Service (Websites)</span><span class="sxs-lookup"><span data-stu-id="87121-141">App Service (Websites)</span></span>
  - <span data-ttu-id="87121-142">SQL Database</span><span class="sxs-lookup"><span data-stu-id="87121-142">SQL Database</span></span>
  - <span data-ttu-id="87121-143">Magazyn</span><span class="sxs-lookup"><span data-stu-id="87121-143">Storage</span></span>
  - <span data-ttu-id="87121-144">Sieć</span><span class="sxs-lookup"><span data-stu-id="87121-144">Network</span></span>

## <a name="next-steps"></a><span data-ttu-id="87121-145">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="87121-145">Next Steps</span></span>

<span data-ttu-id="87121-146">Aby uzyskać więcej informacji o korzystaniu z programu Azure PowerShell, zobacz artykuł [Rozpoczynanie pracy z programem Azure PowerShell](get-started-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="87121-146">For more information about using Azure PowerShell, see the [Get started with Azure PowerShell](get-started-azureps.md) article.</span></span>
