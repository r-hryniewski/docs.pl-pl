---
title: Wprowadzenie Tutorial1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], getting started
- Windows Communication Foundation [WCF], getting started
- getting started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
caps.latest.revision: "47"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5f34ac7ec2761efda640e3c4838a5f44f2e244e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="getting-started-tutorial"></a><span data-ttu-id="87249-102">Wprowadzenie — samouczek</span><span class="sxs-lookup"><span data-stu-id="87249-102">Getting Started Tutorial</span></span>
<span data-ttu-id="87249-103">Tematy zawarte w tej sekcji mają na celu umożliwiają szybkie narażenia na [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] środowisko programowania.</span><span class="sxs-lookup"><span data-stu-id="87249-103">The topics contained in this section are intended to give you quick exposure to the [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] programming experience.</span></span> <span data-ttu-id="87249-104">Są one przeznaczone do wypełnienia kolejności na liście w dolnej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="87249-104">They are designed to be completed in the order of the list at the bottom of this topic.</span></span> <span data-ttu-id="87249-105">Ten samouczek umożliwia poznanie wprowadzające kroków wymaganych do utworzenia [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] usługi i aplikacje klienckie.</span><span class="sxs-lookup"><span data-stu-id="87249-105">Working through this tutorial gives you an introductory understanding of the steps required to create [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service and client applications.</span></span> <span data-ttu-id="87249-106">Usługa udostępnia jeden lub więcej punktów końcowych, z których każdy ujawnia co najmniej jedną operację usługi.</span><span class="sxs-lookup"><span data-stu-id="87249-106">A service exposes one or more endpoints, each of which exposes one or more service operations.</span></span> <span data-ttu-id="87249-107">*Punktu końcowego* usługi Określa adres, gdzie można znaleźć usługi, powiązania, który zawiera informacje opisujące, jak klient musi komunikować się z usługą i kontrakt definiujący funkcje udostępniony przez usługę klientom.</span><span class="sxs-lookup"><span data-stu-id="87249-107">The *endpoint* of a service specifies an address where the service can be found, a binding that contains the information that describes how a client must communicate with the service, and a contract that defines the functionality provided by the service to its clients.</span></span>  
  
 <span data-ttu-id="87249-108">Po zakończeniu pracy z sekwencją tematów w tym samouczku, będzie mieć uruchomioną usługę i klienta, który wywołuje usługę.</span><span class="sxs-lookup"><span data-stu-id="87249-108">After you work through the sequence of topics in this tutorial, you will have a running service, and a client that calls the service.</span></span> <span data-ttu-id="87249-109">Pierwsze trzy tematach opisano, jak definiowanie kontraktu usługi, jak Implementowanie kontraktu usługi oraz sposobu obsługi usługi.</span><span class="sxs-lookup"><span data-stu-id="87249-109">The first three topics describe how to define a service contract, how to implement the service contract, and how to host the service.</span></span> <span data-ttu-id="87249-110">Usługa, która jest tworzona jest samodzielnie hostowana w aplikacji konsoli.</span><span class="sxs-lookup"><span data-stu-id="87249-110">The service that is created is self-hosted within a console application.</span></span> <span data-ttu-id="87249-111">Usługi również może być hostowana w obszarze usługi Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="87249-111">Services can also be hosted under Internet Information Services (IIS).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="87249-112">jak to zrobić, zobacz [porady: hostowanie usługi WCF w programie IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="87249-112"> how to do this, see [How to: Host a WCF Service in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span> <span data-ttu-id="87249-113">Usługa jest skonfigurowana w kodzie; Jednak usługi, można również skonfigurować w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="87249-113">The service is configured in code; however, services can also be configured within a configuration file.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="87249-114">Zobacz użycie pliku konfiguracji [Konfigurowanie usług za pomocą plików konfiguracji](../../../docs/framework/wcf/configuring-services-using-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="87249-114"> using a configuration file see [Configuring Services Using Configuration Files](../../../docs/framework/wcf/configuring-services-using-configuration-files.md).</span></span>  
  
 <span data-ttu-id="87249-115">W trzech kolejnych tematach opisano sposób tworzenia serwera proxy klienta, konfigurowania aplikacji klienckiej i użyć serwera proxy klienta do wywołania operacji usługi udostępniane przez usługę.</span><span class="sxs-lookup"><span data-stu-id="87249-115">The next three topics describe how to create a client proxy, configure the client application, and use the client proxy to call service operation exposed by the service.</span></span> <span data-ttu-id="87249-116">Usługi Publikowanie metadanych, który definiuje informacje potrzebne do komunikowania się z usługi aplikacji klienckiej.</span><span class="sxs-lookup"><span data-stu-id="87249-116">Services publish metadata that define the information a client application needs to communicate with the service.</span></span> [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]<span data-ttu-id="87249-117">automatyzuje proces uzyskiwania dostępu do metadanych i używa go do tworzenia i konfigurowania aplikacji klienckiej dla usługi.</span><span class="sxs-lookup"><span data-stu-id="87249-117"> automates the process of accessing this metadata and uses it to construct and configure the client application for the service.</span></span> <span data-ttu-id="87249-118">Jeśli nie używasz [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], można użyć [narzędzie narzędzia metadanych elementu ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) utworzyć i skonfigurować aplikację klienta dla usługi.</span><span class="sxs-lookup"><span data-stu-id="87249-118">If you are not using [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], you can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to construct and configure the client application for the service.</span></span>  
  
 <span data-ttu-id="87249-119">We wszystkich tematach w tej sekcji założono, że używasz programu Visual Studio 2011 jako Środowisko deweloperskie.</span><span class="sxs-lookup"><span data-stu-id="87249-119">All of the topics in this section assume you are using Visual Studio 2011 as the development environment.</span></span> <span data-ttu-id="87249-120">Jeśli korzystasz z innego środowiska projektowania, Pomiń [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] szczegółowych instrukcji.</span><span class="sxs-lookup"><span data-stu-id="87249-120">If you are using another development environment, ignore the [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] specific instructions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87249-121">Jeśli używasz [!INCLUDE[wv](../../../includes/wv-md.md)] lub nowszymi wersjami systemu operacyjnego Windows, należy uruchomić [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] , przechodząc do Start menu i programu Visual Studio 2011 kliknięcie prawym przyciskiem myszy i wybierając **Uruchom jako Administrator**.</span><span class="sxs-lookup"><span data-stu-id="87249-121">If you are running [!INCLUDE[wv](../../../includes/wv-md.md)] or later versions of the Windows operating system, you must start [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] by going to the Start menu and right clicking Visual Studio 2011 and selecting **Run as Administrator**.</span></span> <span data-ttu-id="87249-122">Można zawsze uruchomić programu Visual Studio 2011 jako administrator możesz można tworzenia skrótów, kliknij prawym przyciskiem myszy skrótów, wybierz polecenie Właściwości, wybierz **zgodności** i sprawdź **uruchomić ten program jako administrator** wyboru.</span><span class="sxs-lookup"><span data-stu-id="87249-122">To always launch Visual Studio 2011 as an administrator you can create a short cut, right click the short cut, select properties, select the **Compatibility** tab, and check the **Run this program as an administrator** checkbox.</span></span> <span data-ttu-id="87249-123">Po uruchomieniu programu Visual Studio 2011 z ten skrót będzie zawsze Uruchom jako administrator.</span><span class="sxs-lookup"><span data-stu-id="87249-123">When you start Visual Studio 2011 with this shortcut, it will always run as administrator.</span></span>  
  
 <span data-ttu-id="87249-124">Dla aplikacji przykładowej, które może być pobierany na dysku twardym i uruchom można znaleźć w tematach w [przykładów Windows Communication Foundation](http://msdn.microsoft.com/en-us/8ec9d192-5d81-4f64-bfd3-90c5e5858c91).</span><span class="sxs-lookup"><span data-stu-id="87249-124">For sample applications that can be downloaded to your hard disk and run, see the topics in [Windows Communication Foundation Samples](http://msdn.microsoft.com/en-us/8ec9d192-5d81-4f64-bfd3-90c5e5858c91).</span></span> <span data-ttu-id="87249-125">W tym temacie można znaleźć, w szczególności [wprowadzenie](../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="87249-125">For this topic, see, in particular, the [Getting Started](../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
 <span data-ttu-id="87249-126">Aby uzyskać więcej szczegółowych informacji o tworzeniu usług i klientów, zobacz [podstawowe programowania WCF](../../../docs/framework/wcf/basic-wcf-programming.md).</span><span class="sxs-lookup"><span data-stu-id="87249-126">For more in-depth information about creating services and clients, see [Basic WCF Programming](../../../docs/framework/wcf/basic-wcf-programming.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="87249-127">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="87249-127">In This Section</span></span>  
 [<span data-ttu-id="87249-128">Porady: definiowanie kontraktu usługi</span><span class="sxs-lookup"><span data-stu-id="87249-128">How to: Define a Service Contract</span></span>](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 <span data-ttu-id="87249-129">Opisuje sposób tworzenia [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] kontraktu przy użyciu interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="87249-129">Describes how to create a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] contract using a user-defined interface.</span></span> <span data-ttu-id="87249-130">Kontrakt definiuje funkcji udostępnianych przez usługę.</span><span class="sxs-lookup"><span data-stu-id="87249-130">The contract defines the functionality exposed by the service.</span></span>  
  
 [<span data-ttu-id="87249-131">Porady: Implementowanie kontraktu usługi</span><span class="sxs-lookup"><span data-stu-id="87249-131">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 <span data-ttu-id="87249-132">Opisuje sposób Implementowanie kontraktu usługi.</span><span class="sxs-lookup"><span data-stu-id="87249-132">Describes how to implement a service contract.</span></span> <span data-ttu-id="87249-133">Gdy kontrakt jest zdefiniowanie, musi być implementowana z klasą usługi.</span><span class="sxs-lookup"><span data-stu-id="87249-133">Once a contract is define, it must be implemented with a service class.</span></span>  
  
 [<span data-ttu-id="87249-134">Porady: hostowanie i uruchamianie podstawowej usługi</span><span class="sxs-lookup"><span data-stu-id="87249-134">How to: Host and Run a Basic Service</span></span>](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md)  
 <span data-ttu-id="87249-135">Zawiera opis sposobu konfigurowania punktu końcowego usługi w kodzie i obsługiwać usługę w aplikacji konsoli.</span><span class="sxs-lookup"><span data-stu-id="87249-135">Describes how to configure an endpoint for the service in code and how to host the service in a console application.</span></span> <span data-ttu-id="87249-136">Staje się aktywny, usługi należy skonfigurować i hostowany w środowisku czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="87249-136">To become active, a service must be configured and hosted within a run-time environment.</span></span> <span data-ttu-id="87249-137">To środowisko tworzy usługi i formanty jego kontekstu i okresem istnienia.</span><span class="sxs-lookup"><span data-stu-id="87249-137">This environment creates the service and controls its context and lifetime.</span></span>  
  
 [<span data-ttu-id="87249-138">Porady: Tworzenie klienta</span><span class="sxs-lookup"><span data-stu-id="87249-138">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 <span data-ttu-id="87249-139">Zawiera opis sposobu pobierania metadanych używany do tworzenia [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proxy klienta z [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] usługi.</span><span class="sxs-lookup"><span data-stu-id="87249-139">Describes how to retrieve metadata used to create a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client proxy from a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="87249-140">Ten proces korzysta z funkcji Dodaj odwołanie do usługi w programie Visual Studio 2011.</span><span class="sxs-lookup"><span data-stu-id="87249-140">This process uses the Add Service Reference functionality within Visual Studio 2011.</span></span>  
  
 [<span data-ttu-id="87249-141">Porady: Konfigurowanie klienta</span><span class="sxs-lookup"><span data-stu-id="87249-141">How to: Configure a Client</span></span>](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
 <span data-ttu-id="87249-142">Opisuje sposób konfigurowania WCF klienta Konfigurowanie klienta wymaga określenia punktu końcowego, który klient używa do uzyskania dostępu do usługi.</span><span class="sxs-lookup"><span data-stu-id="87249-142">Describes how to configure a WCF client Configuring the client requires specifying the endpoint that the client uses to access the service.</span></span>  
  
 [<span data-ttu-id="87249-143">Porady: używanie klienta</span><span class="sxs-lookup"><span data-stu-id="87249-143">How to: Use a Client</span></span>](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)  
 <span data-ttu-id="87249-144">Informacje dotyczące używania [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proxy klienta do wywołania operacji usługi.</span><span class="sxs-lookup"><span data-stu-id="87249-144">Describes how to use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client proxy to invoke service operations.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="87249-145">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="87249-145">Reference</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
  
 <xref:System.ServiceModel.OperationContractAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="87249-146">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="87249-146">Related Sections</span></span>  
 [<span data-ttu-id="87249-147">Windows Communication Foundation — przykłady</span><span class="sxs-lookup"><span data-stu-id="87249-147">Windows Communication Foundation Samples</span></span>](http://msdn.microsoft.com/en-us/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
  
 [<span data-ttu-id="87249-148">Podstawowy cykl życia programowania</span><span class="sxs-lookup"><span data-stu-id="87249-148">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
## <a name="see-also"></a><span data-ttu-id="87249-149">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="87249-149">See Also</span></span>  
 [<span data-ttu-id="87249-150">Omówienie pojęć</span><span class="sxs-lookup"><span data-stu-id="87249-150">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
 [<span data-ttu-id="87249-151">Przewodnik po dokumentacji</span><span class="sxs-lookup"><span data-stu-id="87249-151">Guide to the Documentation</span></span>](../../../docs/framework/wcf/guide-to-the-documentation.md)  
 [<span data-ttu-id="87249-152">Co to jest Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="87249-152">What Is Windows Communication Foundation</span></span>](../../../docs/framework/wcf/whats-wcf.md)  
 [<span data-ttu-id="87249-153">Szczegóły funkcji WCF</span><span class="sxs-lookup"><span data-stu-id="87249-153">WCF Feature Details</span></span>](../../../docs/framework/wcf/feature-details/index.md)