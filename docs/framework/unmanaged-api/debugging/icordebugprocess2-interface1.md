---
title: ICorDebugProcess2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2
helpviewer_keywords: ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca1a73874f6ca2f839639cbaf731a59721b2aede
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2-interface1"></a><span data-ttu-id="2e378-102">ICorDebugProcess2 Interface1</span><span class="sxs-lookup"><span data-stu-id="2e378-102">ICorDebugProcess2 Interface1</span></span>
<span data-ttu-id="2e378-103">Logiczne rozszerzenie ICorDebugProcess — interfejs, który reprezentuje proces uruchamiania kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="2e378-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2e378-104">Metody</span><span class="sxs-lookup"><span data-stu-id="2e378-104">Methods</span></span>  
  
|<span data-ttu-id="2e378-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="2e378-105">Method</span></span>|<span data-ttu-id="2e378-106">Opis</span><span class="sxs-lookup"><span data-stu-id="2e378-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2e378-107">ClearUnmanagedBreakpoint — metoda</span><span class="sxs-lookup"><span data-stu-id="2e378-107">ClearUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="2e378-108">Usunięcie punktu przerwania od wskazanego przesunięcia, który został ustawiony przez wywołanie wcześniejszych `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="2e378-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="2e378-109">GetDesiredNGENCompilerFlags — metoda</span><span class="sxs-lookup"><span data-stu-id="2e378-109">GetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="2e378-110">Pobiera flagi, które muszą być ustawione dla środowisko uruchomieniowe języka wspólnego (CLR) można załadować obrazu z procesem odwołuje się to `ICorDebugProcess2`.</span><span class="sxs-lookup"><span data-stu-id="2e378-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="2e378-111">GetReferenceValueFromGCHandle — metoda</span><span class="sxs-lookup"><span data-stu-id="2e378-111">GetReferenceValueFromGCHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="2e378-112">Pobiera wskaźnik odwołanie do określonego zarządzanego obiektu, który ma obsługiwać wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="2e378-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="2e378-113">GetThreadForTaskID — metoda</span><span class="sxs-lookup"><span data-stu-id="2e378-113">GetThreadForTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="2e378-114">Pobiera wątku, na którym jest wykonywane zadanie o podanym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="2e378-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="2e378-115">GetVersion — metoda</span><span class="sxs-lookup"><span data-stu-id="2e378-115">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|<span data-ttu-id="2e378-116">Pobiera wersję środowiska CLR, na którym jest uruchomiona debugowanego procesu.</span><span class="sxs-lookup"><span data-stu-id="2e378-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="2e378-117">SetDesiredNGENCompilerFlags — metoda</span><span class="sxs-lookup"><span data-stu-id="2e378-117">SetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="2e378-118">Ustawia flagi, które są wymagane dla kompilatora just in time (JIT) można załadować obrazu w debugowanym procesie.</span><span class="sxs-lookup"><span data-stu-id="2e378-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="2e378-119">SetUnmanagedBreakpoint — metoda</span><span class="sxs-lookup"><span data-stu-id="2e378-119">SetUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="2e378-120">Ustawia niezarządzanego punktu przerwania w przesunięciu określonego obrazu macierzystego.</span><span class="sxs-lookup"><span data-stu-id="2e378-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e378-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2e378-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e378-122">Ten interfejs nie obsługuje wywoływany zdalnie, między komputerami lub między procesami.</span><span class="sxs-lookup"><span data-stu-id="2e378-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e378-123">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2e378-123">Requirements</span></span>  
 <span data-ttu-id="2e378-124">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e378-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e378-125">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e378-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e378-126">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e378-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e378-127">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e378-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e378-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2e378-128">See Also</span></span>  
 [<span data-ttu-id="2e378-129">Interfejsy debugowania</span><span class="sxs-lookup"><span data-stu-id="2e378-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)