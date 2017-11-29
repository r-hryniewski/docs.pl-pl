---
title: "&lt;element assemblyIdentity&gt; elementu &lt;środowiska wykonawczego&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 740b08806dff65d3ce1b8de378138c2647944fd4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltassemblyidentitygt-element-for-ltruntimegt"></a><span data-ttu-id="47147-102">&lt;element assemblyIdentity&gt; elementu &lt;środowiska wykonawczego&gt;</span><span class="sxs-lookup"><span data-stu-id="47147-102">&lt;assemblyIdentity&gt; Element for &lt;runtime&gt;</span></span>
<span data-ttu-id="47147-103">Zawiera informacje identyfikujące zestaw.</span><span class="sxs-lookup"><span data-stu-id="47147-103">Contains identifying information about the assembly.</span></span>  
  
 <span data-ttu-id="47147-104">\<Konfiguracja ></span><span class="sxs-lookup"><span data-stu-id="47147-104">\<configuration></span></span>  
<span data-ttu-id="47147-105">\<Runtime ></span><span class="sxs-lookup"><span data-stu-id="47147-105">\<runtime></span></span>  
<span data-ttu-id="47147-106">\<assemblybinding — ></span><span class="sxs-lookup"><span data-stu-id="47147-106">\<assemblyBinding></span></span>  
<span data-ttu-id="47147-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="47147-107">\<dependentAssembly></span></span>  
<span data-ttu-id="47147-108">\<element assemblyIdentity ></span><span class="sxs-lookup"><span data-stu-id="47147-108">\<assemblyIdentity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47147-109">Składnia</span><span class="sxs-lookup"><span data-stu-id="47147-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47147-110">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="47147-110">Attributes and Elements</span></span>  
 <span data-ttu-id="47147-111">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="47147-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47147-112">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="47147-112">Attributes</span></span>  
  
|<span data-ttu-id="47147-113">Atrybut</span><span class="sxs-lookup"><span data-stu-id="47147-113">Attribute</span></span>|<span data-ttu-id="47147-114">Opis</span><span class="sxs-lookup"><span data-stu-id="47147-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="47147-115">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="47147-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="47147-116">Nazwa zestawu</span><span class="sxs-lookup"><span data-stu-id="47147-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="47147-117">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="47147-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="47147-118">Ciąg, który określa język i kraj/region zestawu.</span><span class="sxs-lookup"><span data-stu-id="47147-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="47147-119">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="47147-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="47147-120">Wartość szesnastkowa, która określa silnej nazwy zestawu.</span><span class="sxs-lookup"><span data-stu-id="47147-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="47147-121">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="47147-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="47147-122">Jedna z wartości "x86", "amd64", "msil" lub "ia64", określający architektury procesora dla zestawu, który zawiera kod specyficznych dla procesora.</span><span class="sxs-lookup"><span data-stu-id="47147-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="47147-123">Wartości nie jest rozróżniana.</span><span class="sxs-lookup"><span data-stu-id="47147-123">The values are not case-sensitive.</span></span> <span data-ttu-id="47147-124">Jeśli ten atrybut jest przypisany wszelkie inne wartości, całą `<assemblyIdentity>` element jest ignorowana.</span><span class="sxs-lookup"><span data-stu-id="47147-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="47147-125">Zobacz <xref:System.Reflection.ProcessorArchitecture>.</span><span class="sxs-lookup"><span data-stu-id="47147-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="47147-126">Element processorArchitecture atrybutu</span><span class="sxs-lookup"><span data-stu-id="47147-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="47147-127">Wartość</span><span class="sxs-lookup"><span data-stu-id="47147-127">Value</span></span>|<span data-ttu-id="47147-128">Opis</span><span class="sxs-lookup"><span data-stu-id="47147-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="47147-129">64-bitowy procesor AMD tylko.</span><span class="sxs-lookup"><span data-stu-id="47147-129">A 64-bit AMD processor only.</span></span>|  
|`ia64`|<span data-ttu-id="47147-130">64-bitowy procesor Intel tylko.</span><span class="sxs-lookup"><span data-stu-id="47147-130">A 64-bit Intel processor only.</span></span>|  
|`msil`|<span data-ttu-id="47147-131">Neutralna względem procesora i usługi bits dla programu word</span><span class="sxs-lookup"><span data-stu-id="47147-131">Neutral with respect to processor and bits-per-word</span></span>|  
|`x86`|<span data-ttu-id="47147-132">32-bitowy procesor Intel, albo natywne lub w systemie Windows w środowisku Windows (WOW) w 64-bitowej platformy.</span><span class="sxs-lookup"><span data-stu-id="47147-132">A 32-bit Intel processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47147-133">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="47147-133">Child Elements</span></span>  
 <span data-ttu-id="47147-134">Brak.</span><span class="sxs-lookup"><span data-stu-id="47147-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="47147-135">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="47147-135">Parent Elements</span></span>  
  
|<span data-ttu-id="47147-136">Element</span><span class="sxs-lookup"><span data-stu-id="47147-136">Element</span></span>|<span data-ttu-id="47147-137">Opis</span><span class="sxs-lookup"><span data-stu-id="47147-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="47147-138">Zawiera informacje o przekierowaniu wersji zestawu i lokalizacji zestawów.</span><span class="sxs-lookup"><span data-stu-id="47147-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="47147-139">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="47147-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="47147-140">Hermetyzuje zasady powiązań oraz lokalizację zestawu dla każdego zestawu.</span><span class="sxs-lookup"><span data-stu-id="47147-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="47147-141">Użyj jednej `<dependentAssembly>` elementu dla każdego zestawu.</span><span class="sxs-lookup"><span data-stu-id="47147-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="47147-142">Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="47147-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47147-143">Uwagi</span><span class="sxs-lookup"><span data-stu-id="47147-143">Remarks</span></span>  
 <span data-ttu-id="47147-144">Każdy  **\<dependentAssembly >** element musi mieć jeden  **\<assemblyIdentity >** element podrzędny.</span><span class="sxs-lookup"><span data-stu-id="47147-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="47147-145">Jeśli `processorArchitecture` jest obecny, atrybut `<assemblyIdentity>` element ma zastosowanie tylko do zestawu z odpowiedniej architektury procesora.</span><span class="sxs-lookup"><span data-stu-id="47147-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="47147-146">Jeśli `processorArchitecture` atrybut nie jest obecny, `<assemblyIdentity>` elementu można zastosować do zestawu z dowolnej architektury procesora.</span><span class="sxs-lookup"><span data-stu-id="47147-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="47147-147">W poniższym przykładzie przedstawiono plik konfiguracji dla dwóch zestawów o takiej samej nazwie, która docelowa dwie różne architektury procesora dwóch i których wersje ma nie została zachowana zsynchronizowany. Gdy aplikacja wykonuje na x86 platformy pierwszy `<assemblyIdentity>` element ma zastosowanie i innych jest ignorowana.</span><span class="sxs-lookup"><span data-stu-id="47147-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="47147-148">Jeśli aplikacja jest wykonywana na platformie niż x86 lub ia64, obie są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="47147-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"   
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"   
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"   
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="47147-149">Jeśli plik konfiguracji zawiera `<assemblyIdentity>` elementu bez `processorArchitecture` atrybutu, a nie zawiera element, który odpowiada platformie elementu bez `processorArchitecture` atrybut jest używany.</span><span class="sxs-lookup"><span data-stu-id="47147-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47147-150">Przykład</span><span class="sxs-lookup"><span data-stu-id="47147-150">Example</span></span>  
 <span data-ttu-id="47147-151">Poniższy przykład pokazuje, jak o podanie informacji o zestawie.</span><span class="sxs-lookup"><span data-stu-id="47147-151">The following example shows how to provide information about an assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="47147-152">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="47147-152">See Also</span></span>  
 [<span data-ttu-id="47147-153">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="47147-153">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="47147-154">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="47147-154">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="47147-155">Przekierowywanie wersji zestawu</span><span class="sxs-lookup"><span data-stu-id="47147-155">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)