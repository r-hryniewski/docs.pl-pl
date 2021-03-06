---
title: '&lt;message&gt; w &lt;netHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
ms.openlocfilehash: 1ed52347bf0c62dc451e1f8385884edc4b4bc8d2
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/04/2018
ms.locfileid: "48582388"
---
# <a name="ltmessagegt-of-ltnethttpbindinggt"></a>&lt;message&gt; w &lt;netHttpBinding&gt;
Definiuje ustawienia zabezpieczeń na poziomie komunikatu z [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).  
  
 \<system.ServiceModel>  
\<powiązania >  
\<netHttpBinding >  
\<Powiązanie >  
\<Zabezpieczenia >  
\<message>  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<message   
   algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="UserName/Certificate"/>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|algorithmSuite|Ustawia komunikat algorytmów szyfrowania i zawijania klucza. Ten atrybut jest typu <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, która określa te algorytmy i rozmiary kluczy. Te algorytmy są mapowane na te określone w specyfikacji języka zasad zabezpieczenia (WS-SecurityPolicy).<br /><br /> Wartość domyślna to `Basic256`.|  
|clientCredentialType|Określa typ poświadczenia do użycia podczas przeprowadzania uwierzytelniania klienta przy użyciu zabezpieczeń opartych na komunikat. Wartość domyślna to `UserName`.|  
  
## <a name="clientcredentialtype-attribute"></a>właściwości ClientCredentialType o wartości atrybutu  
  
|Wartość|Opis|  
|-----------|-----------------|  
|UserName|— Wymagają uwierzytelnienia klienta do serwera przy użyciu poświadczeń UserName. To poświadczenie musi być określona za pomocą <`clientCredentials`> element.<br />-WCF nie obsługuje wysyłanie skrótu hasła lub wyprowadzanie kluczy przy użyciu haseł i za pomocą takich klucze dla zabezpieczenia wiadomości. W związku z tym usługi WCF wymusza, czy transport zostać zabezpieczony, korzystając z poświadczeń UserName. Aby uzyskać `basicHttpBinding`, wymaga to skonfigurowanie kanału SSL.|  
|Certyfikat|Wymaga uwierzytelnienia klienta z serwerem przy użyciu certyfikatu. Poświadczeń klienta w tym przypadku musi być określona za pomocą <`clientCredentials`> i <`clientCertificate`>. Ponadto po używających trybu zabezpieczenia wiadomości, klienta musi być obsługiwana za pomocą certyfikatu usługi. Poświadczenia usługi w tym przypadku należy także określić przy użyciu <xref:System.ServiceModel.Description.ClientCredentials> klasy lub `ClientCredentials` element zachowania i określając usługę certyfikatu, przy użyciu \<serviceCertificate > element serviceCredentials.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|<`security`> elementu <`netHttpBinding`>|Definiuje funkcje bezpieczeństwa umożliwiające <`netHttpBinding`> Element.|  
  
## <a name="example"></a>Przykład  
 Ten przykład demonstruje sposób implementacji aplikacji, która używa zabezpieczenia basicHttpBinding i komunikatu. W poniższym przykładzie konfiguracji dla usługi określa basicHttpBinding definicji punktu końcowego, a odwołuje się do konfiguracji powiązania o nazwie `Binding1`. Certyfikat używany przez usługę do samodzielnego uwierzytelnienia klienta znajduje się w `behaviors` części pliku konfiguracyjnego obszarze `serviceCredentials` elementu. Tryb weryfikacji, który ma zastosowanie do certyfikatu używanego przez klienta do samodzielnego uwierzytelnienia usługi jest również ustawiona `behaviors` sekcji `clientCertificate` elementu.  
  
 Szczegóły tego samego powiązania i zabezpieczenia są określone w pliku konfiguracji klienta.  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  bindingConfiguration="Binding1"   
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <bindings>  
      <basicHttpBinding>  
        <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1" >  
          <security mode = "Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--  
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by a client to authenticate the service and provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Zabezpieczanie usług i klientów](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Powiązania](../../../../../docs/framework/wcf/bindings.md)  
 [Konfigurowanie powiązań dostarczanych przez system](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Konfigurowanie usług i klientów za pomocą powiązań](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [\<Powiązanie >](../../../../../docs/framework/misc/binding.md)
