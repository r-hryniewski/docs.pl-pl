---
title: "ICeeGen::GetMethodBuffer — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetMethodBuffer
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetMethodBuffer
helpviewer_keywords:
- ICeeGen::GetMethodBuffer method [.NET Framework metadata]
- GetMethodBuffer method [.NET Framework metadata]
ms.assetid: c7c5b39a-d4ac-41f1-9d1e-44163f563a49
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be6b74de649a9b13092e6a5dcd2d2f80a215a16d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="iceegengetmethodbuffer-method"></a><span data-ttu-id="0ccf0-102">ICeeGen::GetMethodBuffer — Metoda</span><span class="sxs-lookup"><span data-stu-id="0ccf0-102">ICeeGen::GetMethodBuffer Method</span></span>
<span data-ttu-id="0ccf0-103">Pobiera odpowiedni rozmiar buforu dla metody pod określonym adresem wirtualnego względną.</span><span class="sxs-lookup"><span data-stu-id="0ccf0-103">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="0ccf0-104">Ta metoda jest przestarzała i nie powinna być używana.</span><span class="sxs-lookup"><span data-stu-id="0ccf0-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ccf0-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="0ccf0-105">Syntax</span></span>  
  
```  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ccf0-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="0ccf0-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="0ccf0-107">[in] Wirtualny adres względny metody, dla którego ma zostać zwrócona w buforze.</span><span class="sxs-lookup"><span data-stu-id="0ccf0-107">[in] The relative virtual address of the method for which to return a buffer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="0ccf0-108">[out] Wskaźnik do buforu zwrócony.</span><span class="sxs-lookup"><span data-stu-id="0ccf0-108">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ccf0-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0ccf0-109">Requirements</span></span>  
 <span data-ttu-id="0ccf0-110">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ccf0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ccf0-111">**Nagłówek:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0ccf0-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ccf0-112">**Biblioteka:** używany jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0ccf0-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0ccf0-113">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ccf0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ccf0-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0ccf0-114">See Also</span></span>  
 [<span data-ttu-id="0ccf0-115">ICeeGen — interfejs</span><span class="sxs-lookup"><span data-stu-id="0ccf0-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)