---
title: ISymUnmanagedWriter::UsingNamespace — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.UsingNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a5ff52a95fd6ebaec05439cbc702d5513d0cc78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427772"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a>ISymUnmanagedWriter::UsingNamespace — Metoda
Określa, że podana nazwa przestrzeni nazw FQDN jest w użyciu w zakresie leksykalne aktualnie otwarte. Przestrzeń nazw będzie używany w ramach wszystkie zakresy, które dziedziczą po zakresie aktualnie otwarte. Zamykanie bieżącego zakresu spowoduje również przerwanie Użyj przestrzeni nazw.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
#### <a name="parameters"></a>Parametry  
 `fullName`  
 [in] Wskaźnik do w pełni kwalifikowana nazwa przestrzeni nazw.  
  
## <a name="return-value"></a>Wartość zwracana  
 Wartość S_OK, jeśli metoda zakończy się pomyślnie; w przeciwnym razie E_FAIL lub inny kod błędu.  
  
## <a name="requirements"></a>Wymagania  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Zobacz też  
 [ISymUnmanagedWriter, interfejs](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
