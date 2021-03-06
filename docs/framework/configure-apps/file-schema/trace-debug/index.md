---
title: Schemat ustawień śledzenia i debugowania
ms.date: 03/30/2017
helpviewer_keywords:
- tracing [.NET Framework], trace and debug settings schema
- configuration schema [.NET Framework], trace and debug settings
- configuration settings [.NET Framework], tracing
- schema configuration settings
- configuration settings [.NET Framework], debugging
- trace listeners, trace and debug settings schema
- configuration sections [.NET Framework]
- elements [.NET Framework], trace and debug settings
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 9927ad0e853577abb19750d54ba9e852a4e7ec51
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397949"
---
# <a name="trace-and-debug-settings-schema"></a>Schemat ustawień śledzenia i debugowania
Ustawienia śledzenia i debugowania, określ obiektów nasłuchujących śledzenia zbierać, przechowywać i kierowanie komunikatów i poziom, którego ustawiono przełącznikiem śledzenia.  
  
 W poniższej tabeli opisano funkcje każdego elementu ustawienia śledzenia i debugowania.  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|Dodaje odbiornik do `Listeners` kolekcję dla źródła śledzenia.|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|Dodaje odbiornik do `Listeners` kolekcji.|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-sharedlisteners.md)|Dodaje odbiornik do `sharedListeners` kolekcji.|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|Określa poziom, którego ustawiono przełącznikiem śledzenia.|  
|[\<asercja >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|Określa, czy należy wyświetlić okno komunikatu, gdy wywołujesz <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> metody; określa także nazwę pliku do zapisywania komunikatów.|  
|[\<Wyczyść >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|Czyści `Listeners` kolekcję dla źródła śledzenia.|  
|[\<Wyczyść >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|Czyści `Listeners` kolekcji na potrzeby śledzenia.|  
|[\<Filtr >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|Dodaje filtr do odbiornika w `Listeners` kolekcję dla źródła śledzenia.|  
|[\<Filtr >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|Dodaje filtr do odbiornika w `Listeners` kolekcji na potrzeby śledzenia.|  
|[\<Filtr >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|Dodaje filtr do odbiornika w `sharedListeners` kolekcji.|  
|[\<odbiorniki >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|Określa detektory `Listeners` kolekcję dla źródła śledzenia.|  
|[\<odbiorniki >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Określa detektory `Listeners` kolekcji na potrzeby śledzenia.|  
|[\<liczniki wydajności >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|Określa rozmiar pamięci globalnej współużytkowane przez liczniki wydajności.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|Usuwa odbiornik z `Listeners` kolekcji na potrzeby śledzenia.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|Usuwa odbiornik z `Listeners` kolekcję dla źródła śledzenia.|  
|[\<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|Zawiera dowolnego źródła i elementu śledzenia można odwoływać się do obiektów nasłuchujących.|  
|[\<źródła >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|Zawiera źródła śledzenia, które inicjują komunikatów śledzenia.|  
|[\<źródło >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|Określa źródło śledzenia, który inicjuje komunikatów śledzenia.|  
|[\<przełączniki >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|Zawiera przełączniki śledzenia i poziomu, gdzie są ustawione przełączniki śledzenia.|  
|[\<System.Diagnostics >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/system-diagnostics-element.md)|Określa obiektów nasłuchujących śledzenia zbierać, przechowywać i kierowanie komunikatów i poziom, którego ustawiono przełącznikiem śledzenia.|  
|[\<śledzenia >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|Zawiera obiektów nasłuchujących zbierać, przechowywać i kierowanie komunikatów śledzenia.|  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.Debug>  
 [Schemat pliku konfiguracji](../../../../../docs/framework/configure-apps/file-schema/index.md)
