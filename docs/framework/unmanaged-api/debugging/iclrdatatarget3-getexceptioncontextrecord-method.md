---
title: Metoda ICLRDataTarget3::GetExceptionContextRecord
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetContextRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 66076ed5-f05c-4114-9788-94cb143abb8a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 72c45e821a59c1e910b5c8422df02978046eb56b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500511"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a>Metoda ICLRDataTarget3::GetExceptionContextRecord
Metoda wywoływana przez wspólnego języka wspólnego (CLR) usługi dostępu do danych w celu pobrania rekordu kontekstu skojarzonego z procesem docelowym. Na przykład dla elementu docelowego zrzutu jest to równoważne z rekordu kontekstu przekazaną za pomocą `ExceptionParam` argument [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) funkcji w Windows debugowania pomóc w bibliotece (DbgHelp).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `bufferSize`  
 [in] Rozmiar buforu wejściowego w bajtach. Musi to być wystarczająco duży, aby pomieścić rekordu kontekstu.  
  
 `bufferUsed`  
 [out] Wskaźnik do `ULONG32` typu, który odbiera liczbę bajtów, które rzeczywiście zapisanych w buforze.  
  
 `buffer`  
 [out] Wskaźnik do buforu pamięci, który otrzymuje kopię rekordu kontekstu. Rekordu wyjątku jest zwracana jako [KONTEKSTU](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) typu.  
  
## <a name="return-value"></a>Wartość zwracana  
 Wartość zwracana jest `S_OK` na powodzenie lub niepowodzenie `HRESULT` kod błędu. `HRESULT` Mogą obejmować kody, ale nie są ograniczone do następujących:  
  
|Kod powrotu|Opis|  
|-----------------|-----------------|  
|`S_OK`|Metody powiodło się. Rekordu kontekstu został skopiowany do buforu danych wyjściowych.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Nie rekordu kontekstu jest skojarzony z obiektem docelowym.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|Rozmiar buforu wejściowego nie jest wystarczająco duży, aby pomieścić rekordu kontekstu.|  
  
## <a name="remarks"></a>Uwagi  
 [KONTEKST](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) to struktura specyficzne dla platformy, zdefiniowane w nagłówki udostępnione przez zestaw Windows SDK.  
  
 Ta metoda jest implementowana przez moduł zapisujący debugowania aplikacji.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** ClrData.idl, ClrData.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [ICLRDataTarget3, interfejs](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [GetExceptionRecord, metoda](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)  
 [GetExceptionThreadID, metoda](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
