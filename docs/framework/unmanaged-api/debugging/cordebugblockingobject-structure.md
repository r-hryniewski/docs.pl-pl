---
title: CorDebugBlockingObject — Struktura
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed7db321b32657087b791758096c692f25f3d7f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407839"
---
# <a name="cordebugblockingobject-structure"></a>CorDebugBlockingObject — Struktura
Definiuje obiekt, który blokuje wątku i powód, że wątek jest zablokowany.  
  
## <a name="syntax"></a>Składnia  
  
```  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|`pBlockingObject`|Obiekt, w którym wątek jest zablokowana. Ten obiekt jest prawidłowy tylko na czas trwania bieżącego stanu zsynchronizowane. Jeśli na tym samym obiekcie, w ramach tego samego stanu zsynchronizowanych blokują dwoma wątkami, może spodziewać się [ICorDebugValue::GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) metody zwracają taką samą wartość. Jednak interfejsy może lub nie może być wskaźnika równoważne.|  
|`dwTimeout`|Wyrażony w milisekundach czas, przed wykonaniem operacji blokowania będzie limitu czasu lub wartość INFINITE, co oznacza, że będzie on nie upłynął limit czasu. Wartość limitu czasu określa całkowity czas blokowania operacji, nie jest nadal pozostały czas.|  
|`blockingReason`|Powód, że wątek jest zablokowany na tym obiekcie.|  
  
## <a name="remarks"></a>Uwagi  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [Struktury debugowania](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debugowanie](../../../../docs/framework/unmanaged-api/debugging/index.md)
