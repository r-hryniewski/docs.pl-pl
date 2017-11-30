---
title: "ICLRAppDomainResourceMonitor::GetCurrentSurvived — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9fe624c83be5dcf762f1c6036f8e4264f0e45c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="b0856-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived — Metoda</span><span class="sxs-lookup"><span data-stu-id="b0856-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="b0856-103">Pobiera liczbę bajtów, który udało się przetrwać ostatniego pełnego, blokowanie odzyskiwania pamięci i który odwołuje się bieżącej domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b0856-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0856-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b0856-104">Syntax</span></span>  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0856-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b0856-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="b0856-106">[in] Identyfikator domeny żądanej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b0856-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="b0856-107">[out] Wskaźnik do liczba bajtów, które udało przetrwać po ostatnim wyrzucanie elementów bezużytecznych, które są przechowywane w tej domenie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b0856-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="b0856-108">Po pełnej kolekcji ta liczba jest dokładne i kompletne.</span><span class="sxs-lookup"><span data-stu-id="b0856-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="b0856-109">Po pobraniu tymczasowych ta liczba jest potencjalnie niekompletna.</span><span class="sxs-lookup"><span data-stu-id="b0856-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="b0856-110">Ten parametr może być `null`.</span><span class="sxs-lookup"><span data-stu-id="b0856-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="b0856-111">[out] Wskaźnik do całkowita liczba bajtów, które udało przetrwać z ostatnich wyrzucanie elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="b0856-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="b0856-112">Po pełnej kolekcji liczba ta reprezentuje liczbę bajtów, które są przechowywane w stertach zarządzanych.</span><span class="sxs-lookup"><span data-stu-id="b0856-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="b0856-113">Po pobraniu tymczasowych liczba ta reprezentuje liczbę bajtów, które są przechowywane na żywo w generacje tymczasowych.</span><span class="sxs-lookup"><span data-stu-id="b0856-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="b0856-114">Ten parametr może być `null`.</span><span class="sxs-lookup"><span data-stu-id="b0856-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0856-115">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="b0856-115">Return Value</span></span>  
 <span data-ttu-id="b0856-116">Ta metoda zwraca następujące określonych wyników HRESULT, a także HRESULT błędów wskazujących Niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="b0856-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b0856-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b0856-117">HRESULT</span></span>|<span data-ttu-id="b0856-118">Opis</span><span class="sxs-lookup"><span data-stu-id="b0856-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b0856-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0856-119">S_OK</span></span>|<span data-ttu-id="b0856-120">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="b0856-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="b0856-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="b0856-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="b0856-122">Domeny aplikacji został zwolniony lub nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="b0856-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0856-123">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b0856-123">Remarks</span></span>  
 <span data-ttu-id="b0856-124">Statystyki są aktualizowane tylko po pełnej, blokowanie odzyskiwania pamięci; występuje, oznacza to, kolekcję zawierającą wszystkie generacje i zatrzymuje się podczas pobierania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b0856-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="b0856-125">Na przykład <xref:System.GC.Collect?displayProperty=nameWithType> przeciążenie metody wykonuje pełne, blokowanie kolekcji.</span><span class="sxs-lookup"><span data-stu-id="b0856-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="b0856-126">Współbieżne odzyskiwanie pamięci przebiega w tle i nie są blokowane w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b0856-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="b0856-127">`GetCurrentSurvived` Metody jest odpowiednikiem niezarządzane zarządzanej <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> właściwości.</span><span class="sxs-lookup"><span data-stu-id="b0856-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0856-128">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b0856-128">Requirements</span></span>  
 <span data-ttu-id="b0856-129">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0856-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0856-130">**Nagłówek:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="b0856-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b0856-131">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b0856-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0856-132">**Wersje programu .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0856-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0856-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b0856-133">See Also</span></span>  
 [<span data-ttu-id="b0856-134">ICLRAppDomainResourceMonitor — interfejs</span><span class="sxs-lookup"><span data-stu-id="b0856-134">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [<span data-ttu-id="b0856-135">Zasobów domen aplikacji monitorowania</span><span class="sxs-lookup"><span data-stu-id="b0856-135">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="b0856-136">Hosting — interfejsy</span><span class="sxs-lookup"><span data-stu-id="b0856-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="b0856-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="b0856-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)