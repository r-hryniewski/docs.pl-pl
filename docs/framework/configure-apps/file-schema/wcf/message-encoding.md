---
title: Kodowanie komunikatu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f30ee941-aca9-4c67-82a5-421568496f07
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ec7a85e95de9608d7a7daff11d70c9da3ff82989
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="message-encoding"></a><span data-ttu-id="c59c4-102">Kodowanie komunikatu</span><span class="sxs-lookup"><span data-stu-id="c59c4-102">Message Encoding</span></span>
<span data-ttu-id="c59c4-103">Kodowanie jest procesem przekształcania zestawu znaków Unicode do sekwencji bajtów.</span><span class="sxs-lookup"><span data-stu-id="c59c4-103">Encoding is the process of transforming a set of Unicode characters into a sequence of bytes.</span></span> <span data-ttu-id="c59c4-104">Dekodowanie jest procesu.</span><span class="sxs-lookup"><span data-stu-id="c59c4-104">Decoding is the reverse process.</span></span> <span data-ttu-id="c59c4-105">Windows Communication Foundation (WCF) obejmuje trzy rodzaje kodowania protokołu SOAP wiadomości: tekst, dane binarne i mechanizmu optymalizacji transmisji wiadomości (MTOM).</span><span class="sxs-lookup"><span data-stu-id="c59c4-105">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="c59c4-106">`binaryMessageEncoding` Sekcji konfiguracji określa znak kodowanie i wersjonowanie wiadomości używanych dla komunikatów XML na podstawie danych binarnych.</span><span class="sxs-lookup"><span data-stu-id="c59c4-106">The `binaryMessageEncoding` configuration section specifies the character encoding and message versioning used for binary-based XML messages.</span></span> <span data-ttu-id="c59c4-107">Koder komunikatów binarnych koduje wiadomości Windows Communication Foundation (WCF) w dane binarne w połączeniu.</span><span class="sxs-lookup"><span data-stu-id="c59c4-107">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="c59c4-108">Chociaż ten typ kodowania w wyniku bardzo szybko transmisję wiadomości, współdziałanie opartych na WS-* standardów zostaną utracone.</span><span class="sxs-lookup"><span data-stu-id="c59c4-108">While this encoding results in very fast transmission of messages, interoperability based on the WS-* standards is lost.</span></span>  
  
 <span data-ttu-id="c59c4-109">`mtomMessageEncoding` Sekcji konfiguracji określa znak kodowanie i wersjonowanie wiadomości używanych dla wiadomości przy użyciu kodowania mechanizmu optymalizacji transmisji wiadomości (MTOM).</span><span class="sxs-lookup"><span data-stu-id="c59c4-109">The `mtomMessageEncoding` configuration section specifies the character encoding and message versioning used for a message using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="c59c4-110">(MTOM) to technologia wydajne przekazywania danych binarnych w wiadomości Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c59c4-110">(MTOM) is an efficient technology for transmitting binary data in Windows Communication Foundation (WCF) messages.</span></span> <span data-ttu-id="c59c4-111">Koder MTOM próbuje równowagę między wydajności i współdziałanie.</span><span class="sxs-lookup"><span data-stu-id="c59c4-111">The MTOM encoder attempts to strike a balance between efficiency and interoperability.</span></span> <span data-ttu-id="c59c4-112">Kodowanie MTOM przesyła większości XML w postaci tekstowej, ale optymalizuje dużych bloków danych binarnych, przekazując je jako — Brak konwersji na tekst.</span><span class="sxs-lookup"><span data-stu-id="c59c4-112">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to text.</span></span>  
  
 <span data-ttu-id="c59c4-113">`textMessageEncoding` Sekcji konfiguracji określa koder tekstu używany do tworzenia przesyłania wiadomości tekstowych.</span><span class="sxs-lookup"><span data-stu-id="c59c4-113">The `textMessageEncoding` configuration section specifies a text encoder used to create text-based messages on the wire.</span></span> <span data-ttu-id="c59c4-114">Komunikaty generowane przez ten koder nadają się do usługi WS-* na podstawie interop.</span><span class="sxs-lookup"><span data-stu-id="c59c4-114">Messages produced by this encoder are suitable for WS-* based interop.</span></span> <span data-ttu-id="c59c4-115">Klienta usługi sieci Web lub usługi sieci Web zwykle zrozumieć tekstowy XML.</span><span class="sxs-lookup"><span data-stu-id="c59c4-115">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="c59c4-116">Jednak przesyłania dużych bloków danych binarnych jako tekst jest najmniej efektywną metodę kodowania wiadomości XML</span><span class="sxs-lookup"><span data-stu-id="c59c4-116">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c59c4-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c59c4-117">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 [<span data-ttu-id="c59c4-118">Powiązania</span><span class="sxs-lookup"><span data-stu-id="c59c4-118">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c59c4-119">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="c59c4-119">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="c59c4-120">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="c59c4-120">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="c59c4-121">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c59c4-121">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="c59c4-122">Wybieranie kodera komunikatów</span><span class="sxs-lookup"><span data-stu-id="c59c4-122">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)