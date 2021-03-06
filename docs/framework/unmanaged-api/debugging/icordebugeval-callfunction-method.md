---
title: ICorDebugEval::CallFunction — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86d48461c601b53d4461331a11a0e0ac7ddc6e7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412555"
---
# <a name="icordebugevalcallfunction-method"></a>ICorDebugEval::CallFunction — Metoda
Konfiguruje wywołanie określonych funkcji.  
  
 Ta metoda jest przestarzała w programie .NET Framework w wersji 2.0. Użyj [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) zamiast tego.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pFunction`  
 [in] Wskaźnik do obiektu ICorDebugFunction, który określa funkcję, która ma zostać wywołana.  
  
 `nArgs`  
 [in] Liczba argumentów funkcji.  
  
 `ppArgs`  
 [in] Tablicy wskaźników, z których każdy wskazuje obiekt ICorDebugValue określający argument można przekazać do funkcji.  
  
## <a name="remarks"></a>Uwagi  
 Jeśli funkcja jest wirtualny, `CallFunction` wykona wirtualnego wysyłania. Jeśli funkcja znajduje się w domenie innej aplikacji, przejście zostanie przeprowadzona tak długo, jak wszystkie argumenty mają również w tej domenie aplikacji.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** WindowSee [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Zobacz też  
 [CallParameterizedFunction, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)
