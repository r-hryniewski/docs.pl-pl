---
title: "Funkcja GetPropertyQualifierSet (niezarządzany wykaz interfejsów API)"
description: "Funkcja GetPropertyQualifierSet pobiera kwalifikator, ustaw dla właściwości."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyQualifierSet
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyQualifierSet
helpviewer_keywords: GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bd8abdb34f37273e469bdf5fc659b261bb2b9304
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="0d183-103">Funkcja GetPropertyQualifierSet</span><span class="sxs-lookup"><span data-stu-id="0d183-103">GetPropertyQualifierSet function</span></span>
<span data-ttu-id="0d183-104">Pobiera kwalifikator ustawić dla określonej właściwości.</span><span class="sxs-lookup"><span data-stu-id="0d183-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="0d183-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="0d183-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="0d183-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="0d183-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0d183-107">[in] Ten parametr nie jest używana.</span><span class="sxs-lookup"><span data-stu-id="0d183-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0d183-108">[in] Wskaźnik do [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="0d183-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethod`  
<span data-ttu-id="0d183-109">[in] Nazwa właściwości.</span><span class="sxs-lookup"><span data-stu-id="0d183-109">[in] The property  name.</span></span> <span data-ttu-id="0d183-110">`wszProperty`musi wskazywać prawidłowe `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="0d183-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="0d183-111">[out] Odbiera wskaźnika interfejsu, który zezwala na dostęp do kwalifikatory właściwości.</span><span class="sxs-lookup"><span data-stu-id="0d183-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="0d183-112">`ppQualSet`nie może być `null`.</span><span class="sxs-lookup"><span data-stu-id="0d183-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="0d183-113">Jeśli wystąpi błąd, nowego obiektu nie są zwracane, a wskaźnik ma ustawioną wartość wskaż `null`.</span><span class="sxs-lookup"><span data-stu-id="0d183-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="0d183-114">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="0d183-114">Return value</span></span>

<span data-ttu-id="0d183-115">Następujące wartości zwracane przez tę funkcję są zdefiniowane w *WbemCli.h* pliku nagłówka, lub należy je zdefiniować jako stałe w kodzie:</span><span class="sxs-lookup"><span data-stu-id="0d183-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0d183-116">Stała</span><span class="sxs-lookup"><span data-stu-id="0d183-116">Constant</span></span>  |<span data-ttu-id="0d183-117">Wartość</span><span class="sxs-lookup"><span data-stu-id="0d183-117">Value</span></span>  |<span data-ttu-id="0d183-118">Opis</span><span class="sxs-lookup"><span data-stu-id="0d183-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="0d183-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0d183-119">0x80041001</span></span> | <span data-ttu-id="0d183-120">Wystąpił błąd ogólny.</span><span class="sxs-lookup"><span data-stu-id="0d183-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="0d183-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="0d183-121">0x80041002</span></span> | <span data-ttu-id="0d183-122">Określona metoda nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="0d183-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0d183-123">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0d183-123">0x80041006</span></span> | <span data-ttu-id="0d183-124">Za mało pamięci jest dostępna do wykonania operacji.</span><span class="sxs-lookup"><span data-stu-id="0d183-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0d183-125">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0d183-125">0x80041008</span></span> | <span data-ttu-id="0d183-126">Parametr jest `null`.</span><span class="sxs-lookup"><span data-stu-id="0d183-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="0d183-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="0d183-127">0x80041030</span></span> | <span data-ttu-id="0d183-128">Funkcja podejmie próbę uzyskania kwalifikatorów właściwości systemu.</span><span class="sxs-lookup"><span data-stu-id="0d183-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="0d183-129">0</span><span class="sxs-lookup"><span data-stu-id="0d183-129">0</span></span> | <span data-ttu-id="0d183-130">Wywołanie funkcji zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="0d183-130">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0d183-131">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0d183-131">Remarks</span></span>

<span data-ttu-id="0d183-132">Ta funkcja jest zawijana wywołanie [IWbemClassObject::GetPropertyQualifierSet](https://msdn.microsoft.com/library/aa391450(v=vs.85).aspx) metody.</span><span class="sxs-lookup"><span data-stu-id="0d183-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](https://msdn.microsoft.com/library/aa391450(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="0d183-133">Wywołanie tej funkcji jest obsługiwana tylko wtedy, gdy bieżący obiekt jest definicję klasy modelu wspólnych informacji.</span><span class="sxs-lookup"><span data-stu-id="0d183-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="0d183-134">Metoda manipulowania nie jest dostępna dla [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters wskazujące wystąpienia modelu CIM.</span><span class="sxs-lookup"><span data-stu-id="0d183-134">Method manipulation is not available for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters that point to CIM instances.</span></span>

<span data-ttu-id="0d183-135">Ponieważ każda metoda może mieć własną kwalifikatory [wskaźnika IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) umożliwia wywołującego dodać, edytować lub usunąć kwalifikatory.</span><span class="sxs-lookup"><span data-stu-id="0d183-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="0d183-136">Ponieważ właściwości systemu nie ma żadnych kwalifikatorów, funkcja zwraca `WBEM_E_SYSTEM_PROPERTY` przy próbie uzyskania [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) wskaźnika dla właściwości systemu.</span><span class="sxs-lookup"><span data-stu-id="0d183-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="0d183-137">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0d183-137">Requirements</span></span>  
<span data-ttu-id="0d183-138">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d183-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d183-139">**Nagłówek:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0d183-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0d183-140">**Wersje programu .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0d183-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d183-141">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0d183-141">See also</span></span>  
[<span data-ttu-id="0d183-142">Liczniki wydajności (niezarządzany wykaz interfejsów API) i usługi WMI</span><span class="sxs-lookup"><span data-stu-id="0d183-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)