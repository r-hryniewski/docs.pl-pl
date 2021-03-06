---
title: '&lt;System.Diagnostics&gt; — Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 35fe167beb53c27aa511e08507415a26b1749ca2
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2018
ms.locfileid: "48029441"
---
# <a name="ltsystemdiagnosticsgt-element"></a>&lt;System.Diagnostics&gt; — Element
Określa obiektów nasłuchujących śledzenia zbierać, przechowywać i kierowanie komunikatów i poziom, którego ustawiono przełącznikiem śledzenia.  
  
 \<Konfiguracja >  
\<System.Diagnostics >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<asercja >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|Określa, czy należy wyświetlić okno komunikatu, gdy wywołujesz <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> metody; określa także nazwę pliku do zapisywania komunikatów.|  
|[\<liczniki wydajności >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|Określa rozmiar pamięci globalnej współużytkowane przez liczniki wydajności.|  
|[\<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|Zawiera dowolnego źródła i elementu śledzenia można odwoływać się do obiektów nasłuchujących. Odbiorniki zidentyfikowane jako współdzielonych detektorów można dodać do źródła lub śledzenie według nazwy.|  
|[\<źródła >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|Określa źródła śledzenia, które inicjują komunikatów śledzenia.|  
|[\<przełączniki >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|Zawiera poziomy, gdzie są ustawione przełączniki śledzenia i przełączniki śledzenia.|  
|[\<śledzenia >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|Zawiera obiektów nasłuchujących zbierać, przechowywać i kierowanie komunikatów śledzenia.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|`configuration`|Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.|  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak osadzać przełącznikiem śledzenia i detektor śledzenia wewnątrz  **\<system.diagnostics >** elementu. `General` Przełącznikiem śledzenia jest równa <xref:System.Diagnostics.TraceLevel> poziom. Odbiornik śledzenia `myListener` tworzy plik o nazwie `MyListener.log` i zapisuje dane wyjściowe do pliku.  
  
> [!NOTE]
>  W .NET Framework w wersji 2.0 można użyć tekstu, aby określić wartość dla przełącznika. Na przykład można określić `true` dla <xref:System.Diagnostics.BooleanSwitch> lub Użyj tekstu, takie jak reprezentujących wartości wyliczenia `Error` dla <xref:System.Diagnostics.TraceSwitch>. Wiersz `<add name="myTraceSwitch" value="Error" />` jest odpowiednikiem `<add name="myTraceSwitch" value="1" />`.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 [Schemat ustawień śledzenia i debugowania](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
