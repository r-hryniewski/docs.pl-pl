---
title: 'Porady: używanie ForEach do usuwanie elementów BlockingCollection'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collectoin
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44b71ed726af585259b015c608e49d8c81e4e22a
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49120964"
---
# <a name="how-to-use-foreach-to-remove-items-in-a-blockingcollection"></a>Porady: używanie ForEach do usuwanie elementów BlockingCollection
Oprócz wykonywania elementów z <xref:System.Collections.Concurrent.BlockingCollection%601> przy użyciu <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> i <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> metody, można również użyć [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md) ([dla każdego](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md) w języku Visual Basic) do usuwanie elementów, aż do dodawania ukończone i kolekcja jest pusta. Jest to nazywane *mutacja wyliczenie* lub *wykorzystywanie wyliczenie* , ponieważ w odróżnieniu od typowych `foreach` (`For Each`) pętli, ten moduł wyliczający modyfikuje kolekcji źródłowej, usuwając elementy.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak usunąć wszystkie elementy w <xref:System.Collections.Concurrent.BlockingCollection%601> przy użyciu `foreach` (`For Each`) pętli.  
  
 [!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
 [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]  
  
 W tym przykładzie użyto `foreach` pętli z <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> metody w zużywającym wątku, co powoduje, że każdy element do usunięcia z kolekcji jest uprzednie. <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> Ogranicza maksymalną liczbę elementów znajdujących się w kolekcji, w dowolnym momencie. Wyliczanie kolekcji w ten sposób blokuje wątku konsumenta, jeśli nie, nie są dostępne elementy, lub jeśli kolekcja jest pusta. W tym przykładzie blokowania nie ma znaczenia, ponieważ wątek producentów dodaje elementy szybciej niż mogą być używane.  
  
 Nie ma żadnej gwarancji, że elementy są wyliczane w tej samej kolejności, dodawanych przez wątki producenta.  
  
 Wyliczyć kolekcji bez modyfikowania go, wystarczy użyć `foreach` (`For Each`) bez <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> metody. Jednak ważne jest zrozumienie, że ten rodzaj wyliczenie reprezentuje migawkę kolekcji w określonym punkcie w czasie. Jeśli inne wątki dodawania lub usuwania elementów równolegle, gdy są wykonywane pętli, pętla może reprezentuje rzeczywisty stan kolekcji.  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
- [Programowanie równoległe](../../../../docs/standard/parallel-programming/index.md)
