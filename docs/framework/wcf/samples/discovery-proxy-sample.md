---
title: "Przykład serwera proxy odnajdywania"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1dfa02df-15b1-4e97-9c8e-f5f2772711b0
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f16cf2ffc9e03308ce3b8a5e967c29e624ffd1af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="discovery-proxy-sample"></a><span data-ttu-id="5fab2-102">Przykład serwera proxy odnajdywania</span><span class="sxs-lookup"><span data-stu-id="5fab2-102">Discovery Proxy Sample</span></span>
<span data-ttu-id="5fab2-103">W tym przykładzie pokazano, jak utworzyć wdrożenia serwera proxy odnajdywania do przechowywania informacji o istniejących usług i jak klienci mogą wykonywać kwerendę czy serwera proxy, aby uzyskać informacje.</span><span class="sxs-lookup"><span data-stu-id="5fab2-103">This sample shows how to create an implementation of a Discovery proxy to store information about existing services and how clients can query that proxy for information.</span></span> <span data-ttu-id="5fab2-104">Ten przykład zawiera trzy projekty:</span><span class="sxs-lookup"><span data-stu-id="5fab2-104">This sample consists of three projects:</span></span>  
  
-   <span data-ttu-id="5fab2-105">**Usługa**: prosty [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Kalkulator usługa, która rejestruje się przy użyciu serwera proxy odnajdywania.</span><span class="sxs-lookup"><span data-stu-id="5fab2-105">**Service**: A simple [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] calculator service that registers itself with the discovery proxy.</span></span>  
  
-   <span data-ttu-id="5fab2-106">**Serwera Proxy odnajdywania**: implementacja usługi serwera proxy odnajdywania.</span><span class="sxs-lookup"><span data-stu-id="5fab2-106">**Discovery Proxy**: The implementation of a discovery proxy service.</span></span>  
  
-   <span data-ttu-id="5fab2-107">**Klient**: A WCF aplikacji klienckiej, która wymaga usługi serwera proxy odnajdywania do wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="5fab2-107">**Client**: A WCF client application that calls the discovery proxy to search for services.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="5fab2-108">Demonstracje</span><span class="sxs-lookup"><span data-stu-id="5fab2-108">Demonstrates</span></span>  
 <span data-ttu-id="5fab2-109">Implementacja serwera proxy odnajdywania</span><span class="sxs-lookup"><span data-stu-id="5fab2-109">Discovery proxy implementation</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5fab2-110">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="5fab2-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5fab2-111">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="5fab2-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5fab2-112">Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="5fab2-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5fab2-113">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="5fab2-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryProxy`  
  
## <a name="discoveryproxy"></a><span data-ttu-id="5fab2-114">Obiektu DiscoveryProxy</span><span class="sxs-lookup"><span data-stu-id="5fab2-114">DiscoveryProxy</span></span>  
 <span data-ttu-id="5fab2-115">W `Main` metody pliku Program.cs przykładzie przedstawiono sposób usługa typu <xref:System.ServiceModel.Discovery.DiscoveryProxy> jest obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="5fab2-115">In the `Main` method of the Program.cs file, the sample shows how a service of type <xref:System.ServiceModel.Discovery.DiscoveryProxy> is hosted.</span></span> <span data-ttu-id="5fab2-116">Udostępnia ona dwa punkty końcowe, jednego z typów <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> i innego typu <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="5fab2-116">It exposes two endpoints, one of type <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> and another of type <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>.</span></span> <span data-ttu-id="5fab2-117">Oba punkty końcowe użycia TCP jako transportu.</span><span class="sxs-lookup"><span data-stu-id="5fab2-117">Both of the endpoints use TCP as a transport.</span></span> <span data-ttu-id="5fab2-118"><xref:System.ServiceModel.Discovery.DiscoveryEndpoint> Prowadzi nasłuchiwanie na określony przez identyfikator URI `probeEndpointAddress` parametru, jest to, gdzie klienci mogą wysyłać wiadomości sondy do badania serwera proxy danych.</span><span class="sxs-lookup"><span data-stu-id="5fab2-118">The <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> is listening at the URI specified by the `probeEndpointAddress` parameter, this is where clients can send probe messages to query the proxy for its data.</span></span> <span data-ttu-id="5fab2-119"><xref:System.ServiceModel.Discovery.AnnouncementEndpoint> Prowadzi nasłuchiwanie na określony przez identyfikator URI `announcementEndpointAddress` parametru.</span><span class="sxs-lookup"><span data-stu-id="5fab2-119">The <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> is listening at the URI specified by the `announcementEndpointAddress` parameter.</span></span> <span data-ttu-id="5fab2-120">Jest to, gdy serwer proxy nasłuchuje dla anonsów.</span><span class="sxs-lookup"><span data-stu-id="5fab2-120">This is where the proxy listens to for announcements.</span></span> <span data-ttu-id="5fab2-121">Po otrzymaniu powiadomienia online proxy dodaje usługę do pamięci podręcznej i po otrzymaniu powiadomienia w trybie offline Usuwa usługę z pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="5fab2-121">When an online announcement is received, the proxy adds the service to its cache and when an offline announcement is received it removes the service from its cache.</span></span>  
  
 <span data-ttu-id="5fab2-122">DiscoveryProxy.cs zawiera implementację <xref:System.ServiceModel.Discovery.DiscoveryProxy>.</span><span class="sxs-lookup"><span data-stu-id="5fab2-122">The DiscoveryProxy.cs contains the implementation of the <xref:System.ServiceModel.Discovery.DiscoveryProxy>.</span></span> <span data-ttu-id="5fab2-123">Serwer Proxy musi dziedziczyć z <xref:System.Object> klasy i wymaga wykonania <xref:System.Runtime.Remoting.Messaging.AsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="5fab2-123">The Proxy must inherit from the <xref:System.Object> class and requires an implementation of <xref:System.Runtime.Remoting.Messaging.AsyncResult>.</span></span> <span data-ttu-id="5fab2-124">Przy tworzeniu wystąpienia, tworzy nowy serwer Proxy <xref:System.Collections.Generic.Dictionary%602>, która jest używana do przechowywania elementów bez informacji o.</span><span class="sxs-lookup"><span data-stu-id="5fab2-124">At instantiation, the Proxy creates a new <xref:System.Collections.Generic.Dictionary%602>, which it uses to store elements it knows about.</span></span>  
  
 <span data-ttu-id="5fab2-125">Plik jest podzielony na dwa obszary, serwer Proxy pamięci podręcznej metod i wdrażania serwera Proxy odnajdywania.</span><span class="sxs-lookup"><span data-stu-id="5fab2-125">The file is divided into two regions, Proxy Cache Methods and Discovery Proxy Implementation.</span></span> <span data-ttu-id="5fab2-126">Region metody pamięci podręcznej serwera Proxy zawiera metody używane do aktualizowania <xref:System.Collections.Generic.Dictionary%602>, wykonywać zapytania względem <xref:System.Collections.Generic.Dictionary%602>i wydrukować dane użytkowników.</span><span class="sxs-lookup"><span data-stu-id="5fab2-126">The Proxy Cache Methods region contains methods used to update the <xref:System.Collections.Generic.Dictionary%602>, perform queries against the <xref:System.Collections.Generic.Dictionary%602>, and print the data for users.</span></span> <span data-ttu-id="5fab2-127">Region wdrożenia serwera Proxy odnajdywania zawiera przesłonięte metody wymagane dla funkcji anons i badania.</span><span class="sxs-lookup"><span data-stu-id="5fab2-127">The Discovery Proxy Implementation region contains the overridden methods required for the Announcement and Probe functionality.</span></span> <span data-ttu-id="5fab2-128">Określają one akcje wykonywane przez serwer proxy po otrzymaniu powiadomienia Online, anons w trybie Offline lub wiadomości sondy.</span><span class="sxs-lookup"><span data-stu-id="5fab2-128">They define the actions taken by a proxy after receiving an Online Announcement, an Offline Announcement, or a Probe message.</span></span>  
  
## <a name="service"></a><span data-ttu-id="5fab2-129">Usługa</span><span class="sxs-lookup"><span data-stu-id="5fab2-129">Service</span></span>  
 <span data-ttu-id="5fab2-130">W pliku Program.cs w projekcie usługi ten sam identyfikator URI jest używane dla punktu końcowego powiadomienia jako serwera proxy odnajdywania.</span><span class="sxs-lookup"><span data-stu-id="5fab2-130">In the Program.cs file in the Service project, the same URI is used for its announcement endpoint as the discovery proxy.</span></span> <span data-ttu-id="5fab2-131">Jest to spowodowane usługa używa punktu końcowego do wysyłania anonsów, gdy serwer proxy używa go do ich odbierania.</span><span class="sxs-lookup"><span data-stu-id="5fab2-131">This is because service uses the endpoint for sending the announcements, while the proxy uses it for receiving them.</span></span> <span data-ttu-id="5fab2-132">Używane przez usługę <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> i dodaje punkt końcowy powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="5fab2-132">The service uses the <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> and adds an announcement endpoint to it.</span></span>  
  
## <a name="client"></a><span data-ttu-id="5fab2-133">Klient</span><span class="sxs-lookup"><span data-stu-id="5fab2-133">Client</span></span>  
 <span data-ttu-id="5fab2-134">Projekt klienta używa tego samego identyfikatora URI dla punktu końcowego sondowania jako serwer Proxy.</span><span class="sxs-lookup"><span data-stu-id="5fab2-134">The Client project uses the same URI for its probe endpoint as the Proxy.</span></span> <span data-ttu-id="5fab2-135">Jest to spowodowane sond w tym scenariuszu są również emisji pojedynczej specjalnie do punktu końcowego, które są dostępne na serwerze proxy.</span><span class="sxs-lookup"><span data-stu-id="5fab2-135">This is because the probes in this scenario are also being unicast specifically to the endpoint available on the proxy.</span></span> <span data-ttu-id="5fab2-136">Klient łączy się to dobrze znanego adresu, a następnie wysyła zapytanie do usługi.</span><span class="sxs-lookup"><span data-stu-id="5fab2-136">The Client connects to this well-known address and then queries it for the service.</span></span> <span data-ttu-id="5fab2-137">Po odnalezieniu usługi, który nawiązuje z nim połączenie.</span><span class="sxs-lookup"><span data-stu-id="5fab2-137">Once it has found the service it connects to it.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="5fab2-138">Aby użyć tego przykładu</span><span class="sxs-lookup"><span data-stu-id="5fab2-138">To use this sample</span></span>  
  
1.  <span data-ttu-id="5fab2-139">Załadowanie projektu rozwiązania w [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] i skompilować projekt.</span><span class="sxs-lookup"><span data-stu-id="5fab2-139">Load the project solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="5fab2-140">Najpierw uruchom aplikację serwera Proxy odnajdywania, generowane w \DiscoveryProxy\bin\debug [katalogu podstawowego rozwiązania].</span><span class="sxs-lookup"><span data-stu-id="5fab2-140">First run the Discovery Proxy application, generated in [solution base directory]\DiscoveryProxy\bin\debug.</span></span> <span data-ttu-id="5fab2-141">Serwera Proxy odnajdywania muszą najpierw uruchomić, ponieważ punkty końcowe TCP i anonsu musi mieć konto usługi do wysyłania swoich anonsów.</span><span class="sxs-lookup"><span data-stu-id="5fab2-141">The Discovery Proxy must run first because TCP announcement endpoints must be up for the service to send its announcements.</span></span>  
  
3.  <span data-ttu-id="5fab2-142">Po drugie Uruchom aplikację usługi wygenerowanych w \Service\bin\debug [katalogu podstawowego rozwiązania].</span><span class="sxs-lookup"><span data-stu-id="5fab2-142">Second, run the service application generated in [solution base directory]\Service\bin\debug.</span></span> <span data-ttu-id="5fab2-143">Podczas rozruchu usługa wysyła powiadomienia do punktu końcowego powiadomienia odnajdowania serwera proxy i jest zarejestrowana w pamięci podręcznej serwera proxy.</span><span class="sxs-lookup"><span data-stu-id="5fab2-143">At start-up, the service sends an announcement to the announcement endpoint of the discovery proxy and is registered in the proxy’s cache.</span></span>  
  
4.  <span data-ttu-id="5fab2-144">Uruchom aplikację klienta, generowane w \Client\bin\debug [katalogu podstawowego rozwiązania].</span><span class="sxs-lookup"><span data-stu-id="5fab2-144">Next, run the client application, generated in [solution base directory]\Client\bin\debug.</span></span> <span data-ttu-id="5fab2-145">Klient wysyła zapytanie do serwera proxy, pobiera adres usługi i następnie łączy się z usługą.</span><span class="sxs-lookup"><span data-stu-id="5fab2-145">The client queries the proxy, gets the service address and then connects to the service.</span></span>  
  
5.  <span data-ttu-id="5fab2-146">Ponadto przerwanie klienta, usługę, a następnie serwer proxy.</span><span class="sxs-lookup"><span data-stu-id="5fab2-146">Lastly, terminate the client, service and then the proxy.</span></span> <span data-ttu-id="5fab2-147">Serwer proxy musi być uruchomiona, aby otrzymywać powiadomienia w trybie offline usługi.</span><span class="sxs-lookup"><span data-stu-id="5fab2-147">The proxy must be running for it to receive the service's offline announcement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fab2-148">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5fab2-148">See Also</span></span>