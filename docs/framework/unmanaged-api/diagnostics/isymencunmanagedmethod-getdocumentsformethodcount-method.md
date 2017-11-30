---
title: "ISymENCUnmanagedMethod::GetDocumentsForMethodCount — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymENCUnmanagedMethod.GetDocumentsForMethodCount
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymENCUnmanagedMethod::GetDocumentsForMethodCount
helpviewer_keywords:
- GetDocumentsForMethodCount method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount method [.NET Framework debugging]
ms.assetid: cc1a823a-3ff3-4a33-b641-96edc93d2b17
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 49b849ced80d526ed529bad1eaa766d5a2a19d51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="214fe-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount — Metoda</span><span class="sxs-lookup"><span data-stu-id="214fe-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="214fe-103">Pobiera liczbę dokumentów, które ta metoda ma wiersze w.</span><span class="sxs-lookup"><span data-stu-id="214fe-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="214fe-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="214fe-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="214fe-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="214fe-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="214fe-106">[out] Wskaźnik do `ULONG32` odbierająca rozmiar buforu, muszą zawierać dokumenty.</span><span class="sxs-lookup"><span data-stu-id="214fe-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="214fe-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="214fe-107">Return Value</span></span>  
 <span data-ttu-id="214fe-108">Wartość S_OK, jeśli metoda zakończy się pomyślnie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="214fe-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="214fe-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="214fe-109">Requirements</span></span>  
 <span data-ttu-id="214fe-110">**Nagłówek:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="214fe-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="214fe-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="214fe-111">See Also</span></span>  
 [<span data-ttu-id="214fe-112">ISymENCUnmanagedMethod — interfejs</span><span class="sxs-lookup"><span data-stu-id="214fe-112">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)