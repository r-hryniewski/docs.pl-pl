---
title: '&lt;bindingExtensions&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c02af972ad52119af07da404a61fd3afc0facbeb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="ltbindingextensionsgt"></a><span data-ttu-id="d524e-102">&lt;bindingExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="d524e-102">&lt;bindingExtensions&gt;</span></span>
<span data-ttu-id="d524e-103">Ta sekcja umożliwia korzystanie z powiązania z maszyny zdefiniowanego przez użytkownika lub pliku konfiguracji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d524e-103">This section enables the use of a user defined binding from a machine or application configuration file.</span></span> <span data-ttu-id="d524e-104">Można dodać powiązania do tej kolekcji przy użyciu zdefiniowanego przez użytkownika `add` — słowo kluczowe i ustawienie `type` atrybutu elementu powiązania, zdefiniowanego przez użytkownika, jak również `name` powiązania zdefiniowanych dla atrybutu nazwy użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d524e-104">You can add a user defined binding to this collection by using the `add` keyword, and setting the `type` attribute of the element to a user defined binding, as well as the `name` attribute to the name of the user defined binding.</span></span>  
  
 <span data-ttu-id="d524e-105">Powiązanie rozszerzeniom użytkownikowi utworzenie powiązań zdefiniowanych przez użytkownika jako część konfiguracji punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="d524e-105">Binding extensions enable the user to create user-defined bindings for use as part an endpoint configuration.</span></span> <span data-ttu-id="d524e-106">Programowo, rozszerzenia powiązania jest typu, który implementuje klasy abstrakcyjnej <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="d524e-106">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.Binding>.</span></span>  
  
 <span data-ttu-id="d524e-107">W poniższym przykładzie użyto `add` elementu, jak również `name` atrybutu, aby dodać rozszerzenie powiązania do `bindingElementExtensions` sekcji pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="d524e-107">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingElementExtensions` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <bindingExtensions>  
           <add name="MyBinding" type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </bindingExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="d524e-108">Aby dodać możliwości konfiguracji do elementu, użytkownik musi zapisać i Zarejestruj `bindingSection` elementu.</span><span class="sxs-lookup"><span data-stu-id="d524e-108">To add configuration abilities to the element, the user needs to write and register a `bindingSection` element.</span></span> <span data-ttu-id="d524e-109">Aby uzyskać więcej informacji o tym, zobacz <xref:System.Configuration> dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="d524e-109">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="d524e-110">Po zdefiniowaniu elementu i jego typ Konfiguracja rozszerzenia może służyć jako część punktu końcowego jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="d524e-110">After the element and its configuration type are defined, the extension can be used as part of an endpoint as shown in the following example.</span></span>  
  
```xml  
<services>  
    <service name="MyService">  
        <endpoint address="myAddress" binding="MyBinding" />  
    </service>  
</services>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d524e-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d524e-111">See Also</span></span>  
 [<span data-ttu-id="d524e-112">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="d524e-112">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)