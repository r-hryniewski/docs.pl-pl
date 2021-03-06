---
title: 'Porady: pisanie niestandardowej funkcji agregowania w PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82e4ed0f93d7c41bc36427159442cc88b0a7867d
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2018
ms.locfileid: "44038838"
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a>Porady: pisanie niestandardowej funkcji agregowania w PLINQ
W tym przykładzie pokazano, jak używać <xref:System.Linq.ParallelEnumerable.Aggregate%2A> metody do stosowania funkcji agregacji niestandardowej sekwencji źródłowej.  
  
> [!WARNING]
>  W tym przykładzie jest jedynie do zademonstrowania określonych użycia i może nie działać szybciej niż równoważna sekwencyjnego LINQ do kwerendy obiekty. Aby uzyskać więcej informacji na temat przyspieszenie zobacz [ogólne informacje o przyspieszeniach w PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie oblicza odchylenie standardowe sekwencją liczb całkowitych.  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 W tym przykładzie używane jest przeciążenie agregacji standardowego operatora zapytania unikatowe dla PLINQ. To przeciążenie zajmuje dodatkowy <xref:System.Func%603?displayProperty=nameWithType> jako trzeci parametr wejściowy. Ten delegat łączy wyniki ze wszystkich wątków, przed wykonaniem obliczeń końcowego według wyników zagregowanych. W tym przykładzie dodamy razem kwoty ze wszystkich wątków.  
  
 Należy pamiętać, że jeśli treść wyrażenia lambda składa się z pojedynczego wyrażenia, wartość zwracana przez <xref:System.Func%602?displayProperty=nameWithType> delegat jest wartość wyrażenia.  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Linq.ParallelEnumerable>  
- [Równoległe LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
