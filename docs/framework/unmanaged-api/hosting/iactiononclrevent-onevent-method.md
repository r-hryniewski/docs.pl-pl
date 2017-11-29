---
title: "IActionOnCLREvent::OnEvent — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IActionOnCLREvent.OnEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b2f609969ccf67f07701d20578225f1618293968
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="26b1b-102">IActionOnCLREvent::OnEvent — Metoda</span><span class="sxs-lookup"><span data-stu-id="26b1b-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="26b1b-103">Wykonuje wywołania zwrotne na zdarzenia, które zostały zarejestrowane przy użyciu wywołania [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) metody.</span><span class="sxs-lookup"><span data-stu-id="26b1b-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26b1b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="26b1b-104">Syntax</span></span>  
  
```  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="26b1b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="26b1b-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="26b1b-106">[in] Jeden z [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) wartości, które wskazuje typ zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="26b1b-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="26b1b-107">[in] Wskaźnik do obiektu, który zawiera szczegółowe informacje o `event`.</span><span class="sxs-lookup"><span data-stu-id="26b1b-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26b1b-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="26b1b-108">Return Value</span></span>  
  
|<span data-ttu-id="26b1b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="26b1b-109">HRESULT</span></span>|<span data-ttu-id="26b1b-110">Opis</span><span class="sxs-lookup"><span data-stu-id="26b1b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="26b1b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="26b1b-111">S_OK</span></span>|<span data-ttu-id="26b1b-112">`OnEvent`zwrócona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="26b1b-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="26b1b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="26b1b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="26b1b-114">Środowisko uruchomieniowe języka wspólnego (CLR) nie został załadowany do procesu lub CLR jest w stanie, w którym nie można uruchamiać kodu zarządzanego lub pomyślnie przetworzyć wywołania.</span><span class="sxs-lookup"><span data-stu-id="26b1b-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="26b1b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="26b1b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="26b1b-116">Upłynął limit czasu wywołania.</span><span class="sxs-lookup"><span data-stu-id="26b1b-116">The call timed out.</span></span>|  
|<span data-ttu-id="26b1b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="26b1b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="26b1b-118">Obiekt wywołujący nie jest właścicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="26b1b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="26b1b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="26b1b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="26b1b-120">Zdarzenie zostało anulowane podczas zablokowanych wątku lub włókna oczekiwał na nim.</span><span class="sxs-lookup"><span data-stu-id="26b1b-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="26b1b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="26b1b-121">E_FAIL</span></span>|<span data-ttu-id="26b1b-122">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="26b1b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="26b1b-123">Jeśli metoda zwraca E_FAIL, CLR nie będzie już można używać w ramach procesu.</span><span class="sxs-lookup"><span data-stu-id="26b1b-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="26b1b-124">Kolejne wywołania do dowolnej metody hostingu zwracać HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="26b1b-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26b1b-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="26b1b-125">Remarks</span></span>  
 <span data-ttu-id="26b1b-126">`data` Parametr jest wskaźnik do obiektu nieokreślonego typu.</span><span class="sxs-lookup"><span data-stu-id="26b1b-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="26b1b-127">Jeśli `event` parametr jest `Event_DomainUnload`, `data` jest identyfikator liczbowy <xref:System.AppDomain> który został zwolniony.</span><span class="sxs-lookup"><span data-stu-id="26b1b-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="26b1b-128">Hosta można podjąć odpowiednie działania, przy użyciu tego identyfikatora jako klucza.</span><span class="sxs-lookup"><span data-stu-id="26b1b-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="26b1b-129">Jeśli `event` jest `Event_MDAFired`, `data` jest wskaźnikiem do [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) wystąpienia, które zawiera dane wyjściowe z zarządzanego debugowania Asystenta (MDA) komunikatu.</span><span class="sxs-lookup"><span data-stu-id="26b1b-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="26b1b-130">Mda są funkcją środowiska CLR, która pomóc deweloperom z debugowaniem, generując XML komunikaty o zdarzeniach, które w przeciwnym razie są trudne do pułapki.</span><span class="sxs-lookup"><span data-stu-id="26b1b-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="26b1b-131">Wysyłanie wiadomości tego może być szczególnie przydatne w debugowaniu przejścia między zarządzanymi i niezarządzanymi kodu.</span><span class="sxs-lookup"><span data-stu-id="26b1b-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="26b1b-132">Aby uzyskać więcej informacji, zobacz [diagnozowanie problemów z Asystenci zarządzanego debugowania](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="26b1b-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26b1b-133">Wymagania</span><span class="sxs-lookup"><span data-stu-id="26b1b-133">Requirements</span></span>  
 <span data-ttu-id="26b1b-134">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26b1b-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26b1b-135">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="26b1b-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="26b1b-136">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="26b1b-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26b1b-137">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26b1b-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26b1b-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="26b1b-138">See Also</span></span>  
 [<span data-ttu-id="26b1b-139">Diagnozowanie błędów przy użyciu Asystenci zarządzanego debugowania</span><span class="sxs-lookup"><span data-stu-id="26b1b-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="26b1b-140">EClrEvent — wyliczenie</span><span class="sxs-lookup"><span data-stu-id="26b1b-140">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="26b1b-141">IActionOnCLREvent — interfejs</span><span class="sxs-lookup"><span data-stu-id="26b1b-141">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="26b1b-142">ICLRControl — interfejs</span><span class="sxs-lookup"><span data-stu-id="26b1b-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="26b1b-143">ICLROnEventManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="26b1b-143">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="26b1b-144">MDAInfo — struktura</span><span class="sxs-lookup"><span data-stu-id="26b1b-144">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)