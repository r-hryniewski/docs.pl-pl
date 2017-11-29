---
title: "ICorProfilerCallback::RemotingClientReceivingReply — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientReceivingReply
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f1dd027dc113abfceeb88abbc82c69ed395584e1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="7fbf1-102">ICorProfilerCallback::RemotingClientReceivingReply — Metoda</span><span class="sxs-lookup"><span data-stu-id="7fbf1-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="7fbf1-103">Powiadamia profiler Zakończono po stronie serwera część wywołaniem funkcji zdalnych i teraz odbiera klienta i informacje o przetwarzanie odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="7fbf1-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fbf1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7fbf1-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="7fbf1-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7fbf1-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="7fbf1-106">[in] Wartość, która będzie zgodne z wartością w [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) w tych warunkach:</span><span class="sxs-lookup"><span data-stu-id="7fbf1-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="7fbf1-107">Pliki cookie GUID komunikacji zdalnej są aktywne.</span><span class="sxs-lookup"><span data-stu-id="7fbf1-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="7fbf1-108">Kanał pomyślnie przesyła komunikat.</span><span class="sxs-lookup"><span data-stu-id="7fbf1-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="7fbf1-109">Identyfikator GUID pliki cookie są aktywne w procesie po stronie serwera.</span><span class="sxs-lookup"><span data-stu-id="7fbf1-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="7fbf1-110">Dzięki temu można łatwo parowanie zdalnych wywołań.</span><span class="sxs-lookup"><span data-stu-id="7fbf1-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="7fbf1-111">[in] Wartość, która jest `true` Jeśli wywołanie jest asynchroniczne, a w przeciwnym razie `false`.</span><span class="sxs-lookup"><span data-stu-id="7fbf1-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fbf1-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7fbf1-112">Requirements</span></span>  
 <span data-ttu-id="7fbf1-113">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fbf1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fbf1-114">**Nagłówek:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7fbf1-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7fbf1-115">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fbf1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fbf1-116">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fbf1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fbf1-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7fbf1-117">See Also</span></span>  
 [<span data-ttu-id="7fbf1-118">ICorProfilerCallback — interfejs</span><span class="sxs-lookup"><span data-stu-id="7fbf1-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)