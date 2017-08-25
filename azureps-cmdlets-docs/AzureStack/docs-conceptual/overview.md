---
title: "Omówienie programu Azure Stack PowerShell | Microsoft Docs"
description: "Omówienie instalacji i konfiguracji programu Azure Stack PowerShell."
author: SnehaGunda
manager: Byronr
ms.product: azure-stack
ms.service: powershell
ms.devlang: powershell
ms.topic: reference
ms.author: sngun
ms.manager: byronr
ms.openlocfilehash: 2a03697e0f3e80d63c48f2dc5615f6c99b9ef716
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2017
---
# <a name="azure-stack-powershell"></a><span data-ttu-id="cf5db-103">Azure Stack PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf5db-103">Azure Stack PowerShell</span></span> 

<span data-ttu-id="cf5db-104">Usługa Azure Stack wymaga dwóch następujących modułów programu PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cf5db-104">Azure Stack requires the following two PowerShell modules:</span></span>  

1. <span data-ttu-id="cf5db-105">Zgodny z usługą Azure Stack moduł **AzureRM**, który jest dostępny po zainstalowaniu profilu wersji interfejsu API **2017-03-09-profile**.</span><span class="sxs-lookup"><span data-stu-id="cf5db-105">The Azure Stack compatible **AzureRM** module which is available by installing the **2017-03-09-profile** API Version Profile.</span></span> <span data-ttu-id="cf5db-106">Z poleceń cmdlet zainstalowanych za pomocą tego profilu mogą korzystać administratorzy chmury usługi Azure Stack oraz dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="cf5db-106">The cmdlets installed by using this profile can be used by the Azure Stack cloud administrators and the tenants.</span></span> <span data-ttu-id="cf5db-107">Aby dowiedzieć się więcej o poleceniach cmdlet programu PowerShell dostępnych w tym profilu, zobacz zawartość dokumentacji programu PowerShell dla modułu [AzureRM w wersji 1.2.9](https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-1.2.9).</span><span class="sxs-lookup"><span data-stu-id="cf5db-107">To learn about the PowerShell cmdlets that are available in this profile, see the PowerShell reference content for the [1.2.9 version of AzureRM](https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-1.2.9) module.</span></span>  

2. <span data-ttu-id="cf5db-108">Wersja **1.2.9** modułu **AzureStack**.</span><span class="sxs-lookup"><span data-stu-id="cf5db-108">The **1.2.9** version of the **AzureStack** module.</span></span> <span data-ttu-id="cf5db-109">Z poleceń cmdlet zainstalowanych za pomocą tego modułu mogą korzystać tylko administratorzy chmury usługi Azure Stack.</span><span class="sxs-lookup"><span data-stu-id="cf5db-109">The cmdlets installed by using this module can be used by Azure Stack cloud administrators only.</span></span> <span data-ttu-id="cf5db-110">Administrator może wykonywać operacje, takie jak zarządzanie ofertami, planami, usługami, przydziałami itp., przy użyciu poleceń cmdlet programu PowerShell oferowanymi przez ten moduł.</span><span class="sxs-lookup"><span data-stu-id="cf5db-110">Administrator can perform operations such as manage offers, plans, services, quotas, etc. by using the PowerShell cmdlets provided by this module.</span></span> <span data-ttu-id="cf5db-111">Aby dowiedzieć się więcej o poleceniach cmdlet programu PowerShell dostępnych w tym module, zobacz zawartość dokumentacji rozwiązań [AzureStackAdmin](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.9#azurerm.azurestackadmin) i [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.9#azurerm.azurestackstorage).</span><span class="sxs-lookup"><span data-stu-id="cf5db-111">To learn about the PowerShell cmdlets available in this module, see the [AzureStackAdmin](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.9#azurerm.azurestackadmin) and [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.9#azurerm.azurestackstorage) Reference content.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cf5db-112">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="cf5db-112">Next Steps</span></span>

* [<span data-ttu-id="cf5db-113">Install PowerShell for Azure Stack</span><span class="sxs-lookup"><span data-stu-id="cf5db-113">Install PowerShell for Azure Stack</span></span>](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-install?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9) (Instalowanie programu PowerShell dla usługi Azure Stack)
* [<span data-ttu-id="cf5db-114">Configure PowerShell for use with Azure Stack</span><span class="sxs-lookup"><span data-stu-id="cf5db-114">Configure PowerShell for use with Azure Stack</span></span>](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-configure?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9) (Konfigurowanie programu PowerShell do używania z usługą Azure Stack)


