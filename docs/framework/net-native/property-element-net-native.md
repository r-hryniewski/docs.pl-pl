---
title: Element &lt;Property&gt; (architektura .NET Native)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d41e05c39f8483cc668962c53534bb531a8007ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltpropertygt-element-net-native"></a><span data-ttu-id="37b2c-102">Element &lt;Property&gt; (architektura .NET Native)</span><span class="sxs-lookup"><span data-stu-id="37b2c-102">&lt;Property&gt; Element (.NET Native)</span></span>
<span data-ttu-id="37b2c-103">Zastosowanie zasad wykonywania odbicia właściwości.</span><span class="sxs-lookup"><span data-stu-id="37b2c-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37b2c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="37b2c-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37b2c-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="37b2c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="37b2c-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="37b2c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37b2c-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="37b2c-107">Attributes</span></span>  
  
|<span data-ttu-id="37b2c-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="37b2c-108">Attribute</span></span>|<span data-ttu-id="37b2c-109">Typ atrybutu</span><span class="sxs-lookup"><span data-stu-id="37b2c-109">Attribute type</span></span>|<span data-ttu-id="37b2c-110">Opis</span><span class="sxs-lookup"><span data-stu-id="37b2c-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="37b2c-111">Ogólne</span><span class="sxs-lookup"><span data-stu-id="37b2c-111">General</span></span>|<span data-ttu-id="37b2c-112">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="37b2c-112">Required attribute.</span></span> <span data-ttu-id="37b2c-113">Określa nazwę właściwości.</span><span class="sxs-lookup"><span data-stu-id="37b2c-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="37b2c-114">Odbicie</span><span class="sxs-lookup"><span data-stu-id="37b2c-114">Reflection</span></span>|<span data-ttu-id="37b2c-115">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="37b2c-115">Optional attribute.</span></span> <span data-ttu-id="37b2c-116">Określa, czy wykonywania zapytania dotyczącego informacji o wyliczaniu właściwości, ale nie umożliwia dostępu dynamicznej w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="37b2c-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="37b2c-117">Odbicie</span><span class="sxs-lookup"><span data-stu-id="37b2c-117">Reflection</span></span>|<span data-ttu-id="37b2c-118">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="37b2c-118">Optional attribute.</span></span> <span data-ttu-id="37b2c-119">Formanty środowiska uruchomieniowego dostępu do właściwości, aby włączyć dynamiczne programowania.</span><span class="sxs-lookup"><span data-stu-id="37b2c-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="37b2c-120">Ta zasada zapewnia, że właściwość można ustawić ani pobrać dynamicznie w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="37b2c-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="37b2c-121">Serializacja</span><span class="sxs-lookup"><span data-stu-id="37b2c-121">Serialization</span></span>|<span data-ttu-id="37b2c-122">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="37b2c-122">Optional attribute.</span></span> <span data-ttu-id="37b2c-123">Formanty środowiska uruchomieniowego dostęp do właściwości w celu włączenia wystąpień typów przez biblioteki, takich jak serializator Newtonsoft JSON lub do użycia dla powiązania danych.</span><span class="sxs-lookup"><span data-stu-id="37b2c-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="37b2c-124">Nazwa atrybutu</span><span class="sxs-lookup"><span data-stu-id="37b2c-124">Name attribute</span></span>  
  
|<span data-ttu-id="37b2c-125">Wartość</span><span class="sxs-lookup"><span data-stu-id="37b2c-125">Value</span></span>|<span data-ttu-id="37b2c-126">Opis</span><span class="sxs-lookup"><span data-stu-id="37b2c-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="37b2c-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="37b2c-127">*method_name*</span></span>|<span data-ttu-id="37b2c-128">Nazwa właściwości.</span><span class="sxs-lookup"><span data-stu-id="37b2c-128">The property name.</span></span> <span data-ttu-id="37b2c-129">Typ właściwości jest zdefiniowana przez nadrzędny [ \<typu >](../../../docs/framework/net-native/type-element-net-native.md) lub [ \<TypeInstantiation >](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="37b2c-129">The type of the property is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="37b2c-130">Inne atrybuty</span><span class="sxs-lookup"><span data-stu-id="37b2c-130">All other attributes</span></span>  
  
|<span data-ttu-id="37b2c-131">Wartość</span><span class="sxs-lookup"><span data-stu-id="37b2c-131">Value</span></span>|<span data-ttu-id="37b2c-132">Opis</span><span class="sxs-lookup"><span data-stu-id="37b2c-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="37b2c-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="37b2c-133">*policy_setting*</span></span>|<span data-ttu-id="37b2c-134">To ustawienie, aby zastosować do tego typu właściwości.</span><span class="sxs-lookup"><span data-stu-id="37b2c-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="37b2c-135">Możliwe wartości to `Auto`, `Excluded`, `Included`, i `Required`.</span><span class="sxs-lookup"><span data-stu-id="37b2c-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="37b2c-136">Aby uzyskać więcej informacji, zobacz [ustawienia zasad dyrektyw środowiska uruchomieniowego](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="37b2c-136">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37b2c-137">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="37b2c-137">Child Elements</span></span>  
 <span data-ttu-id="37b2c-138">Brak.</span><span class="sxs-lookup"><span data-stu-id="37b2c-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="37b2c-139">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="37b2c-139">Parent Elements</span></span>  
  
|<span data-ttu-id="37b2c-140">Element</span><span class="sxs-lookup"><span data-stu-id="37b2c-140">Element</span></span>|<span data-ttu-id="37b2c-141">Opis</span><span class="sxs-lookup"><span data-stu-id="37b2c-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37b2c-142">\<Typ ></span><span class="sxs-lookup"><span data-stu-id="37b2c-142">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="37b2c-143">Stosuje odbicia zasady do typu i jej elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="37b2c-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="37b2c-144">\<TypeInstantiation ></span><span class="sxs-lookup"><span data-stu-id="37b2c-144">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="37b2c-145">Stosuje zasady odbicia do skonstruowanego typu ogólnego i jej elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="37b2c-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37b2c-146">Uwagi</span><span class="sxs-lookup"><span data-stu-id="37b2c-146">Remarks</span></span>  
 <span data-ttu-id="37b2c-147">Jeśli właściwość zasad nie jest jawnie zdefiniowany, dziedziczy zasad wykonywania jego elementu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="37b2c-147">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37b2c-148">Przykład</span><span class="sxs-lookup"><span data-stu-id="37b2c-148">Example</span></span>  
 <span data-ttu-id="37b2c-149">W poniższym przykładzie użyto odbicia do utworzenia wystąpienia `Book` obiektu i wyświetlić jej wartości właściwości.</span><span class="sxs-lookup"><span data-stu-id="37b2c-149">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="37b2c-150">Oryginalny plik default.rd.xml projektu wygląda następująco:</span><span class="sxs-lookup"><span data-stu-id="37b2c-150">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="37b2c-151">Zastosowanie pliku `All` do wartości `Activate` zasady dla `Book` klasy, która zezwala na dostęp do konstruktorów klasy przy użyciu odbicia.</span><span class="sxs-lookup"><span data-stu-id="37b2c-151">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="37b2c-152">`Browse` Zasady dla `Book` klasy jest dziedziczona z jej nadrzędną przestrzeń nazw.</span><span class="sxs-lookup"><span data-stu-id="37b2c-152">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="37b2c-153">Ta wartość jest równa `Required Public`, który udostępnia metadane w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="37b2c-153">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="37b2c-154">Oto przykładowy kod źródłowy.</span><span class="sxs-lookup"><span data-stu-id="37b2c-154">The following is the source code for the example.</span></span> <span data-ttu-id="37b2c-155">`outputBlock` Reprezentuje zmienną [blok tekstu](http://msdn.microsoft.com/library/windows.ui.xaml.controls.textblock.aspx) formantu.</span><span class="sxs-lookup"><span data-stu-id="37b2c-155">The `outputBlock` variable represents a [TextBlock](http://msdn.microsoft.com/library/windows.ui.xaml.controls.textblock.aspx) control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="37b2c-156">Jednakże, kompilowania i wykonywania w tym przykładzie zgłasza [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) wyjątku.</span><span class="sxs-lookup"><span data-stu-id="37b2c-156">However, compiling and executing this example throws a [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="37b2c-157">Mimo że wprowadziliśmy metadanych `Book` typ jest dostępny, już nie możemy udostępnić implementacje metody pobierające właściwości dynamicznie.</span><span class="sxs-lookup"><span data-stu-id="37b2c-157">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="37b2c-158">Firma Microsoft może rozwiązać ten problem przez w jeden z dwóch sposobów:</span><span class="sxs-lookup"><span data-stu-id="37b2c-158">We can correct this error by either in one of two ways:</span></span>  
  
-   <span data-ttu-id="37b2c-159">Definiując `Dynamic` zasady dla `Book` wpisz jego [ \<typu >](../../../docs/framework/net-native/type-element-net-native.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="37b2c-159">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element.</span></span>  
  
-   <span data-ttu-id="37b2c-160">Dodając zagnieżdżoną [ \<właściwość >](../../../docs/framework/net-native/property-element-net-native.md) dla każdej właściwości, którego metoda pobierająca chcielibyśmy do wywołania, tak jak w następującym pliku default.rd.xml.</span><span class="sxs-lookup"><span data-stu-id="37b2c-160">By adding a nested [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
    ```xml  
    <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
       <Application>  
          <Namespace Name="LibraryApplications"  Browse="Required Public" >  
             <Type Name="Book"   Activate="All" >  
                <Property Name="Title" Dynamic="Required" />  
                <Property Name="Author" Dynamic="Required" />  
                  <Property Name="ISBN" Dynamic="Required" />  
             </Type>  
          </Namespace>  
       </Application>  
    </Directives>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="37b2c-161">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="37b2c-161">See Also</span></span>  
 [<span data-ttu-id="37b2c-162">Odwołanie do pliku konfiguracji dyrektyw (rd.xml) środowiska wykonawczego</span><span class="sxs-lookup"><span data-stu-id="37b2c-162">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="37b2c-163">Elementy dyrektyw środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="37b2c-163">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="37b2c-164">Ustawienia zasad dyrektyw środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="37b2c-164">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)