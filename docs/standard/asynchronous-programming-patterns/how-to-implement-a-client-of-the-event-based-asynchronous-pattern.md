---
title: 'Porady: implementacja klienta wzorca asynchronicznego opartego na zdarzeniach'
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
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b70d4ba205d39ad8fcbc7c7f6fa1f5b34a36c98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a><span data-ttu-id="6a291-102">Porady: implementacja klienta wzorca asynchronicznego opartego na zdarzeniach</span><span class="sxs-lookup"><span data-stu-id="6a291-102">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="6a291-103">Poniższy przykład kodu pokazuje sposób użycia składnika zgodną [oparty na zdarzeniach asynchroniczny wzorzec — Przegląd](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6a291-103">The following code example demonstrates how to use a component that adheres to the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span> <span data-ttu-id="6a291-104">W tym przykładzie używa `PrimeNumberCalculator` opisanych w części [porady: implementacja składnika obsługującego wzorzec asynchroniczny oparty na zdarzeniach](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="6a291-104">The form for this example uses the `PrimeNumberCalculator` component described in [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>  
  
 <span data-ttu-id="6a291-105">Po uruchomieniu projektu, który korzysta z tego przykładu, zobaczysz formularz "Liczba pierwsza Kalkulator" z siatki i dwa przyciski: **Rozpocznij nowe zadanie** i **anulować**.</span><span class="sxs-lookup"><span data-stu-id="6a291-105">When you run a project that uses this example, you will see a "Prime Number Calculator" form with a grid and two buttons: **Start New Task** and **Cancel**.</span></span> <span data-ttu-id="6a291-106">Możesz kliknąć **Rozpocznij nowe zadanie** przycisk kilka razy pod rząd, przy każdym kliknięciu operację asynchroniczną zostanie rozpoczęta i obliczeń, aby określić, czy liczba losowo wygenerowany test jest pierwsze.</span><span class="sxs-lookup"><span data-stu-id="6a291-106">You can click the **Start New Task** button several times in succession, and for each click, an asynchronous operation will begin a computation to determine if a randomly generated test number is prime.</span></span> <span data-ttu-id="6a291-107">Formularz okresowo wyświetli się postęp i wyniki przyrostowe.</span><span class="sxs-lookup"><span data-stu-id="6a291-107">The form will periodically display progress and incremental results.</span></span> <span data-ttu-id="6a291-108">Każda operacja jest przypisana zadań Unikatowy identyfikator.</span><span class="sxs-lookup"><span data-stu-id="6a291-108">Each operation is assigned a unique task ID.</span></span> <span data-ttu-id="6a291-109">Wynikiem obliczenia jest wyświetlany w **wynik** kolumny; Jeśli kod testu nie jest podstawowym, jest oznaczone jako **złożonego,** i jego pierwszy dzielnik jest wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="6a291-109">The result of the computation is displayed in the **Result** column; if the test number is not prime, it is labeled as **Composite,** and its first divisor is displayed.</span></span>  
  
 <span data-ttu-id="6a291-110">Oczekujących operacji mogą zostać anulowane z **anulować** przycisku.</span><span class="sxs-lookup"><span data-stu-id="6a291-110">Any pending operation can be canceled with the **Cancel** button.</span></span> <span data-ttu-id="6a291-111">Wielokrotny będzie możliwe.</span><span class="sxs-lookup"><span data-stu-id="6a291-111">Multiple selections can be made.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a291-112">Większość numerów nie jest pierwsze.</span><span class="sxs-lookup"><span data-stu-id="6a291-112">Most numbers will not be prime.</span></span> <span data-ttu-id="6a291-113">Jeśli nie znajdziesz liczba pierwsza po kilku ukończone operacje, wystarczy uruchomić więcej zadań, a ostatecznie można znaleźć niektórych liczb pierwszych.</span><span class="sxs-lookup"><span data-stu-id="6a291-113">If you have not found a prime number after several completed operations, simply start more tasks, and eventually you will find some prime numbers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a291-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="6a291-114">Example</span></span>  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="6a291-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6a291-115">See Also</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>