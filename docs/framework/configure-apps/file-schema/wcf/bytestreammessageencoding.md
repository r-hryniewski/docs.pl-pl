---
title: '&lt;byteStreamMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 4b031bfb0d0979dc99df13c104a712d6dd771e8a
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2018
ms.locfileid: "44225191"
---
# <a name="ltbytestreammessageencodinggt"></a>&lt;byteStreamMessageEncoding&gt;
Określa kodowanie komunikatu jako strumień bajtów z opcją określenia kodowania znaków.  
  
 \<system.serviceModel>  
\<powiązania >  
\<customBinding>  
\<Powiązanie >  
\<binaryMessageEncoding >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<byteStreamMessageEncoding/>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|Element messageVersion|Określa wersję SOAP komunikatów wysyłanych za pomocą tego powiązania. Tę właściwość można ustawić tylko wartość wersji wiadomości <xref:System.ServiceModel.Channels.MessageVersion.None%2A>. Koder komunikatów strumień bajtów nie obsługuje inne wersje komunikatów.<br /><br /> Ten atrybut jest typu <xref:System.ServiceModel.Channels.MessageVersion>.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<readerQuotas>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Definiuje ograniczenia złożoności wiadomości SOAP, które mogą być przetwarzane przez punkty końcowe skonfigurowane dla tego wiązania. Ten element jest typu <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<Powiązanie >](../../../../../docs/framework/misc/binding.md)|Definiuje wszystkie funkcje powiązania niestandardowego powiązania.|  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>  
 [Kodowanie komunikatu](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [Wybieranie kodera komunikatów](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [Powiązania](../../../../../docs/framework/wcf/bindings.md)  
 [Rozszerzanie powiązań](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Powiązania niestandardowe](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
