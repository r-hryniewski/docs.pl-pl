---
title: "ICLRTaskManager::SetUILocale — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager.SetUILocale
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager::SetUILocale
helpviewer_keywords:
- ICLRTaskManager::SetUILocale method [.NET Framework hosting]
- SetUILocale method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 03adaa9a-2beb-49b3-b2c4-6b4fc3f10715
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 28ecba8b88ceadaf743f5c65bc6f257f7ef8cd60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="d3949-102">ICLRTaskManager::SetUILocale — Metoda</span><span class="sxs-lookup"><span data-stu-id="d3949-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="d3949-103">Powiadamia środowisko uruchomieniowe języka wspólnego (CLR), czy host został zmodyfikowany, ustawienia regionalne interfejsu użytkownika lub kultury, na aktualnie wykonywanego zadania.</span><span class="sxs-lookup"><span data-stu-id="d3949-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3949-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d3949-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3949-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d3949-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="d3949-106">[in] Wartość identyfikatora ustawień regionalnych mapy do nowo przypisanej kultury geograficzne i język interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d3949-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3949-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="d3949-107">Return Value</span></span>  
  
|<span data-ttu-id="d3949-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d3949-108">HRESULT</span></span>|<span data-ttu-id="d3949-109">Opis</span><span class="sxs-lookup"><span data-stu-id="d3949-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d3949-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3949-110">S_OK</span></span>|<span data-ttu-id="d3949-111">`SetUILocale`zwrócona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="d3949-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="d3949-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d3949-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d3949-113">Środowisko CLR nie został załadowany do procesu lub CLR jest w stanie, w którym nie można uruchamiać kodu zarządzanego lub pomyślnie przetworzyć wywołania.</span><span class="sxs-lookup"><span data-stu-id="d3949-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d3949-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d3949-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d3949-115">Upłynął limit czasu wywołania.</span><span class="sxs-lookup"><span data-stu-id="d3949-115">The call timed out.</span></span>|  
|<span data-ttu-id="d3949-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d3949-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d3949-117">Obiekt wywołujący nie jest właścicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="d3949-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d3949-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d3949-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d3949-119">Zdarzenie zostało anulowane podczas zablokowanych wątku lub włókna oczekiwał na nim.</span><span class="sxs-lookup"><span data-stu-id="d3949-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d3949-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d3949-120">E_FAIL</span></span>|<span data-ttu-id="d3949-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="d3949-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d3949-122">Gdy metoda zwróci wartość E_FAIL, CLR nie jest już możliwe w ramach procesu.</span><span class="sxs-lookup"><span data-stu-id="d3949-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d3949-123">Kolejne wywołania metody hosting zwracać HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d3949-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3949-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d3949-124">Remarks</span></span>  
 <span data-ttu-id="d3949-125">`SetUILocale`zapewnia możliwość hosta do wykonywania jakichkolwiek mechanizmów, który może mieć synchronizacji ustawień regionalnych.</span><span class="sxs-lookup"><span data-stu-id="d3949-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3949-126">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d3949-126">Requirements</span></span>  
 <span data-ttu-id="d3949-127">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3949-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3949-128">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d3949-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3949-129">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d3949-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3949-130">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3949-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3949-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d3949-131">See Also</span></span>  
 [<span data-ttu-id="d3949-132">ICLRTask — interfejs</span><span class="sxs-lookup"><span data-stu-id="d3949-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="d3949-133">ICLRTaskManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="d3949-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="d3949-134">IHostTask — interfejs</span><span class="sxs-lookup"><span data-stu-id="d3949-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="d3949-135">IHostTaskManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="d3949-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)