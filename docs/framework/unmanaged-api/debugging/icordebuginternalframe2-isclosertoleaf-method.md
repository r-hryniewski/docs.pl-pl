---
title: "ICorDebugInternalFrame2::IsCloserToLeaf — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 60e63800ade5fb0d4a222d80ebfe43c3d84c2815
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="1c5c1-102">ICorDebugInternalFrame2::IsCloserToLeaf — Metoda</span><span class="sxs-lookup"><span data-stu-id="1c5c1-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="1c5c1-103">Sprawdza, czy `this` wewnętrzny ramki jest bliżej niż określony obiekt ICorDebugFrame liścia.</span><span class="sxs-lookup"><span data-stu-id="1c5c1-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c5c1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="1c5c1-104">Syntax</span></span>  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c5c1-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="1c5c1-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="1c5c1-106">[in] Wskaźnik do porównania `ICorDebugFrame` obiektu.</span><span class="sxs-lookup"><span data-stu-id="1c5c1-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="1c5c1-107">[out] `true` Jeśli `this` wewnętrzny ramki jest bliżej liścia niż ramki określony przez `pFrameToCompare`; w przeciwnym razie `false`.</span><span class="sxs-lookup"><span data-stu-id="1c5c1-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c5c1-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="1c5c1-108">Return Value</span></span>  
 <span data-ttu-id="1c5c1-109">Ta metoda zwraca następujące określonych wyników HRESULT, a także HRESULT błędów wskazujących Niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="1c5c1-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1c5c1-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1c5c1-110">HRESULT</span></span>|<span data-ttu-id="1c5c1-111">Opis</span><span class="sxs-lookup"><span data-stu-id="1c5c1-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1c5c1-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1c5c1-112">S_OK</span></span>|<span data-ttu-id="1c5c1-113">Porównanie zostało wykonane pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="1c5c1-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="1c5c1-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1c5c1-114">E_FAIL</span></span>|<span data-ttu-id="1c5c1-115">Nie można wykonać porównania.</span><span class="sxs-lookup"><span data-stu-id="1c5c1-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="1c5c1-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1c5c1-116">E_INVALIDARG</span></span>|<span data-ttu-id="1c5c1-117">`pFrameToCompare`lub `pIsCloser` ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="1c5c1-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c5c1-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1c5c1-118">Remarks</span></span>  
 <span data-ttu-id="1c5c1-119">`IsCloserToLeaf`może służyć do zaimplementowania zasad dla naprzemiennego wykonywania wewnętrznego ramki z innych ramek na stosie.</span><span class="sxs-lookup"><span data-stu-id="1c5c1-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c5c1-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1c5c1-120">Requirements</span></span>  
 <span data-ttu-id="1c5c1-121">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c5c1-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c5c1-122">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c5c1-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c5c1-123">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c5c1-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c5c1-124">**Wersje programu .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c5c1-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c5c1-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1c5c1-125">See Also</span></span>  
 [<span data-ttu-id="1c5c1-126">ICorDebugInternalFrame2 — interfejs</span><span class="sxs-lookup"><span data-stu-id="1c5c1-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 [<span data-ttu-id="1c5c1-127">Interfejsy debugowania</span><span class="sxs-lookup"><span data-stu-id="1c5c1-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="1c5c1-128">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="1c5c1-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)