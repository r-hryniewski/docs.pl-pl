---
title: '&lt;filtry&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37a87222-ec78-4728-8105-9ca1bd961f0c
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 21f2115f83772312e1b9f42a66c53ba8ee2834f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="ltfiltersgt"></a><span data-ttu-id="d375a-102">&lt;filtry&gt;</span><span class="sxs-lookup"><span data-stu-id="d375a-102">&lt;filters&gt;</span></span>

<span data-ttu-id="d375a-103">`filters` Element przetrzymuje kolekcję filtrów XPath używane do kontrolowania, jakiego rodzaju komunikat jest rejestrowany.</span><span class="sxs-lookup"><span data-stu-id="d375a-103">The `filters` element holds a collection of XPath filters used to control what kind of message is logged.</span></span>

<span data-ttu-id="d375a-104">Filtry są stosowane tylko w przypadku warstwy transportu, określonej przez `logMessagesAtTransportLevel` jest `true`.</span><span class="sxs-lookup"><span data-stu-id="d375a-104">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="d375a-105">Usługa rejestrowania komunikatów poziomu i źle sformułowane nie dotyczy filtrów.</span><span class="sxs-lookup"><span data-stu-id="d375a-105">Service level and malformed message logging are not affected by filters.</span></span>

<span data-ttu-id="d375a-106">Aby dodać filtr do kolekcji, użyj `add` — słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="d375a-106">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="d375a-107">Po zdefiniowaniu co najmniej jeden filtr są rejestrowane tylko komunikatów spełniających co najmniej jeden z filtrów.</span><span class="sxs-lookup"><span data-stu-id="d375a-107">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="d375a-108">Jeśli nie jest definiować filtru, wszystkie komunikaty przekazywane.</span><span class="sxs-lookup"><span data-stu-id="d375a-108">If no filter is defined, all messages pass through.</span></span>

<span data-ttu-id="d375a-109">Filtry obsługuje pełnej składni języka XPath i są stosowane w kolejności, w jakiej znajdują się w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="d375a-109">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="d375a-110">Nieprawidłowy filtr powoduje wyjątek konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="d375a-110">A syntactically incorrect filter results in a configuration exception.</span></span>

<span data-ttu-id="d375a-111">Poniżej znajduje się przykład sposobu konfigurowania filtr, który rejestruje tylko komunikaty, które mają sekcji nagłówka SOAP.</span><span class="sxs-lookup"><span data-stu-id="d375a-111">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>

```xml
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="420">  
  <filters>  
    <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">  
      /soap:Envelope/soap:Headers  
    </add>  
  </filters>  
</messageLogging>
```

## <a name="see-also"></a><span data-ttu-id="d375a-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d375a-112">See also</span></span>

 <span data-ttu-id="d375a-113"><xref:System.ServiceModel.Configuration.DiagnosticSection><xref:System.ServiceModel.Diagnostics> <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> <xref:System.ServiceModel.Configuration.MessageLoggingElement> <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A> <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection> <xref:System.ServiceModel.Configuration.XPathMessageFilterElement> <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> [Konfigurowanie rejestrowania komunikatów](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) [ \<messageLogging >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)</span><span class="sxs-lookup"><span data-stu-id="d375a-113"><xref:System.ServiceModel.Configuration.DiagnosticSection> <xref:System.ServiceModel.Diagnostics> <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> <xref:System.ServiceModel.Configuration.MessageLoggingElement> <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A> <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection> <xref:System.ServiceModel.Configuration.XPathMessageFilterElement> <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> [Configuring Message Logging](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) [\<messageLogging>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)</span></span>