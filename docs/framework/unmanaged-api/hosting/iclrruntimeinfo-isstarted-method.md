---
title: "ICLRRuntimeInfo::IsStarted — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.IsStarted
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d6bcaf6e0d10bd935e7ba4a2bb79941be1af6950
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="c13ba-102">ICLRRuntimeInfo::IsStarted — Metoda</span><span class="sxs-lookup"><span data-stu-id="c13ba-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="c13ba-103">Wskazuje, czy środowisko uruchomieniowe zostało rozpoczęte (to znaczy czy [ICLRRuntimeHost::Start — metoda](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) została wywołana i zakończyła się pomyślnie).</span><span class="sxs-lookup"><span data-stu-id="c13ba-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c13ba-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c13ba-104">Syntax</span></span>  
  
```  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c13ba-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c13ba-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="c13ba-106">[out] `true` Jeżeli to środowisko uruchomieniowe jest uruchomiony; w przeciwnym razie `false`.</span><span class="sxs-lookup"><span data-stu-id="c13ba-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="c13ba-107">[out] Zwraca flagi, które były używane do uruchamiania środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="c13ba-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c13ba-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="c13ba-108">Return Value</span></span>  
 <span data-ttu-id="c13ba-109">Ta metoda zwraca następujące określonych wyników HRESULT, a także HRESULT błędów wskazujących Niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="c13ba-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c13ba-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c13ba-110">HRESULT</span></span>|<span data-ttu-id="c13ba-111">Opis</span><span class="sxs-lookup"><span data-stu-id="c13ba-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c13ba-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c13ba-112">S_OK</span></span>|<span data-ttu-id="c13ba-113">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="c13ba-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="c13ba-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="c13ba-114">E_NOTIMPL</span></span>|<span data-ttu-id="c13ba-115">Typowe wersja środowiska uruchomieniowego (języka wspólnego CLR) języka jest starsza niż wersja CLR w [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c13ba-115">The common language runtime (CLR) version is earlier than the CLR version in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c13ba-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c13ba-116">Remarks</span></span>  
 <span data-ttu-id="c13ba-117">Ta metoda nie działa z CLR wersji wcześniejszych niż wersja środowiska CLR w [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c13ba-117">This method does not work with CLR versions earlier than the CLR version in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c13ba-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c13ba-118">Requirements</span></span>  
 <span data-ttu-id="c13ba-119">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c13ba-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c13ba-120">**Nagłówek:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c13ba-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c13ba-121">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c13ba-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c13ba-122">**Wersje programu .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c13ba-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c13ba-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c13ba-123">See Also</span></span>  
 [<span data-ttu-id="c13ba-124">ICLRRuntimeInfo — interfejs</span><span class="sxs-lookup"><span data-stu-id="c13ba-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="c13ba-125">Hosting — interfejsy</span><span class="sxs-lookup"><span data-stu-id="c13ba-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="c13ba-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="c13ba-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)