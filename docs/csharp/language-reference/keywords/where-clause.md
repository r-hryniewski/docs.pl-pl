---
title: Klauzula where (odwołanie w C#)
ms.date: 07/20/2015
f1_keywords:
- whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
ms.openlocfilehash: 8607c79a8b1e9a9fd999e4f5b77ecfac786161b3
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43499864"
---
# <a name="where-clause-c-reference"></a>Klauzula where (odwołanie w C#)
`where` Klauzula jest używany w wyrażeniu zapytania, aby określić, które elementy ze źródła danych zostaną zwrócone w wyrażeniu zapytania. Ma to zastosowanie warunek logiczny (*predykatu*) do każdego elementu źródłowego (odwołuje się zmienna zakresu) i zwraca te, dla których określony warunek ma wartość true. Wyrażenie jedno zapytanie może zawierać więcej niż jednego `where` klauzul i jedną klauzulę może zawierać wiele podwyrażenia predykatu.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie `where` klauzuli odfiltrowuje wszystkie liczby z wyjątkiem tych, które są mniej niż pięć. Jeśli usuniesz `where` klauzuli, zostaną zwrócone wszystkie numery ze źródła danych. Wyrażenie `num < 5` jest predykat, która jest stosowana do każdego elementu.  
  
 [!code-csharp[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]  
  
## <a name="example"></a>Przykład  
 W obrębie pojedynczego `where` klauzuli, można określić dowolną liczbę predykatów zgodnie z potrzebami przy użyciu [ && ](../../../csharp/language-reference/operators/conditional-and-operator.md) i [ &#124; &#124; ](../../../csharp/language-reference/operators/conditional-or-operator.md) operatorów. W poniższym przykładzie zapytanie określa predykatów dwa, aby wybrać tylko liczby parzyste z zakresu, które są mniej niż pięć.  
  
 [!code-csharp[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]  
  
## <a name="example"></a>Przykład  
 A `where` klauzula może zawierać jedną lub więcej metod, które zwracają wartości logiczne. W poniższym przykładzie `where` klauzuli używa metody w celu ustalenia, czy bieżąca wartość zmiennej zakresu jest parzysta lub nieparzysta.  
  
 [!code-csharp[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]  
  
## <a name="remarks"></a>Uwagi  
 `where` Klauzula jest mechanizm filtrowania. Jego można umieścić praktycznie dowolnym miejscu w wyrażeniu zapytania z tym nie może być pierwszej lub ostatniej klauzuli. A `where` klauzula może występować przed lub po [grupy](../../../csharp/language-reference/keywords/group-clause.md) klauzuli w zależności od tego, czy masz do filtrowania elementów źródła przed lub po ich grupowania.  
  
 Jeśli określony predykat nie jest prawidłowy dla elementów w źródle danych, spowoduje błąd kompilacji. To jest jedną z zalet silne sprawdzania typów dostarczonych przez [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].  
  
 W czasie kompilacji `where` — słowo kluczowe jest konwertowana na wywołanie <xref:System.Linq.Enumerable.Where%2A> metody standardowej kwerendy operatora.  
  
## <a name="see-also"></a>Zobacz też

- [Słowa kluczowe zapytania (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
- [from, klauzula](../../../csharp/language-reference/keywords/from-clause.md)  
- [select, klauzula](../../../csharp/language-reference/keywords/select-clause.md)  
- [Filtrowanie danych](../../programming-guide/concepts/linq/filtering-data.md)  
- [Wyrażenia zapytań LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
- [Wprowadzenie do korzystania z LINQ w C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
