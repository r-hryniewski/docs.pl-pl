---
title: "IHostGCManager::SuspensionStarting — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager.SuspensionStarting
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9c807a124570f38922509d27e52936b980e36fba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="3170f-102">IHostGCManager::SuspensionStarting — Metoda</span><span class="sxs-lookup"><span data-stu-id="3170f-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="3170f-103">Powiadamia hosta, że środowisko uruchomieniowe języka wspólnego (CLR) wstrzymuje wykonywanie zadań do wykonania wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="3170f-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3170f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3170f-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3170f-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="3170f-105">Return Value</span></span>  
  
|<span data-ttu-id="3170f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3170f-106">HRESULT</span></span>|<span data-ttu-id="3170f-107">Opis</span><span class="sxs-lookup"><span data-stu-id="3170f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3170f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3170f-108">S_OK</span></span>|<span data-ttu-id="3170f-109">`SuspensionStarting`zwrócona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="3170f-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="3170f-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3170f-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3170f-111">Środowisko CLR nie został załadowany do procesu lub CLR jest w stanie, w którym nie można uruchamiać kodu zarządzanego lub pomyślnie przetworzyć wywołania.</span><span class="sxs-lookup"><span data-stu-id="3170f-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3170f-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3170f-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3170f-113">Upłynął limit czasu wywołania.</span><span class="sxs-lookup"><span data-stu-id="3170f-113">The call timed out.</span></span>|  
|<span data-ttu-id="3170f-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3170f-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3170f-115">Obiekt wywołujący nie jest właścicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="3170f-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3170f-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3170f-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3170f-117">Zdarzenie zostało anulowane podczas zablokowanych wątku lub włókna oczekiwał na nim.</span><span class="sxs-lookup"><span data-stu-id="3170f-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3170f-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3170f-118">E_FAIL</span></span>|<span data-ttu-id="3170f-119">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="3170f-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3170f-120">Gdy metoda zwróci wartość E_FAIL, CLR nie jest już możliwe w ramach procesu.</span><span class="sxs-lookup"><span data-stu-id="3170f-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3170f-121">Kolejne wywołania metody hosting zwracać HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3170f-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3170f-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3170f-122">Remarks</span></span>  
 <span data-ttu-id="3170f-123">Wywołania CLR `SuspensionStarting` poinformowanie hosta, który występuje wyrzucanie elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="3170f-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3170f-124">Nie harmonogram tego zadania.</span><span class="sxs-lookup"><span data-stu-id="3170f-124">Do not reschedule this task.</span></span> <span data-ttu-id="3170f-125">Host musi zmienić harmonogram zadania po [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="3170f-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3170f-126">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3170f-126">Requirements</span></span>  
 <span data-ttu-id="3170f-127">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3170f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3170f-128">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3170f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3170f-129">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3170f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3170f-130">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3170f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3170f-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3170f-131">See Also</span></span>  
 [<span data-ttu-id="3170f-132">ICLRTask — interfejs</span><span class="sxs-lookup"><span data-stu-id="3170f-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="3170f-133">ICLRTaskManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="3170f-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="3170f-134">IHostTask — interfejs</span><span class="sxs-lookup"><span data-stu-id="3170f-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="3170f-135">IHostTaskManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="3170f-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="3170f-136">IHostGCManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="3170f-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)