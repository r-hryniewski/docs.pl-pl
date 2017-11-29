---
title: "ICorProfilerCallback::ExceptionThrown — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionThrown
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3986ca8205297a36bb54825a7af72aeb9821f75b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="6416d-102">ICorProfilerCallback::ExceptionThrown — Metoda</span><span class="sxs-lookup"><span data-stu-id="6416d-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="6416d-103">Powiadamia profilera zgłosił wyjątek.</span><span class="sxs-lookup"><span data-stu-id="6416d-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6416d-104">Ta funkcja jest wywoływana tylko wtedy, gdy wyjątek osiągnie kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="6416d-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6416d-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="6416d-105">Syntax</span></span>  
  
```  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6416d-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="6416d-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="6416d-107">[in] Identyfikator obiektu, który spowodował wyjątek zostanie wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="6416d-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6416d-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6416d-108">Remarks</span></span>  
 <span data-ttu-id="6416d-109">Profilera nie należy zablokować w jej implementacja tej metody, ponieważ stos nie może być w stanie, który umożliwia odzyskiwanie pamięci i dlatego nie można włączyć cenią sobie wcześniejsze wyrzucanie elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="6416d-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="6416d-110">Jeśli profilera blokuje tutaj i nastąpiła wyrzucanie elementów bezużytecznych, środowisko uruchomieniowe zablokuje dopóki zwraca tego wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="6416d-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="6416d-111">Profiler implementacja tej metody nie powinny wywoływać kodu zarządzanego lub w dowolnym Przyczyna sposób alokacji pamięci zarządzane.</span><span class="sxs-lookup"><span data-stu-id="6416d-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6416d-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6416d-112">Requirements</span></span>  
 <span data-ttu-id="6416d-113">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6416d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6416d-114">**Nagłówek:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6416d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6416d-115">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6416d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6416d-116">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6416d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6416d-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6416d-117">See Also</span></span>  
 [<span data-ttu-id="6416d-118">ICorProfilerCallback — interfejs</span><span class="sxs-lookup"><span data-stu-id="6416d-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)