---
title: Wątkowość (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 704bb04b-ff23-471d-ab12-3cec1c2bca59
ms.openlocfilehash: 366c88db5d229120b1e626f275b4eeb8ecd42dba
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123101"
---
# <a name="threading-visual-basic"></a>Wątkowość (Visual Basic)
Wątkowość Włącza program Visual Basic, aby wykonać równoczesne przetwarzanie, dzięki czemu możesz zrobić więcej niż jedną operację naraz. Na przykład umożliwia wątkowości monitorować dane wejściowe od użytkownika, wykonywanie zadań w tle i obsługi równoczesnymi strumieniami danych wejściowych.  
  
 Wątki mają następujące właściwości:  
  
-   Wątki umożliwić programowi przeprowadzić równoczesne przetwarzanie.  
  
-   .NET Framework <xref:System.Threading> przestrzeni nazw sprawia, że wątki łatwiejsze.  
  
-   Wątki współużytkują zasoby aplikacji. Aby uzyskać więcej informacji, zobacz [za pomocą wątków i wątki](../../../../standard/threading/using-threads-and-threading.md).  
  
 Domyślnie program Visual Basic ma jeden wątek. Jednakże wątki pomocnicze można tworzyć i umożliwia wykonanie kodu równolegle z wątku głównego. Te wątki są często nazywane *wątków roboczych*.  
  
 Wątki robocze może służyć do wykonywania zadań czasochłonne lub wrażliwego na czas bez zajmowania wątku głównego. Na przykład wątki robocze są często używane w aplikacjach serwerowych do spełnienia żądania przychodzące bez oczekiwania na ukończenie poprzedniego żądania. Wątki robocze są również używane do wykonywania zadań "tła" w aplikacjach pulpitu tak, aby główny wątek — dyski elementy interfejsu użytkownika — pozostaje reagują na czynności użytkownika.  
  
 Wątkowość rozwiązuje problemy z przepływności i czasu odpowiedzi, ale również mogą wprowadzać udostępnianie zasobów problemy, takie jak zakleszczeń i sytuacje wyścigu. Wiele wątków są najlepsze w przypadku zadań, które wymagają różnych zasobów, takich jak dojścia do plików i połączeń sieciowych. Przypisywanie wielu wątków do pojedynczego zasobu jest może spowodować problemy z synchronizacją i konieczności często blokowane podczas oczekiwania na inne wątki wątki pozbawia przy użyciu wielu wątków.  
  
 Typowe strategia polega na wątki robocze do wykonania czasochłonnych lub wrażliwego na czas zadania, które nie wymagają wielu zasoby używane przez inne wątki. Oczywiście niektórych zasobów w programie muszą być dostępne w wielu wątkach. W takich przypadkach <xref:System.Threading> przestrzeń nazwy udostępnia klasy do synchronizacji wątków. Te klasy mają <xref:System.Threading.Mutex>, <xref:System.Threading.Monitor>, <xref:System.Threading.Interlocked>, <xref:System.Threading.AutoResetEvent>, i <xref:System.Threading.ManualResetEvent>.  
  
 Niektórych lub wszystkich tych klas służy do synchronizowania działania wielu wątków, ale niektóre Obsługa wątkowości jest obsługiwany przez język Visual Basic. Na przykład [SyncLock — instrukcja](../../../../visual-basic/language-reference/statements/synclock-statement.md) udostępnia funkcje synchronizacji przy użyciu niejawnego <xref:System.Threading.Monitor>.  
  
> [!NOTE]
>  Począwszy od [!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)], programowanie wielowątkowe zostało znacznie uproszczone dzięki <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> i <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> klas, [Parallel LINQ (PLINQ)](../../../../standard/parallel-programming/parallel-linq-plinq.md), nowej kolekcji współbieżnych klas w <xref:System.Collections.Concurrent?displayProperty=nameWithType> przestrzeń nazw, a nowy model programowania, który opiera się na koncepcji zadania, a nie wątków. Aby uzyskać więcej informacji, zobacz [programowania równoległego](../../../../standard/parallel-programming/index.md).  
  
## <a name="related-topics"></a>Tematy pokrewne  
  
|Tytuł|Opis|  
|-----------|-----------------|  
|[Wątkowość](../../../../standard/threading/index.md)|Opisuje sposób implementacji wątkowości w programie .NET Framework.|
