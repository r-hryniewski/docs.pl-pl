---
title: "ICorDebugDataTarget::GetPlatform — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget.GetPlatform Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cf2f852d0da36211e379a4068cccff9dfc656100
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="701e7-102">ICorDebugDataTarget::GetPlatform — Metoda</span><span class="sxs-lookup"><span data-stu-id="701e7-102">ICorDebugDataTarget::GetPlatform Method</span></span>
<span data-ttu-id="701e7-103">Zawiera informacje o platformie, w tym architektury procesora i systemu operacyjnego, na którym jest uruchomiony proces docelowy.</span><span class="sxs-lookup"><span data-stu-id="701e7-103">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="701e7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="701e7-104">Syntax</span></span>  
  
```  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="701e7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="701e7-105">Parameters</span></span>  
 `pTargetPlatform`  
 <span data-ttu-id="701e7-106">[out] Wskaźnik do [cordebugplatformenum —](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) wyliczenie opisujące platformy docelowej.</span><span class="sxs-lookup"><span data-stu-id="701e7-106">[out] A pointer to a [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="701e7-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="701e7-107">Remarks</span></span>  
 <span data-ttu-id="701e7-108">`CorDebugPlatformEnum` Zwracana wartość wyliczenia jest używany przez [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfejsu, aby określić szczegóły procesu docelowego, na przykład jego rozmiar wskaźnika, układ przestrzeni adresów, zestaw rejestru, format instrukcji, układ kontekstu i Konwencje wywoływania.</span><span class="sxs-lookup"><span data-stu-id="701e7-108">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="701e7-109">`pTargetPlatform` Wartość może odwoływać się do platformy, która jest emulowane dla elementu docelowego zamiast określania rzeczywistego sprzętu w użyciu.</span><span class="sxs-lookup"><span data-stu-id="701e7-109">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="701e7-110">Na przykład, należy użyć procesu, który jest uruchomiony w systemie Windows w środowisku Windows (WOW) w 64-bitowej wersji systemu operacyjnego Windows `CORDB_PLATFORM_WINDOWS_X86` wartość [cordebugplatformenum —](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="701e7-110">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="701e7-111">Ta metoda musi zakończyć się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="701e7-111">This method must succeed.</span></span> <span data-ttu-id="701e7-112">W przypadku niepowodzenia platformy docelowej jest korzystanie z niej.</span><span class="sxs-lookup"><span data-stu-id="701e7-112">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="701e7-113">Metoda może się nie powieść z następujących powodów:</span><span class="sxs-lookup"><span data-stu-id="701e7-113">The method may fail for the following reasons:</span></span>  
  
-   <span data-ttu-id="701e7-114">Platforma, która jest emulowane dla obiekt docelowy jest korzystanie z niej.</span><span class="sxs-lookup"><span data-stu-id="701e7-114">The platform that is being emulated for the target is unusable.</span></span>  
  
-   <span data-ttu-id="701e7-115">Nadaje się sprzętem na platformie docelowej.</span><span class="sxs-lookup"><span data-stu-id="701e7-115">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="701e7-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="701e7-116">Requirements</span></span>  
 <span data-ttu-id="701e7-117">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="701e7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="701e7-118">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="701e7-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="701e7-119">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="701e7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="701e7-120">**Wersje programu .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="701e7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="701e7-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="701e7-121">See Also</span></span>  
 [<span data-ttu-id="701e7-122">ICorDebugDataTarget — interfejs</span><span class="sxs-lookup"><span data-stu-id="701e7-122">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="701e7-123">Interfejsy debugowania</span><span class="sxs-lookup"><span data-stu-id="701e7-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="701e7-124">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="701e7-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)