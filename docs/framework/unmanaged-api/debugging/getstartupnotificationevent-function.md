---
title: GetStartupNotificationEvent — Funkcja
ms.date: 03/30/2017
api_name:
- GetStartupNotificationEvent
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- GetStartupNotificationEvent
helpviewer_keywords:
- GetStartupNotificationEvent function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: c94b1b61-045a-4695-bacd-0f18c5acc246
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3692471e0652a1a812b1d0cbed9e38cc32112ef4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404313"
---
# <a name="getstartupnotificationevent-function"></a>GetStartupNotificationEvent — Funkcja
Tworzy lub otwiera obsługi zdarzenia, które są sygnalizowane po przez dowolnego środowisko uruchomieniowe języka wspólnego (CLR), który jest ładowany w procesie określonego obiektu docelowego.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
#### <a name="parameters"></a>Parametry  
 `debuggeePID`  
 [in] Identyfikator procesu Proces docelowy, z których chcesz otrzymywać powiadomienia uruchamiania CLR.  
  
 `phStartupEvent`  
 [out] Wskaźnik do uchwytu, które zostanie zgłoszony przez środowisko CLR podczas uruchamiania.  
  
## <a name="return-value"></a>Wartość zwracana  
 S_OK  
 Pomyślnie uzyskano dojścia do uruchamiania zdarzeń powiadomień.  
  
 E_INVALIDARG  
 `phStartupEvent` ma wartość null lub `debuggeePID` nie odwołuje się do procesu, który jest obecnie uruchomiona.  
  
 E_FAIL (lub inne kody powrotu E_)  
 Nie można uzyskać dojścia do uruchamiania zdarzeń powiadomień.  
  
## <a name="remarks"></a>Uwagi  
 W systemie operacyjnym Windows `debuggeePID` identyfikator przetworzyć map do systemu operacyjnego.  
  
 Zdarzenie jest sygnalizowane przed każdą zarządzane, że kod jest wykonywany przez środowisko CLR, która sygnalizuje zdarzenia.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** dbgshim.h  
  
 **Biblioteka:** biblioteki dbgshim.dll  
  
 **Wersje programu .NET framework:** 3.5 z dodatkiem SP1
