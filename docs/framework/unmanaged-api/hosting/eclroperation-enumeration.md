---
title: EClrOperation — Wyliczenie
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b18c89cee0c3f5088a9978e448a0d61de1b9848
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434248"
---
# <a name="eclroperation-enumeration"></a>EClrOperation — Wyliczenie
W tym artykule opisano zestaw działań, dla których hosta można zastosować akcje zasady.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|Hosta można określić zasady akcje do wykonania, kiedy <xref:System.AppDomain> jest zwalnianie w sposób (niegrzeczny) nie jest bezpieczne.|  
|`OPR_AppDomainUnload`|Hosta można określić zasady akcje do wykonania, kiedy <xref:System.AppDomain> zostanie zwolniona.|  
|`OPR_FinalizerRun`|Hosta można określić zasady akcje do wykonania podczas uruchamiania finalizatory.|  
|`OPR_ProcessExit`|Hosta można określić zasady akcje do wykonania, gdy kończy proces.|  
|`OPR_ThreadAbort`|Hosta można określić zasady akcje do wykonania, gdy wątek został przerwany.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|Hosta można określić zasady akcje do wykonania, kiedy występuje przerwania niegrzeczny wątku w regionie krytyczne kodu.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|Hosta można określić zasady akcje podjęcie sytuacji przerwania niegrzeczny wątku w regionie niekrytyczne kodu.|  
  
## <a name="remarks"></a>Uwagi  
 Wspólna infrastruktura niezawodności środowiska uruchomieniowego (języka wspólnego CLR) języka rozróżnia przerwań i zasobów alokacji błędów występujących w regionach krytyczne kodu i tych, które występują w regionach niekrytyczne kodu. Ta różnica umożliwia hostom skonfigurowanie różnych zasad w zależności od tego, gdzie występuje błąd w kodzie.  
  
 A *krytyczne region kodu* dowolnego miejsca, gdzie CLR nie może zagwarantować, że przerywanie zadania lub nie można ukończyć żądania dla zasobów wpłynie na bieżące zadanie. Na przykład, jeśli zadanie jest blokada i otrzyma HRESULT wskazujący błąd podczas tworzenia żądania alokacji pamięci, jest za mało, aby po prostu przerwać tego zadania w celu zapewnienia stabilności <xref:System.AppDomain>, ponieważ <xref:System.AppDomain> może zawierać inne Oczekiwanie na tym samym blokady zadania. Aby odrzucić bieżący zadania może spowodować, że te inne zadania przestać odpowiadać (lub Rozłącz) przez nieograniczony czas. W takim przypadku host musi mieć możliwość zwolnienia całą <xref:System.AppDomain> zamiast niestabilność potencjalne zagrożenia.  
  
 A *niekrytyczne region kodu*, z drugiej strony, jest regionu, w którym środowiska CLR może zagwarantować, że przerwania lub awarii będzie miało wpływ na zadania, na których występuje błąd.  
  
 Środowisko CLR rozróżnia również bezpieczne i łagodne przerwań (niegrzeczny). Ogólnie rzecz biorąc przerwania normalne lub bezpieczne sprawia, że wszelkich starań, aby uruchomić procedury obsługi wyjątków i finalizatory przed przerwaniem zadania, podczas gdy niegrzeczny przerwania sprawia, że nie gwarancje.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE.h  
  
 **Biblioteka:** biblioteki MSCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [EClrFailure, wyliczenie](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [EPolicyAction, wyliczenie](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [ICLRPolicyManager, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [IHostPolicyManager, interfejs](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [Hosting — wyliczenia](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
