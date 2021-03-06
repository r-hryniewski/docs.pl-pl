---
title: StrongNameCompareAssemblies — Funkcja
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bd1d098f21a3d5ba43b6251c87c36df4347a924
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457564"
---
# <a name="strongnamecompareassemblies-function"></a>StrongNameCompareAssemblies — Funkcja
Określa, czy dwa zestawy różnią się tylko ich podpisów silnej nazwy.  
  
 Ta funkcja jest przestarzała. Użyj [ICLRStrongName::StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) metody zamiast tego.  
  
## <a name="syntax"></a>Składnia  
  
```  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `wszAssembly1`  
 [in] Ścieżka do pierwszego zestawu.  
  
 `wszAssembly2`  
 [in] Ścieżka do drugiego zestawu.  
  
 `pdwResult`  
 [out] Jedna z następujących wartości:  
  
-   `SN_CMP_DIFFERENT` (0) — określa, czy zestawy zawierać innych danych.  
  
-   `SN_CMP_IDENTICAL` (1) — określa, czy zestawy są dokładnie takie same, w tym ich podpisów i sumy kontrolnej.  
  
-   `SN_CMP_SIGONLY` (2) — określa, czy zestawy różnią się jedynie podpisu i sumy kontrolnej.  
  
## <a name="return-value"></a>Wartość zwracana  
 `true` Po pomyślnym ukończeniu; w przeciwnym razie `false`.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** StrongName.h  
  
 **Biblioteka:** uwzględnione jako zasób w MsCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="remarks"></a>Uwagi  
 Podpis silnej nazwy zestawu składa się z zestawu tekst nazwę, wersję, kulturę i token klucza publicznego.  
  
 Jeśli `StrongNameCompareAssemblies` funkcji nie powiodło się, wywołania [strongnameerrorinfo —](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funkcji, aby pobrać ostatniego wygenerowany błąd.  
  
## <a name="see-also"></a>Zobacz też  
 [StrongNameCompareAssemblies, metoda](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)  
 [ICLRStrongName, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
