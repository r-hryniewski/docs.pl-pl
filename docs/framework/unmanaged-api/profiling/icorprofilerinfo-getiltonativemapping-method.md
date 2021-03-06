---
title: ICorProfilerInfo::GetILToNativeMapping — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILToNativeMapping
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetILToNativeMapping method [.NET Framework profiling]
ms.assetid: 6a5431ef-22fb-4e53-bac5-703986297eb1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 61b097fad670c49680d6a2cc0f99ca0d53ef4691
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456921"
---
# <a name="icorprofilerinfogetiltonativemapping-method"></a>ICorProfilerInfo::GetILToNativeMapping — Metoda
Pobiera mapy firmy Microsoft do natywnej przesunięć kod źródłowy znajdujący się w określonej funkcji powoduje przesunięcie język pośredni (MSIL).  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
#### <a name="parameters"></a>Parametry  
 `functionId`  
 [in] Identyfikator funkcji, która zawiera kod.  
  
 `cMap`  
 [in] Maksymalny rozmiar `map` tablicy.  
  
 `pcMap`  
 [out] Całkowita liczba dostępnych cor_debug_il_to_native_map — struktury.  
  
 `map`  
 [out] Tablica `COR_DEBUG_IL_TO_NATIVE_MAP` struktury, z których każdy określa przesunięcie. Po `GetILToNativeMapping` zwraca metoda `map` będzie zawierał niektórych lub wszystkich `COR_DEBUG_IL_TO_NATIVE_MAP` struktury.  
  
## <a name="remarks"></a>Uwagi  
 `GetILToNativeMapping` Metoda zwraca tablicę `COR_DEBUG_IL_TO_NATIVE_MAP` struktury. W celu przekazania, że niektórych zakresów instrukcji natywnego odpowiadają specjalne regiony kodu (na przykład prologu), może mieć wpisem w tablicy jego `ilOffset` pole ustawione na wartość [cordebugiltonativemappingtypes —](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) wyliczenie.  
  
 Po `GetILToNativeMapping` zwróci wartość, należy sprawdzić, czy `map` bufor był wystarczająco duży, aby pomieścić wszystkie `COR_DEBUG_IL_TO_NATIVE_MAP` struktury. Aby to zrobić, porównanie wartości `cMap` z wartością `pcMap` parametru. Jeśli `pcMap` wartość pomnożona przez rozmiar `COR_DEBUG_IL_TO_NATIVE_MAP` struktury, jest większy niż `cMap`, Przydziel większy `map` buforu, zaktualizuj `cMap` z nowej, większy rozmiar i wywołanie `GetILToNativeMapping` ponownie.  
  
 Alternatywnie można wywołać `GetILToNativeMapping` o zerowej długości `map` buforu w celu uzyskania rozmiar buforu poprawne. Rozmiar buforu można następnie ustawić wartość zwracana w `pcMap` i Wywołaj `GetILToNativeMapping` ponownie.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf.idl, CorProf.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [ICorProfilerInfo, interfejs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [GetILToNativeMapping2, metoda](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)  
 [Interfejsy profilowania](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilowanie](../../../../docs/framework/unmanaged-api/profiling/index.md)
