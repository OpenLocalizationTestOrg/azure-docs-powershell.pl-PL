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
# <a name="azure-stack-powershell"></a>Azure Stack PowerShell 

Usługa Azure Stack wymaga dwóch następujących modułów programu PowerShell:  

1. Zgodny z usługą Azure Stack moduł **AzureRM**, który jest dostępny po zainstalowaniu profilu wersji interfejsu API **2017-03-09-profile**. Z poleceń cmdlet zainstalowanych za pomocą tego profilu mogą korzystać administratorzy chmury usługi Azure Stack oraz dzierżawy. Aby dowiedzieć się więcej o poleceniach cmdlet programu PowerShell dostępnych w tym profilu, zobacz zawartość dokumentacji programu PowerShell dla modułu [AzureRM w wersji 1.2.9](https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-1.2.9).  

2. Wersja **1.2.9** modułu **AzureStack**. Z poleceń cmdlet zainstalowanych za pomocą tego modułu mogą korzystać tylko administratorzy chmury usługi Azure Stack. Administrator może wykonywać operacje, takie jak zarządzanie ofertami, planami, usługami, przydziałami itp., przy użyciu poleceń cmdlet programu PowerShell oferowanymi przez ten moduł. Aby dowiedzieć się więcej o poleceniach cmdlet programu PowerShell dostępnych w tym module, zobacz zawartość dokumentacji rozwiązań [AzureStackAdmin](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.9#azurerm.azurestackadmin) i [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.9#azurerm.azurestackstorage).

## <a name="next-steps"></a>Następne kroki

* [Install PowerShell for Azure Stack](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-install?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9) (Instalowanie programu PowerShell dla usługi Azure Stack)
* [Configure PowerShell for use with Azure Stack](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-configure?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9) (Konfigurowanie programu PowerShell do używania z usługą Azure Stack)


