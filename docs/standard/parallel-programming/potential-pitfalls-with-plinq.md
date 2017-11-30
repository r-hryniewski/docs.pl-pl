---
title: "Potencjalne pułapki związane z PLINQ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PLINQ queries, pitfalls
ms.assetid: 75a38b55-4bc4-488a-87d5-89dbdbdc76a2
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f7c971d2c039e6441669108e966eba472819fde5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="potential-pitfalls-with-plinq"></a><span data-ttu-id="1ecff-102">Potencjalne pułapki związane z PLINQ</span><span class="sxs-lookup"><span data-stu-id="1ecff-102">Potential Pitfalls with PLINQ</span></span>
<span data-ttu-id="1ecff-103">W wielu przypadkach PLINQ można zapewnia znaczną poprawę wydajności za pośrednictwem sekwencyjnych LINQ do obiektów zapytań.</span><span class="sxs-lookup"><span data-stu-id="1ecff-103">In many cases, PLINQ can provide significant performance improvements over sequential LINQ to Objects queries.</span></span> <span data-ttu-id="1ecff-104">Jednak pracy parallelizing wykonywania zapytania wprowadza złożoności, który może prowadzić do problemów, które w kolejnych kodu nie są jako wspólne lub w ogóle nie wystąpi.</span><span class="sxs-lookup"><span data-stu-id="1ecff-104">However, the work of parallelizing the query execution introduces complexity that can lead to problems that, in sequential code, are not as common or are not encountered at all.</span></span> <span data-ttu-id="1ecff-105">W tym temacie wymieniono niektóre praktyki, których należy unikać podczas pisania zapytania dotyczące technologii PLINQ.</span><span class="sxs-lookup"><span data-stu-id="1ecff-105">This topic lists some practices to avoid when you write PLINQ queries.</span></span>  
  
## <a name="do-not-assume-that-parallel-is-always-faster"></a><span data-ttu-id="1ecff-106">Nie przyjęto założenie, że równolegle jest zawsze szybsze</span><span class="sxs-lookup"><span data-stu-id="1ecff-106">Do Not Assume That Parallel Is Always Faster</span></span>  
 <span data-ttu-id="1ecff-107">Czasami paralelizacja powoduje, że zapytania PLINQ działać wolniej niż jego LINQ do obiektów równoważne.</span><span class="sxs-lookup"><span data-stu-id="1ecff-107">Parallelization sometimes causes a PLINQ query to run slower than its LINQ to Objects equivalent.</span></span> <span data-ttu-id="1ecff-108">Podstawowe zasadą to zapytań, które ma kilka elementy źródłowe i delegatów szybkiego użytkownika prawdopodobnie nie będzie przyspieszenie znacznie.</span><span class="sxs-lookup"><span data-stu-id="1ecff-108">The basic rule of thumb is that queries that have few source elements and fast user delegates are unlikely to speedup much.</span></span> <span data-ttu-id="1ecff-109">Jednak ponieważ wydajności są związane z wielu czynników, zaleca się zmierzyć rzeczywiste wyniki, przed podjęciem decyzji o tym, czy używać PLINQ.</span><span class="sxs-lookup"><span data-stu-id="1ecff-109">However, because many factors are involved in performance, we recommend that you measure actual results before you decide whether to use PLINQ.</span></span> <span data-ttu-id="1ecff-110">Aby uzyskać więcej informacji, zobacz [przyspieszeniach w PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="1ecff-110">For more information, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="avoid-writing-to-shared-memory-locations"></a><span data-ttu-id="1ecff-111">Unikaj zapisywanie w lokalizacji pamięci współużytkowanej</span><span class="sxs-lookup"><span data-stu-id="1ecff-111">Avoid Writing to Shared Memory Locations</span></span>  
 <span data-ttu-id="1ecff-112">W kolejnych kodu nie jest rzadko do odczytu lub zapisu zmienne statyczne lub pola klasy.</span><span class="sxs-lookup"><span data-stu-id="1ecff-112">In sequential code, it is not uncommon to read from or write to static variables or class fields.</span></span> <span data-ttu-id="1ecff-113">Zawsze, gdy wiele wątków uzyskują dostęp do tych zmiennych współbieżnie, istnieje jednak możliwość big wyścigu.</span><span class="sxs-lookup"><span data-stu-id="1ecff-113">However, whenever multiple threads are accessing such variables concurrently, there is a big potential for race conditions.</span></span> <span data-ttu-id="1ecff-114">Mimo że używasz blokad synchronizujący dostęp do zmiennej, kosztów synchronizacji może pogarszać wydajność.</span><span class="sxs-lookup"><span data-stu-id="1ecff-114">Even though you can use locks to synchronize access to the variable, the cost of synchronization can hurt performance.</span></span> <span data-ttu-id="1ecff-115">Dlatego zalecamy można uniknąć, lub co najmniej ograniczyć dostęp do udostępniania stanu w zapytaniu PLINQ możliwie.</span><span class="sxs-lookup"><span data-stu-id="1ecff-115">Therefore, we recommend that you avoid, or at least limit, access to shared state in a PLINQ query as much as possible.</span></span>  
  
## <a name="avoid-over-parallelization"></a><span data-ttu-id="1ecff-116">Unikaj nadmiernego Paralelizacja</span><span class="sxs-lookup"><span data-stu-id="1ecff-116">Avoid Over-Parallelization</span></span>  
 <span data-ttu-id="1ecff-117">Za pomocą `AsParallel` operatora ponoszenia kosztów partycjonowania kolekcji źródłowej i synchronizowanie wątków roboczych.</span><span class="sxs-lookup"><span data-stu-id="1ecff-117">By using the `AsParallel` operator, you incur the overhead costs of partitioning the source collection and synchronizing the worker threads.</span></span> <span data-ttu-id="1ecff-118">Korzyści równoległości dalsze są ograniczone przez liczbę procesorów w komputerze.</span><span class="sxs-lookup"><span data-stu-id="1ecff-118">The benefits of parallelization are further limited by the number of processors on the computer.</span></span> <span data-ttu-id="1ecff-119">Nie ma żadnych przyspieszenie, które można uzyskać, uruchamiając wiele wątków wiązaniem obliczeń w tylko jednym procesorze.</span><span class="sxs-lookup"><span data-stu-id="1ecff-119">There is no speedup to be gained by running multiple compute-bound threads on just one processor.</span></span> <span data-ttu-id="1ecff-120">W związku z tym należy uważać, aby nie nadmiernie parallelize zapytania.</span><span class="sxs-lookup"><span data-stu-id="1ecff-120">Therefore, you must be careful not to over-parallelize a query.</span></span>  
  
 <span data-ttu-id="1ecff-121">Najbardziej typowy scenariusz, w które nadmierne paralelizacja może wystąpić jest zapytania zagnieżdżone, jak pokazano w poniższy fragment kodu.</span><span class="sxs-lookup"><span data-stu-id="1ecff-121">The most common scenario in which over-parallelization can occur is in nested queries, as shown in the following snippet.</span></span>  
  
 [!code-csharp[PLINQ#20](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
 [!code-vb[PLINQ#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]  
  
 <span data-ttu-id="1ecff-122">W takim przypadku warto parallelize tylko zewnętrzne źródło danych (klienci), chyba że zastosowanie co najmniej jeden z następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="1ecff-122">In this case, it is best to parallelize only the outer data source (customers) unless one or more of the following conditions apply:</span></span>  
  
-   <span data-ttu-id="1ecff-123">Źródło danych wewnętrzny (odbiorcy. Zamówienia) jest uznany za długa.</span><span class="sxs-lookup"><span data-stu-id="1ecff-123">The inner data source (cust.Orders) is known to be very long.</span></span>  
  
-   <span data-ttu-id="1ecff-124">Kosztowna obliczenia są wykonywane na każdej kolejności.</span><span class="sxs-lookup"><span data-stu-id="1ecff-124">You are performing an expensive computation on each order.</span></span> <span data-ttu-id="1ecff-125">(Operacja pokazano w przykładzie nie jest kosztowna).</span><span class="sxs-lookup"><span data-stu-id="1ecff-125">(The operation shown in the example is not expensive.)</span></span>  
  
-   <span data-ttu-id="1ecff-126">System docelowy jest znana wystarczającą do obsługi liczby wątków, które zostaną utworzone przez parallelizing zapytanie na procesorów `cust.Orders`.</span><span class="sxs-lookup"><span data-stu-id="1ecff-126">The target system is known to have enough processors to handle the number of threads that will be produced by parallelizing the query on `cust.Orders`.</span></span>  
  
 <span data-ttu-id="1ecff-127">We wszystkich przypadkach najlepszy sposób, aby ustalić optymalne zapytania kształtu jest do testowania i miar.</span><span class="sxs-lookup"><span data-stu-id="1ecff-127">In all cases, the best way to determine the optimum query shape is to test and measure.</span></span> <span data-ttu-id="1ecff-128">Aby uzyskać więcej informacji, zobacz [porady: wydajności zapytań PLINQ miary](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).</span><span class="sxs-lookup"><span data-stu-id="1ecff-128">For more information, see [How to: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).</span></span>  
  
## <a name="avoid-calls-to-non-thread-safe-methods"></a><span data-ttu-id="1ecff-129">Unikaj wywołania metod innych niż wątkowo</span><span class="sxs-lookup"><span data-stu-id="1ecff-129">Avoid Calls to Non-Thread-Safe Methods</span></span>  
 <span data-ttu-id="1ecff-130">Zapisywanie do metod innych niż wątkowo wystąpienia z PLINQ zapytanie może doprowadzić do uszkodzenia danych, które mogą lub nie mogą zostać wykryte w programie.</span><span class="sxs-lookup"><span data-stu-id="1ecff-130">Writing to non-thread-safe instance methods from a PLINQ query can lead to data corruption which may or may not go undetected in your program.</span></span> <span data-ttu-id="1ecff-131">Również może prowadzić do wyjątków.</span><span class="sxs-lookup"><span data-stu-id="1ecff-131">It can also lead to exceptions.</span></span> <span data-ttu-id="1ecff-132">W poniższym przykładzie, wiele wątków czy próba wywołania `Filestream.Write` metody równocześnie, który nie jest obsługiwany przez klasę.</span><span class="sxs-lookup"><span data-stu-id="1ecff-132">In the following example, multiple threads would be attempting to call the `Filestream.Write` method simultaneously, which is not supported by the class.</span></span>  
  
```vb  
Dim fs As FileStream = File.OpenWrite(…)  
a.Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))  
```  
  
```csharp  
FileStream fs = File.OpenWrite(...);  
a.Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));  
```  
  
## <a name="limit-calls-to-thread-safe-methods"></a><span data-ttu-id="1ecff-133">Limit wywołania metod obsługujące wielowątkowość</span><span class="sxs-lookup"><span data-stu-id="1ecff-133">Limit Calls to Thread-Safe Methods</span></span>  
 <span data-ttu-id="1ecff-134">Najbardziej statycznej metody w programie .NET Framework są wątkowo i może zostać wywołana z wiele wątków jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="1ecff-134">Most static methods in the .NET Framework are thread-safe and can be called from multiple threads concurrently.</span></span> <span data-ttu-id="1ecff-135">Jednak nawet w takich przypadkach zaangażowanych synchronizacji może prowadzić do znaczne spowolnienie w zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="1ecff-135">However, even in these cases, the synchronization involved can lead to significant slowdown in the query.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ecff-136">Można przetestować tego samodzielnie przez wstawienie pewnych wywołań <xref:System.Console.WriteLine%2A> zapytania.</span><span class="sxs-lookup"><span data-stu-id="1ecff-136">You can test for this yourself by inserting some calls to <xref:System.Console.WriteLine%2A> in your queries.</span></span> <span data-ttu-id="1ecff-137">Mimo że ta metoda jest używana w przykładach dokumentacji dla celów demonstracyjnych, nie należy go używać zapytania dotyczące technologii PLINQ i.</span><span class="sxs-lookup"><span data-stu-id="1ecff-137">Although this method is used in the documentation examples for demonstration purposes, do not use it in PLINQ queries.</span></span>  
  
## <a name="avoid-unnecessary-ordering-operations"></a><span data-ttu-id="1ecff-138">Unikaj niepotrzebnych operacji kolejności</span><span class="sxs-lookup"><span data-stu-id="1ecff-138">Avoid Unnecessary Ordering Operations</span></span>  
 <span data-ttu-id="1ecff-139">Podczas PLINQ zapytania równolegle, dzieli sekwencji źródłowej na partycje, które może być obsługiwany przez jednocześnie na wielu wątków.</span><span class="sxs-lookup"><span data-stu-id="1ecff-139">When PLINQ executes a query in parallel, it divides the source sequence into partitions that can be operated on concurrently on multiple threads.</span></span> <span data-ttu-id="1ecff-140">Domyślnie nie jest przewidywalnej kolejności partycje są przetwarzane i wyniki są dostarczane (z wyjątkiem operatorów, takich jak `OrderBy`).</span><span class="sxs-lookup"><span data-stu-id="1ecff-140">By default, the order in which the partitions are processed and the results are delivered is not predictable (except for operators such as `OrderBy`).</span></span> <span data-ttu-id="1ecff-141">Możesz wydać PLINQ w celu zachowania kolejności żadnych sekwencji źródłowej, ale ma negatywny wpływ na wydajność.</span><span class="sxs-lookup"><span data-stu-id="1ecff-141">You can instruct PLINQ to preserve the ordering of any source sequence, but this has a negative impact on performance.</span></span> <span data-ttu-id="1ecff-142">Najlepszym rozwiązaniem, jeśli to możliwe, jest struktura zapytania tak, aby nie należy polegać na zachowanie porządku.</span><span class="sxs-lookup"><span data-stu-id="1ecff-142">The best practice, whenever possible, is to structure queries so that they do not rely on order preservation.</span></span> <span data-ttu-id="1ecff-143">Aby uzyskać więcej informacji, zobacz [zamawianie zachowywania w PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="1ecff-143">For more information, see [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).</span></span>  
  
## <a name="prefer-forall-to-foreach-when-it-is-possible"></a><span data-ttu-id="1ecff-144">ForAll — wolą ForEach, gdy jest to możliwe</span><span class="sxs-lookup"><span data-stu-id="1ecff-144">Prefer ForAll to ForEach When It Is Possible</span></span>  
 <span data-ttu-id="1ecff-145">Chociaż PLINQ wykonuje zapytanie na wiele wątków, jeśli korzystanie z powoduje `foreach` pętli (`For Each` w języku Visual Basic), a następnie wyniki zapytania musi być scalone jeden wątek i szeregowe używane przez moduł wyliczający.</span><span class="sxs-lookup"><span data-stu-id="1ecff-145">Although PLINQ executes a query on multiple threads, if you consume the results in a `foreach` loop (`For Each` in Visual Basic), then the query results must be merged back into one thread and accessed serially by the enumerator.</span></span> <span data-ttu-id="1ecff-146">W niektórych przypadkach jest to nieuniknione; Jednak jeśli to możliwe, użyj `ForAll` metodę umożliwiającą włączenie każdy wątek do wyjściowego własną wyników, na przykład, wpisując je do kolekcji wątkowo takich jak <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1ecff-146">In some cases, this is unavoidable; however, whenever possible, use the `ForAll` method to enable each thread to output its own results, for example, by writing to a thread-safe collection such as <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="1ecff-147">Ten sam problem dotyczy <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> innymi słowy, `source.AsParallel().Where().ForAll(...)` powinny być silnie preferowana względem</span><span class="sxs-lookup"><span data-stu-id="1ecff-147">The same issue applies to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> In other words, `source.AsParallel().Where().ForAll(...)` should be strongly preferred to</span></span>  
  
 <span data-ttu-id="1ecff-148">`Parallel.ForEach(source.AsParallel().Where(), ...)`.</span><span class="sxs-lookup"><span data-stu-id="1ecff-148">`Parallel.ForEach(source.AsParallel().Where(), ...)`.</span></span>  
  
## <a name="be-aware-of-thread-affinity-issues"></a><span data-ttu-id="1ecff-149">Należy pamiętać o problemy koligacji wątku</span><span class="sxs-lookup"><span data-stu-id="1ecff-149">Be Aware of Thread Affinity Issues</span></span>  
 <span data-ttu-id="1ecff-150">Niektóre technologie, na przykład współdziałanie COM dla składników Single-Threaded Apartment (STA), formularze systemu Windows i Windows Presentation Foundation (WPF), nakładają ograniczenia koligacji wątków, które wymagają kodu do uruchomienia na konkretnym wątkiem.</span><span class="sxs-lookup"><span data-stu-id="1ecff-150">Some technologies, for example, COM interoperability for Single-Threaded Apartment (STA) components, Windows Forms, and Windows Presentation Foundation (WPF), impose thread affinity restrictions that require code to run on a specific thread.</span></span> <span data-ttu-id="1ecff-151">Na przykład w formularzach systemu Windows i WPF formantu można uzyskać tylko w wątku, w którym został utworzony.</span><span class="sxs-lookup"><span data-stu-id="1ecff-151">For example, in both Windows Forms and WPF, a control can only be accessed on the thread on which it was created.</span></span> <span data-ttu-id="1ecff-152">Jeśli spróbujesz uzyskać dostępu do udostępnionych stan formantu formularzy systemu Windows w zapytaniu PLINQ jest zgłoszony wyjątek, jeśli używasz w debugerze.</span><span class="sxs-lookup"><span data-stu-id="1ecff-152">If you try to access the shared state of a Windows Forms control in a PLINQ query, an exception is raised if you are running in the debugger.</span></span> <span data-ttu-id="1ecff-153">(To ustawienie można wyłączyć.) Jednak zapytania jest używany w wątku interfejsu użytkownika, następnie można przejść do formantu z `foreach` wyników pętli, które wylicza zapytania, ponieważ ten kod wykonywany tylko jednego wątku.</span><span class="sxs-lookup"><span data-stu-id="1ecff-153">(This setting can be turned off.) However, if your query is consumed on the UI thread, then you can access the control from the `foreach` loop that enumerates the query results because that code executes on just one thread.</span></span>  
  
## <a name="do-not-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a><span data-ttu-id="1ecff-154">Nie należy zakładać, że iteracji ForEach, dla i ForAll — zawsze wykonywanie równoległe</span><span class="sxs-lookup"><span data-stu-id="1ecff-154">Do Not Assume that Iterations of ForEach, For and ForAll Always Execute in Parallel</span></span>  
 <span data-ttu-id="1ecff-155">Należy pamiętać, że poszczególne iteracji w <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> lub <xref:System.Linq.ParallelEnumerable.ForAll%2A> pętla może, ale nie ma potrzeby wykonywania równolegle.</span><span class="sxs-lookup"><span data-stu-id="1ecff-155">It is important to keep in mind that individual iterations in a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> or <xref:System.Linq.ParallelEnumerable.ForAll%2A> loop may but do not have to execute in parallel.</span></span> <span data-ttu-id="1ecff-156">W związku z tym należy unikać pisania kodu, który jest zależny pod kątem poprawności na wykonywanie równoległe iteracji lub wykonywania iteracji w określonej kolejności.</span><span class="sxs-lookup"><span data-stu-id="1ecff-156">Therefore, you should avoid writing any code that depends for correctness on parallel execution of iterations or on the execution of iterations in any particular order.</span></span>  
  
 <span data-ttu-id="1ecff-157">Na przykład ten kod prawdopodobnie zakleszczenie:</span><span class="sxs-lookup"><span data-stu-id="1ecff-157">For example, this code is likely to deadlock:</span></span>  
  
```vb  
Dim mre = New ManualResetEventSlim()  
    Enumerable.Range(0, ProcessorCount * 100).AsParallel().ForAll(Sub(j)   
  
                                                     If j = Environment.ProcessorCount Then  
  
                                                         Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)  
                                                         mre.Set()  
  
                                                     Else  
  
                                                         Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)  
                                                         mre.Wait()  
                                                     End If  
    End Sub) ' deadlocks  
```  
  
```csharp  
ManualResetEventSlim mre = new ManualResetEventSlim();  
            Enumerable.Range(0, ProcessorCount * 100).AsParallel().ForAll((j) =>  
            {  
                if (j == Environment.ProcessorCount)  
                {  
                    Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);  
                    mre.Set();  
                }  
                else  
                {  
                    Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);  
                    mre.Wait();  
                }  
            }); //deadlocks  
```  
  
 <span data-ttu-id="1ecff-158">W tym przykładzie iteracji jednego ustawia zdarzenie, a wszystkie inne iteracji oczekiwania na zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="1ecff-158">In this example, one iteration sets an event, and all other iterations wait on the event.</span></span> <span data-ttu-id="1ecff-159">Brak iteracji oczekiwania można wykonać dopiero po ukończeniu iteracji ustawienie zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="1ecff-159">None of the waiting iterations can complete until the event-setting iteration has completed.</span></span> <span data-ttu-id="1ecff-160">Jednak jest możliwe, że iteracji oczekiwania Blokuj wszystkie wątki, które są używane do wykonywania pętli równoległej, przed iteracji ustawienie zdarzenia miał możliwość wykonania.</span><span class="sxs-lookup"><span data-stu-id="1ecff-160">However, it is possible that the waiting iterations block all threads that are used to execute the parallel loop, before the event-setting iteration has had a chance to execute.</span></span> <span data-ttu-id="1ecff-161">Powoduje to zakleszczenie — nigdy nie wykona iteracji ustawienie zdarzenia i nigdy nie wzbudzania iteracji oczekiwania.</span><span class="sxs-lookup"><span data-stu-id="1ecff-161">This results in a deadlock – the event-setting iteration will never execute, and the waiting iterations will never wake up.</span></span>  
  
 <span data-ttu-id="1ecff-162">W szczególności jeden iteracji pętli równoległej nigdy nie należy czekać na inny iteracji pętli postęp.</span><span class="sxs-lookup"><span data-stu-id="1ecff-162">In particular, one iteration of a parallel loop should never wait on another iteration of the loop to make progress.</span></span> <span data-ttu-id="1ecff-163">Jeśli równoległej pętli decyduje się na Planowanie iteracji sekwencyjnie, ale w kolejności przeciwnej, nastąpi zakleszczenie.</span><span class="sxs-lookup"><span data-stu-id="1ecff-163">If the parallel loop decides to schedule the iterations sequentially but in the opposite order, a deadlock will occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ecff-164">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1ecff-164">See Also</span></span>  
 [<span data-ttu-id="1ecff-165">Równoległe LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="1ecff-165">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)