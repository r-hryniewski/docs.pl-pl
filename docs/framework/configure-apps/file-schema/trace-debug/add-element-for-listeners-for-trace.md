---
title: "&lt;Dodaj&gt; elementu &lt;odbiorników&gt; dla &lt;śledzenia&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
caps.latest.revision: "24"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bbb74d9a542833a96c61bcc09f6e4e5f0807843d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="a52ff-102">&lt;Dodaj&gt; elementu &lt;odbiorników&gt; dla &lt;śledzenia&gt;</span><span class="sxs-lookup"><span data-stu-id="a52ff-102">&lt;add&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="a52ff-103">Dodaje odbiornika do **odbiorników** kolekcji.</span><span class="sxs-lookup"><span data-stu-id="a52ff-103">Adds a listener to the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="a52ff-104">\<Konfiguracja ></span><span class="sxs-lookup"><span data-stu-id="a52ff-104">\<configuration></span></span>  
<span data-ttu-id="a52ff-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="a52ff-105">\<system.diagnostics></span></span>  
<span data-ttu-id="a52ff-106">\<śledzenia ></span><span class="sxs-lookup"><span data-stu-id="a52ff-106">\<trace></span></span>  
<span data-ttu-id="a52ff-107">\<obiekty nasłuchujące ></span><span class="sxs-lookup"><span data-stu-id="a52ff-107">\<listeners></span></span>  
<span data-ttu-id="a52ff-108">\<Dodaj ></span><span class="sxs-lookup"><span data-stu-id="a52ff-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a52ff-109">Składnia</span><span class="sxs-lookup"><span data-stu-id="a52ff-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a52ff-110">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="a52ff-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a52ff-111">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="a52ff-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a52ff-112">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="a52ff-112">Attributes</span></span>  
  
|<span data-ttu-id="a52ff-113">Atrybut</span><span class="sxs-lookup"><span data-stu-id="a52ff-113">Attribute</span></span>|<span data-ttu-id="a52ff-114">Opis</span><span class="sxs-lookup"><span data-stu-id="a52ff-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a52ff-115">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a52ff-115">**type**</span></span>|<span data-ttu-id="a52ff-116">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="a52ff-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="a52ff-117">Określa typ odbiornika.</span><span class="sxs-lookup"><span data-stu-id="a52ff-117">Specifies the type of the listener.</span></span> <span data-ttu-id="a52ff-118">Należy użyć ciągu, który spełnia wymagania określone w [określenie pełni kwalifikowane nazwy typów](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="a52ff-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="a52ff-119">**initializeData —**</span><span class="sxs-lookup"><span data-stu-id="a52ff-119">**initializeData**</span></span>|<span data-ttu-id="a52ff-120">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="a52ff-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a52ff-121">Ciąg przekazany do konstruktora dla określonej klasy.</span><span class="sxs-lookup"><span data-stu-id="a52ff-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="a52ff-122">**Nazwa**</span><span class="sxs-lookup"><span data-stu-id="a52ff-122">**name**</span></span>|<span data-ttu-id="a52ff-123">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="a52ff-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a52ff-124">Określa nazwę odbiornika.</span><span class="sxs-lookup"><span data-stu-id="a52ff-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a52ff-125">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="a52ff-125">Child Elements</span></span>  
  
|<span data-ttu-id="a52ff-126">Element</span><span class="sxs-lookup"><span data-stu-id="a52ff-126">Element</span></span>|<span data-ttu-id="a52ff-127">Opis</span><span class="sxs-lookup"><span data-stu-id="a52ff-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a52ff-128">\<Filtr ></span><span class="sxs-lookup"><span data-stu-id="a52ff-128">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="a52ff-129">Dodaje filtr do odbiornika w `Listeners` kolekcji dla śledzenia.</span><span class="sxs-lookup"><span data-stu-id="a52ff-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a52ff-130">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="a52ff-130">Parent Elements</span></span>  
  
|<span data-ttu-id="a52ff-131">Element</span><span class="sxs-lookup"><span data-stu-id="a52ff-131">Element</span></span>|<span data-ttu-id="a52ff-132">Opis</span><span class="sxs-lookup"><span data-stu-id="a52ff-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a52ff-133">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a52ff-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="a52ff-134">Określa odbiornika zbiera, magazynów i kieruje komunikaty.</span><span class="sxs-lookup"><span data-stu-id="a52ff-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="a52ff-135">Odbiorniki bezpośrednie dane wyjściowe śledzenia do odpowiedniego obiektu docelowego.</span><span class="sxs-lookup"><span data-stu-id="a52ff-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a52ff-136">Określa element root dla sekcji konfiguracji ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a52ff-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="a52ff-137">Zawiera nasłuchujących zbierania, przechowywania i trasy śledzenia wiadomości.</span><span class="sxs-lookup"><span data-stu-id="a52ff-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a52ff-138">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a52ff-138">Remarks</span></span>  
 <span data-ttu-id="a52ff-139"><xref:System.Diagnostics.Debug> i <xref:System.Diagnostics.Trace> klasy udostępnianie takie same **odbiorników** kolekcji.</span><span class="sxs-lookup"><span data-stu-id="a52ff-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="a52ff-140">Jeśli obiekt odbiornika zostanie dodany do kolekcji w jednym z tych klas, inne klasy używa tego samego odbiornika.</span><span class="sxs-lookup"><span data-stu-id="a52ff-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="a52ff-141">Klasy odbiornika pochodzić od <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="a52ff-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="a52ff-142">Jeśli nie określisz `name` atrybutu obiektu nasłuchującego śledzenia <xref:System.Diagnostics.TraceListener.Name%2A> domyślnych ustawień odbiornika śledzenia na ciąg pusty ("").</span><span class="sxs-lookup"><span data-stu-id="a52ff-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="a52ff-143">Jeśli aplikacja ma tylko jeden odbiornik, można dodać go bez określania nazwy i usuń go przez określenie pustego ciągu w nazwie.</span><span class="sxs-lookup"><span data-stu-id="a52ff-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="a52ff-144">Jednak jeśli aplikacja ma więcej niż jeden odbiornik, należy określić unikatową nazwę każdego nasłuchującego śledzenia, który służy do identyfikowania i zarządzania nim obiekty nasłuchujące śledzenia poszczególnych w <xref:System.Diagnostics.Debug.Listeners%2A> i <xref:System.Diagnostics.Trace.Listeners%2A> kolekcji.</span><span class="sxs-lookup"><span data-stu-id="a52ff-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a52ff-145">Dodanie więcej niż jeden odbiornik śledzenia tego samego typu i o tej samej nazwie wyniki śledzenia tylko jednego odbiornika tego typu i nazwy dodawane do `Listeners` kolekcji.</span><span class="sxs-lookup"><span data-stu-id="a52ff-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="a52ff-146">Jednak programowo można dodać wiele odbiorników identyczne do `Listeners` kolekcji.</span><span class="sxs-lookup"><span data-stu-id="a52ff-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="a52ff-147">Wartość **initializeData —** atrybutu zależy od typu tworzenia odbiornika.</span><span class="sxs-lookup"><span data-stu-id="a52ff-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="a52ff-148">Nie wszystkie obiekty nasłuchujące śledzenia wymagają określenia **initializeData —**.</span><span class="sxs-lookup"><span data-stu-id="a52ff-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a52ff-149">Jeśli używasz `initializeData` atrybutu, mogą wystąpić kompilatora ostrzeżenie "atrybutu"initializeData —"nie został zadeklarowany."</span><span class="sxs-lookup"><span data-stu-id="a52ff-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="a52ff-150">To ostrzeżenie występuje, ponieważ ustawienia konfiguracji są sprawdzane w abstrakcyjnej klasy podstawowej <xref:System.Diagnostics.TraceListener>, którego nie rozpoznaje `initializeData` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="a52ff-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="a52ff-151">Zazwyczaj można zignorować to ostrzeżenie implementacji odbiornika śledzenia, które mają Konstruktor, który przyjmuje parametr.</span><span class="sxs-lookup"><span data-stu-id="a52ff-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="a52ff-152">Poniższa tabela przedstawia obiekty nasłuchujące śledzenia, które są dołączone do programu .NET Framework oraz opis wartość ich **initializeData —** atrybutów.</span><span class="sxs-lookup"><span data-stu-id="a52ff-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="a52ff-153">Klasa odbiornika śledzenia</span><span class="sxs-lookup"><span data-stu-id="a52ff-153">Trace listener class</span></span>|<span data-ttu-id="a52ff-154">initializeData — wartość atrybutu</span><span class="sxs-lookup"><span data-stu-id="a52ff-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a52ff-155">`useErrorStream` Wartość <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> konstruktora.</span><span class="sxs-lookup"><span data-stu-id="a52ff-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="a52ff-156">Ustaw `initializeData` atrybutu "`true`" zapisu śledzenia i debugowania dane wyjściowe do <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" do zapisu <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a52ff-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a52ff-157">Nazwa pliku <xref:System.Diagnostics.DelimitedListTraceListener> zapisuje.</span><span class="sxs-lookup"><span data-stu-id="a52ff-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a52ff-158">Nazwa nazwę istniejącego źródła dziennika zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="a52ff-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a52ff-159">Nazwa pliku, który <xref:System.Diagnostics.EventSchemaTraceListener> zapisuje.</span><span class="sxs-lookup"><span data-stu-id="a52ff-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a52ff-160">Nazwa pliku, który <xref:System.Diagnostics.TextWriterTraceListener> zapisuje.</span><span class="sxs-lookup"><span data-stu-id="a52ff-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a52ff-161">Nazwa pliku, który <xref:System.Diagnostics.XmlWriterTraceListener> zapisuje.</span><span class="sxs-lookup"><span data-stu-id="a52ff-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a52ff-162">Przykład</span><span class="sxs-lookup"><span data-stu-id="a52ff-162">Example</span></span>  
 <span data-ttu-id="a52ff-163">Poniższy przykład przedstawia użycie  **\<Dodaj >** elementy do dodania odbiorniki `MyListener` i `MyEventListener` do **odbiorników** kolekcji.</span><span class="sxs-lookup"><span data-stu-id="a52ff-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="a52ff-164">`MyListener`Tworzy plik o nazwie `MyListener.log` i zapisuje dane wyjściowe do pliku.</span><span class="sxs-lookup"><span data-stu-id="a52ff-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="a52ff-165">`MyEventListener`tworzy wpis w dzienniku zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="a52ff-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a52ff-166">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a52ff-166">See Also</span></span>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 [<span data-ttu-id="a52ff-167">Schemat ustawień debugowania i śledzenia</span><span class="sxs-lookup"><span data-stu-id="a52ff-167">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="a52ff-168">Obiekty nasłuchujące śledzenia</span><span class="sxs-lookup"><span data-stu-id="a52ff-168">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)