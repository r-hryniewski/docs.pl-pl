---
title: 'Porady: wywoływanie funkcji bazy danych'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
ms.openlocfilehash: 4a18bbad4bf38c69f86a320d95e893a7680315fb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43499903"
---
# <a name="how-to-call-database-functions"></a>Porady: wywoływanie funkcji bazy danych
<xref:System.Data.Objects.SqlClient.SqlFunctions> Klasa zawiera metody, które udostępniają funkcje programu SQL Server do użycia w składniku LINQ do zapytań jednostki. Kiedy używasz <xref:System.Data.Objects.SqlClient.SqlFunctions> metody w składniku LINQ do kwerendy jednostek, z odpowiednimi funkcjami bazy danych są wykonywane w bazie danych.  
  
> [!NOTE]
>  Funkcje bazy danych, wykonywania obliczeń na zbiór wartości, które zwraca pojedynczą wartość (znany także jako funkcje agregujące bazy danych), może być wywoływany bezpośrednio. Inne funkcje canonical można wywołać tylko jako część zapytaniu składnika LINQ to Entities. Aby wywołać funkcję agregującą bezpośrednio, należy przekazać <xref:System.Data.Objects.ObjectQuery%601> do funkcji. Aby uzyskać więcej informacji zobacz drugi przykład poniżej.  
  
> [!NOTE]
>  Metody w <xref:System.Data.Objects.SqlClient.SqlFunctions> klasy są specyficzne dla funkcji programu SQL Server. Podobne klas, które udostępniają funkcje bazy danych mogą być dostępne za pośrednictwem innych dostawców.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832). Kod w przykładzie wykonuje zapytaniu składnika LINQ to Entities używającej <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> metodę, aby zwrócić wszystkie kontakty, których nazwisko zaczyna się od "Si":  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832). Przykład wywołuje agregacji <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A> bezpośrednio metodę. Należy pamiętać, że <xref:System.Data.Objects.ObjectQuery%601> jest przekazywany do funkcji, co pozwala na można wywołać bez bycie częścią zapytaniu składnika LINQ to Entities.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## <a name="see-also"></a>Zobacz też  
 [Wywoływanie funkcji w zapytaniach składnika LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [Zapytania w składniku LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
