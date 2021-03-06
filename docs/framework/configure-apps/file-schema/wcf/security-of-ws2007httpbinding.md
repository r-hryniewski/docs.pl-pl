---
title: '&lt;security&gt; w &lt;ws2007HttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: fb92e7549b86a2c4a4a8453d13f6c4f08d696348
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199386"
---
# <a name="ltsecuritygt-of-ltws2007httpbindinggt"></a>&lt;security&gt; w &lt;ws2007HttpBinding&gt;
Reprezentuje ustawienia zabezpieczeń używane dla [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) elementu.  
  
 \<system.serviceModel>  
\<powiązania >  
\<ws2007HttpBinding>  
\<Powiązanie >  
\<Zabezpieczenia >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<system.serviceModel>  
    <bindings>  
        <ws2007HttpBinding>  
            <binding name = "string">  
              <security mode="None/Message/Transport/TransportWithMessageCredential">  
                  <transport>  
                  </transport>  
                  <message>  
                  </message>  
              </security  
        </ws2007HttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`mode`|— Opcjonalne. Określa typ zabezpieczeń, która jest stosowana. Wartość domyślna to `Message`.<br /><br /> Ten atrybut jest typu <xref:System.ServiceModel.SecurityMode>.|  
  
## <a name="mode-attribute"></a>Tryb atrybutu  
  
|Wartość|Opis|  
|-----------|-----------------|  
|`None`|Zabezpieczenia są wyłączone.|  
|`Transport`|Zabezpieczenia przy użyciu protokołu HTTPS. Usługa musi być skonfigurowany przy użyciu certyfikatów Secure Sockets Layer (SSL). Komunikat jest całkowicie zabezpieczony przy użyciu protokołu HTTPS, a usługa jest uwierzytelniany przez klienta za pomocą certyfikatu SSL usługi. Uwierzytelnianie klienta jest kontrolowany za pośrednictwem `ClientCredentials` atrybutu [ \<transportu >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) elementu.|  
|`Message`|Zabezpieczenia korzystanie z zabezpieczeń komunikatów protokołu SOAP. Domyślnie treści protokołu SOAP jest zaszyfrowany i podpisany. Ten tryb zapewnia szeroką gamę funkcji, takich jak tego, czy poświadczenia usługi są dostępne pod adresem klientem poza pasmem, pakiet algorytmów, używać oraz poziom ochrony do zastosowania do treści wiadomości, za pośrednictwem <xref:System.ServiceModel.Security.SecurityMessageProperty>. Uwierzytelnianie klienta jest wykonywana raz dla każdej sesji i wyniki uwierzytelniania są buforowane na czas trwania sesji.|  
|`TransportWithMessageCredential`|W tym trybie HTTPS zapewnia integralność, poufność i uwierzytelniania serwera i zabezpieczenia wiadomości protokołu SOAP zapewnia uwierzytelnianie klienta. Domyślnie uwierzytelnianie klienta jest wykonywana raz dla każdej sesji, a wyniki uwierzytelniania są buforowane na czas trwania sesji.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<transport >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md)|Określa ustawienia zabezpieczenia transportu. Ten element odnosi się do <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> typu. Te ustawienia są stosowane tylko wtedy, gdy tryb jest ustawiony na Transport.|  
|[\<message>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|Definiuje ustawienia zabezpieczeń dla wiadomości. Ten element odnosi się do <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> typu. Te ustawienia nie są stosowane, gdy tryb jest ustawiony jako transportu.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|Bezpiecznego powiązania aplikacji transportu HTTP.|  
  
## <a name="remarks"></a>Uwagi  
 Ten element jest przeznaczona dla współdziałanie z usługami, które implementują WS-* specyfikacji. Zabezpieczenia transportu dla tego powiązania jest Secure Sockets Layer (SSL) za pośrednictwem protokołu HTTP lub HTTPS.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [Zabezpieczanie usług i klientów](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Powiązania](../../../../../docs/framework/wcf/bindings.md)  
 [Konfigurowanie powiązań dostarczanych przez system](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Konfigurowanie usług i klientów za pomocą powiązań](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [\<Powiązanie >](../../../../../docs/framework/misc/binding.md)
