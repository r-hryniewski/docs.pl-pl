---
title: Zdarzenia ETW międzyoperacyjności
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3bc9a90e9d889673d8f67e4f9158edebcb65235b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33396370"
---
# <a name="interop-etw-events"></a>Zdarzenia ETW międzyoperacyjności
<a name="top"></a> Zdarzenia międzyoperacyjności przechwytywanie informacji na temat generowania szkieletu język pośredni (MSIL) firmy Microsoft i buforowania.  
  
 Ta kategoria obejmuje następujące zdarzenia:  
  
-   [Zdarzenie ILStubGenerated](#ilstubgenerated_event)  
  
-   [Zdarzenie ILStubCacheHit](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a>Zdarzenie ILStubGenerated  
 W poniższej tabeli przedstawiono — słowo kluczowe i poziom. (Aby uzyskać więcej informacji, zobacz [słowa kluczowe CLR ETW i poziomy](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)  
  
|Słowo kluczowe wywołaniem zdarzenia|Poziom|  
|-----------------------------------|-----------|  
|`InteropKeyword` (0x2000)|Informational(4)|  
  
 W poniższej tabeli przedstawiono informacje dotyczące zdarzenia.  
  
|Zdarzenie|Identyfikator zdarzenia|Wywoływane, gdy|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|88|MSIL stub został wygenerowany.|  
  
 W poniższej tabeli przedstawiono dane zdarzenia.  
  
|Nazwa pola|Typ danych|Opis|  
|----------------|---------------|-----------------|  
|ModuleID|Windows: UInt16|Identyfikator modułu.|  
|StubMethodID|Windows: UInt64|Identyfikator metody stub.|  
|StubFlags|Windows: UInt64|Flagi dla elementu zastępczego:<br /><br /> 0x1 — odwrotne interop.<br /><br /> 0x2 — COM interop.<br /><br /> 0x4 - stub generowane przez NGen.exe.<br /><br /> 0x8 - delegata.<br /><br /> 0x10 - arrgument zmiennej.<br /><br /> 0x20 - wywoływany niezarządzane.|  
|ManagedInteropMethodToken|Windows: UInt32.|Token dla zarządzanych metoda międzyoperacyjna.|  
|ManagedInteropMethodNameSpace|Windows: UnicodeString|Przestrzeń nazw zarządzana metoda międzyoperacyjnego.|  
|ManagedInteropMethodName|Windows: UnicodeString|Nazwa zarządzanego metoda międzyoperacyjna.|  
|ManagedInteropMethodSignature|Windows: UnicodeString|Podpis zarządzana metoda międzyoperacyjnego.|  
|NativeMethodSignature|Windows: UnicodeString|Podpis metody natywnej.|  
|StubMethodSignature|Windows: UnicodeString|Podpis metody stub.|  
|StubMethodILCode|Windows: UnicodeString|Kod metody zastępczej MSIL.|  
|ClrInstanceID|Windows: UInt16|Unikatowy identyfikator wystąpienia CLR lub środowisko CoreCLR.|  
  
 [Powrót do początku](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a>Zdarzenie ILStubCacheHit  
 W poniższej tabeli przedstawiono — słowo kluczowe i poziom.  
  
|Słowo kluczowe wywołaniem zdarzenia|Poziom|  
|-----------------------------------|-----------|  
|`InteropKeyword` (0x2000)|Informational(4)|  
  
 W poniższej tabeli przedstawiono informacje dotyczące zdarzenia.  
  
|Zdarzenie|Identyfikator zdarzenia|Wywoływane, gdy|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|89|Uzyskał dostęp do pamięci podręcznej MSIL.|  
  
 W poniższej tabeli przedstawiono dane zdarzenia.  
  
|Nazwa pola|Typ danych|Opis|  
|----------------|---------------|-----------------|  
|ModuleID|Windows: UInt16|Identyfikator modułu.|  
|StubMethodID|Windows: UInt64|Identyfikator metody stub.|  
|ManagedInteropMethodToken|Windows: UInt32.|Token dla zarządzanych metoda międzyoperacyjna.|  
|ManagedInteropMethodNameSpace|Windows: UnicodeString|Przestrzeń nazw zarządzana metoda międzyoperacyjnego.|  
|ManagedInteropMethodName|Windows: UnicodeString|Nazwa zarządzanego metoda międzyoperacyjna.|  
|ManagedInteropMethodSignature|Windows: UnicodeString|Podpis zarządzana metoda międzyoperacyjnego.|  
|ClrInstanceID|Windows: UInt16|Unikatowy identyfikator wystąpienia CLR lub środowisko CoreCLR.|  
  
 [Powrót do początku](#top)  
  
## <a name="see-also"></a>Zobacz też  
 [Zdarzenia CLR ETW](../../../docs/framework/performance/clr-etw-events.md)
