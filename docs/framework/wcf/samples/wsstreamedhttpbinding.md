---
title: WSStreamedHttpBinding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97ce4d3d-ca6f-45fa-b33b-2429bb84e65b
caps.latest.revision: "27"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8238ede6fd43cc5cca2df1f8c7f9162f9c4a1302
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="wsstreamedhttpbinding"></a><span data-ttu-id="5f6e0-102">WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="5f6e0-102">WSStreamedHttpBinding</span></span>
<span data-ttu-id="5f6e0-103">Przykład przedstawia sposób tworzenia powiązania, które umożliwia obsługę przesyłania strumieniowego scenariuszy stosowania transportu HTTP.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-103">The sample demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f6e0-104">Procedury i kompilacji instrukcje dotyczące instalacji dla tego przykładu znajdują się na końcu tego tematu.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5f6e0-105">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5f6e0-106">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="5f6e0-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5f6e0-107">Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5f6e0-108">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Binding\WSStreamedHttpBinding`  
  
 <span data-ttu-id="5f6e0-109">Dostępne są następujące kroki, aby utworzyć i skonfigurować nowe powiązanie standardowe.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-109">The steps to create and configure a new standard binding are as follows.</span></span>  
  
1.  <span data-ttu-id="5f6e0-110">Utwórz nowe powiązanie standardowe</span><span class="sxs-lookup"><span data-stu-id="5f6e0-110">Create a new standard binding</span></span>  
  
     <span data-ttu-id="5f6e0-111">Standardowe powiązania w [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] takie jak basicHttpBinding i netTcpBinding Konfigurowanie transportów podstawowej i stosu kanału dla określonych wymagań.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-111">The standard bindings in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] such as basicHttpBinding, and netTcpBinding configure the underlying transports and channel stack for specific requirements.</span></span> <span data-ttu-id="5f6e0-112">W tym przykładzie `WSStreamedHttpBinding` konfiguruje stosu kanału w celu obsługi przesyłania strumieniowego.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-112">In this sample, `WSStreamedHttpBinding` configures the channel stack to support streaming.</span></span> <span data-ttu-id="5f6e0-113">Domyślnie WS-Security i niezawodna obsługa komunikatów nie są dodawane do stosu kanału, ponieważ obie funkcje nie są obsługiwane przez przesyłania strumieniowego.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-113">By default, WS-Security and reliable messaging are not added to the channel stack because both features are not supported by streaming.</span></span> <span data-ttu-id="5f6e0-114">Nowe powiązanie jest zaimplementowana w klasie `WSStreamedHttpBinding` która pochodzi z <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-114">The new binding is implemented in the class `WSStreamedHttpBinding` that derives from <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="5f6e0-115">`WSStreamedHttpBinding` Zawiera następujące elementy powiązania: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, i <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-115">The `WSStreamedHttpBinding` contains the following binding elements: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, and <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span></span> <span data-ttu-id="5f6e0-116">Ta klasa dostarcza `CreateBindingElements()` Metoda konfiguracji wynikowy stosu powiązanie, jak pokazano w poniższym kodzie próbki.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-116">The class provides a `CreateBindingElements()` method to configure the resulting binding stack, as shown in the following sample code.</span></span>  
  
    ```  
    public override BindingElementCollection CreateBindingElements()  
    {  
         // return collection of BindingElements  
         BindingElementCollection bindingElements = new BindingElementCollection();  
  
        // the order of binding elements within the collection is important: layered channels are applied in the order included, followed by  
        // the message encoder, and finally the transport at the end  
        if (flowTransactions)  
        {  
            bindingElements.Add(transactionFlow);  
        }  
        bindingElements.Add(textEncoding);  
  
        // add transport (http or https)  
        bindingElements.Add(transport);  
        return bindingElements.Clone();  
    }  
    ```  
  
2.  <span data-ttu-id="5f6e0-117">Dodawanie obsługi konfiguracji</span><span class="sxs-lookup"><span data-stu-id="5f6e0-117">Add configuration support</span></span>  
  
     <span data-ttu-id="5f6e0-118">Do udostępnienia transportu za pomocą konfiguracji próbki implementuje dwie klasy więcej —`WSStreamedHttpBindingConfigurationElement` i `WSStreamedHttpBindingSection`.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-118">To expose the transport through configuration the sample implements two more classes—`WSStreamedHttpBindingConfigurationElement` and `WSStreamedHttpBindingSection`.</span></span> <span data-ttu-id="5f6e0-119">Klasa `WSStreamedHttpBindingSection` jest <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> który uwidacznia `WSStreamedHttpBinding` do [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] system konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-119">The class `WSStreamedHttpBindingSection` is a <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> that exposes `WSStreamedHttpBinding` to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration system.</span></span> <span data-ttu-id="5f6e0-120">Delegowane do zbiorczego wdrożenia `WSStreamedHttpBindingConfigurationElement`, która jest pochodną <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-120">The bulk of the implementation is delegated to `WSStreamedHttpBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="5f6e0-121">Klasa `WSStreamedHttpBindingConfigurationElement` ma właściwości, które odpowiadają właściwości `WSStreamedHttpBinding`i funkcji do mapowania każdego elementu konfiguracji powiązania.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-121">The class `WSStreamedHttpBindingConfigurationElement` has properties that correspond to the properties of `WSStreamedHttpBinding`, and functions to map each configuration element to a binding.</span></span>  
  
     <span data-ttu-id="5f6e0-122">Zarejestruj program obsługi przy użyciu systemu konfiguracji przez dodanie następujących sekcji w pliku konfiguracji usługi.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-122">Register the handler with the configuration system, by adding the following section to the service's configuration file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <extensions>  
          <bindingExtensions>  
            <add name="wsStreamedHttpBinding" type="Microsoft.ServiceModel.Samples.WSStreamedHttpBindingCollectionElement, WSStreamedHttpBinding, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
          </bindingExtensions>  
        </extensions>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="5f6e0-123">Program obsługi można odwoływać się następnie z sekcji konfiguracji serviceModel.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-123">The handler can then be referenced from the serviceModel configuration section.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint  
                    address="https://localhost/servicemodelsamples/service.svc"  
                    bindingConfiguration="Binding"  
                    binding="wsStreamedHttpBinding"  
                    contract="Microsoft.ServiceModel.Samples.IStreamedEchoService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5f6e0-124">Aby skonfigurować, kompilacji, a następnie uruchom próbki</span><span class="sxs-lookup"><span data-stu-id="5f6e0-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="5f6e0-125">Zainstaluj [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 za pomocą następującego polecenia.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-125">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="5f6e0-126">Upewnij się, że wykonano czynności opisane w [jednorazowego procedurę instalacji dla przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5f6e0-126">Ensure that you have performed the steps listed in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="5f6e0-127">Upewnij się, że wykonano procedurę [instrukcje instalacji certyfikatu serwera Internet Information Services (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="5f6e0-127">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
4.  <span data-ttu-id="5f6e0-128">Postępuj zgodnie z instrukcjami w celu skompilowania rozwiązania, [kompilowanie przykładów programu Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5f6e0-128">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="5f6e0-129">Aby uruchomić przykładowy w konfiguracji między komputerami, postępuj zgodnie z instrukcjami w [uruchamiania przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5f6e0-129">To run the sample in a cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
6.  <span data-ttu-id="5f6e0-130">Po wyświetleniu okna klienta, wpisz "Przykład.txt".</span><span class="sxs-lookup"><span data-stu-id="5f6e0-130">When the client window displays, type "Sample.txt".</span></span> <span data-ttu-id="5f6e0-131">"Kopiowania z przykład.txt" powinien znajdować się w katalogu.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-131">You should find a "Copy of Sample.txt" in your directory.</span></span>  
  
## <a name="the-wsstreamedhttpbinding-sample-service"></a><span data-ttu-id="5f6e0-132">Usługa WSStreamedHttpBinding próbki</span><span class="sxs-lookup"><span data-stu-id="5f6e0-132">The WSStreamedHttpBinding Sample Service</span></span>  
 <span data-ttu-id="5f6e0-133">Usługa próbki, która używa `WSStreamedHttpBinding` znajduje się w podkatalogu usługi.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-133">The sample service that uses `WSStreamedHttpBinding` is located in the service subdirectory.</span></span> <span data-ttu-id="5f6e0-134">Implementacja `OperationContract` używa `MemoryStream` najpierw pobrać wszystkich danych ze strumienia przychodzącego przed zwróceniem `MemoryStream`.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-134">The implementation of `OperationContract` uses a `MemoryStream` to first retrieve all data from the incoming stream before returning the `MemoryStream`.</span></span> <span data-ttu-id="5f6e0-135">Usługa próbki jest obsługiwana przez Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="5f6e0-135">The sample service is hosted by Internet Information Services (IIS).</span></span>  
  
```  
[ServiceContract]  
public interface IStreamedEchoService  
{  
    [OperationContract]  
    Stream Echo(Stream data);  
}  
  
public class StreamedEchoService : IStreamedEchoService  
{  
    public Stream Echo(Stream data)  
    {  
        MemoryStream dataStorage = new MemoryStream();  
        byte[] byteArray = new byte[8192];  
        int bytesRead = data.Read(byteArray, 0, 8192);  
        while (bytesRead > 0)  
        {  
            dataStorage.Write(byteArray, 0, bytesRead);  
            bytesRead = data.Read(byteArray, 0, 8192);  
        }  
        data.Close();  
        dataStorage.Seek(0, SeekOrigin.Begin);  
  
        return dataStorage;  
    }  
}  
```  
  
## <a name="the-wsstreamedhttpbinding-sample-client"></a><span data-ttu-id="5f6e0-136">Przykładowe WSStreamedHttpBinding klienta</span><span class="sxs-lookup"><span data-stu-id="5f6e0-136">The WSStreamedHttpBinding Sample Client</span></span>  
 <span data-ttu-id="5f6e0-137">Klient, który służy do interakcji z usługi przy użyciu `WSStreamedHttpBinding` znajduje się w podkatalogu klienta.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-137">The client that is used to interact with the service using `WSStreamedHttpBinding` is located in the client subdirectory.</span></span> <span data-ttu-id="5f6e0-138">Ponieważ certyfikat użyty w tym przykładzie jest certyfikatu testowego utworzone za pomocą Makecert.exe, alert zabezpieczeń wyświetlany, gdy próbują uzyskać dostęp w przeglądarce, takie jak https://localhost/servicemodelsamples/service.svc adres HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-138">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert displays when you attempt to access an HTTPS address in your browser such as https://localhost/servicemodelsamples/service.svc.</span></span> <span data-ttu-id="5f6e0-139">Aby umożliwić [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta, aby pracować przy użyciu certyfikatu testowego w miejscu, dodatkowy kod został dodany do klienta dla pomijania alertu zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-139">To allow the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="5f6e0-140">Kod i towarzyszące klasy nie są wymagane, podczas korzystania z certyfikatów w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-140">The code and the accompanying class are not required when using production certificates.</span></span>  
  
```  
// WARNING: This code is only required for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f6e0-141">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5f6e0-141">See Also</span></span>