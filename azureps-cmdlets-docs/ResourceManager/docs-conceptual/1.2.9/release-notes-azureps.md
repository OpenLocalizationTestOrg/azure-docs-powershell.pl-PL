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
ms.openlocfilehash: 5fe7591855577e083aad5923aed37b18d0b2a40c
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="eb0a1-103">Informacje o wersji</span><span class="sxs-lookup"><span data-stu-id="eb0a1-103">Release notes</span></span>
<a id="release-notes" class="xliff"></a>

<span data-ttu-id="eb0a1-104">To jest lista zmian wprowadzonych w programie Azure PowerShell w tym wydaniu.</span><span class="sxs-lookup"><span data-stu-id="eb0a1-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <span data-ttu-id="eb0a1-105">Wersja 1.2.9</span><span class="sxs-lookup"><span data-stu-id="eb0a1-105">Version 1.2.9</span></span>
<a id="version-129" class="xliff"></a>

<span data-ttu-id="eb0a1-106">Zmiany w tej wersji</span><span class="sxs-lookup"><span data-stu-id="eb0a1-106">Changes This Release</span></span>

* <span data-ttu-id="eb0a1-107">Moduł AzureRm.AzureStackAdmin</span><span class="sxs-lookup"><span data-stu-id="eb0a1-107">AzureRm.AzureStackAdmin Module</span></span>
    + <span data-ttu-id="eb0a1-108">Zmiany w poleceniu cmdlet Add-AzureRmResourceProviderRegistration w celu obsługi podziału na administratora usługi Azure Resource Manager i dzierżawę usługi Azure Resource Manager.</span><span class="sxs-lookup"><span data-stu-id="eb0a1-108">Changes in the Add-AzureRmResourceProviderRegistration cmdlet for the support of Admin Azure resource manager and tenant azure resource manager split.</span></span> <span data-ttu-id="eb0a1-109">Został dodany nowy parametr -ResourceManagerType.</span><span class="sxs-lookup"><span data-stu-id="eb0a1-109">A new parameter -ResourceManagerType has been added.</span></span>
    + <span data-ttu-id="eb0a1-110">Z każdego polecenia cmdlet usunięto parametry -AdminUri, -ApiVersion, -SubscriptionId i -Token.</span><span class="sxs-lookup"><span data-stu-id="eb0a1-110">Removal of the parameters -AdminUri, -ApiVersion, -SubscriptionId and -Token from each cmdlets.</span></span> <span data-ttu-id="eb0a1-111">Generowane były ostrzeżenia, że te parametry zostaną wycofane, a teraz zostały one usunięte.</span><span class="sxs-lookup"><span data-stu-id="eb0a1-111">We have been printing warnings that these parameters will be deprecated and now they got removed.</span></span>
* <span data-ttu-id="eb0a1-112">Moduł AzureStackStorage</span><span class="sxs-lookup"><span data-stu-id="eb0a1-112">AzureStackStorage module</span></span>
    + <span data-ttu-id="eb0a1-113">Dodano nowe polecenia cmdlet do obsługi scenariuszy migracji kontenera.</span><span class="sxs-lookup"><span data-stu-id="eb0a1-113">Added new cmdlets to support container migration scenarios.</span></span>
    + <span data-ttu-id="eb0a1-114">Usunięto polecenia cmdlet odwołujące się do wewnętrznych składników i podstawowych funkcji.</span><span class="sxs-lookup"><span data-stu-id="eb0a1-114">Removed cmdlets referring to internal components and underlying features.</span></span>
* <span data-ttu-id="eb0a1-115">AzureRM.BootStrapper</span><span class="sxs-lookup"><span data-stu-id="eb0a1-115">AzureRM.BootStrapper</span></span>
    + <span data-ttu-id="eb0a1-116">Utworzono nowy moduł do zarządzania wersjami poleceń cmdlet programu Azure PowerShell przy użyciu profilów wersji</span><span class="sxs-lookup"><span data-stu-id="eb0a1-116">Created new module to manage versions of Azure PowerShell cmdlets through the use of version profiles</span></span>