---
title: "Korzystanie z eksperymentalnych modułów programu Azure PowerShell"
description: "Wyjaśnienie filozofii i zasad użycia eksperymentalnych modułów programu Azure PowerShell."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/05/2017
ms.openlocfilehash: 7a01957040be7c0498ef4f0e9b8f7297119221a5
ms.sourcegitcommit: 358d260a867c6ee2e8700b91f776ba4f1b0e24a5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2017
---
# <a name="using-experimental-azure-powershell-modules"></a><span data-ttu-id="c140b-103">Korzystanie z eksperymentalnych modułów programu Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="c140b-103">Using experimental Azure PowerShell modules</span></span>

<span data-ttu-id="c140b-104">Zespół programu Azure PowerShell eksperymentuje z wieloma udoskonaleniami w zakresie korzystania z tego programu, ze szczególnym uwzględnieniem narzędzi dla deweloperów (w szczególności interfejsów wiersza polecenia).</span><span class="sxs-lookup"><span data-stu-id="c140b-104">With the emphasis on developer tools (especially CLIs) in Azure, the Azure PowerShell team is experimenting with many improvements to the Azure PowerShell experience.</span></span>

## <a name="experimentation-methodology"></a><span data-ttu-id="c140b-105">Metodologia eksperymentów</span><span class="sxs-lookup"><span data-stu-id="c140b-105">Experimentation methodology</span></span>

<span data-ttu-id="c140b-106">Aby ułatwić eksperymenty, tworzymy nowe moduły programu Azure PowerShell, które wdrażają istniejące funkcje zestawu SDK platformy Azure przy użyciu nowych, łatwiejszych w obsłudze sposobów.</span><span class="sxs-lookup"><span data-stu-id="c140b-106">To facilitate experimentation, we are creating new Azure PowerShell modules that implement existing Azure SDK functionality in new, easier to use ways.</span></span> <span data-ttu-id="c140b-107">W większości przypadków polecenia cmdlet dokładnie duplikują istniejące polecenia cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c140b-107">In most cases, the cmdlets exactly mirror existing cmdlets.</span></span> <span data-ttu-id="c140b-108">Jednak eksperymentalne polecenia cmdlet są dostępne ze skróconą notacją i bardziej inteligentnymi wartościami domyślnymi, co ułatwia tworzenie zasobów platformy Azure i zarządzanie nimi.</span><span class="sxs-lookup"><span data-stu-id="c140b-108">However, the experimental cmdlets provide a shorthand notation and smarter default values that make it easier to create and manage Azure resources.</span></span>

<span data-ttu-id="c140b-109">Te moduły mogą być instalowane obok istniejących modułów programu Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c140b-109">These modules can be installed side-by-side with existing Azure PowerShell modules.</span></span> <span data-ttu-id="c140b-110">Nazwy poleceń cmdlet zostały skrócone, aby zmniejszyć ich długość i wyeliminować konflikty z istniejącymi poleceniami cmdlet, które nie są eksperymentalne.</span><span class="sxs-lookup"><span data-stu-id="c140b-110">The cmdlet names have been shortened to provide shorter names and avoid name conflicts with existing, non-experimental cmdlets.</span></span>

<span data-ttu-id="c140b-111">W przypadku nazw modułów eksperymentalnych obowiązuje następująca konwencja nazewnictwa:</span><span class="sxs-lookup"><span data-stu-id="c140b-111">The experimental modules use the following naming convention:</span></span>

- <span data-ttu-id="c140b-112">AzureRM.Compute.Experiments</span><span class="sxs-lookup"><span data-stu-id="c140b-112">AzureRM.Compute.Experiments</span></span>
- <span data-ttu-id="c140b-113">AzureRM.Websites.Experiments</span><span class="sxs-lookup"><span data-stu-id="c140b-113">AzureRM.Websites.Experiments</span></span>

<span data-ttu-id="c140b-114">Ta konwencja nazewnictwa przypomina nazewnictwo modułów z wersji zapoznawczej: `AzureRM.*.Preview`.</span><span class="sxs-lookup"><span data-stu-id="c140b-114">This naming convention is similar to the naming of Preview modules: `AzureRM.*.Preview`.</span></span> <span data-ttu-id="c140b-115">Moduły z wersji zapoznawczej różnią się od modułów eksperymentalnych.</span><span class="sxs-lookup"><span data-stu-id="c140b-115">Preview modules differ from experimental modules.</span></span> <span data-ttu-id="c140b-116">Moduły z wersji zapoznawczej wdrażają nowe funkcje usług platformy Azure, które są dostępne tylko w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="c140b-116">Preview modules implement new functionality of Azure services that is only available as a Preview offering.</span></span> <span data-ttu-id="c140b-117">Moduły z wersji zapoznawczej zastępują istniejące moduły programu Azure PowerShell i używają tych samych nazw poleceń cmdlet i nazw parametrów.</span><span class="sxs-lookup"><span data-stu-id="c140b-117">Preview modules replace existing Azure PowerShell modules and use the same cmdlet and parameter names.</span></span>

## <a name="how-to-install-an-experimental-module"></a><span data-ttu-id="c140b-118">Jak zainstalować moduł eksperymentalny</span><span class="sxs-lookup"><span data-stu-id="c140b-118">How to install an experimental module</span></span>

<span data-ttu-id="c140b-119">Moduły eksperymentalne są publikowane w galerii programu PowerShell tak samo, jak istniejące moduły programu Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c140b-119">Experimental modules are published to the PowerShell Gallery just like the existing Azure PowerShell modules.</span></span> <span data-ttu-id="c140b-120">Aby wyświetlić listę modułów eksperymentalnych, uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="c140b-120">To see a list of experimental modules, run the following command:</span></span>

```powershell
Find-Module AzureRM.*.Experiments
```

```Output
Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.0.0      AzureRM.Websites.Experiments        PSGallery            Create and deploy web applications using Azure Ap...
1.0.25     AzureRM.Compute.Experiments         PSGallery            Azure Compute experiments for VM creation
```

<span data-ttu-id="c140b-121">Aby zainstalować moduł eksperymentalny, użyj następujących poleceń w sesji programu PowerShell z podwyższonym poziomem uprawnień:</span><span class="sxs-lookup"><span data-stu-id="c140b-121">To install the experimental module, use the following commands from an elevated PowerShell session:</span></span>

```powershell
Install-Module AzureRM.Compute.Experiments
Install-Module AzureRM.Websites.Experiments
```

### <a name="documentation-and-support"></a><span data-ttu-id="c140b-122">Dokumentacja i pomoc techniczna</span><span class="sxs-lookup"><span data-stu-id="c140b-122">Documentation and support</span></span>

<span data-ttu-id="c140b-123">Dokumentacja jest zawarta w pakiecie instalacyjnym, a dostęp do niej można uzyskiwać za pomocą polecenia cmdlet `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="c140b-123">Documentation is included in the install package and is accessed using the `Get-Help` cmdlet.</span></span> <span data-ttu-id="c140b-124">Dla modułów eksperymentalnych nie jest publikowana oficjalna dokumentacja.</span><span class="sxs-lookup"><span data-stu-id="c140b-124">No official documentation is published for experimental modules.</span></span>

<span data-ttu-id="c140b-125">Zachęcamy do testowania tych modułów.</span><span class="sxs-lookup"><span data-stu-id="c140b-125">We encourage you to test these modules.</span></span> <span data-ttu-id="c140b-126">Wasze opinie pozwalają nam poprawiać użyteczność i reagować na Wasze potrzeby.</span><span class="sxs-lookup"><span data-stu-id="c140b-126">Your feedback allows us to improve usability and respond to your needs.</span></span> <span data-ttu-id="c140b-127">Jednak wsparcie dla tych modułów jest ograniczone z uwagi na to, że są to moduły eksperymentalne.</span><span class="sxs-lookup"><span data-stu-id="c140b-127">However, being experimental, support for these modules is limited.</span></span> <span data-ttu-id="c140b-128">Pytania i raporty dotyczące problemów można przekazywać, tworząc [problem](https://github.com/Azure/azure-powershell/issues) w repozytorium GitHub.</span><span class="sxs-lookup"><span data-stu-id="c140b-128">Questions or problem reports can be submitted by creating an [issue](https://github.com/Azure/azure-powershell/issues) in the GitHub repository.</span></span>

## <a name="experiments-and-areas-of-improvement"></a><span data-ttu-id="c140b-129">Eksperymenty i obszary ulepszeń</span><span class="sxs-lookup"><span data-stu-id="c140b-129">Experiments and areas of improvement</span></span>

<span data-ttu-id="c140b-130">Te ulepszenia zostały wybrane na podstawie kluczowych różnic w konkurencyjnych produktach.</span><span class="sxs-lookup"><span data-stu-id="c140b-130">These improvements were selected based on key differentiators in competing products.</span></span> <span data-ttu-id="c140b-131">Na przykład w interfejsie wiersza polecenia platformy Azure w wersji 2.0 oparto polecenia na _scenariuszach_, a nie na _obszarze powierzchni interfejsu API_.</span><span class="sxs-lookup"><span data-stu-id="c140b-131">For example, Azure CLI 2.0 has made a point of basing commands on _scenarios_ rather than _API surface area_.</span></span>
<span data-ttu-id="c140b-132">W interfejsie wiersza polecenia platformy Azure w wersji 2.0 używana jest pewna liczba domyślnych ustawień inteligentnych, dzięki którym korzystanie ze scenariuszy wprowadzających jest łatwiejsze dla użytkowników.</span><span class="sxs-lookup"><span data-stu-id="c140b-132">Azure CLI 2.0 use a number of smart defaults that make "getting started" scenarios easier for end users.</span></span>

### <a name="core-improvements"></a><span data-ttu-id="c140b-133">Ulepszenia funkcji podstawowych</span><span class="sxs-lookup"><span data-stu-id="c140b-133">Core improvements</span></span>

<span data-ttu-id="c140b-134">Ulepszenia funkcji podstawowych są traktowane jako zdroworozsądkowe, a w celu wdrożenia tych aktualizacji potrzebne jest eksperymentowanie tylko w ograniczonym zakresie.</span><span class="sxs-lookup"><span data-stu-id="c140b-134">The core improvements are regarded as "common sense", and little experimentation is needed to move forward in implementing these updates.</span></span>

- <span data-ttu-id="c140b-135">Polecenia cmdlet oparte na scenariuszach — **wszystkie* polecenia cmdlet powinny być projektowane wokół scenariuszy, a nie w oparciu o usługę Azure REST.</span><span class="sxs-lookup"><span data-stu-id="c140b-135">Scenario-based Cmdlets - **All*- cmdlets should be designed around scenarios, not the Azure REST service.</span></span>

- <span data-ttu-id="c140b-136">Krótsze nazwy — obejmują nazwy poleceń cmdlet (na przykład `New-AzureRmVM` => `New-AzVm`) oraz nazwy parametrów (na przykład `-ResourceGroupName` => `-Rg`).</span><span class="sxs-lookup"><span data-stu-id="c140b-136">Shorter Names - Includes the names of cmdlets (for example, `New-AzureRmVM` => `New-AzVm`) and the names of parameters (for example, `-ResourceGroupName` => `-Rg`).</span></span> <span data-ttu-id="c140b-137">W celu zapewniania zgodności ze „starymi” poleceniami cmdlet należy stosować aliasy.</span><span class="sxs-lookup"><span data-stu-id="c140b-137">Use aliases for compatibility with "old" cmdlets.</span></span> <span data-ttu-id="c140b-138">Wymagane jest udostępnianie zestawów parametrów _zgodnych z poprzednimi wersjami_.</span><span class="sxs-lookup"><span data-stu-id="c140b-138">Provide _backwards compatible_ parameter sets.</span></span>

- <span data-ttu-id="c140b-139">Inteligentne wartości domyślne — inteligentne wartości domyślne należy tworzyć, aby wypełniać „wymagane” informacje.</span><span class="sxs-lookup"><span data-stu-id="c140b-139">Smart Defaults - Create smart defaults to fill in "required" information.</span></span> <span data-ttu-id="c140b-140">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="c140b-140">For example:</span></span>
  - <span data-ttu-id="c140b-141">Grupa zasobów</span><span class="sxs-lookup"><span data-stu-id="c140b-141">Resource Group</span></span>
  - <span data-ttu-id="c140b-142">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="c140b-142">Location</span></span>
  - <span data-ttu-id="c140b-143">Zasoby zależne</span><span class="sxs-lookup"><span data-stu-id="c140b-143">Dependent resources</span></span>

### <a name="experimental-improvements"></a><span data-ttu-id="c140b-144">Ulepszenia eksperymentalne</span><span class="sxs-lookup"><span data-stu-id="c140b-144">Experimental improvements</span></span>

<span data-ttu-id="c140b-145">Ulepszenia eksperymentalne stanowią istotną zmianę, którą zespół chce zweryfikować za pośrednictwem eksperymentów.</span><span class="sxs-lookup"><span data-stu-id="c140b-145">The experimental improvements present a significant change that the team wants to validate via experimentation.</span></span>

- <span data-ttu-id="c140b-146">Typy proste — scenariusze tworzenia powinny odbiegać od typów złożonych i obiektów konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c140b-146">Simple types - Create scenarios should move away from complex types and config objects.</span></span> <span data-ttu-id="c140b-147">Konfiguracja powinna być uproszczona i ograniczona do jednego lub dwóch parametrów.</span><span class="sxs-lookup"><span data-stu-id="c140b-147">Simplify the configuration down to one or two parameters.</span></span>

- <span data-ttu-id="c140b-148">„Tworzenie inteligentne” — żadne scenariusze tworzenia, które wdrażają „Tworzenie inteligentne”, _nie powinny_ zawierać parametrów wymaganych: wszystkie wymagane informacje powinny być wybierane w programie Azure PowerShell jako opcje.</span><span class="sxs-lookup"><span data-stu-id="c140b-148">"Smart Create" - All create scenarios implementing "Smart Create" would have _no_ required parameters: all necessary information would be chosen by Azure PowerShell in an opinionated fashion.</span></span>

- <span data-ttu-id="c140b-149">Parametry szare — w wielu przypadkach niektóre parametry mogą być „szare” lub półopcjonalne.</span><span class="sxs-lookup"><span data-stu-id="c140b-149">Gray Parameters - In many cases, some parameters could be "gray" or semi-optional.</span></span> <span data-ttu-id="c140b-150">Jeśli parametr nie jest określony, użytkownik jest pytany, czy chce, aby parametr został dla niego wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="c140b-150">If the parameter is not specified, the user is asked if they want the parameter generated for them.</span></span> <span data-ttu-id="c140b-151">Dodatkowo warto, aby za zgodą użytkownika parametry szare otrzymywały wartości na podstawie kontekstu.</span><span class="sxs-lookup"><span data-stu-id="c140b-151">It also makes sense for gray parameters to infer a value based on context with the user's consent.</span></span>
  <span data-ttu-id="c140b-152">Na przykład rozsądne może okazać się, aby parametr szary sugerował wartość, która została użyta jako ostatnia.</span><span class="sxs-lookup"><span data-stu-id="c140b-152">For example, it may make sense to have the gray parameter suggest the most recently used value.</span></span>

- <span data-ttu-id="c140b-153">Przełącznik `-Auto` — przełącznik `-Auto` stanowi sposób, dzięki któremu użytkownicy mogą „wybrać opcję” _ustawienia domyślnego dla wszystkich elementów_ z zachowaniem integralności wymaganych parametrów w ścieżce głównej.</span><span class="sxs-lookup"><span data-stu-id="c140b-153">`-Auto` Switch - The `-Auto` switch would provide an "opt-in" way for users to _default all the things_ while maintaining the integrity of required parameters in the mainline path.</span></span>

### <a name="feature-specific-switches"></a><span data-ttu-id="c140b-154">Przełączniki właściwe dla funkcji</span><span class="sxs-lookup"><span data-stu-id="c140b-154">Feature-specific switches</span></span>

<span data-ttu-id="c140b-155">Na przykład scenariusz „Tworzenie aplikacji internetowej” może zawierać przełącznik `-Git` lub `-AddRemote`, który automatycznie dodaje zdalne środowisko platformy „azure” do istniejącego repozytorium Git.</span><span class="sxs-lookup"><span data-stu-id="c140b-155">For example, the "Create web app" scenario might have a `-Git` or `-AddRemote` switch that would automatically add an "azure" remote to an existing git repository.</span></span>

- <span data-ttu-id="c140b-156">Wartości domyślne dostępne do konfigurowania — użytkownicy powinni mieć możliwość ustawiania wartości domyślnych dla niektórych parametrów wszechobecnych, takich jak `-ResourceGroupName` i `-Location`.</span><span class="sxs-lookup"><span data-stu-id="c140b-156">Settable Defaults - Users should have the ability to default certain ubiquitous parameters like `-ResourceGroupName` and `-Location`.</span></span>

- <span data-ttu-id="c140b-157">Rozmiary domyślne — „rozmiary” zasobów mogą być mylące dla użytkowników, ponieważ wielu dostawców zasobów używa różnych nazw (na przykład „Standardowa\_DS1\_v2” lub „S1”).</span><span class="sxs-lookup"><span data-stu-id="c140b-157">Size Defaults - Resource "sizes" can be confusing to users since many Resource Providers use different names (for example, "Standard\_DS1\_v2" or "S1").</span></span> <span data-ttu-id="c140b-158">Jednak większość użytkowników najbardziej martwi się o koszty.</span><span class="sxs-lookup"><span data-stu-id="c140b-158">However, most users care more about cost.</span></span> <span data-ttu-id="c140b-159">Z tego względu warto zdefiniować „uniwersalne” rozmiary oparte na harmonogramie cen.</span><span class="sxs-lookup"><span data-stu-id="c140b-159">Therefore, it makes sense to define "universal" sizes based on a pricing schedule.</span></span> <span data-ttu-id="c140b-160">Użytkownicy mogą wybrać konkretny rozmiar albo pozwolić programowi Azure PowerShell wybrać _najlepszą opcję_ w oparciu o budżet na zasoby.</span><span class="sxs-lookup"><span data-stu-id="c140b-160">Users can choose a specific size or let Azure PowerShell choose the _best option_ based on the resource the budget.</span></span>

- <span data-ttu-id="c140b-161">Format wyjściowy — program Azure PowerShell aktualnie zwraca obiekty `PSObject`, a ilość danych wyjściowych konsoli jest niewielka.</span><span class="sxs-lookup"><span data-stu-id="c140b-161">Output Format - Azure PowerShell currently returns `PSObject`s and there is little console output.</span></span> <span data-ttu-id="c140b-162">Program Azure PowerShell może wymagać wyświetlenia pewnych informacji dla użytkownika w odniesieniu do używanych „domyślnych ustawień inteligentnych”.</span><span class="sxs-lookup"><span data-stu-id="c140b-162">Azure PowerShell may need to display some information to the user regarding the "smart defaults" used.</span></span>

## <a name="try-using-the-experiments"></a><span data-ttu-id="c140b-163">Wypróbuj eksperymenty</span><span class="sxs-lookup"><span data-stu-id="c140b-163">Try using the experiments</span></span>

### <a name="install"></a><span data-ttu-id="c140b-164">Instalowanie</span><span class="sxs-lookup"><span data-stu-id="c140b-164">Install</span></span>

```powershell
Install-Module AzureRM.Compute.Experiments
```

### <a name="create-a-vm"></a><span data-ttu-id="c140b-165">Tworzenie maszyny wirtualnej</span><span class="sxs-lookup"><span data-stu-id="c140b-165">Create a VM</span></span>

```powershell
$job = New-AzVm -Name MyVm -AsJob
Receive-Job $job
```

### <a name="send-us-feedback"></a><span data-ttu-id="c140b-166">Wysyłanie do nas opinii</span><span class="sxs-lookup"><span data-stu-id="c140b-166">Send us feedback</span></span>

```powershell
Send-Feedback
```

### <a name="uninstall-the-experimental-modules"></a><span data-ttu-id="c140b-167">Odinstalowywanie modułów eksperymentalnych</span><span class="sxs-lookup"><span data-stu-id="c140b-167">Uninstall the experimental modules</span></span>

```powershell
Uninstall-Module AzureRM.Compute.Experiments
```