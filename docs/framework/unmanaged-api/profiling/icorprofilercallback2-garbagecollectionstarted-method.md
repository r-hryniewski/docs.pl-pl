---
title: ICorProfilerCallback2::GarbageCollectionStarted — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a447dca98e5010163d5cc5f4f3da4333f4cdf7d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455273"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>ICorProfilerCallback2::GarbageCollectionStarted — Metoda
Powiadamia profilera kodu rozpoczęto wyrzucanie elementów bezużytecznych.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cGenerations`  
 [in] Całkowita liczba wpisów w `generationCollected` tablicy.  
  
 `generationCollected`  
 [in] Tablica wartości logicznych, które są `true` Jeśli generacji, który odpowiada indeks tablicy jest zebranych przez ten wyrzucanie elementów bezużytecznych; w przeciwnym razie `false`.  
  
 Tablica jest indeksowany przez wartość [cor_prf_gc_generation —](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) wyliczenia, co oznacza generacji.  
  
 `reason`  
 [in] Wartość [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) zostało wywołane przez wyliczenie wskazujący przyczynę wyrzucanie elementów bezużytecznych.  
  
## <a name="remarks"></a>Uwagi  
 Wszystkie wywołania zwrotne, które odnoszą się do tego wyrzucanie elementów bezużytecznych nastąpi między `GarbageCollectionStarted` wywołania zwrotnego i odpowiadający mu [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) wywołania zwrotnego. Tych wywołań zwrotnych nie muszą występować na tym samym wątku.  
  
 Bezpiecznie dla profiler do zbadania obiektów w ich oryginalnych lokalizacji podczas `GarbageCollectionStarted` wywołania zwrotnego. Moduł zbierający elementy bezużyteczne rozpocznie się przenoszenie obiektów po powrocie z `GarbageCollectionStarted`. Po profilera zwrócił to wywołanie zwrotne, profilera należy wziąć pod uwagę wszystkie identyfikatory obiektu jest nieprawidłowy, dopóki nie odbierze `ICorProfilerCallback2::GarbageCollectionFinished` wywołania zwrotnego.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf.idl, CorProf.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [ICorProfilerCallback, interfejs](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback2, interfejs](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
