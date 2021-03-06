---
title: ICorDebugProcess2::GetReferenceValueFromGCHandle — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60624a5f6323399d06bda4e0280de8fbe861bd9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419588"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a>ICorDebugProcess2::GetReferenceValueFromGCHandle — Metoda
Pobiera wskaźnik odwołanie do określonego zarządzanego obiektu, który ma obsługiwać wyrzucania elementów bezużytecznych.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `handle`  
 [in] Wskaźnik do zarządzanego obiektu, który ma uchwyt kolekcji pamięci. Ta wartość jest <xref:System.IntPtr> obiektu i mogą być pobierane z <xref:System.Runtime.InteropServices.GCHandle> dla obiekt zarządzany.  
  
 `pOutValue`  
 [out] Wskaźnik do adresu ICorDebugReferenceValue obiekt, który reprezentuje odwołanie do określonego obiektu zarządzanego.  
  
## <a name="remarks"></a>Uwagi  
 Nie należy mylić wartości zwracane odwołanie o wartości odwołania kolekcji pamięci.  
  
 Zwracane odwołanie zachowuje się jak normalne odwołania. Gdy kontynuuje wykonywanie kodu po punkt przerwania jest wyłączona. Okres istnienia obiektu docelowego nie ma wpływu na okres istnienia wartości odwołania.  
  
> [!NOTE]
>  `GetReferenceValueFromGCHandle` Metody nie można zweryfikować dojście. W związku z tym `GetReferenceValueFromGCHandle` metody może potencjalnie uszkodzić zarówno debugera i kod debugowany, jeżeli nie przekazano nieprawidłowe dojście.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
