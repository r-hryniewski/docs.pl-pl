---
title: "ICLRRuntimeInfo::LoadLibrary — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.LoadLibrary
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c1d943f45a4e665836f376bddf65d84329c1900e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="f765b-102">ICLRRuntimeInfo::LoadLibrary — Metoda</span><span class="sxs-lookup"><span data-stu-id="f765b-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="f765b-103">Ładuje Biblioteka programu .NET Framework z środowisko uruchomieniowe języka wspólnego (CLR) reprezentowany przez [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfejsu.</span><span class="sxs-lookup"><span data-stu-id="f765b-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="f765b-104">Ta metoda zastępuje [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) funkcji.</span><span class="sxs-lookup"><span data-stu-id="f765b-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f765b-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="f765b-105">Syntax</span></span>  
  
```  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f765b-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="f765b-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="f765b-107">[in] Nazwa zestawu do załadowania.</span><span class="sxs-lookup"><span data-stu-id="f765b-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="f765b-108">[out] Dojście do załadowanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="f765b-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f765b-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="f765b-109">Return Value</span></span>  
 <span data-ttu-id="f765b-110">Ta metoda zwraca następujące określonych wyników HRESULT, a także HRESULT błędów wskazujących Niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="f765b-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f765b-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f765b-111">HRESULT</span></span>|<span data-ttu-id="f765b-112">Opis</span><span class="sxs-lookup"><span data-stu-id="f765b-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f765b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f765b-113">S_OK</span></span>|<span data-ttu-id="f765b-114">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="f765b-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="f765b-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f765b-115">E_POINTER</span></span>|<span data-ttu-id="f765b-116">`pwzDllName`lub `phndModule` ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="f765b-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="f765b-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f765b-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f765b-118">Za mało pamięci jest dostępna do obsługi żądania.</span><span class="sxs-lookup"><span data-stu-id="f765b-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f765b-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f765b-119">Remarks</span></span>  
 <span data-ttu-id="f765b-120">Ta metoda ładuje tylko biblioteki DLL uwzględniona w pakiet redystrybucyjny programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f765b-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="f765b-121">Nie można załadować zestawów generowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f765b-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f765b-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f765b-122">Requirements</span></span>  
 <span data-ttu-id="f765b-123">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f765b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f765b-124">**Nagłówek:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f765b-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f765b-125">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f765b-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f765b-126">**Wersje programu .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f765b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f765b-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f765b-127">See Also</span></span>  
 [<span data-ttu-id="f765b-128">ICLRRuntimeInfo — interfejs</span><span class="sxs-lookup"><span data-stu-id="f765b-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="f765b-129">Hosting — interfejsy</span><span class="sxs-lookup"><span data-stu-id="f765b-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="f765b-130">Hosting</span><span class="sxs-lookup"><span data-stu-id="f765b-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)