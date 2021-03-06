---
title: Dynamiczne określanie filtrów predykatów w środowisku uruchomieniowym (LINQ w C#)
description: Dowiedz się, jak i dynamiczne określanie filtrów predykatów w czasie wykonywania za pomocą LINQ w C#.
ms.date: 12/1/2016
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.openlocfilehash: ece5940edd615f30acab06a429de300e27811a66
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/25/2018
ms.locfileid: "50038491"
---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a>Dynamiczne określanie filtrów predykatów w środowisku uruchomieniowym

W niektórych przypadkach nie wiesz, do czasu wykonywania ile predykaty, należy zastosować do elementów źródła w `where` klauzuli. Jednym ze sposobów dynamiczne określanie filtrów predykatów wielu jest użycie <xref:System.Linq.Enumerable.Contains%2A> metodzie, jak pokazano w poniższym przykładzie. Przykład jest tworzona na dwa sposoby. Po pierwsze projekt jest uruchamiane przez filtrowanie według wartości, które znajdują się w programie. Projekt jest następnie uruchom ponownie przy użyciu danych wejściowych dostarczonych w czasie wykonywania.

## <a name="to-filter-by-using-the-contains-method"></a>Aby filtrować przy użyciu metody zawiera

1. Otwórz nową aplikację konsolową i nadaj mu nazwę `PredicateFilters`.

2. Kopiuj `StudentClass` klasy z [kwerenda dotycząca kolekcji obiektów](query-a-collection-of-objects.md) i wklej go do obszaru nazw `PredicateFilters` poniżej klasy `Program`. `StudentClass` zawiera listę `Student` obiektów.

3. Komentarz `Main` method in Class metoda `StudentClass`.

4. Zastąp klasę `Program` następującym kodem:

     [!code-csharp[csProgGuideLINQ#26](~/samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]

5. Dodaj następujący wiersz do `Main` metody w klasie `DynamicPredicates`, w ramach deklaracji `ids`.

     ```csharp
     QueryById(ids);
     ```

6. Uruchom projekt.

7. W oknie konsoli wyświetlane są następujące dane wyjściowe:

     Garcia: 114

     O'Donnell: 112

     Omelchenko: 111

8. Następnym krokiem jest, aby ponownie uruchomić projekt, tym razem przy użyciu danych wejściowych wprowadzić w czasie wykonywania, zamiast tablicy `ids`. Zmiana `QueryByID(ids)` do `QueryByID(args)` w `Main` metody.

9. Uruchom projekt z argumentami wiersza polecenia `122 117 120 115`. Po uruchomieniu projektu, te wartości stają się elementy `args`, parametr `Main` metody.

10. W oknie konsoli wyświetlane są następujące dane wyjściowe:

     Adams: 120

     We Feng: 117

     Garcia: 115

     Tucker: 122

## <a name="to-filter-by-using-a-switch-statement"></a>Aby filtrować przy użyciu instrukcji switch

1. Możesz użyć `switch` instrukcję, aby wybrać wśród uprzednio określonym alternatywnych zapytań. W poniższym przykładzie `studentQuery` używa innego `where` klauzuli zależności od tego, w którym klasy korporacyjnej poziom lub roku, jest określony w czasie wykonywania.

2. Kopiuj następującą metodę i wkleić go do klasy `DynamicPredicates`.

     [!code-csharp[csProgGuideLINQ#27](~/samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]

3. W `Main` metody, Zastąp wywołanie `QueryByID` przy użyciu następującego wywołania, które wysyła pierwszego elementu z `args` tablicę jako jej argument: `QueryByYear(args[0])`.

4. Uruchom projekt z argumentem wiersza polecenia z wartością całkowitą z zakresu od 1 do 4.

## <a name="see-also"></a>Zobacz także

- [Language Integrated Query (LINQ)](index.md)
- [where, klauzula](../language-reference/keywords/where-clause.md)
