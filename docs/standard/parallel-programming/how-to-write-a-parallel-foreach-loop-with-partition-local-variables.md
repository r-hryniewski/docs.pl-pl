---
title: 'Porady: zapisywanie równoległej pętli Foreach ze zmiennymi lokalnymi partycji'
ms.date: 06/26/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel foreach loop, how to use local state
ms.assetid: 24b10041-b30b-45cb-aa65-66cf568ca76d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: edcc390014cfc70f4da4f72270c7dd53f9b9423b
ms.sourcegitcommit: 9e18e4a18284ae9e54c515e30d019c0bbff9cd37
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/28/2018
ms.locfileid: "37076267"
---
# <a name="how-to-write-a-parallelforeach-loop-with-partition-local-variables"></a><span data-ttu-id="7fa2f-102">Porady: zapisywanie równoległej pętli Foreach ze zmiennymi lokalnymi partycji</span><span class="sxs-lookup"><span data-stu-id="7fa2f-102">How to: Write a Parallel.ForEach loop with partition-local variables</span></span>
<span data-ttu-id="7fa2f-103">Poniższy przykład przedstawia sposób zapisania <xref:System.Threading.Tasks.Parallel.ForEach%2A> metody, która używa zmiennych lokalnych partycji.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-103">The following example shows how to write a <xref:System.Threading.Tasks.Parallel.ForEach%2A> method that uses partition-local variables.</span></span> <span data-ttu-id="7fa2f-104">Gdy wykonywana jest pętla <xref:System.Threading.Tasks.Parallel.ForEach%2A>, kolekcja źródłowa jest dzielona na wiele partycji.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-104">When a <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop executes, it divides its source collection into multiple partitions.</span></span> <span data-ttu-id="7fa2f-105">Każda partycja ma własną kopię zmiennej lokalnej partycji.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-105">Each partition has its own copy of the partition-local variable.</span></span> <span data-ttu-id="7fa2f-106">Zmiennej lokalnej partycji jest podobny do [zmiennej lokalnej wątku](xref:System.Threading.ThreadLocal%601), z wyjątkiem tego, że wiele partycji można uruchomić w jednym wątku.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-106">A partition-local variable is similar to a [thread-local variable](xref:System.Threading.ThreadLocal%601), except that multiple partitions can run on a single thread.</span></span>
  
 <span data-ttu-id="7fa2f-107">Kod i parametry w przykładzie przypominają zbliżone w odpowiadającej metodzie <xref:System.Threading.Tasks.Parallel.For%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-107">The code and parameters in this example closely resemble the corresponding <xref:System.Threading.Tasks.Parallel.For%2A> method.</span></span> <span data-ttu-id="7fa2f-108">Aby uzyskać więcej informacji, zobacz [porady: zapisywanie równoległej pętli for ze zmiennymi lokalnymi wątku](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="7fa2f-108">For more information, see [How to: Write a Parallel.For Loop with Thread-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md).</span></span>  
  
 <span data-ttu-id="7fa2f-109">Aby użyć zmiennej lokalnej partycji w <xref:System.Threading.Tasks.Parallel.ForEach%2A> pętli, należy wywołać jednego z przeciążeń metody, które przyjmuje dwa parametry typu.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-109">To use a partition-local variable in a <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop, you must call one of the method overloads that takes two type parameters.</span></span> <span data-ttu-id="7fa2f-110">Pierwszy parametr typu `TSource`, określa typ elementu źródła, a drugi parametr typu `TLocal`, określa typ zmiennej lokalnej partycji.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-110">The first type parameter, `TSource`, specifies the type of the source element, and the second type parameter, `TLocal`, specifies the type of the partition-local variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fa2f-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="7fa2f-111">Example</span></span>  
 <span data-ttu-id="7fa2f-112">Następujące przykładowe wywołania <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> przeciążenia do obliczenia sumy tablicę elementów milion.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-112">The following example calls the <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> overload to compute the sum of an array of one million elements.</span></span> <span data-ttu-id="7fa2f-113">To przeciążenie ma cztery parametry:</span><span class="sxs-lookup"><span data-stu-id="7fa2f-113">This overload has four parameters:</span></span>  
  
-   <span data-ttu-id="7fa2f-114">`source`, który jest źródłem danych.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-114">`source`, which is the data source.</span></span> <span data-ttu-id="7fa2f-115">Musi on implementować <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-115">It must implement <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="7fa2f-116">Źródło danych w tym przykładzie jest elementem członkowskim milion `IEnumerable<Int32>` obiektu zwróconego przez <xref:System.Linq.Enumerable.Range%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-116">The data source in our example is the one million member `IEnumerable<Int32>` object returned by the <xref:System.Linq.Enumerable.Range%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="7fa2f-117">`localInit`, lub funkcji, która inicjuje zmiennej lokalnej partycji.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-117">`localInit`, or the function that initializes the partition-local variable.</span></span> <span data-ttu-id="7fa2f-118">Ta funkcja jest wywoływana raz dla każdej partycji, w którym <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> wykonuje operację.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-118">This function is called once for each partition in which the <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> operation executes.</span></span> <span data-ttu-id="7fa2f-119">Naszym przykładzie inicjuje zmiennej lokalnej partycji od zera.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-119">Our example initializes the partition-local variable to zero.</span></span>  
  
-   <span data-ttu-id="7fa2f-120">`body`, <xref:System.Func%604> który jest wywoływany przez równoległej pętli w każdej iteracji pętli.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-120">`body`, a <xref:System.Func%604> that is invoked by the parallel loop on each iteration of the loop.</span></span> <span data-ttu-id="7fa2f-121">Podpis jest `Func\<TSource, ParallelLoopState, TLocal, TLocal>`.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-121">Its signature is `Func\<TSource, ParallelLoopState, TLocal, TLocal>`.</span></span> <span data-ttu-id="7fa2f-122">Podaj kod dla obiekt delegowany i przekazuje pętli w parametrach wejściowych, które są:</span><span class="sxs-lookup"><span data-stu-id="7fa2f-122">You supply the code for the delegate, and the loop passes in the input parameters, which are:</span></span>  
  
    -   <span data-ttu-id="7fa2f-123">Bieżący element <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-123">The current element of the <xref:System.Collections.Generic.IEnumerable%601>.</span></span>
  
    -   <span data-ttu-id="7fa2f-124">A <xref:System.Threading.Tasks.ParallelLoopState> zmiennej, czy można użyć w kodzie pełnomocnika, aby sprawdzić stan pętli.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-124">A <xref:System.Threading.Tasks.ParallelLoopState> variable that you can use in your delegate's code to examine the state of the loop.</span></span>  
  
    -   <span data-ttu-id="7fa2f-125">Zmiennej lokalnej partycji.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-125">The partition-local variable.</span></span>  
  
     <span data-ttu-id="7fa2f-126">Pełnomocnika zwraca zmiennej lokalnej partycji, które są następnie przekazywane do następnej iteracji pętli, które wykonuje w tej określonej partycji.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-126">Your delegate returns the partition-local variable, which is then passed to the next iteration of the loop that executes in that particular partition.</span></span> <span data-ttu-id="7fa2f-127">Każda partycja pętli przechowuje oddzielnego wystąpienia tej zmiennej.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-127">Each loop partition maintains a separate instance of this variable.</span></span>  
  
     <span data-ttu-id="7fa2f-128">W tym przykładzie delegat dodaje wartość całkowitą każdej zmiennej lokalnej partycji, co umożliwia utrzymywanie uruchomionej całkowitej wartości elementów całkowitą w tej partycji.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-128">In the example, the delegate adds the value of each integer to the partition-local variable, which maintains a running total of the values of the integer elements in that partition.</span></span>  
  
-   <span data-ttu-id="7fa2f-129">`localFinally`, `Action<TLocal>` delegata, który <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> wywołuje po zakończeniu operacji pętli w każdej partycji.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-129">`localFinally`, an `Action<TLocal>` delegate that the <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> invokes when the looping operations in each partition have completed.</span></span> <span data-ttu-id="7fa2f-130"><xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> Metoda przekazuje Twojej `Action<TLocal>` delegowanie końcowa wartość zmiennej lokalnej partycji dla tej partycji pętli i podaj kod, który wykonuje akcję wymagane połączenie wyniku z tej partycji z wyników partycje.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-130">The <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> method passes your `Action<TLocal>` delegate the final value of the partition-local variable for this loop partition, and you provide the code that performs the required action for combining the result from this partition with the results from the other partitions.</span></span> <span data-ttu-id="7fa2f-131">Delegat może być wywoływany współbieżnie przez wiele zadań.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-131">This delegate can be invoked concurrently by multiple tasks.</span></span> <span data-ttu-id="7fa2f-132">W związku z tym w przykładzie użyto <xref:System.Threading.Interlocked.Add%28System.Int32%40%2CSystem.Int32%29?displayProperty=nameWithType> metody synchronizujący dostęp do `total` zmiennej.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-132">Because of this, the example uses the <xref:System.Threading.Interlocked.Add%28System.Int32%40%2CSystem.Int32%29?displayProperty=nameWithType> method to synchronize access to the `total` variable.</span></span> <span data-ttu-id="7fa2f-133">Ponieważ typ delegata to <xref:System.Action%601>, żadna wartość nie jest zwracana.</span><span class="sxs-lookup"><span data-stu-id="7fa2f-133">Because the delegate type is an <xref:System.Action%601>, there is no return value.</span></span>  
  
 [!code-csharp[TPL_Parallel#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/foreachthreadlocal.cs#04)]
 [!code-vb[TPL_Parallel#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/foreachthreadlocal.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="7fa2f-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7fa2f-134">See Also</span></span>  
 [<span data-ttu-id="7fa2f-135">Równoległość danych</span><span class="sxs-lookup"><span data-stu-id="7fa2f-135">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [<span data-ttu-id="7fa2f-136">Instrukcje: zapisywanie pętli Parallel.For ze zmiennymi lokalnymi wątku</span><span class="sxs-lookup"><span data-stu-id="7fa2f-136">How to: Write a Parallel.For Loop with Thread-Local Variables</span></span>](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md)  
 [<span data-ttu-id="7fa2f-137">Wyrażenia Lambda w PLINQ i TPL</span><span class="sxs-lookup"><span data-stu-id="7fa2f-137">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)