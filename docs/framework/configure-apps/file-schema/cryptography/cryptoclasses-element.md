---
title: "&lt;cryptoclasses —&gt; — Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
caps.latest.revision: "16"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7ed25fa1a2bdedc410fccf48802742766287c438
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltcryptoclassesgt-element"></a><span data-ttu-id="51f6e-102">&lt;cryptoclasses —&gt; — Element</span><span class="sxs-lookup"><span data-stu-id="51f6e-102">&lt;cryptoClasses&gt; Element</span></span>
<span data-ttu-id="51f6e-103">Zawiera listę klasy kryptografii, które ma mapowania do przyjazną nazwę w [ \<nameentry — >](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="51f6e-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="51f6e-104">\<Konfiguracja ></span><span class="sxs-lookup"><span data-stu-id="51f6e-104">\<configuration></span></span>  
<span data-ttu-id="51f6e-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="51f6e-105">\<mscorlib></span></span>  
<span data-ttu-id="51f6e-106">\<cryptographysettings — ></span><span class="sxs-lookup"><span data-stu-id="51f6e-106">\<cryptographySettings></span></span>  
<span data-ttu-id="51f6e-107">\<cryptonamemapping — ></span><span class="sxs-lookup"><span data-stu-id="51f6e-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="51f6e-108">\<cryptoclasses — ></span><span class="sxs-lookup"><span data-stu-id="51f6e-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51f6e-109">Składnia</span><span class="sxs-lookup"><span data-stu-id="51f6e-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51f6e-110">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="51f6e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="51f6e-111">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="51f6e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51f6e-112">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="51f6e-112">Attributes</span></span>  
 <span data-ttu-id="51f6e-113">Brak.</span><span class="sxs-lookup"><span data-stu-id="51f6e-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="51f6e-114">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="51f6e-114">Child Elements</span></span>  
  
|<span data-ttu-id="51f6e-115">Element</span><span class="sxs-lookup"><span data-stu-id="51f6e-115">Element</span></span>|<span data-ttu-id="51f6e-116">Opis</span><span class="sxs-lookup"><span data-stu-id="51f6e-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51f6e-117">\<cryptoclass — ></span><span class="sxs-lookup"><span data-stu-id="51f6e-117">\<cryptoClass></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="51f6e-118">Zawiera klasy kryptografii, która ma mapowania przyjazną nazwę w  **\<nameentry — >** elementu.</span><span class="sxs-lookup"><span data-stu-id="51f6e-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="51f6e-119">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="51f6e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="51f6e-120">Element</span><span class="sxs-lookup"><span data-stu-id="51f6e-120">Element</span></span>|<span data-ttu-id="51f6e-121">Opis</span><span class="sxs-lookup"><span data-stu-id="51f6e-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="51f6e-122">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="51f6e-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="51f6e-123">Zawiera ustawienia szyfrowania.</span><span class="sxs-lookup"><span data-stu-id="51f6e-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="51f6e-124">Zawiera mapowania klasy przyjazne nazwy.</span><span class="sxs-lookup"><span data-stu-id="51f6e-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="51f6e-125">Zawiera `cryptographySettings` elementu.</span><span class="sxs-lookup"><span data-stu-id="51f6e-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="51f6e-126">Przykład</span><span class="sxs-lookup"><span data-stu-id="51f6e-126">Example</span></span>  
 <span data-ttu-id="51f6e-127">Poniższy przykład przedstawia sposób użycia  **\<cryptoclass — >** element odwołuje się do klasy kryptografii i skonfigurować środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="51f6e-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="51f6e-128">Ciąg "RSA" można następnie przekazać do <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> — metoda i użyj <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> metodę, aby zwrócić `MyCryptoRSAClass` obiektu.</span><span class="sxs-lookup"><span data-stu-id="51f6e-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="51f6e-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="51f6e-129">See Also</span></span>  
 <xref:System.Security.Cryptography>  
 [<span data-ttu-id="51f6e-130">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="51f6e-130">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="51f6e-131">Schemat ustawień kryptografii</span><span class="sxs-lookup"><span data-stu-id="51f6e-131">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="51f6e-132">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="51f6e-132">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="51f6e-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="51f6e-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)  
 [<span data-ttu-id="51f6e-134">Konfigurowanie klasy kryptografii</span><span class="sxs-lookup"><span data-stu-id="51f6e-134">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)