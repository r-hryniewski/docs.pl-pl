---
title: ICorDebugProcess::ReadMemory — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a0063e33a6a7861815ebb9d9eb3dabec64dd4b9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419656"
---
# <a name="icordebugprocessreadmemory-method"></a>ICorDebugProcess::ReadMemory — Metoda
Odczytuje określony obszar pamięci dla tego procesu.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
#### <a name="parameters"></a>Parametry  
 `address`  
 [in] A `CORDB_ADDRESS` określający adres podstawowy pamięci do odczytu.  
  
 `size`  
 [in] Liczba bajtów do odczytu z pamięci.  
  
 `buffer`  
 [out] Bufor, który odbiera zawartość pamięci.  
  
 `read`  
 [out] Wskaźnik do liczba bajtów przesłanych w buforze określona.  
  
## <a name="remarks"></a>Uwagi  
 `ReadMemory` Metody jest przeznaczone głównie do użycia przez debugowania międzyoperacyjnego do zbadania regiony pamięci są używane przez niezarządzane część debugowany. Tej metody można również odczytać kodu języka pośredniego (MSIL) firmy Microsoft i kod natywny kompilacji JIT.  
  
 Wszystkie punkty przerwania w zarządzanych zostaną usunięte z danych, która jest zwracana w `buffer` parametru. Bez korekt nie były nawiązywane dla macierzystych punktów przerwania ustawionych przez [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 Odbywa się bez buforowania pamięci procesu.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
