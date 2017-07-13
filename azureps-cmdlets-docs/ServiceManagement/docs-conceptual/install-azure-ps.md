---
title: "<span data-ttu-id=\"d453f-101\">Instalowanie i konfigurowanie modułu zarządzania usługami programu Azure PowerShell | Microsoft Docs</span><span class=\"sxs-lookup\"><span data-stu-id=\"d453f-101\">Install and configure the Azure PowerShell Service Management module | Microsoft Docs</span></span>"
description: "<span data-ttu-id=\"d453f-102\">Jak zainstalować i skonfigurować program Azure PowerShell do pierwszego użycia.</span><span class=\"sxs-lookup\"><span data-stu-id=\"d453f-102\">How to install and configure Azure PowerShell for first time use.</span></span>"
services: azure
author: sdwheeler
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/06/2017
ms.openlocfilehash: c51c727c1cb022eca59f819c7f24d8e058c677da
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="d453f-103">Instalowanie modułu zarządzania usługami programu Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="d453f-103">Installing the Azure PowerShell Service Management module</span></span>
<a id="installing-the-azure-powershell-service-management-module" class="xliff"></a>

<span data-ttu-id="d453f-104">Instalowanie programu Azure PowerShell z [Galerii programu PowerShell](https://www.powershellgallery.com/) jest preferowaną metodą instalacji.</span><span class="sxs-lookup"><span data-stu-id="d453f-104">Installing Azure PowerShell from the [PowerShell Gallery](https://www.powershellgallery.com/) is the preferred method of installation.</span></span>

## <span data-ttu-id="d453f-105">Krok 1. Zainstaluj moduł PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="d453f-105">Step 1: Install PowerShellGet</span></span>
<a id="step-1-install-powershellget" class="xliff"></a>

<span data-ttu-id="d453f-106">Instalowanie elementów z Galerii programu PowerShell wymaga modułu PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="d453f-106">Installing items from the PowerShell Gallery requires the PowerShellGet module.</span></span> <span data-ttu-id="d453f-107">Upewnij się, że masz odpowiednią wersję modułu PowerShellGet oraz spełnione inne wymagania systemowe.</span><span class="sxs-lookup"><span data-stu-id="d453f-107">Make sure you have the appropriate version of PowerShellGet and other system requirements.</span></span> <span data-ttu-id="d453f-108">Uruchom następujące polecenie, aby sprawdzić, czy w Twoim systemie został zainstalowany moduł PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="d453f-108">Run the following command to see if you have PowerShellGet installed on your system.</span></span>

```powershell
Get-Module PowerShellGet -list | Select-Object Name,Version,Path
```

<span data-ttu-id="d453f-109">Powinny zostać wyświetlone dane wyjściowe podobne do poniższych:</span><span class="sxs-lookup"><span data-stu-id="d453f-109">You should see something similar to the following output:</span></span>

```
Name          Version Path
----          ------- ----
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

<span data-ttu-id="d453f-110">Jeśli nie masz zainstalowanego modułu PowerShellGet, zobacz sekcję [Jak uzyskać moduł PowerShellGet](install-azurerm-ps.md#how-to-get-powershellget).</span><span class="sxs-lookup"><span data-stu-id="d453f-110">If you do not have PowerShellGet installed, see the [How to get PowerShellGet](install-azurerm-ps.md#how-to-get-powershellget).</span></span>

## <span data-ttu-id="d453f-111">Krok 2. Zainstaluj program Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="d453f-111">Step 2: Install Azure PowerShell</span></span>
<a id="step-2-install-azure-powershell" class="xliff"></a>

<span data-ttu-id="d453f-112">Uruchom następujące polecenie z poziomu konsoli programu Windows PowerShell jako administrator:</span><span class="sxs-lookup"><span data-stu-id="d453f-112">Run the following command from the Windows PowerShell console running as Administrator:</span></span>

```powershell
Install-Module Azure
```

<span data-ttu-id="d453f-113">Moduł Azure to zbiorczy moduł poleceń cmdlet usługi Azure Resource Manager.</span><span class="sxs-lookup"><span data-stu-id="d453f-113">The Azure module is a rollup module for the Azure Resource Manager cmdlets.</span></span> <span data-ttu-id="d453f-114">Po zainstalowaniu modułu AzureRM każdy moduł platformy Azure, który nie został wcześniej zainstalowany, zostanie pobrany i zainstalowany z Galerii programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d453f-114">When you install the AzureRM module, any other Azure modules that have not previously been installed will be downloaded and installed from the PowerShell Gallery.</span></span>

<span data-ttu-id="d453f-115">Moduł zarządzania usługami platformy Azure udostępnia zależności z modułami usługi Azure PowerShell Resource Manager.</span><span class="sxs-lookup"><span data-stu-id="d453f-115">The Azure Service Management module shares dependencies with the Azure PowerShell Resource Manager modules.</span></span> <span data-ttu-id="d453f-116">Jeśli masz zainstalowane moduły usługi Azure PowerShell Resource Manager, musisz dodać parametr `-AllowClobber` do polecenia instalacji.</span><span class="sxs-lookup"><span data-stu-id="d453f-116">If you have installed the Azure PowerShell Resource Manager modules, you will need to add the `-AllowClobber` parameter to the install command.</span></span> <span data-ttu-id="d453f-117">Umożliwi to aktualizowanie istniejących udostępnionych zależności.</span><span class="sxs-lookup"><span data-stu-id="d453f-117">This allows this existing shared dependencies to be updated.</span></span> <span data-ttu-id="d453f-118">Bez tego parametru nie można zainstalować modułu.</span><span class="sxs-lookup"><span data-stu-id="d453f-118">Without this parameter, installation of the module fails.</span></span>

```powershell
Install-Module Azure -AllowClobber
```

<span data-ttu-id="d453f-119">Po zainstalowaniu tego modułu należy zaimportować moduł za pomocą następującego polecenia:</span><span class="sxs-lookup"><span data-stu-id="d453f-119">After you install this module, you can import the module by running the following command:</span></span>

```powershell
Import-Module Azure
```

## <span data-ttu-id="d453f-120">Aby korzystać z poleceń cmdlet</span><span class="sxs-lookup"><span data-stu-id="d453f-120">To use the cmdlets</span></span>
<a id="to-use-the-cmdlets" class="xliff"></a>

<span data-ttu-id="d453f-121">Aby rozpocząć pracę z poleceniami cmdlet zarządzania usługami platformy Azure, najpierw zaloguj się do konta platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="d453f-121">To start working with the Azure Service Management cmdlets, first log on to your Azure account.</span></span> <span data-ttu-id="d453f-122">Aby zalogować się do konta, uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="d453f-122">To log on to your account, run the following command:</span></span>

```powershell
Add-AzureAccount
```

<span data-ttu-id="d453f-123">Gdy zalogujesz się do platformy Azure, program Azure PowerShell utworzy kontekst dla danej sesji.</span><span class="sxs-lookup"><span data-stu-id="d453f-123">After logging into Azure, Azure PowerShell creates a context for the given session.</span></span> <span data-ttu-id="d453f-124">Ten kontekst zawiera środowisko, konto, dzierżawę i subskrypcję programu Azure PowerShell, które będą używane dla wszystkich poleceń cmdlet w tej sesji.</span><span class="sxs-lookup"><span data-stu-id="d453f-124">That context contains the Azure PowerShell environment, account, tenant, and subscription that will be used for all cmdlets within that session.</span></span> <span data-ttu-id="d453f-125">Teraz możesz używać poniższych modułów.</span><span class="sxs-lookup"><span data-stu-id="d453f-125">Now you are ready to use the modules below.</span></span>

## <span data-ttu-id="d453f-126">Polecenia cmdlet zarządzania usługami platformy Azure</span><span class="sxs-lookup"><span data-stu-id="d453f-126">Azure Service Management cmdlets</span></span>
<a id="azure-service-management-cmdlets" class="xliff"></a>

<span data-ttu-id="d453f-127">Moduły programu Azure PowerShell są często aktualizowane.</span><span class="sxs-lookup"><span data-stu-id="d453f-127">Azure PowerShell modules are updated frequently.</span></span> <span data-ttu-id="d453f-128">Jeśli zauważysz, że pomoc online do polecenia cmdlet zawiera polecenia cmdlet lub parametry, których nie ma w module, pobierz i zainstaluj najnowszą wersję modułu.</span><span class="sxs-lookup"><span data-stu-id="d453f-128">If you notice that the online cmdlet help includes cmdlets or parameters that are not in your module, download and install the latest version of the module.</span></span> <span data-ttu-id="d453f-129">Aby znaleźć wersji modułu, wpisz: `(Get-Module Azure).Version`.</span><span class="sxs-lookup"><span data-stu-id="d453f-129">To find the version of your module, type: `(Get-Module Azure).Version`.</span></span>

<span data-ttu-id="d453f-130">Przykładowe skrypty, które mogą pomóc zautomatyzować niektóre typowe zadania na platformie Azure, można znaleźć w temacie [Centrum skryptów Microsoft Azure](http://www.windowsazure.com/documentation/scripts/).</span><span class="sxs-lookup"><span data-stu-id="d453f-130">For sample scripts that can help you automate some of the common tasks in Azure, see the [Windows Azure Script Center](http://www.windowsazure.com/documentation/scripts/).</span></span>

<span data-ttu-id="d453f-131">Ogólne informacje na temat instalowania, używania i dostosowywania środowiska programu Windows PowerShell oraz powiązanych szkoleń można znaleźć w temacie [Scripting with Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=320210) (Obsługa skryptów w programie Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="d453f-131">For general information about installing, learning, using, and customizing Windows PowerShell, see [Scripting with Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=320210).</span></span>
