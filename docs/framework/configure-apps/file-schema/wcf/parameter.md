---
title: '&lt;Parametr&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e9db1921e2a6ee1ae2780f744c45fdb25efbf797
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltparametergt"></a><span data-ttu-id="6eaa7-102">&lt;Parametr&gt;</span><span class="sxs-lookup"><span data-stu-id="6eaa7-102">&lt;parameter&gt;</span></span>
<span data-ttu-id="6eaa7-103">Określa parametr generyczny, gdy deklarowany typ jest typem ogólnym.</span><span class="sxs-lookup"><span data-stu-id="6eaa7-103">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="6eaa7-104">\<System.Runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="6eaa7-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="6eaa7-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="6eaa7-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="6eaa7-106">\<declaredTypes > — Element</span><span class="sxs-lookup"><span data-stu-id="6eaa7-106">\<declaredTypes> Element</span></span>  
<span data-ttu-id="6eaa7-107">\<Dodaj > elementu \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="6eaa7-107">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="6eaa7-108">\<Typ knownType > — Element</span><span class="sxs-lookup"><span data-stu-id="6eaa7-108">\<knownType> Element</span></span>  
<span data-ttu-id="6eaa7-109">\<Parametr > — Element</span><span class="sxs-lookup"><span data-stu-id="6eaa7-109">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eaa7-110">Składnia</span><span class="sxs-lookup"><span data-stu-id="6eaa7-110">Syntax</span></span>  
  
```xml  
<parameter index="integer"  
                      type=String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6eaa7-111">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="6eaa7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6eaa7-112">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="6eaa7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6eaa7-113">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="6eaa7-113">Attributes</span></span>  
  
|<span data-ttu-id="6eaa7-114">Atrybut</span><span class="sxs-lookup"><span data-stu-id="6eaa7-114">Attribute</span></span>|<span data-ttu-id="6eaa7-115">Opis</span><span class="sxs-lookup"><span data-stu-id="6eaa7-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6eaa7-116">indeks</span><span class="sxs-lookup"><span data-stu-id="6eaa7-116">index</span></span>|<span data-ttu-id="6eaa7-117">Gdy deklarowany typ jest typem ogólnym, określa parametr generyczny, który zwróci typ znany.</span><span class="sxs-lookup"><span data-stu-id="6eaa7-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="6eaa7-118">— typ</span><span class="sxs-lookup"><span data-stu-id="6eaa7-118">type</span></span>|<span data-ttu-id="6eaa7-119">Ciąg opisujący znany typ używany do serializacji i deserializacji.</span><span class="sxs-lookup"><span data-stu-id="6eaa7-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="6eaa7-120">Indeks atrybut</span><span class="sxs-lookup"><span data-stu-id="6eaa7-120">index Attribute</span></span>  
  
|<span data-ttu-id="6eaa7-121">Wartość</span><span class="sxs-lookup"><span data-stu-id="6eaa7-121">Value</span></span>|<span data-ttu-id="6eaa7-122">Opis</span><span class="sxs-lookup"><span data-stu-id="6eaa7-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6eaa7-123">„0”</span><span class="sxs-lookup"><span data-stu-id="6eaa7-123">"0"</span></span>|<span data-ttu-id="6eaa7-124">Pierwszy parametr typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="6eaa7-124">The first parameter in the generic type.</span></span> <span data-ttu-id="6eaa7-125">Na przykład <xref:System.Collections.Generic.List%601> ma tylko jeden parametr.</span><span class="sxs-lookup"><span data-stu-id="6eaa7-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="6eaa7-126">Jeśli jest on używany jako deklarowanego typu, indeks ustawiał "0".</span><span class="sxs-lookup"><span data-stu-id="6eaa7-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="6eaa7-127">"1"</span><span class="sxs-lookup"><span data-stu-id="6eaa7-127">"1"</span></span>|<span data-ttu-id="6eaa7-128">Drugi parametr typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="6eaa7-128">The second parameter in a generic type.</span></span> <span data-ttu-id="6eaa7-129">Na przykład <xref:System.Collections.Generic.Dictionary%602> zawiera dwa parametry.</span><span class="sxs-lookup"><span data-stu-id="6eaa7-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="6eaa7-130">Jeśli drugi parametr zwracany jest znanym typem, ustaw dla atrybutu indeksu "1".</span><span class="sxs-lookup"><span data-stu-id="6eaa7-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6eaa7-131">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="6eaa7-131">Child Elements</span></span>  
 <span data-ttu-id="6eaa7-132">Brak.</span><span class="sxs-lookup"><span data-stu-id="6eaa7-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6eaa7-133">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="6eaa7-133">Parent Elements</span></span>  
  
|<span data-ttu-id="6eaa7-134">Element</span><span class="sxs-lookup"><span data-stu-id="6eaa7-134">Element</span></span>|<span data-ttu-id="6eaa7-135">Opis</span><span class="sxs-lookup"><span data-stu-id="6eaa7-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6eaa7-136">\<Typ knownType ></span><span class="sxs-lookup"><span data-stu-id="6eaa7-136">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="6eaa7-137">Określa znanym typem, który może być zwracany przez pole lub właściwość deklarowanego typu.</span><span class="sxs-lookup"><span data-stu-id="6eaa7-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6eaa7-138">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6eaa7-138">Remarks</span></span>  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="6eaa7-139">znane typy, zobacz [znane typy kontraktu danych](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) i <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6eaa7-139"> known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="6eaa7-140">Zobacz [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) przykład za pomocą tego elementu.</span><span class="sxs-lookup"><span data-stu-id="6eaa7-140">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="6eaa7-141">Ten element konfiguracji nie może mieć obu atrybutów, w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="6eaa7-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="6eaa7-142">Jeśli oba atrybuty są ustawione, <xref:System.Configuration.ConfigurationErrorsException> występuje.</span><span class="sxs-lookup"><span data-stu-id="6eaa7-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eaa7-143">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6eaa7-143">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="6eaa7-144">Znane typy kontraktów danych</span><span class="sxs-lookup"><span data-stu-id="6eaa7-144">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="6eaa7-145">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="6eaa7-145">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="6eaa7-146">\<Dodaj ></span><span class="sxs-lookup"><span data-stu-id="6eaa7-146">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)