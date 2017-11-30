---
title: '&lt;transport&gt; w &lt;ws2007HttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 31c5404b29f025af5193386eccafdbeab95cb2cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltws2007httpbindinggt"></a><span data-ttu-id="9a0cb-102">&lt;transport&gt; w &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="9a0cb-102">&lt;transport&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="9a0cb-103">Definiuje ustawienia uwierzytelniania dla transportu HTTP.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="9a0cb-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="9a0cb-104">\<system.serviceModel></span></span>  
<span data-ttu-id="9a0cb-105">\<powiązania ></span><span class="sxs-lookup"><span data-stu-id="9a0cb-105">\<bindings></span></span>  
<span data-ttu-id="9a0cb-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="9a0cb-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="9a0cb-107">\<Powiązanie ></span><span class="sxs-lookup"><span data-stu-id="9a0cb-107">\<binding></span></span>  
<span data-ttu-id="9a0cb-108">\<Zabezpieczenia ></span><span class="sxs-lookup"><span data-stu-id="9a0cb-108">\<security></span></span>  
<span data-ttu-id="9a0cb-109">\<transport ></span><span class="sxs-lookup"><span data-stu-id="9a0cb-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a0cb-110">Składnia</span><span class="sxs-lookup"><span data-stu-id="9a0cb-110">Syntax</span></span>  
  
```  
transport clientCredentialType =   
       "Basic/Certificate/Digest/None/Ntlm/Windows"  
       proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
       realm="string"   
```  
  
## <a name="type"></a><span data-ttu-id="9a0cb-111">Typ</span><span class="sxs-lookup"><span data-stu-id="9a0cb-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a0cb-112">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="9a0cb-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9a0cb-113">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a0cb-114">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="9a0cb-114">Attributes</span></span>  
  
|<span data-ttu-id="9a0cb-115">Atrybut</span><span class="sxs-lookup"><span data-stu-id="9a0cb-115">Attribute</span></span>|<span data-ttu-id="9a0cb-116">Opis</span><span class="sxs-lookup"><span data-stu-id="9a0cb-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="9a0cb-117">Określa poświadczenia używane do uwierzytelniania klienta do usługi.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="9a0cb-118">Ten atrybut jest typu <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="9a0cb-119">Określa poświadczenia używane do uwierzytelniania klienta na serwerze proxy domeny.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="9a0cb-120">Ten atrybut jest typu <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="9a0cb-121">Obszar uwierzytelniania dla uwierzytelniania podstawowego lub szyfrowanego.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="9a0cb-122">Wartość domyślna to ciąg pusty.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="9a0cb-123">Obszar uwierzytelniania określa co najmniej nazwę hosta, który przeprowadza uwierzytelnianie.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="9a0cb-124">Można również określić zbiór użytkowników, którzy mają dostęp.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="9a0cb-125">Użytkownik może zapytania obszaru uwierzytelniania, aby określić jedną z kilku możliwych nazwy użytkowników i hasła może służyć.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="9a0cb-126">właściwości ClientCredentialType o wartości atrybutu</span><span class="sxs-lookup"><span data-stu-id="9a0cb-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9a0cb-127">Wartość</span><span class="sxs-lookup"><span data-stu-id="9a0cb-127">Value</span></span>|<span data-ttu-id="9a0cb-128">Opis</span><span class="sxs-lookup"><span data-stu-id="9a0cb-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9a0cb-129">Brak</span><span class="sxs-lookup"><span data-stu-id="9a0cb-129">None</span></span>|<span data-ttu-id="9a0cb-130">Zabezpieczenia są wyłączone.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-130">Security is disabled.</span></span>|  
|<span data-ttu-id="9a0cb-131">Podstawowy</span><span class="sxs-lookup"><span data-stu-id="9a0cb-131">Basic</span></span>|<span data-ttu-id="9a0cb-132">Korzysta z uwierzytelniania podstawowego.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="9a0cb-133">Skrót</span><span class="sxs-lookup"><span data-stu-id="9a0cb-133">Digest</span></span>|<span data-ttu-id="9a0cb-134">Uwierzytelnianie szyfrowane używa.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="9a0cb-135">Uwierzytelnianie NTLM</span><span class="sxs-lookup"><span data-stu-id="9a0cb-135">Ntlm</span></span>|<span data-ttu-id="9a0cb-136">Korzysta z uwierzytelniania NTLM, jako rezerwowe z domeny systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="9a0cb-137">Windows</span><span class="sxs-lookup"><span data-stu-id="9a0cb-137">Windows</span></span>|<span data-ttu-id="9a0cb-138">Używa zintegrowanego uwierzytelniania systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="9a0cb-139">certyfikat</span><span class="sxs-lookup"><span data-stu-id="9a0cb-139">Certificate</span></span>|<span data-ttu-id="9a0cb-140">Używa certyfikatów X.509 do uwierzytelniania klienta.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="9a0cb-141">proxyCredentialType atrybutu</span><span class="sxs-lookup"><span data-stu-id="9a0cb-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9a0cb-142">Wartość</span><span class="sxs-lookup"><span data-stu-id="9a0cb-142">Value</span></span>|<span data-ttu-id="9a0cb-143">Opis</span><span class="sxs-lookup"><span data-stu-id="9a0cb-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9a0cb-144">Brak</span><span class="sxs-lookup"><span data-stu-id="9a0cb-144">None</span></span>|<span data-ttu-id="9a0cb-145">Zabezpieczenia są wyłączone.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-145">Security is disabled.</span></span>|  
|<span data-ttu-id="9a0cb-146">Podstawowy</span><span class="sxs-lookup"><span data-stu-id="9a0cb-146">Basic</span></span>|<span data-ttu-id="9a0cb-147">Korzysta z uwierzytelniania podstawowego.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="9a0cb-148">Skrót</span><span class="sxs-lookup"><span data-stu-id="9a0cb-148">Digest</span></span>|<span data-ttu-id="9a0cb-149">Uwierzytelnianie szyfrowane używa.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="9a0cb-150">Uwierzytelnianie NTLM</span><span class="sxs-lookup"><span data-stu-id="9a0cb-150">Ntlm</span></span>|<span data-ttu-id="9a0cb-151">Używa protokołu NTLM jako rezerwowe z domeny systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="9a0cb-152">Windows</span><span class="sxs-lookup"><span data-stu-id="9a0cb-152">Windows</span></span>|<span data-ttu-id="9a0cb-153">Używa zintegrowanego uwierzytelniania systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="9a0cb-154">certyfikat</span><span class="sxs-lookup"><span data-stu-id="9a0cb-154">Certificate</span></span>|<span data-ttu-id="9a0cb-155">Używa certyfikatów X.509 do uwierzytelniania klienta.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a0cb-156">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="9a0cb-156">Child Elements</span></span>  
 <span data-ttu-id="9a0cb-157">Brak</span><span class="sxs-lookup"><span data-stu-id="9a0cb-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a0cb-158">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="9a0cb-158">Parent Elements</span></span>  
  
|<span data-ttu-id="9a0cb-159">Element</span><span class="sxs-lookup"><span data-stu-id="9a0cb-159">Element</span></span>|<span data-ttu-id="9a0cb-160">Opis</span><span class="sxs-lookup"><span data-stu-id="9a0cb-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a0cb-161">\<Zabezpieczenia ></span><span class="sxs-lookup"><span data-stu-id="9a0cb-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|<span data-ttu-id="9a0cb-162">Reprezentuje możliwości zabezpieczeń [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="9a0cb-162">Represents the security capabilities of the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a0cb-163">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9a0cb-163">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>  
 [<span data-ttu-id="9a0cb-164">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="9a0cb-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="9a0cb-165">Powiązania</span><span class="sxs-lookup"><span data-stu-id="9a0cb-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="9a0cb-166">Konfigurowanie powiązań dostarczanych przez System</span><span class="sxs-lookup"><span data-stu-id="9a0cb-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="9a0cb-167">Konfigurowanie usług Windows Communication Foundation i klientów za pomocą powiązań</span><span class="sxs-lookup"><span data-stu-id="9a0cb-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="9a0cb-168">\<Powiązanie ></span><span class="sxs-lookup"><span data-stu-id="9a0cb-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)