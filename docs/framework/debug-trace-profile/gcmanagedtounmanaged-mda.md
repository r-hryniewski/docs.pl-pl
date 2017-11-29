---
title: gcManagedToUnmanaged MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GcManagedToUnmanaged MDA
- GC managed to unmanaged
- transitioning threads managed to unmanaged code
- threading [.NET Framework], garbage collection
- managed to unmanaged garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
ms.assetid: 7417f837-805e-4fed-a430-ca919c8421dc
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1aa528eb2acc872b1956edef3af3724bb3b54d67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="gcmanagedtounmanaged-mda"></a><span data-ttu-id="76913-102">gcManagedToUnmanaged MDA</span><span class="sxs-lookup"><span data-stu-id="76913-102">gcManagedToUnmanaged MDA</span></span>
<span data-ttu-id="76913-103">`gcManagedToUnmanaged` Zarządzany Asystent debugowania (MDA) powoduje wyrzucania elementów bezużytecznych zawsze, gdy wątek przejścia z kodu zarządzanego do kodu niezarządzanego.</span><span class="sxs-lookup"><span data-stu-id="76913-103">The `gcManagedToUnmanaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="76913-104">Symptomy</span><span class="sxs-lookup"><span data-stu-id="76913-104">Symptoms</span></span>  
 <span data-ttu-id="76913-105">Składnik niezarządzane użytkownika zgłasza naruszenia zasad dostępu podczas próby użycia zarządzanego obiektu, który ma zostać udostępnione modelowi COM.</span><span class="sxs-lookup"><span data-stu-id="76913-105">An unmanaged user component throws an access violation when trying to use a managed object that had been exposed to COM.</span></span> <span data-ttu-id="76913-106">Obiekt COM może zostały zwolnione.</span><span class="sxs-lookup"><span data-stu-id="76913-106">The COM object appears to have been released.</span></span> <span data-ttu-id="76913-107">Naruszenia zasad dostępu jest niejednoznaczny.</span><span class="sxs-lookup"><span data-stu-id="76913-107">The access violation is nondeterministic.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="76913-108">Przyczyna</span><span class="sxs-lookup"><span data-stu-id="76913-108">Cause</span></span>  
 <span data-ttu-id="76913-109">Jeśli niezarządzane składnik nie jest zliczanie zarządzanego obiektu COM poprawnie, środowisko uruchomieniowe można zebrać ujawniony dla modelu COM, gdy składnik niezarządzane nadal będzie zawierać odwołania do obiektu zarządzanego obiektu.</span><span class="sxs-lookup"><span data-stu-id="76913-109">If an unmanaged component is not reference counting a managed COM object correctly, then the runtime could collect a managed object exposed to COM when the unmanaged component still holds a reference to the object.</span></span> <span data-ttu-id="76913-110">Wywołania środowiska uruchomieniowego <xref:System.Runtime.InteropServices.Marshal.Release%2A> podczas wyrzucania, więc jeśli składnik użytkownika używa obiektu przed wyrzucania, następnie go zostanie nie jeszcze zostać zebrane.</span><span class="sxs-lookup"><span data-stu-id="76913-110">The runtime calls <xref:System.Runtime.InteropServices.Marshal.Release%2A> during garbage collections, so if the user component uses the object before the garbage collection occurs, then it will not yet have been collected.</span></span> <span data-ttu-id="76913-111">Jest to źródłem nondeterminism.</span><span class="sxs-lookup"><span data-stu-id="76913-111">This is the source of the nondeterminism.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="76913-112">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="76913-112">Resolution</span></span>  
 <span data-ttu-id="76913-113">Włączenie tego Asystenta skraca czas między gdy obiekt jest uprawniona do kolekcji i <xref:System.Runtime.InteropServices.Marshal.Release%2A> jest wywoływana, co pomaga śledzić, który składnik niezarządzane najpierw próbuje uzyskać dostęp do połączonego obiektu.</span><span class="sxs-lookup"><span data-stu-id="76913-113">Enabling this assistant reduces the time between when the object is eligible for collection and <xref:System.Runtime.InteropServices.Marshal.Release%2A> is called, helping to track down which unmanaged component first tries to access the collected object.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="76913-114">Wpływ na środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="76913-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="76913-115">Wyrzucanie elementów bezużytecznych zawsze, gdy wątek przejść z kodu zarządzanego do kodu niezarządzanego przyczyny.</span><span class="sxs-lookup"><span data-stu-id="76913-115">Causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="76913-116">Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="76913-116">Output</span></span>  
 <span data-ttu-id="76913-117">To zdarzenie MDA tworzy żadnych danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="76913-117">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="76913-118">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="76913-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="76913-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="76913-119">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="76913-120">Diagnozowanie błędów przy użyciu Asystenci zarządzanego debugowania</span><span class="sxs-lookup"><span data-stu-id="76913-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="76913-121">Przekazywanie międzyoperacyjne</span><span class="sxs-lookup"><span data-stu-id="76913-121">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 [<span data-ttu-id="76913-122">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="76913-122">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)