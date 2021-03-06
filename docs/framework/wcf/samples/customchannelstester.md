---
title: CustomChannelsTester
ms.date: 03/30/2017
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
ms.openlocfilehash: eebe4f15095c7cefbd32971fd2f3ee308e9916b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499391"
---
# <a name="customchannelstester"></a>CustomChannelsTester
`CustomChannelsTester` To narzędzie, które służy do testowania implementacjach użytkownika niestandardowym kanale z zestawem kontraktów usług wstępnie zdefiniowane. Możesz wybrać zestaw kontraktów usług i przekaż go za pomocą pliku XML. Narzędzie generuje następnie usługi i klienta, który korzysta z implementacji niestandardowego kanału podczas wymiany wiadomości.  
  
### <a name="to-build-the-tool"></a>Aby utworzyć narzędzie  
  
1.  Postępuj zgodnie z instrukcjami w celu skompilowania rozwiązania, [kompilowanie przykładów programu Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Tworzenie rozwiązania generuje trzy pliki: CustomChannelsTester.exe, TestSpec.xml i SampleRun.cmd. Plik SampleRun.cmd zawiera przykładowy wiersz polecenia, który przedstawia sposób użycia tego narzędzia do testowania [transportu: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) próbki.  
  
### <a name="to-run-the-tool"></a>Aby uruchomić narzędzie  
  
-   W wierszu polecenia wpisz następujące polecenie:  
  
    ```  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     Przy użyciu `/binding` opcja jest wymagana.  
  
     `/dll` jest wymagany, jeśli "powiązanie" nie jest dostarczane przez system powiązania dostarczane przez Windows Communication Foundation (WCF).  
  
     `/testspec` jest opcjonalna.  
  
     Spowoduje to utworzenie serwer i klienci na podstawie specyfikacji testu i powiązania.  
  
     Wykonuje klienta i serwera i zwraca wyniki.  
  
     Poniżej przedstawiono przykładowe XML opisu specyfikacji testu (testspec.xml):  
  
    ```xml  
    <TestSpec xmlns="http://WCF/TestSpec" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >  
    <ServiceContract>  
    <!-- Test a contract which has oneway / twoway operations. If you set ExpandAll = true, both types of contracts are tested -->    <IsOneWay ExpandAll="true">true</IsOneWay>  
    <!-- Test a contract with Asynchronous / Synchronous Operations-->  
        <IsAsync>false</IsAsync>   
    <!-- Test a sessionful / sessionless contract-->      
        <IsSession ExpandAll="true">true</IsSession>  
    <!-- If the Service Contract includes a CallBack Contract-->      
        <IsCallBack ExpandAll="true">true</IsCallBack>  
    </ServiceContract>  
    <TestDetails>  
    <!-- Name of the machine that runs the server - required if you want to run the test crossmachine-->  
        <ServerName>ReplaceThisWithTheServerMachineName</ServerName>  
    <!-- Port Number - Optional-->  
        <Port>8000</Port>  
    <!--URI for the callBack address for the CLient. The client will receive the messages from the server on this address in case of a CallBack Contract-->  
        <ClientCallBackAddress/>      
    <!-- Duration (in sec) after the server has started, it times out - optional(default = 300sec) -->  
        <ServerTimeout>300</ServerTimeout>  
    <!-- Duration (in sec) before the Client initializes -optional(default = 60sec) -->  
        <ClientTimeout>60</ClientTimeout>  
    <!-- Number of clients for each service - optional(default = 1) -->  
        <NumberOfClients>1</NumberOfClients>  
    <!-- Number of messages each client sends to the service - optional(default = 1) -->  
        <MessagesPerClient>1</MessagesPerClient>  
    </TestDetails>  
    </TestSpec>  
    ```  
  
## <a name="see-also"></a>Zobacz też
