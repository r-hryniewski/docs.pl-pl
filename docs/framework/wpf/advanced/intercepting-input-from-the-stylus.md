---
title: Przechwycenie danych z pisaka
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 611a2d2de56025e2f1b5add6106294834586f9af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="intercepting-input-from-the-stylus"></a><span data-ttu-id="df6cc-102">Przechwycenie danych z pisaka</span><span class="sxs-lookup"><span data-stu-id="df6cc-102">Intercepting Input from the Stylus</span></span>
<span data-ttu-id="df6cc-103"><xref:System.Windows.Input.StylusPlugIns> Architektura udostępnia mechanizm dla implementacji kontrolę niskiego poziomu nad <xref:System.Windows.Input.Stylus> dane wejściowe i tworzenia elektroniczne pismo odręczne <xref:System.Windows.Ink.Stroke> obiektów.</span><span class="sxs-lookup"><span data-stu-id="df6cc-103">The <xref:System.Windows.Input.StylusPlugIns> architecture provides a mechanism for implementing low-level control over <xref:System.Windows.Input.Stylus> input and the creation of digital ink <xref:System.Windows.Ink.Stroke> objects.</span></span> <span data-ttu-id="df6cc-104"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Klasa udostępnia mechanizm do implementowania niestandardowych zachowania i zastosować je w strumieniu danych przesyłanych przez pióro urządzenie pod kątem uzyskania optymalnej wydajności.</span><span class="sxs-lookup"><span data-stu-id="df6cc-104">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> class provides a mechanism for you to implement custom behavior and apply it to the stream of data coming from the stylus device for the optimal performance.</span></span>  
  
 <span data-ttu-id="df6cc-105">Ten temat zawiera następujące podsekcje:</span><span class="sxs-lookup"><span data-stu-id="df6cc-105">This topic contains the following subsections:</span></span>  
  
-   [<span data-ttu-id="df6cc-106">Architektura</span><span class="sxs-lookup"><span data-stu-id="df6cc-106">Architecture</span></span>](#Architecture)  
  
-   [<span data-ttu-id="df6cc-107">Implementowanie wtyczek pióra</span><span class="sxs-lookup"><span data-stu-id="df6cc-107">Implementing Stylus Plug-ins</span></span>](#ImplementingStylusPlugins)  
  
-   [<span data-ttu-id="df6cc-108">Dodawanie użytkownika wtyczki do InkCanvas.</span><span class="sxs-lookup"><span data-stu-id="df6cc-108">Adding Your Plug-in to an InkCanvas</span></span>](#AddingYourPluginToAnInkCanvas)  
  
-   [<span data-ttu-id="df6cc-109">Zawierania</span><span class="sxs-lookup"><span data-stu-id="df6cc-109">Conclusion</span></span>](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a><span data-ttu-id="df6cc-110">Architektura</span><span class="sxs-lookup"><span data-stu-id="df6cc-110">Architecture</span></span>  
 <span data-ttu-id="df6cc-111"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Jest rozwoju [StylusInput](http://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) interfejsów API, które są opisane w [dostęp i manipulowanie piórem](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)w [Microsoft Windows XP Tablet PC Edition oprogramowania Zestaw deweloperski 1.7](http://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="df6cc-111">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> is the evolution of the [StylusInput](http://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) APIs, described in [Accessing and Manipulating Pen Input](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409), in the [Microsoft Windows XP Tablet PC Edition Software Development Kit 1.7](http://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409).</span></span>  
  
 <span data-ttu-id="df6cc-112">Każdy <xref:System.Windows.UIElement> ma <xref:System.Windows.UIElement.StylusPlugIns%2A> właściwość, która jest <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span><span class="sxs-lookup"><span data-stu-id="df6cc-112">Each <xref:System.Windows.UIElement> has a <xref:System.Windows.UIElement.StylusPlugIns%2A> property that is a <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span> <span data-ttu-id="df6cc-113">Możesz dodać <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> do elementu <xref:System.Windows.UIElement.StylusPlugIns%2A> właściwości do manipulowania <xref:System.Windows.Input.StylusPoint> danych, ponieważ jest generowany.</span><span class="sxs-lookup"><span data-stu-id="df6cc-113">You can add a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> to an element's <xref:System.Windows.UIElement.StylusPlugIns%2A> property to manipulate <xref:System.Windows.Input.StylusPoint> data as it is generated.</span></span> <span data-ttu-id="df6cc-114"><xref:System.Windows.Input.StylusPoint>dane zawierają wszystkie właściwości, które są obsługiwane przez system dyskretyzatora, w tym <xref:System.Windows.Input.StylusPoint.X%2A> i <xref:System.Windows.Input.StylusPoint.Y%2A> punktu danych, a także <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> danych.</span><span class="sxs-lookup"><span data-stu-id="df6cc-114"><xref:System.Windows.Input.StylusPoint> data consists of all the properties supported by the system digitizer, including the <xref:System.Windows.Input.StylusPoint.X%2A> and <xref:System.Windows.Input.StylusPoint.Y%2A> point data, as well as <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> data.</span></span>  
  
 <span data-ttu-id="df6cc-115">Twoje <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> obiekty są wstawiane bezpośrednio w strumieniu danych przesyłanych przez <xref:System.Windows.Input.Stylus> urządzenia podczas dodawania <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> do <xref:System.Windows.UIElement.StylusPlugIns%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="df6cc-115">Your <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects are inserted directly into the stream of data coming from the <xref:System.Windows.Input.Stylus> device when you add the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> to the <xref:System.Windows.UIElement.StylusPlugIns%2A> property.</span></span> <span data-ttu-id="df6cc-116">Kolejność, w którym dodatki plug-in są dodawane do <xref:System.Windows.UIElement.StylusPlugIns%2A> kolekcji określa kolejność, w którym zostanie wyświetlony <xref:System.Windows.Input.StylusPoint> danych.</span><span class="sxs-lookup"><span data-stu-id="df6cc-116">The order in which plug-ins are added to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection dictates the order in which they will receive <xref:System.Windows.Input.StylusPoint> data.</span></span> <span data-ttu-id="df6cc-117">Na przykład, jeśli można dodać filtr wtyczki ograniczającej danych wejściowych do określonego regionu, a następnie dodaj wtyczki, które rozpoznaje gesty, ponieważ są one zapisywane, wtyczka rozpoznającego gestów zostanie wyświetlony filtrowane <xref:System.Windows.Input.StylusPoint> danych.</span><span class="sxs-lookup"><span data-stu-id="df6cc-117">For example, if you add a filter plug-in that restricts input to a particular region, and then add a plug-in that recognizes gestures as they are written, the plug-in that recognizes gestures will receive filtered <xref:System.Windows.Input.StylusPoint> data.</span></span>  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a><span data-ttu-id="df6cc-118">Implementowanie wtyczek pióra</span><span class="sxs-lookup"><span data-stu-id="df6cc-118">Implementing Stylus Plug-ins</span></span>  
 <span data-ttu-id="df6cc-119">Aby zaimplementować wtyczki, klasa wyprowadzona z <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.</span><span class="sxs-lookup"><span data-stu-id="df6cc-119">To implement a plug-in, derive a class from <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.</span></span> <span data-ttu-id="df6cc-120">Ta klasa jest stosowane o strumienia danych, ponieważ pochodzi z <xref:System.Windows.Input.Stylus>.</span><span class="sxs-lookup"><span data-stu-id="df6cc-120">This class is applied o the stream of data as it comes in from the <xref:System.Windows.Input.Stylus>.</span></span> <span data-ttu-id="df6cc-121">W tej klasy można zmodyfikować wartości <xref:System.Windows.Input.StylusPoint> danych.</span><span class="sxs-lookup"><span data-stu-id="df6cc-121">In this class you can modify the values of the <xref:System.Windows.Input.StylusPoint> data.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="df6cc-122">Jeśli <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> zgłasza lub powoduje zgłoszenie wyjątku zostanie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="df6cc-122">If a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> throws or causes an exception, the application will close.</span></span> <span data-ttu-id="df6cc-123">Należy dokładnie przetestować formanty używające <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> i formantu należy używać tylko, jeśli masz pewność <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> nie spowoduje zgłoszenie wyjątku.</span><span class="sxs-lookup"><span data-stu-id="df6cc-123">You should thoroughly test controls that consume a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and only use a control if you are certain the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> will not throw an exception.</span></span>  
  
 <span data-ttu-id="df6cc-124">W poniższym przykładzie pokazano wtyczka, która ogranicza wprowadzania danych piórem modyfikując <xref:System.Windows.Input.StylusPoint.X%2A> i <xref:System.Windows.Input.StylusPoint.Y%2A> wartości w <xref:System.Windows.Input.StylusPoint> pochodzą dane w postaci, w jakiej <xref:System.Windows.Input.Stylus> urządzenia.</span><span class="sxs-lookup"><span data-stu-id="df6cc-124">The following example demonstrates a plug-in that restricts the stylus input by modifying the <xref:System.Windows.Input.StylusPoint.X%2A> and <xref:System.Windows.Input.StylusPoint.Y%2A> values in the <xref:System.Windows.Input.StylusPoint> data as it comes in from the <xref:System.Windows.Input.Stylus> device.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a><span data-ttu-id="df6cc-125">Dodawanie użytkownika wtyczki do InkCanvas.</span><span class="sxs-lookup"><span data-stu-id="df6cc-125">Adding Your Plug-in to an InkCanvas</span></span>  
 <span data-ttu-id="df6cc-126">Najprostszym sposobem użycia niestandardowe wtyczka jest implementacja klasy, która jest pochodną InkCanvas i dodać go do <xref:System.Windows.UIElement.StylusPlugIns%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="df6cc-126">The easiest way to use your custom plug-in is to implement a class that derives from InkCanvas and add it to the <xref:System.Windows.UIElement.StylusPlugIns%2A> property.</span></span>  
  
 <span data-ttu-id="df6cc-127">W poniższym przykładzie pokazano niestandardowego <xref:System.Windows.Controls.InkCanvas> który filtry pismo odręczne.</span><span class="sxs-lookup"><span data-stu-id="df6cc-127">The following example demonstrates a custom <xref:System.Windows.Controls.InkCanvas> that filters the ink.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 <span data-ttu-id="df6cc-128">Jeśli dodasz `FilterInkCanvas` do aplikacji i uruchom ją, można zauważyć, że pismo odręczne nie jest ograniczone do regionu do, zakończone pociągnięcia przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="df6cc-128">If you add a `FilterInkCanvas` to your application and run it, you will notice that the ink isn't restricted to a region until after the user completes a stroke.</span></span> <span data-ttu-id="df6cc-129">Jest to spowodowane <xref:System.Windows.Controls.InkCanvas> ma <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> właściwość, która jest <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> i jest już członkiem <xref:System.Windows.UIElement.StylusPlugIns%2A> kolekcji.</span><span class="sxs-lookup"><span data-stu-id="df6cc-129">This is because the <xref:System.Windows.Controls.InkCanvas> has a <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> property, which is a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and is already a member of the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection.</span></span> <span data-ttu-id="df6cc-130">Niestandardowa <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> zostanie dodany do <xref:System.Windows.UIElement.StylusPlugIns%2A> odbiera kolekcji <xref:System.Windows.Input.StylusPoint> danych po <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> odbiera dane.</span><span class="sxs-lookup"><span data-stu-id="df6cc-130">The custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> you added to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection receives the <xref:System.Windows.Input.StylusPoint> data after <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> receives data.</span></span> <span data-ttu-id="df6cc-131">W związku z tym <xref:System.Windows.Input.StylusPoint> danych nie będą filtrowane do czasu, po użytkownika wind pióra do końca linii.</span><span class="sxs-lookup"><span data-stu-id="df6cc-131">As a result, the <xref:System.Windows.Input.StylusPoint> data will not be filtered until after the user lifts the pen to end a stroke.</span></span> <span data-ttu-id="df6cc-132">Aby filtrować pismo odręczne, jak użytkownik wprowadzi go, należy wstawić `FilterPlugin` przed <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span><span class="sxs-lookup"><span data-stu-id="df6cc-132">To filter the ink as the user draws it, you must insert the `FilterPlugin` before the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span>  
  
 <span data-ttu-id="df6cc-133">Poniższy kod C# przedstawia niestandardowego <xref:System.Windows.Controls.InkCanvas> który filtry pismo odręczne podczas wprowadzania.</span><span class="sxs-lookup"><span data-stu-id="df6cc-133">The following C# code demonstrates a custom <xref:System.Windows.Controls.InkCanvas> that filters the ink as it is drawn.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a><span data-ttu-id="df6cc-134">Wniosek</span><span class="sxs-lookup"><span data-stu-id="df6cc-134">Conclusion</span></span>  
 <span data-ttu-id="df6cc-135">Przez wyprowadzanie własne <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> klasy i wstawianie ich do <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> kolekcji, mogą znacznie zwiększyć zachowanie odręcznego cyfrowego.</span><span class="sxs-lookup"><span data-stu-id="df6cc-135">By deriving your own <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classes and inserting them into <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> collections, you can greatly enhance the behavior of your digital ink.</span></span> <span data-ttu-id="df6cc-136">Masz dostęp do <xref:System.Windows.Input.StylusPoint> danych, ponieważ jest generowany, umożliwiając dostosować <xref:System.Windows.Input.Stylus> wejściowego.</span><span class="sxs-lookup"><span data-stu-id="df6cc-136">You have access to the <xref:System.Windows.Input.StylusPoint> data as it is generated, giving you the opportunity to customize the <xref:System.Windows.Input.Stylus> input.</span></span> <span data-ttu-id="df6cc-137">Ponieważ taki dostęp niskiego poziomu do <xref:System.Windows.Input.StylusPoint> danych, można zaimplementować odręczne kolekcji i renderowania z optymalną wydajnością aplikacji.</span><span class="sxs-lookup"><span data-stu-id="df6cc-137">Because you have such low-level access to the <xref:System.Windows.Input.StylusPoint> data, you can implement ink collection and rendering with optimal performance for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df6cc-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="df6cc-138">See Also</span></span>  
 [<span data-ttu-id="df6cc-139">Obsługa zaawansowanych odręcznego</span><span class="sxs-lookup"><span data-stu-id="df6cc-139">Advanced Ink Handling</span></span>](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)  
 [<span data-ttu-id="df6cc-140">Uzyskiwanie dostępu i operowanie nimi piórem</span><span class="sxs-lookup"><span data-stu-id="df6cc-140">Accessing and Manipulating Pen Input</span></span>](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)