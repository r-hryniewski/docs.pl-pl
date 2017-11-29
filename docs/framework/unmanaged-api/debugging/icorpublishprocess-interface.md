---
title: "ICorPublishProcess — Interfejs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess
helpviewer_keywords: ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cb62da277ff13bea33969bb9c728cac5d5a15554
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="b1d7f-102">ICorPublishProcess — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b1d7f-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="b1d7f-103">Udostępnia metody, które uzyskują dostęp do informacji wyświetlanych dotyczące procesu.</span><span class="sxs-lookup"><span data-stu-id="b1d7f-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b1d7f-104">Metody</span><span class="sxs-lookup"><span data-stu-id="b1d7f-104">Methods</span></span>  
  
|<span data-ttu-id="b1d7f-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="b1d7f-105">Method</span></span>|<span data-ttu-id="b1d7f-106">Opis</span><span class="sxs-lookup"><span data-stu-id="b1d7f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b1d7f-107">EnumAppDomains — metoda</span><span class="sxs-lookup"><span data-stu-id="b1d7f-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="b1d7f-108">Pobiera [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) wystąpienia, które zawiera domeny aplikacji w procesie odwołuje się to `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="b1d7f-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="b1d7f-109">GetDisplayName — metoda</span><span class="sxs-lookup"><span data-stu-id="b1d7f-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="b1d7f-110">Pobiera pełną ścieżkę do pliku wykonywalnego procesu, który odwołuje się ten `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="b1d7f-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="b1d7f-111">GetProcessID — metoda</span><span class="sxs-lookup"><span data-stu-id="b1d7f-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="b1d7f-112">Pobiera identyfikator system operacyjny dla procesu, który odwołuje się to `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="b1d7f-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="b1d7f-113">IsManaged — metoda</span><span class="sxs-lookup"><span data-stu-id="b1d7f-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="b1d7f-114">Pobiera wartość wskazującą, czy proces odwołuje się ten `ICorPublishProcess` wiadomo, że jest uruchomiona kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="b1d7f-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b1d7f-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b1d7f-115">Requirements</span></span>  
 <span data-ttu-id="b1d7f-116">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1d7f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1d7f-117">**Nagłówek:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="b1d7f-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b1d7f-118">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1d7f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1d7f-119">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1d7f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d7f-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b1d7f-120">See Also</span></span>  
 [<span data-ttu-id="b1d7f-121">Interfejsy debugowania</span><span class="sxs-lookup"><span data-stu-id="b1d7f-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b1d7f-122">Corpubpublish — klasa Coclass</span><span class="sxs-lookup"><span data-stu-id="b1d7f-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)