---
title: "Wyświetlanie dzienników komunikatów"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3012fa13-f650-45fb-aaea-c5cca8c7d372
caps.latest.revision: "22"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 10a4c0e9e2680e2f858f2a0e3e1045ab346c3f14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="viewing-message-logs"></a><span data-ttu-id="4a66c-102">Wyświetlanie dzienników komunikatów</span><span class="sxs-lookup"><span data-stu-id="4a66c-102">Viewing Message Logs</span></span>
<span data-ttu-id="4a66c-103">W tym temacie opisano sposób wyświetlania dzienników komunikatów.</span><span class="sxs-lookup"><span data-stu-id="4a66c-103">This topic describes how you can view message logs.</span></span>  
  
## <a name="viewing-message-logs-in-the-service-trace-viewer"></a><span data-ttu-id="4a66c-104">Wyświetlanie komunikatów dzienniki w podglądzie śledzenia usługi</span><span class="sxs-lookup"><span data-stu-id="4a66c-104">Viewing Message Logs in the Service Trace Viewer</span></span>  
 <span data-ttu-id="4a66c-105">Zostanie on przekształcony komunikat jest przetwarzany przez [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a66c-105">A message will be transformed as it is processed by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="4a66c-106">W związku z tym rejestrowany komunikat odzwierciedla tylko treści wiadomości w momencie zarejestrowania go, nie zawartości w sieci.</span><span class="sxs-lookup"><span data-stu-id="4a66c-106">Therefore, a message being logged reflects only the message's content at the point it was logged, not the content on the wire.</span></span>  
  
 <span data-ttu-id="4a66c-107">Ponieważ dane wyjściowe rejestrowania komunikatów nie ma relacji do formatu transferu wiadomości, zawsze rejestrowania komunikatów generuje dekodowane wiadomości.</span><span class="sxs-lookup"><span data-stu-id="4a66c-107">Since the output of message logging has no relationship to the transfer format of the message, message logging always outputs the decoded message.</span></span> <span data-ttu-id="4a66c-108">Jeśli zostały skonfigurowane prawidłowo rejestrowanie komunikatów, wszelkie zarejestrowany komunikat należy w postaci zwykłego tekstu.</span><span class="sxs-lookup"><span data-stu-id="4a66c-108">If you have configured message logging properly, any logged message should be in plain text.</span></span> <span data-ttu-id="4a66c-109">Na przykład format (zwykły tekst) zarejestrowane komunikaty, nie ma wpływu na użycie binarnego kodera wiadomości.</span><span class="sxs-lookup"><span data-stu-id="4a66c-109">For example, the format (plain text) of the logged messages is not affected by the usage of a binary message encoder.</span></span>  
  
 <span data-ttu-id="4a66c-110">Dane wyjściowe XmlWriterTraceListener jest plik, który zawiera sekwencję fragmenty XML.</span><span class="sxs-lookup"><span data-stu-id="4a66c-110">The output of the XmlWriterTraceListener is a file that contains a sequence of XML fragments.</span></span> <span data-ttu-id="4a66c-111">Należy pamiętać, że plik nie jest prawidłowym plikiem XML.</span><span class="sxs-lookup"><span data-stu-id="4a66c-111">You should be aware that the file is not a valid XML file.</span></span> <span data-ttu-id="4a66c-112">Zaleca się, że używasz [narzędzia podglądu śledzenia usług (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) do wyświetlania plików dziennika komunikatów.</span><span class="sxs-lookup"><span data-stu-id="4a66c-112">It is recommended that you use the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) to view the message log files.</span></span> <span data-ttu-id="4a66c-113">Aby uzyskać więcej informacji na temat korzystania z tego narzędzia, zobacz [przy użyciu przeglądarki śledzenia usługi do wyświetlania skorelowanych danych śledzenia i rozwiązywania problemów](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="4a66c-113">For more information on how to use this tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span></span>  
  
 <span data-ttu-id="4a66c-114">W podglądzie śledzenia usługi, komunikaty są wyświetlane w **komunikat** kartę. Komunikaty, które spowodowały lub które są związane z, błąd przetwarzania są wyróżnione żółty (poziom ostrzeżenia) albo czerwony (poziom błędu), w zależności od ważności błędu.</span><span class="sxs-lookup"><span data-stu-id="4a66c-114">In the Service Trace Viewer, messages are listed in the **Message** tab. Messages that have caused, or are related to, a processing error are highlighted in yellow (warning level) or red (error level), depending on the severity of the error.</span></span> <span data-ttu-id="4a66c-115">Dwukrotne kliknięcie komunikatu powoduje wyświetlenie komunikatów śledzenia w kontekście przetwarzania żądania.</span><span class="sxs-lookup"><span data-stu-id="4a66c-115">Double-clicking on the message brings up the message trace in the context of the processing request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a66c-116">Jeśli komunikat nie ma nagłówka, nie `<header/>` tag jest rejestrowane.</span><span class="sxs-lookup"><span data-stu-id="4a66c-116">If a message has no header, no `<header/>` tag is logged.</span></span>  
  
## <a name="viewing-messages-logged-by-a-client-a-relay-and-a-service"></a><span data-ttu-id="4a66c-117">Wyświetlanie informacji zarejestrowanych przez klienta, przekazywania i usługi</span><span class="sxs-lookup"><span data-stu-id="4a66c-117">Viewing Messages Logged by a Client, a Relay, and a Service</span></span>  
 <span data-ttu-id="4a66c-118">W środowisku może znajdować się klienta, który wysyła komunikat do przekazywania, który następnie przekazuje komunikat do usługi.</span><span class="sxs-lookup"><span data-stu-id="4a66c-118">Your environment may contain a client, which sends a message to a relay, that subsequently forwards the message to the service.</span></span> <span data-ttu-id="4a66c-119">Jeśli rejestrowanie komunikatów jest włączona na wszystkich trzech lokalizacji, a wszystkie trzy dzienniki wiadomości są wyświetlane w [narzędzia podglądu śledzenia usług (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) jednocześnie, wymiany komunikatów dziennika są nieprawidłowo wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="4a66c-119">When message logging is enabled on all three locations, and all three message logs are viewed in [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) simultaneously, the message log exchanges will be incorrectly rendered.</span></span> <span data-ttu-id="4a66c-120">Jest to spowodowane `CorrelationId` i `ActivityId` w nagłówku wiadomości nie są unikatowe dla każdej pary send-receive.</span><span class="sxs-lookup"><span data-stu-id="4a66c-120">This is because the `CorrelationId` and `ActivityId` in the Message header are not unique for every send-receive pair.</span></span>  
  
 <span data-ttu-id="4a66c-121">Jedną z następujących metod służy do rozwiązania tego problemu.</span><span class="sxs-lookup"><span data-stu-id="4a66c-121">You can use either one of the following methods to resolve this problem.</span></span>  
  
-   <span data-ttu-id="4a66c-122">Tylko wyświetlić dwie z trzech dzienników wiadomości w [narzędzia podglądu śledzenia usług (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) w dowolnym momencie.</span><span class="sxs-lookup"><span data-stu-id="4a66c-122">Only view two of the three message logs in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) at any time.</span></span>  
  
-   <span data-ttu-id="4a66c-123">Jeśli należy wyświetlić wszystkie trzy dzienniki w [narzędzia podglądu śledzenia usług (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) w tym samym czasie, można zmodyfikować usługi przekazywania przez utworzenie nowej <xref:System.ServiceModel.Channels.Message> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="4a66c-123">If you must view all three logs in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) at the same time, you can modify the relay service by creating a new <xref:System.ServiceModel.Channels.Message> instance.</span></span> <span data-ttu-id="4a66c-124">To wystąpienie powinno być kopią treści komunikatu przychodzącego, a także wszystkich nagłówków z wyjątkiem `ActivityId` i `Action` nagłówków.</span><span class="sxs-lookup"><span data-stu-id="4a66c-124">This instance should be a copy of the body of the incoming message, plus all the headers except for the `ActivityId` and `Action` headers.</span></span> <span data-ttu-id="4a66c-125">Poniższy przykład kodu pokazuje, jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="4a66c-125">The following example code demonstrates how to do this.</span></span>  
  
```  
Message outgoingMessage = Message.CreateMessage(incomingMessage.Version, incomingMessage.Headers.Action, incomingMessage.GetReaderAtBodyContents());  
  
for (int i = 0; i < incomingMessage.Headers.Count; i++)  
{  
   if (incomingMessage.Headers[i].Name.Equals("ActivityId", StringComparison.InvariantCultureIgnoreCase) ||  
incomingMessage.Headers[i].Name.Equals("Action", StringComparison.InvariantCultureIgnoreCase))  
   {  
      continue;  
    }  
    outgoingMessage.Headers.CopyHeaderFrom(incomingMessage, i);  
}  
```  
  
## <a name="exceptional-cases-for-inaccurate-message-logging-content"></a><span data-ttu-id="4a66c-126">Wyjątki dla zawartości rejestrowania komunikatów niedokładne</span><span class="sxs-lookup"><span data-stu-id="4a66c-126">Exceptional Cases for Inaccurate Message Logging Content</span></span>  
 <span data-ttu-id="4a66c-127">W następujących warunkach komunikaty są rejestrowane może nie być dokładnie reprezentację strumień oktetu obecny umieszczonego w.</span><span class="sxs-lookup"><span data-stu-id="4a66c-127">Under the following conditions, messages being logged might not be the exact representation of the octet stream present on the wire.</span></span>  
  
-   <span data-ttu-id="4a66c-128">Dla klasy BasicHttpBinding, koperty nagłówki są rejestrowane na komunikaty przychodzące w / adresowania/Brak przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="4a66c-128">For BasicHttpBinding, envelope headers are logged for the incoming messages in the /addressing/none namespace.</span></span>  
  
-   <span data-ttu-id="4a66c-129">Mogą być niezgodne białe znaki.</span><span class="sxs-lookup"><span data-stu-id="4a66c-129">Whitespaces can be mismatched.</span></span>  
  
-   <span data-ttu-id="4a66c-130">Dla komunikatów przychodzących pustych elementów może być reprezentowany inaczej.</span><span class="sxs-lookup"><span data-stu-id="4a66c-130">For incoming messages, empty elements can be represented differently.</span></span> <span data-ttu-id="4a66c-131">Na przykład \<tag >\</tagu > zamiast \<tagu / ></span><span class="sxs-lookup"><span data-stu-id="4a66c-131">For example, \<tag>\</tag> instead of  \<tag/></span></span>  
  
-   <span data-ttu-id="4a66c-132">Gdy rejestrowanie znanych danych osobowych jest wyłączone przez domyślne lub enableLoggingKnownPii jawne ustawienie = "true".</span><span class="sxs-lookup"><span data-stu-id="4a66c-132">When known PII logging is disabled either by default or explicit setting enableLoggingKnownPii="true".</span></span>  
  
-   <span data-ttu-id="4a66c-133">Kodowanie jest włączona dla transformacji UTF-8.</span><span class="sxs-lookup"><span data-stu-id="4a66c-133">Encoding is enabled for transforming to UTF-8.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a66c-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4a66c-134">See Also</span></span>  
 [<span data-ttu-id="4a66c-135">Narzędzie podglądu śledzenia usług (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="4a66c-135">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [<span data-ttu-id="4a66c-136">Przy użyciu przeglądarki śledzenia usługi do wyświetlania skorelowanych danych śledzenia i rozwiązywania problemów</span><span class="sxs-lookup"><span data-stu-id="4a66c-136">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [<span data-ttu-id="4a66c-137">Rejestrowanie komunikatów</span><span class="sxs-lookup"><span data-stu-id="4a66c-137">Message Logging</span></span>](../../../../docs/framework/wcf/diagnostics/message-logging.md)