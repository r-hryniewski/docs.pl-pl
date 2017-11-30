---
title: "Wykorzystywanie niezarządzanych funkcji DLL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unmanaged functions, calling
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- platform invoke, about platform invoke
- DLL functions, consuming unmanaged
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke
- DLL functions
ms.assetid: eca7606e-ebfb-4f47-b8d9-289903fdc045
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ec93728566d6aa16d4b9b15b171d79831cc0dbeb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="consuming-unmanaged-dll-functions"></a><span data-ttu-id="48252-102">Wykorzystywanie niezarządzanych funkcji DLL</span><span class="sxs-lookup"><span data-stu-id="48252-102">Consuming Unmanaged DLL Functions</span></span>
<span data-ttu-id="48252-103">Wywołanie platformy to usługa, że umożliwia zarządzanego kodu wywoływanie niezarządzanych funkcji zaimplementowana w biblioteki dołączanej dynamicznie (dll), takich jak w interfejsie API Win32.</span><span class="sxs-lookup"><span data-stu-id="48252-103">Platform invoke is a service that enables managed code to call unmanaged functions implemented in dynamic link libraries (DLLs), such as those in the Win32 API.</span></span> <span data-ttu-id="48252-104">Lokalizuje i wywołuje wyeksportowanej funkcji i marshals granicy współdziałanie argumenty (liczby całkowite, ciągi, tablic, struktur i tak dalej), zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="48252-104">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span> <span data-ttu-id="48252-105">Aby uzyskać więcej informacji na temat tej usługi, zobacz [A bliżej przyjrzeć się wywołanie platformy](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243).</span><span class="sxs-lookup"><span data-stu-id="48252-105">For more information about this service, see [A Closer Look at Platform Invoke](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243).</span></span>  
  
 <span data-ttu-id="48252-106">W tej sekcji przedstawiono kilka zadań związanych z wykorzystywanie niezarządzanych funkcji DLL.</span><span class="sxs-lookup"><span data-stu-id="48252-106">This section introduces several tasks associated with consuming unmanaged DLL functions.</span></span> <span data-ttu-id="48252-107">Oprócz następujące zadania są ogólne zagadnienia i łącza, co zapewnia dodatkowe informacje i przykłady.</span><span class="sxs-lookup"><span data-stu-id="48252-107">In addition to the following tasks, there are general considerations and a link providing additional information and examples.</span></span>  
  
#### <a name="to-consume-exported-dll-functions"></a><span data-ttu-id="48252-108">Aby korzystać z wyeksportowanych funkcji DLL</span><span class="sxs-lookup"><span data-stu-id="48252-108">To consume exported DLL functions</span></span>  
  
1.  <span data-ttu-id="48252-109">[Identyfikowanie funkcji w bibliotekach DLL](../../../docs/framework/interop/identifying-functions-in-dlls.md).</span><span class="sxs-lookup"><span data-stu-id="48252-109">[Identify functions in DLLs](../../../docs/framework/interop/identifying-functions-in-dlls.md).</span></span>  
  
     <span data-ttu-id="48252-110">Minimalny należy określić nazwę funkcji i nazwy biblioteki dll, która go zawiera.</span><span class="sxs-lookup"><span data-stu-id="48252-110">Minimally, you must specify the name of the function and name of the DLL that contains it.</span></span>  
  
2.  <span data-ttu-id="48252-111">[Tworzenie klasy utrzymującej funkcje DLL](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md).</span><span class="sxs-lookup"><span data-stu-id="48252-111">[Create a class to hold DLL functions](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md).</span></span>  
  
     <span data-ttu-id="48252-112">Można użyć istniejącej klasy, Utwórz poszczególnych klas dla każdej funkcji niezarządzanej lub utworzyć jedną klasę, która zawiera zestaw powiązanych funkcji niezarządzanej.</span><span class="sxs-lookup"><span data-stu-id="48252-112">You can use an existing class, create an individual class for each unmanaged function, or create one class that contains a set of related unmanaged functions.</span></span>  
  
3.  <span data-ttu-id="48252-113">[Tworzenie prototypów w kodzie zarządzanym](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span><span class="sxs-lookup"><span data-stu-id="48252-113">[Create prototypes in managed code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span></span>  
  
     <span data-ttu-id="48252-114">[Visual Basic] Użyj **Declare** instrukcji z **funkcja** i **Lib** słów kluczowych.</span><span class="sxs-lookup"><span data-stu-id="48252-114">[Visual Basic] Use the **Declare** statement with the **Function** and **Lib** keywords.</span></span> <span data-ttu-id="48252-115">W rzadkich przypadkach można użyć **elementu DllImportAttribute** z **funkcji udostępnionych** słów kluczowych.</span><span class="sxs-lookup"><span data-stu-id="48252-115">In some rare cases, you can use the **DllImportAttribute** with the **Shared Function** keywords.</span></span> <span data-ttu-id="48252-116">Te przypadki są objaśnione później w tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="48252-116">These cases are explained later in this section.</span></span>  
  
     <span data-ttu-id="48252-117">[C#] Użyj **elementu DllImportAttribute** do identyfikowania biblioteki DLL i funkcji.</span><span class="sxs-lookup"><span data-stu-id="48252-117">[C#] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="48252-118">Oznacz metodę z **statycznych** i **extern** modyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="48252-118">Mark the method with the **static** and **extern** modifiers.</span></span>  
  
     <span data-ttu-id="48252-119">[C++] Użyj **elementu DllImportAttribute** do identyfikowania biblioteki DLL i funkcji.</span><span class="sxs-lookup"><span data-stu-id="48252-119">[C++] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="48252-120">Oznacz metodę otoki lub funkcji z **zewnętrzne "C"**.</span><span class="sxs-lookup"><span data-stu-id="48252-120">Mark the wrapper method or function with **extern "C"**.</span></span>  
  
4.  <span data-ttu-id="48252-121">[Wywoływanie funkcji DLL](../../../docs/framework/interop/calling-a-dll-function.md).</span><span class="sxs-lookup"><span data-stu-id="48252-121">[Call a DLL function](../../../docs/framework/interop/calling-a-dll-function.md).</span></span>  
  
     <span data-ttu-id="48252-122">Wywołaj metodę w klasie zarządzanej, jak w przypadku innych metod zarządzanych.</span><span class="sxs-lookup"><span data-stu-id="48252-122">Call the method on your managed class as you would any other managed method.</span></span> <span data-ttu-id="48252-123">[Przekazywanie struktur](../../../docs/framework/interop/passing-structures.md) i [Implementowanie funkcji wywołania zwrotnego](../../../docs/framework/interop/callback-functions.md) przypadków specjalnych.</span><span class="sxs-lookup"><span data-stu-id="48252-123">[Passing structures](../../../docs/framework/interop/passing-structures.md) and [implementing callback functions](../../../docs/framework/interop/callback-functions.md) are special cases.</span></span>  
  
 <span data-ttu-id="48252-124">Aby uzyskać przykłady pokazujące, które pokazują, jak utworzyć. Deklaracje opartych na potrzeby używania z platformy invoke, zobacz [organizowanie danych za pomocą wywołania platformy](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="48252-124">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="a-closer-look-at-platform-invoke"></a><span data-ttu-id="48252-125">Bliższe spojrzenie na platformie wywołania</span><span class="sxs-lookup"><span data-stu-id="48252-125">A closer look at platform invoke</span></span>  
 <span data-ttu-id="48252-126">Wywołanie platformy opiera się na metadanych, aby zlokalizować eksportowane funkcje i kierować ich argumentów w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="48252-126">Platform invoke relies on metadata to locate exported functions and marshal their arguments at run time.</span></span> <span data-ttu-id="48252-127">Na poniższej ilustracji przedstawiono ten proces.</span><span class="sxs-lookup"><span data-stu-id="48252-127">The following illustration shows this process.</span></span>  
  
 <span data-ttu-id="48252-128">![Wywołanie platformy](../../../docs/framework/interop/media/pinvoke.gif "funkcji pinvoke")</span><span class="sxs-lookup"><span data-stu-id="48252-128">![Platform invoke](../../../docs/framework/interop/media/pinvoke.gif "pinvoke")</span></span>  
<span data-ttu-id="48252-129">Wywołanie funkcji niezarządzanej DLL wywołanie platformy</span><span class="sxs-lookup"><span data-stu-id="48252-129">A platform invoke call to an unmanaged DLL function</span></span>  
  
 <span data-ttu-id="48252-130">Gdy wywołanie platformy wywołania funkcji niezarządzanej wykonywania następującej akcji:</span><span class="sxs-lookup"><span data-stu-id="48252-130">When platform invoke calls an unmanaged function, it performs the following sequence of actions:</span></span>  
  
1.  <span data-ttu-id="48252-131">Lokalizuje pliku DLL zawierającego funkcję.</span><span class="sxs-lookup"><span data-stu-id="48252-131">Locates the DLL containing the function.</span></span>  
  
2.  <span data-ttu-id="48252-132">Ładuje bibliotekę DLL do pamięci.</span><span class="sxs-lookup"><span data-stu-id="48252-132">Loads the DLL into memory.</span></span>  
  
3.  <span data-ttu-id="48252-133">Lokalizuje adres funkcji w pamięci i wypchnięcia jej argumentów na stosie, organizowanie danych zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="48252-133">Locates the address of the function in memory and pushes its arguments onto the stack, marshaling data as required.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="48252-134">Lokalizowania i ładowania biblioteki DLL i znajdowanie adresu funkcji w pamięci występuje tylko w pierwszym wywołaniu funkcji.</span><span class="sxs-lookup"><span data-stu-id="48252-134">Locating and loading the DLL, and locating the address of the function in memory occur only on the first call to the function.</span></span>  
  
4.  <span data-ttu-id="48252-135">Formant transferu do funkcji niezarządzanej.</span><span class="sxs-lookup"><span data-stu-id="48252-135">Transfers control to the unmanaged function.</span></span>  
  
 <span data-ttu-id="48252-136">Wywołanie platformy zgłasza wyjątki generowane przez funkcję niezarządzane do zarządzanego obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="48252-136">Platform invoke throws exceptions generated by the unmanaged function to the managed caller.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48252-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="48252-137">See Also</span></span>  
 [<span data-ttu-id="48252-138">Współdziałanie z kodem niezarządzanym</span><span class="sxs-lookup"><span data-stu-id="48252-138">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)  
 [<span data-ttu-id="48252-139">Przykłady wywołań platformy</span><span class="sxs-lookup"><span data-stu-id="48252-139">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="48252-140">Przekazywanie międzyoperacyjne</span><span class="sxs-lookup"><span data-stu-id="48252-140">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 [<span data-ttu-id="48252-141">Wykorzystywanie niezarządzanych funkcji DLL</span><span class="sxs-lookup"><span data-stu-id="48252-141">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)