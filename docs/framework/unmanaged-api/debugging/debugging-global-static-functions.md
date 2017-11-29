---
title: Debugowanie statycznych funkcji globalnych
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- global static functions [.NET Framework debugging]
- debugging global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], debugging
ms.assetid: efc64414-77c3-48d0-881a-8594ed416aad
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ad5d3ef689a251ea4b154afc5d1bfb387388ddb3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-global-static-functions"></a><span data-ttu-id="16bb2-102">Debugowanie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="16bb2-102">Debugging Global Static Functions</span></span>
<span data-ttu-id="16bb2-103">W tej sekcji opisano niezarządzane statyczne funkcje globalne, które używa interfejsu API debugowania.</span><span class="sxs-lookup"><span data-stu-id="16bb2-103">This section describes the unmanaged global static functions that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16bb2-104">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="16bb2-104">In This Section</span></span>  
 [<span data-ttu-id="16bb2-105">_Efn_getmanagedexcepstack — funkcja</span><span class="sxs-lookup"><span data-stu-id="16bb2-105">_EFN_GetManagedExcepStack Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedexcepstack-function.md)  
 <span data-ttu-id="16bb2-106">Podany adres obiektu zarządzanym wyjątku zwraca ciąg wersji śladu stosu znajdująca się wewnątrz.</span><span class="sxs-lookup"><span data-stu-id="16bb2-106">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
 [<span data-ttu-id="16bb2-107">_Efn_getmanagedobjectfieldinfo — funkcja</span><span class="sxs-lookup"><span data-stu-id="16bb2-107">_EFN_GetManagedObjectFieldInfo Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedobjectfieldinfo-function.md)  
 <span data-ttu-id="16bb2-108">Pobiera przesunięcie od początku obiektu, do pola i wartość do pola, używając udostępnionego obiektu wskaźnik i nazwy pola.</span><span class="sxs-lookup"><span data-stu-id="16bb2-108">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
 [<span data-ttu-id="16bb2-109">_Efn_getmanagedobjectname — funkcja</span><span class="sxs-lookup"><span data-stu-id="16bb2-109">_EFN_GetManagedObjectName Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedobjectname-function.md)  
 <span data-ttu-id="16bb2-110">Pobiera nazwę typu przy użyciu wskaźnika podanego obiektu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="16bb2-110">Gets the name of a type by using the provided managed object pointer.</span></span>  
  
 [<span data-ttu-id="16bb2-111">_Efn_stacktrace — funkcja</span><span class="sxs-lookup"><span data-stu-id="16bb2-111">_EFN_StackTrace Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/efn-stacktrace-function.md)  
 <span data-ttu-id="16bb2-112">Udostępnia reprezentację tekst ślad stosu zarządzanych i tablicę `CONTEXT` rejestruje, jeden dla każdego przejścia między niezarządzanych i kod zarządzany.</span><span class="sxs-lookup"><span data-stu-id="16bb2-112">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
 [<span data-ttu-id="16bb2-113">Clrdatacreateinstance — funkcja</span><span class="sxs-lookup"><span data-stu-id="16bb2-113">CLRDataCreateInstance Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatacreateinstance-function.md)  
 <span data-ttu-id="16bb2-114">Metoda wywoływana przez wspólne języka wspólnego (CLR) danych dostęp do usługi można utworzyć obiektu określonego interfejsu dla procesu określonego obiektu docelowego.</span><span class="sxs-lookup"><span data-stu-id="16bb2-114">Called by the common language runtime (CLR) data access services to create the specified interface object for the specified target process.</span></span>  
  
 [<span data-ttu-id="16bb2-115">Pfn_clrdatacreateinstance — wskaźnik funkcji</span><span class="sxs-lookup"><span data-stu-id="16bb2-115">PFN_CLRDataCreateInstance Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/debugging/pfn-clrdatacreateinstance-function-pointer.md)  
 <span data-ttu-id="16bb2-116">Punkty do funkcji, która jest wywoływana przez danych CLR dostęp do usług można utworzyć obiektu określonego interfejsu dla procesu określonego obiektu docelowego.</span><span class="sxs-lookup"><span data-stu-id="16bb2-116">Points to a function that is called by the CLR data access services to create the specified interface object for the specified target process.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="16bb2-117">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="16bb2-117">Related Sections</span></span>  
 [<span data-ttu-id="16bb2-118">Klasy coclass debugowania</span><span class="sxs-lookup"><span data-stu-id="16bb2-118">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="16bb2-119">Interfejsy debugowania</span><span class="sxs-lookup"><span data-stu-id="16bb2-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="16bb2-120">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="16bb2-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="16bb2-121">Struktury debugowania</span><span class="sxs-lookup"><span data-stu-id="16bb2-121">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)