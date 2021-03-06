---
title: Wiele operacji kopiowania zbiorczego
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
ms.openlocfilehash: e6a9a82a49d2db2f1a49420c296be6dbf6d37d67
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520299"
---
# <a name="multiple-bulk-copy-operations"></a>Wiele operacji kopiowania zbiorczego
Można wykonać wiele operacji kopiowania zbiorczego przy użyciu pojedynczego wystąpienia <xref:System.Data.SqlClient.SqlBulkCopy> klasy. Jeśli zmienisz parametry operacji między kopii (na przykład nazwa tabeli docelowej), należy zaktualizować je przed kolejnych wywołań do któregokolwiek elementu **WriteToServer** metody, jak pokazano w poniższym przykładzie. Chyba że jawnie zmieniona wartości wszystkich właściwości pozostają takie same, jakie były na poprzedniej operacji kopiowania zbiorczego dla danego wystąpienia.  
  
> [!NOTE]
>  Wykonując wiele operacji kopiowania zbiorczego przy użyciu tego samego wystąpienia <xref:System.Data.SqlClient.SqlBulkCopy> jest zazwyczaj bardziej efektywne niż przy użyciu oddzielnego wystąpienia dla każdej operacji.  
  
 Należy wykonać kilka operacji kopiowania zbiorczego, korzystając z tych samych <xref:System.Data.SqlClient.SqlBulkCopy> obiektu, nie ma żadnych ograniczeń, czy informacje o źródłowej lub docelowej jest taki sam lub inne w przypadku każdej operacji. Jednak upewnij się, że informacji o skojarzeniu kolumny są ustawione właściwie każdorazowo, gdy zapisu na serwerze.  
  
> [!IMPORTANT]
>  W tym przykładzie nie będzie działać, chyba że utworzonego tabelami pracy zgodnie z opisem w [Konfiguracja przykładu kopiowania zbiorczego](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md). Ten kod jest dostarczany do zademonstrowania składnia przy użyciu **SqlBulkCopy** tylko. Jeśli tabele źródłowy i docelowy znajdują się w tym samym wystąpieniu programu SQL Server, jest łatwiejsze i szybsze użyj instrukcji Transact-SQL `INSERT … SELECT` instrukcję, aby skopiować dane.  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a>Zobacz też  
 [Operacje kopiowania masowego w programie SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [ADO.NET zarządzanego dostawcy i Centrum deweloperów zestawu danych](https://go.microsoft.com/fwlink/?LinkId=217917)
