---
title: <span data-ttu-id="308b0-101">Rozpoczynanie pracy z programem Azure PowerShell | Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="308b0-101">Get started with Azure PowerShell | Microsoft Docs</span></span>
description: 
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: get-started-article
ms.date: 03/30/2017
ms.openlocfilehash: 4bfa14f4f139fa8c35d4bb51ae81baea819188ce
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="308b0-102">Rozpoczynanie pracy z programem Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="308b0-102">Getting started with Azure PowerShell</span></span>
<a id="getting-started-with-azure-powershell" class="xliff"></a>

<span data-ttu-id="308b0-103">Program Azure PowerShell jest przeznaczony do zarządzania i administrowania zasobami platformy Azure przy użyciu wiersza polecenia oraz do tworzenia skryptów automatyzacji, które pozwalają obsługiwać usługę Azure Resource Manager.</span><span class="sxs-lookup"><span data-stu-id="308b0-103">Azure PowerShell is designed for managing and administering Azure resources from the command line, and for building automation scripts that work against the Azure Resource Manager.</span></span> <span data-ttu-id="308b0-104">W tym artykule przedstawiono podstawowe pojęcia związane z programem Azure PowerShell, które ułatwiają rozpoczęcie korzystania z niego.</span><span class="sxs-lookup"><span data-stu-id="308b0-104">This article helps get you started using it, and teaches you the core concepts behind it.</span></span>


## <span data-ttu-id="308b0-105">Instalowanie programu Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="308b0-105">Install Azure PowerShell</span></span>
<a id="install-azure-powershell" class="xliff"></a>
<span data-ttu-id="308b0-106">Pierwszym krokiem jest upewnienie się, że jest zainstalowana najnowsza wersja programu Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="308b0-106">The first step is to make sure you have the latest version of the Azure PowerShell installed.</span></span>  <span data-ttu-id="308b0-107">Najnowsza wersja ma numer 4.1.0.</span><span class="sxs-lookup"><span data-stu-id="308b0-107">The latest version is 4.1.0.</span></span>

1. <span data-ttu-id="308b0-108">[Zainstalowanie programu Azure PowerShell](install-azurerm-ps.md).</span><span class="sxs-lookup"><span data-stu-id="308b0-108">[Install Azure PowerShell](install-azurerm-ps.md).</span></span>

2. <span data-ttu-id="308b0-109">Aby sprawdzić, czy instalacja się powiodła, uruchom polecenie `Get-Module AzureRM` w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="308b0-109">To verify the installation was successful, run `Get-Module AzureRM` from your command line.</span></span>


## <span data-ttu-id="308b0-110">Zaloguj się do platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="308b0-110">Log in to Azure</span></span>
<a id="log-in-to-azure" class="xliff"></a>

<span data-ttu-id="308b0-111">Logowanie interaktywne:</span><span class="sxs-lookup"><span data-stu-id="308b0-111">Sign on interactively:</span></span>

1. <span data-ttu-id="308b0-112">Wpisz polecenie `Login-AzureRmAccount`.</span><span class="sxs-lookup"><span data-stu-id="308b0-112">Type `Login-AzureRmAccount`.</span></span>  <span data-ttu-id="308b0-113">Zostanie wyświetlone okno dialogowe z monitem o podanie poświadczeń platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="308b0-113">You will get dialog box asking for your Azure credentials.</span></span> <span data-ttu-id="308b0-114">Opcja „-EnvironmentName” pozwala zalogować się na platformie Azure (Chiny) lub Azure (Niemcy).</span><span class="sxs-lookup"><span data-stu-id="308b0-114">Option '-EnvironmentName' can let you login in Azure China or Azure Germany.</span></span>
   <span data-ttu-id="308b0-115">np. Login-AzureRmAccount -EnvironmentName AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="308b0-115">e.g. Login-AzureRmAccount -EnvironmentName AzureChinaCloud</span></span>

2. <span data-ttu-id="308b0-116">Wpisz adres e-mail i hasło skojarzone z kontem.</span><span class="sxs-lookup"><span data-stu-id="308b0-116">Type the email address and password associated with your account.</span></span> <span data-ttu-id="308b0-117">Nastąpi uwierzytelnienie i zapisanie informacji o poświadczeniach na platformie Azure, a następnie zamknięcie okna.</span><span class="sxs-lookup"><span data-stu-id="308b0-117">Azure authenticates and saves the credential information, and then closes the window.</span></span>

<span data-ttu-id="308b0-118">Po zalogowaniu się do konta platformy Azure można korzystać z poleceń cmdlet programu Azure PowerShell w celu uzyskania dostępu do zasobów subskrypcji i zarządzania nimi.</span><span class="sxs-lookup"><span data-stu-id="308b0-118">Once you have signed in to an Azure account, you can use the Azure PowerShell cmdlets to access and manager the resources in your subscription.</span></span>

## <span data-ttu-id="308b0-119">Tworzenie grupy zasobów</span><span class="sxs-lookup"><span data-stu-id="308b0-119">Create a resource group</span></span>
<a id="create-a-resource-group" class="xliff"></a>

<span data-ttu-id="308b0-120">Teraz gdy wszystko jest już skonfigurowane, użyjemy programu Azure PowerShell do utworzenia zasobów na platformie Azure.</span><span class="sxs-lookup"><span data-stu-id="308b0-120">Now that we've got everything set up, let's use Azure PowerShell to create resources within Azure.</span></span>

<span data-ttu-id="308b0-121">Najpierw utwórz grupę zasobów.</span><span class="sxs-lookup"><span data-stu-id="308b0-121">First, create a Resource Group.</span></span> <span data-ttu-id="308b0-122">Grupy zasobów na platformie Azure umożliwiają zarządzanie wieloma zasobami, które chcesz logicznie pogrupować razem.</span><span class="sxs-lookup"><span data-stu-id="308b0-122">Resource Groups in Azure provide a way to manage multiple resources that you want to logically group together.</span></span> <span data-ttu-id="308b0-123">Możesz na przykład utworzyć grupę zasobów dla aplikacji lub projektu i dodać do niej maszynę wirtualną, bazę danych i usługę CDN.</span><span class="sxs-lookup"><span data-stu-id="308b0-123">For example, you might create a Resource Group for an application or project and add a virtual machine, a database and a CDN service within it.</span></span>

<span data-ttu-id="308b0-124">Utworzymy grupę zasobów o nazwie „MyResourceGroup” w regionie westeurope świadczenia usługi Azure.</span><span class="sxs-lookup"><span data-stu-id="308b0-124">Let's create a resource group named "MyResourceGroup" in the westeurope region of Azure.</span></span> <span data-ttu-id="308b0-125">W tym celu wpisz następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="308b0-125">To do so type the following command:</span></span>

```powershell
New-AzureRmResourceGroup -Name 'myResourceGroup' -Location 'westeurope'
```

```
ResourceGroupName : myResourceGroup
Location          : westeurope
ProvisioningState : Succeeded
Tags              :
ResourceId        : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/myResourceGroup
```

## <span data-ttu-id="308b0-126">Tworzenie maszyny wirtualnej z systemem Windows</span><span class="sxs-lookup"><span data-stu-id="308b0-126">Create a Windows Virtual Machine</span></span>
<a id="create-a-windows-virtual-machine" class="xliff"></a>

<span data-ttu-id="308b0-127">Teraz gdy mamy grupę zasobów, utwórzmy w niej maszynę wirtualną z systemem Windows.</span><span class="sxs-lookup"><span data-stu-id="308b0-127">Now that we have our resource group, let's create a Windows VM within it.</span></span> <span data-ttu-id="308b0-128">Aby utworzyć nową maszynę wirtualną, musimy najpierw utworzyć inne wymagane zasoby i przypisać je do konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="308b0-128">To create a new VM we must first create the other required resources and assign them to a configuration.</span></span> <span data-ttu-id="308b0-129">Następnie możemy użyć tej konfiguracji do utworzenia maszyny wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="308b0-129">Then we can use that configuration to create the VM.</span></span>

### <span data-ttu-id="308b0-130">Tworzenie wymaganych zasobów sieciowych</span><span class="sxs-lookup"><span data-stu-id="308b0-130">Create the required network resources</span></span>
<a id="create-the-required-network-resources" class="xliff"></a>

<span data-ttu-id="308b0-131">Najpierw musimy utworzyć konfigurację podsieci, która będzie używana w procesie tworzenia sieci wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="308b0-131">First we need to create a subnet configuration to be used with the virtual network creation process.</span></span> <span data-ttu-id="308b0-132">Musimy również utworzyć publiczny adres IP umożliwiający nawiązywanie połączeń z tą maszyną wirtualną.</span><span class="sxs-lookup"><span data-stu-id="308b0-132">We also create a public IP address so that we can connect to this VM.</span></span> <span data-ttu-id="308b0-133">Dostęp do publicznego adresu zostanie zabezpieczony przy użyciu sieciowej grupy zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="308b0-133">We create a network security group to secure access to the public address.</span></span> <span data-ttu-id="308b0-134">Na koniec za pomocą wszystkich wymienionych zasobów utworzymy wirtualną kartę sieciową.</span><span class="sxs-lookup"><span data-stu-id="308b0-134">Finally we create the virtual NIC using all of the previous resources.</span></span>

```powershell
# Variables for common values
$resourceGroup = "myResourceGroup"
$location = "westeurope"
$vmName = "myWindowsVM"

# Create a subnet configuration
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet1 -AddressPrefix 192.168.1.0/24

# Create a virtual network
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName $resourceGroup -Location $location `
  -Name MYvNET1 -AddressPrefix 192.168.0.0/16 -Subnet $subnetConfig

# Create a public IP address and specify a DNS name
$publicIp = New-AzureRmPublicIpAddress -ResourceGroupName $resourceGroup -Location $location `
  -Name "mypublicdns$(Get-Random)" -AllocationMethod Static -IdleTimeoutInMinutes 4
$publicIp | Select-Object Name,IpAddress

# Create an inbound network security group rule for port 3389
$nsgRuleRDP = New-AzureRmNetworkSecurityRuleConfig -Name myNetworkSecurityGroupRuleRDP  -Protocol Tcp `
  -Direction Inbound -Priority 1000 -SourceAddressPrefix * -SourcePortRange * -DestinationAddressPrefix * `
  -DestinationPortRange 3389 -Access Allow

# Create a network security group
$nsg = New-AzureRmNetworkSecurityGroup -ResourceGroupName $resourceGroup -Location $location `
  -Name myNetworkSecurityGroup1 -SecurityRules $nsgRuleRDP

# Create a virtual network card and associate with public IP address and NSG
$nic = New-AzureRmNetworkInterface -Name myNic1 -ResourceGroupName $resourceGroup -Location $location `
  -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $publicIp.Id -NetworkSecurityGroupId $nsg.Id
```

### <span data-ttu-id="308b0-135">Tworzenie maszyny wirtualnej</span><span class="sxs-lookup"><span data-stu-id="308b0-135">Create the virtual machine</span></span>
<a id="create-the-virtual-machine" class="xliff"></a>

<span data-ttu-id="308b0-136">Potrzebujemy zestawu poświadczeń dla systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="308b0-136">First we need a set of credentials for the OS.</span></span>

```powershell
# Create user object
$cred = Get-Credential -Message "Enter a username and password for the virtual machine."
```

<span data-ttu-id="308b0-137">Teraz gdy mamy potrzebne zasoby, możemy utworzyć maszynę wirtualną.</span><span class="sxs-lookup"><span data-stu-id="308b0-137">Now that we have the required resources we can create the VM.</span></span> <span data-ttu-id="308b0-138">W tym kroku utworzymy obiekt konfiguracji maszyny wirtualnej, a następnie użyjemy tej konfiguracji do utworzenia maszyny wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="308b0-138">For this step, we create a VM configuration object, then we use the configuration to create the VM.</span></span>

```powershell
# Create a virtual machine configuration
$vmConfig = New-AzureRmVMConfig -VMName $vmName -VMSize Standard_D1 |
  Set-AzureRmVMOperatingSystem -Windows -ComputerName $vmName -Credential $cred |
  Set-AzureRmVMSourceImage -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version latest |
  Add-AzureRmVMNetworkInterface -Id $nic.Id

# Create a virtual machine
New-AzureRmVM -ResourceGroupName $resourceGroup -Location $location -VM $vmConfig
```

<span data-ttu-id="308b0-139">Polecenie `New-AzureRmVM` zwraca dane wyjściowe, gdy maszyna wirtualna została w pełni utworzona i można jej używać.</span><span class="sxs-lookup"><span data-stu-id="308b0-139">The `New-AzureRmVM` command outputs results once the VM has been fully created and is ready to be used.</span></span>

```
RequestId IsSuccessStatusCode StatusCode ReasonPhrase
--------- ------------------- ---------- ------------
                         True         OK OK
```

<span data-ttu-id="308b0-140">Teraz zaloguj się do nowo utworzonej maszyny wirtualnej z systemem Windows Server za pomocą pulpitu zdalnego i publicznego adresu IP maszyny wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="308b0-140">Now log on to your newly created Windows Server VM using Remote Desktop and the public IP address of the VM.</span></span> <span data-ttu-id="308b0-141">Następujące polecenie umożliwia wyświetlenie publicznego adresu IP utworzonego w poprzednim skrypcie.</span><span class="sxs-lookup"><span data-stu-id="308b0-141">The following command displays the public IP address created in the previous script.</span></span>

```powershell
$publicIp | Select-Object Name,IpAddress
```

```
Name                  IpAddress
----                  ---------
mypublicdns1400512543 xx.xx.xx.xx
```

<span data-ttu-id="308b0-142">Jeśli korzystasz z komputera z systemem Windows, możesz to zrobić w wierszu polecenia przy użyciu polecenia mstsc:</span><span class="sxs-lookup"><span data-stu-id="308b0-142">If you are on a Windows-based system, you can do this from the command line using the mstsc command:</span></span>

```
mstsc /v:xx.xxx.xx.xxx
```

<span data-ttu-id="308b0-143">Aby się zalogować, podaj tę samą kombinację nazwy użytkownika/hasła, którą podano podczas tworzenia maszyny wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="308b0-143">Supply the same username/password combination you used when creating the VM to log in.</span></span>


## <span data-ttu-id="308b0-144">Tworzenie maszyny wirtualnej z systemem Linux</span><span class="sxs-lookup"><span data-stu-id="308b0-144">Create a Linux Virtual Machine</span></span>
<a id="create-a-linux-virtual-machine" class="xliff"></a>

<span data-ttu-id="308b0-145">Aby utworzyć nową maszynę wirtualną z systemem Linux, musimy najpierw utworzyć inne wymagane zasoby i przypisać je do konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="308b0-145">To create a new Linux VM we must first create the other required resources and assign them to a configuration.</span></span> <span data-ttu-id="308b0-146">Następnie możemy użyć tej konfiguracji do utworzenia maszyny wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="308b0-146">Then we can use that configuration to create the VM.</span></span> <span data-ttu-id="308b0-147">Zakłada się, że została już utworzona grupa zasobów zgodnie z wcześniejszymi instrukcjami.</span><span class="sxs-lookup"><span data-stu-id="308b0-147">This assumes that you have already created the resource group as previously shown.</span></span> <span data-ttu-id="308b0-148">Ponadto w katalogu ssh profilu użytkownika musi znajdować się klucz publiczny SSH o nazwie `id_rsa.pub`.</span><span class="sxs-lookup"><span data-stu-id="308b0-148">Also, you will need to have an SSH public key named `id_rsa.pub` in the .ssh directory of your user profile.</span></span>

### <span data-ttu-id="308b0-149">Tworzenie wymaganych zasobów sieciowych</span><span class="sxs-lookup"><span data-stu-id="308b0-149">Create the required network resources</span></span>
<a id="create-the-required-network-resources" class="xliff"></a>

<span data-ttu-id="308b0-150">Najpierw musimy utworzyć konfigurację podsieci, która będzie używana w procesie tworzenia sieci wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="308b0-150">First we need to create a subnet configuration to be used with the virtual network creation process.</span></span> <span data-ttu-id="308b0-151">Musimy również utworzyć publiczny adres IP umożliwiający nawiązywanie połączeń z tą maszyną wirtualną.</span><span class="sxs-lookup"><span data-stu-id="308b0-151">We also create a public IP address so that we can connect to this VM.</span></span> <span data-ttu-id="308b0-152">Dostęp do publicznego adresu zostanie zabezpieczony przy użyciu sieciowej grupy zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="308b0-152">We create a network security group to secure access to the public address.</span></span> <span data-ttu-id="308b0-153">Na koniec za pomocą wszystkich wymienionych zasobów utworzymy wirtualną kartę sieciową.</span><span class="sxs-lookup"><span data-stu-id="308b0-153">Finally we create the virtual NIC using all of the previous resources.</span></span>

```powershell
# Variables for common values
$resourceGroup = "myResourceGroup"
$location = "westeurope"
$vmName = "myLinuxVM"

# Definer user name and blank password
$securePassword = ConvertTo-SecureString ' ' -AsPlainText -Force
$cred = New-Object System.Management.Automation.PSCredential ("azureuser", $securePassword)

# Create a subnet configuration
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet2 -AddressPrefix 192.168.2.0/24

# Create a virtual network
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName $resourceGroup -Location $location `
  -Name MYvNET2 -AddressPrefix 192.168.0.0/16 -Subnet $subnetConfig

# Create a public IP address and specify a DNS name
$publicIp = New-AzureRmPublicIpAddress -ResourceGroupName $resourceGroup -Location $location `
  -Name "mypublicdns$(Get-Random)" -AllocationMethod Static -IdleTimeoutInMinutes 4
$publicIp | Select-Object Name,IpAddress

# Create an inbound network security group rule for port 22
$nsgRuleSSH = New-AzureRmNetworkSecurityRuleConfig -Name myNetworkSecurityGroupRuleSSH  -Protocol Tcp `
  -Direction Inbound -Priority 1000 -SourceAddressPrefix * -SourcePortRange * -DestinationAddressPrefix * `
  -DestinationPortRange 22 -Access Allow

# Create a network security group
$nsg = New-AzureRmNetworkSecurityGroup -ResourceGroupName $resourceGroup -Location $location `
  -Name myNetworkSecurityGroup2 -SecurityRules $nsgRuleSSH

# Create a virtual network card and associate with public IP address and NSG
$nic = New-AzureRmNetworkInterface -Name myNic2 -ResourceGroupName $resourceGroup -Location $location `
  -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $publicIp.Id -NetworkSecurityGroupId $nsg.Id
```

### <span data-ttu-id="308b0-154">Tworzenie maszyny wirtualnej</span><span class="sxs-lookup"><span data-stu-id="308b0-154">Create the virtual machine</span></span>
<a id="create-the-virtual-machine" class="xliff"></a>

<span data-ttu-id="308b0-155">Teraz gdy mamy potrzebne zasoby, możemy utworzyć maszynę wirtualną.</span><span class="sxs-lookup"><span data-stu-id="308b0-155">Now that we have the required resources we can create the VM.</span></span> <span data-ttu-id="308b0-156">W tym kroku utworzymy obiekt konfiguracji maszyny wirtualnej, a następnie użyjemy tej konfiguracji do utworzenia maszyny wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="308b0-156">For this step, we create a VM configuration object, then we use the configuration to create the VM.</span></span>

```powershell
# Create a virtual machine configuration
$vmConfig = New-AzureRmVMConfig -VMName $vmName -VMSize Standard_D1 |
  Set-AzureRmVMOperatingSystem -Linux -ComputerName $vmName -Credential $cred -DisablePasswordAuthentication |
  Set-AzureRmVMSourceImage -PublisherName Canonical -Offer UbuntuServer -Skus 14.04.2-LTS -Version latest |
  Add-AzureRmVMNetworkInterface -Id $nic.Id

# Configure SSH Keys
$sshPublicKey = Get-Content "$env:USERPROFILE\.ssh\id_rsa.pub"
Add-AzureRmVMSshPublicKey -VM $vmConfig -KeyData $sshPublicKey -Path "/home/azureuser/.ssh/authorized_keys"

# Create a virtual machine
New-AzureRmVM -ResourceGroupName $resourceGroup -Location $location -VM $vmConfig
```

<span data-ttu-id="308b0-157">Teraz gdy maszyna wirtualna została już utworzona, możesz zalogować się do swojej nowej maszyny wirtualnej z systemem Linux przy użyciu protokołu SSH i publicznego adresu IP utworzonej maszyny wirtualnej:</span><span class="sxs-lookup"><span data-stu-id="308b0-157">Now that the VM has been created, you can log on to your new Linux VM using SSH with the public IP address of the VM you created:</span></span>

```bash
ssh xx.xxx.xxx.xxx
```

```
Welcome to Ubuntu 14.04.4 LTS (GNU/Linux 3.19.0-65-generic x86_64)

 * Documentation:  https://help.ubuntu.com/

  System information as of Sun Feb 19 00:32:28 UTC 2017

  System load: 0.31              Memory usage: 3%   Processes:       89
  Usage of /:  39.6% of 1.94GB   Swap usage:   0%   Users logged in: 0

  Graph this data and manage this system at:
    https://landscape.canonical.com/

  Get cloud support with Ubuntu Advantage Cloud Guest:
    http://www.ubuntu.com/business/services/cloud

0 packages can be updated.
0 updates are security updates.



The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

my-login@MyLinuxVM:~$
```

## <span data-ttu-id="308b0-158">Tworzenie innych zasobów na platformie Azure</span><span class="sxs-lookup"><span data-stu-id="308b0-158">Creating other resources in Azure</span></span>
<a id="creating-other-resources-in-azure" class="xliff"></a>

<span data-ttu-id="308b0-159">Omówiliśmy sposób tworzenia grupy zasobów, maszyny wirtualnej z systemem Linux i maszyny wirtualnej z systemem Windows Server.</span><span class="sxs-lookup"><span data-stu-id="308b0-159">We've now walked through how to create a Resource Group, a Linux VM, and a Windows Server VM.</span></span> <span data-ttu-id="308b0-160">Możesz również utworzyć wiele innych typów zasobów platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="308b0-160">You can create many other types of Azure resources as well.</span></span>

<span data-ttu-id="308b0-161">Aby na przykład utworzyć moduł równoważenia obciążenia sieci platformy Azure, który można będzie potem skojarzyć z nowo utworzonymi maszynami wirtualnymi, możemy użyć następującego polecenia create:</span><span class="sxs-lookup"><span data-stu-id="308b0-161">For example, to create an Azure Network Load Balancer that we could then associate with our newly created VMs, we can use the following create command:</span></span>

```powershell
New-AzureRmLoadBalancer -Name MyLoadBalancer -ResourceGroupName myResourceGroup -Location westeurope
```

<span data-ttu-id="308b0-162">Możemy także utworzyć nową prywatną sieć wirtualną (nazywaną „VNet” na platformie Azure) dla naszej infrastruktury, korzystając z następującego polecenia:</span><span class="sxs-lookup"><span data-stu-id="308b0-162">We could also create a new private Virtual Network (commonly referred to as a "VNet" within Azure) for our infrastructure using the following command:</span></span>

```powershell
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet2 -AddressPrefix 10.0.0.0/16
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName myResourceGroup -Location westeurope `
  -Name MYvNET3 -AddressPrefix 10.0.0.0/16 -Subnet $subnetConfig
```

<span data-ttu-id="308b0-163">Tym, co sprawia, że platforma Azure i program Azure PowerShell są tak przydatne, jest to, że możemy ich używać nie tylko do uzyskiwania infrastruktury opartej na chmurze, ale również do tworzenia zarządzanych usług platformy.</span><span class="sxs-lookup"><span data-stu-id="308b0-163">What makes Azure and the Azure PowerShell powerful is that we can use it not just to get cloud-based infrastructure but also to create managed platform services.</span></span> <span data-ttu-id="308b0-164">Zarządzane usługi platformy można również łączyć z infrastrukturą w celu tworzenia jeszcze bardziej zaawansowanych rozwiązań.</span><span class="sxs-lookup"><span data-stu-id="308b0-164">The managed platform services can also be combined with infrastructure to build even more powerful solutions.</span></span>

<span data-ttu-id="308b0-165">Możesz na przykład użyć programu Azure PowerShell do utworzenia usługi Azure App Service.</span><span class="sxs-lookup"><span data-stu-id="308b0-165">For example, you can use the Azure PowerShell to create an Azure AppService.</span></span> <span data-ttu-id="308b0-166">Usługa Azure App Service to zarządzana usługa platformy, która zapewnia doskonały sposób hostowania aplikacji sieci Web bez konieczności troszczenia się o infrastrukturę.</span><span class="sxs-lookup"><span data-stu-id="308b0-166">Azure AppService is a managed platform service that provides a great way to host web apps without having to worry about infrastructure.</span></span> <span data-ttu-id="308b0-167">Po utworzeniu usługi Azure App Service możesz utworzyć dwie nowe aplikacje Azure Web Apps w ramach usługi App Service, korzystając z następujących poleceń:</span><span class="sxs-lookup"><span data-stu-id="308b0-167">After creating the Azure AppService, you can create two new Azure Web Apps within the AppService using the following commands:</span></span>

```powershell
# Create an Azure AppService that we can host any number of web apps within
New-AzureRmAppServicePlan -Name MyAppServicePlan -Tier Basic -NumberofWorkers 2 -WorkerSize Small -ResourceGroupName myResourceGroup -Location westeurope

# Create Two Web Apps within the AppService (note: name param must be a unique DNS entry)
New-AzureRmWebApp -Name MyWebApp43432 -AppServicePlan MyAppServicePlan -ResourceGroupName myResourceGroup -Location westeurope
New-AzureRmWebApp -Name MyWebApp43433 -AppServicePlan MyAppServicePlan -ResourceGroupName myResourceGroup -Location westeurope
```

## <span data-ttu-id="308b0-168">Wyświetlanie listy wdrożonych zasobów</span><span class="sxs-lookup"><span data-stu-id="308b0-168">Listing deployed resources</span></span>
<a id="listing-deployed-resources" class="xliff"></a>

<span data-ttu-id="308b0-169">Listę zasobów uruchomionych na platformie Azure można wyświetlić za pomocą polecenia cmdlet `Get-AzureRmResource`.</span><span class="sxs-lookup"><span data-stu-id="308b0-169">You can use the `Get-AzureRmResource` cmdlet to list the resources running in Azure.</span></span> <span data-ttu-id="308b0-170">W poniższym przykładzie zostaną wyświetlone zasoby utworzone w nowej grupie zasobów.</span><span class="sxs-lookup"><span data-stu-id="308b0-170">The following example shows the resources we just created in the new resource group.</span></span>

```powershell
Get-AzureRmResource |
  Where-Object ResourceGroupName -eq myResourceGroup |
    Select-Object Name,Location,ResourceType
```

```
Name                                                  Location   ResourceType
----                                                  --------   ------------
myLinuxVM_OsDisk_1_36ca038791f642ba91270879088c249a   westeurope Microsoft.Compute/disks
myWindowsVM_OsDisk_1_f627e6e2bb454c72897d72e9632adf9a westeurope Microsoft.Compute/disks
myLinuxVM                                             westeurope Microsoft.Compute/virtualMachines
myWindowsVM                                           westeurope Microsoft.Compute/virtualMachines
myWindowsVM/BGInfo                                    westeurope Microsoft.Compute/virtualMachines/extensions
myNic1                                                westeurope Microsoft.Network/networkInterfaces
myNic2                                                westeurope Microsoft.Network/networkInterfaces
myNetworkSecurityGroup1                               westeurope Microsoft.Network/networkSecurityGroups
myNetworkSecurityGroup2                               westeurope Microsoft.Network/networkSecurityGroups
mypublicdns245369171                                  westeurope Microsoft.Network/publicIPAddresses
mypublicdns779537141                                  westeurope Microsoft.Network/publicIPAddresses
MYvNET1                                               westeurope Microsoft.Network/virtualNetworks
MYvNET2                                               westeurope Microsoft.Network/virtualNetworks
micromyresomywi032907510                              westeurope Microsoft.Storage/storageAccounts
```

## <span data-ttu-id="308b0-171">Usuwanie zasobów</span><span class="sxs-lookup"><span data-stu-id="308b0-171">Deleting resources</span></span>
<a id="deleting-resources" class="xliff"></a>

<span data-ttu-id="308b0-172">Wyczyszczenie konta platformy Azure polega na usunięciu zasobów utworzonych w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="308b0-172">To clean up your Azure account, you want to remove the resources we created in this example.</span></span> <span data-ttu-id="308b0-173">Aby usunąć zasoby, które nie są już potrzebne, możesz użyć poleceń cmdlet `Remove-AzureRm*`.</span><span class="sxs-lookup"><span data-stu-id="308b0-173">You can use the `Remove-AzureRm*` cmdlets to delete the resources you no longer need.</span></span> <span data-ttu-id="308b0-174">Aby usunąć utworzoną maszynę wirtualną z systemem Windows, użyj następującego polecenia:</span><span class="sxs-lookup"><span data-stu-id="308b0-174">To remove the Windows VM we created, using the following command:</span></span>

```powershell
Remove-AzureRmVM -Name myWindowsVM -ResourceGroupName myResourceGroup
```

<span data-ttu-id="308b0-175">Pojawi się monit o potwierdzenie usunięcia zasobu.</span><span class="sxs-lookup"><span data-stu-id="308b0-175">You will be prompted to confirm that you want to remove the resource.</span></span>

```
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

<span data-ttu-id="308b0-176">Można także usuwać wiele zasobów jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="308b0-176">You can also use the delete many resources at one time.</span></span> <span data-ttu-id="308b0-177">Na przykład następujące polecenie pozwala usunąć całą grupę zasobów „MyResourceGroup”, która była używana we wszystkich przykładach w tym samouczku wprowadzającym.</span><span class="sxs-lookup"><span data-stu-id="308b0-177">For example, the following command deletes all the resource group "MyResourceGroup" that we've used for all the samples in this Get Started tutorial.</span></span> <span data-ttu-id="308b0-178">Usunięta zostanie grupa zasobów i wszystkie zasoby w niej zawarte.</span><span class="sxs-lookup"><span data-stu-id="308b0-178">This removes the resource group and all of the resources in it.</span></span>

```powershell
Remove-AzureRmResourceGroup -Name myResourceGroup
```

```
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

<span data-ttu-id="308b0-179">Może to potrwać kilka minut.</span><span class="sxs-lookup"><span data-stu-id="308b0-179">This can take several minutes to complete.</span></span>

## <span data-ttu-id="308b0-180">Pobieranie przykładów</span><span class="sxs-lookup"><span data-stu-id="308b0-180">Get samples</span></span>
<a id="get-samples" class="xliff"></a>

<span data-ttu-id="308b0-181">Aby dowiedzieć się więcej o sposobach używania programu Azure PowerShell, zapoznaj się z naszymi najbardziej typowymi skryptami dla [maszyn wirtualnych z systemem Linux](/azure/virtual-machines/virtual-machines-linux-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [maszyn wirtualnych z systemem Windows](/azure/virtual-machines/virtual-machines-windows-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [aplikacji sieci Web](/azure/app-service-web/app-service-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json) i [baz danych SQL](/azure/sql-database/sql-database-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="308b0-181">To learn more about ways to use the Azure PowerShell, check out our most common scripts for [Linux VMs](/azure/virtual-machines/virtual-machines-linux-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [Windows VMs](/azure/virtual-machines/virtual-machines-windows-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [Web Apps](/azure/app-service-web/app-service-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), and [SQL Databases](/azure/sql-database/sql-database-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json).</span></span>

## <span data-ttu-id="308b0-182">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="308b0-182">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

* [<span data-ttu-id="308b0-183">Logowanie za pomocą programu Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="308b0-183">Login with Azure PowerShell</span></span>](authenticate-azureps.md)
* [<span data-ttu-id="308b0-184">Zarządzanie subskrypcjami platformy Azure za pomocą programu Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="308b0-184">Manage Azure subscriptions with Azure PowerShell</span></span>](manage-subscriptions-azureps.md)
* [<span data-ttu-id="308b0-185">Tworzenie jednostek usługi na platformie Azure przy użyciu programu Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="308b0-185">Create service principals in Azure using Azure PowerShell</span></span>](create-azure-service-principal-azureps.md)
* <span data-ttu-id="308b0-186">Informacje dotyczące migracji ze starszej wersji: [https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes](https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes).</span><span class="sxs-lookup"><span data-stu-id="308b0-186">Read the Release notes about migrating from an older release: [https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes](https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes).</span></span>
* <span data-ttu-id="308b0-187">Uzyskiwanie pomocy od społeczności:</span><span class="sxs-lookup"><span data-stu-id="308b0-187">Get help from the community:</span></span>
  + [<span data-ttu-id="308b0-188">Forum platformy Azure w witrynie MSDN</span><span class="sxs-lookup"><span data-stu-id="308b0-188">Azure forum on MSDN</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=320212)
  + [<span data-ttu-id="308b0-189">Witryna Stackoverflow</span><span class="sxs-lookup"><span data-stu-id="308b0-189">stackoverflow</span></span>](http://go.microsoft.com/fwlink/?LinkId=320213)