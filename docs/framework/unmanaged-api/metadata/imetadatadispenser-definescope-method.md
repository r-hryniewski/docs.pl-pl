---
title: "IMetaDataDispenser::DefineScope — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenser.DefineScope
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 964e6df1b6aba7ca85b627cf19c38f5df600b6ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="399f6-102">IMetaDataDispenser::DefineScope — Metoda</span><span class="sxs-lookup"><span data-stu-id="399f6-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="399f6-103">Tworzy nowy obszar w pamięci, w którym można utworzyć nowe metadane.</span><span class="sxs-lookup"><span data-stu-id="399f6-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="399f6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="399f6-104">Syntax</span></span>  
  
```  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="399f6-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="399f6-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="399f6-106">[in] Identyfikator CLSID wersji struktur metadanych ma zostać utworzony.</span><span class="sxs-lookup"><span data-stu-id="399f6-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="399f6-107">Ta wartość musi być CLSID_CorMetaDataRuntime dla programu .NET Framework w wersji 2.0.</span><span class="sxs-lookup"><span data-stu-id="399f6-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="399f6-108">[in] Flagi, które określają opcje.</span><span class="sxs-lookup"><span data-stu-id="399f6-108">[in] Flags that specify options.</span></span> <span data-ttu-id="399f6-109">Ta wartość musi wynosić zero dla programu .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="399f6-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="399f6-110">[in] Uzyskanie identyfikatora IID interfejsu odpowiednie metadane zwrócone; obiekt wywołujący będą używać interfejsu, aby utworzyć nowe metadane.</span><span class="sxs-lookup"><span data-stu-id="399f6-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="399f6-111">Wartość `riid` należy określić jeden z interfejsów "Emituj".</span><span class="sxs-lookup"><span data-stu-id="399f6-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="399f6-112">Prawidłowe wartości to IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit lub IID_IMetaDataEmit2.</span><span class="sxs-lookup"><span data-stu-id="399f6-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="399f6-113">[out] Wskaźnik do interfejsu zwrócony.</span><span class="sxs-lookup"><span data-stu-id="399f6-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="399f6-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="399f6-114">Remarks</span></span>  
 <span data-ttu-id="399f6-115">`DefineScope`Tworzy zestaw tabel metadanych w pamięci, generuje unikatowy identyfikator GUID (identyfikator wersji modułu lub identyfikatora MVID) metadanych i tworzy wpis w tabeli modułu dla jednostki kompilacji jest emitowany.</span><span class="sxs-lookup"><span data-stu-id="399f6-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="399f6-116">Możesz dołączyć atrybuty do zakresu metadanych jako całość przy użyciu [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) lub [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) metody, zależnie od potrzeb.</span><span class="sxs-lookup"><span data-stu-id="399f6-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="399f6-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="399f6-117">Requirements</span></span>  
 <span data-ttu-id="399f6-118">**Platforma:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="399f6-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="399f6-119">**Nagłówek:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="399f6-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="399f6-120">**Biblioteka:** używany jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="399f6-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="399f6-121">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="399f6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="399f6-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="399f6-122">See Also</span></span>  
 [<span data-ttu-id="399f6-123">IMetaDataDispenser — interfejs</span><span class="sxs-lookup"><span data-stu-id="399f6-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [<span data-ttu-id="399f6-124">IMetaDataDispenserEx — interfejs</span><span class="sxs-lookup"><span data-stu-id="399f6-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="399f6-125">IMetaDataAssemblyEmit — interfejs</span><span class="sxs-lookup"><span data-stu-id="399f6-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="399f6-126">IMetaDataEmit — interfejs</span><span class="sxs-lookup"><span data-stu-id="399f6-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="399f6-127">IMetaDataEmit2 — interfejs</span><span class="sxs-lookup"><span data-stu-id="399f6-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)