---
title: Podczas badania zestawów danych (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: 5ecf85a73cd38fc1fa575bd591618e5273b390e0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510145"
---
# <a name="querying-datasets-linq-to-dataset"></a>Podczas badania zestawów danych (LINQ to DataSet)
Po <xref:System.Data.DataSet> obiektu została wypełniona danymi, można rozpocząć, badając ją. Formułowanie zapytania z [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] jest podobne do [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] względem innych [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]— włączone źródeł danych. Należy jednak pamiętać, że gdy używasz [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] zapytań <xref:System.Data.DataSet> obiektu jest wykonywane zapytanie wyliczenie <xref:System.Data.DataRow> obiekty, zamiast wyliczenie typu niestandardowego. Oznacza to, że można użyć dowolnego z elementów członkowskich <xref:System.Data.DataRow> klasy w swojej [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] zapytania. Dzięki temu można tworzyć zaawansowane, złożone zapytania.  
  
 Podobnie jak w przypadku innych implementacji [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], możesz utworzyć [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] zapytania w dwóch różnych formach: składnia wyrażenia oraz składni zapytania oparte na metodzie zapytania. Aby uzyskać więcej informacji na temat tych dwóch formach zobacz [wprowadzenie do LINQ](https://msdn.microsoft.com/library/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9). Można użyć składni wyrażeń zapytania lub składni zapytania oparte na metodzie do wykonania zapytania względem pojedynczej tabel w <xref:System.Data.DataSet>, dla wielu tabel w <xref:System.Data.DataSet>, lub dla tabel w typizowanych <xref:System.Data.DataSet>.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Zapytania jednotabelowe](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 W tym artykule opisano, jak wykonywać zapytania jednotabelowe.  
  
 [Zapytania wielotabelowe](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 Opisuje sposób wykonywania zapytań między tabelami.  
  
 [Wykonywanie zapytania do typizowanych zestawów danych](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 W tym artykule opisano sposób tworzenia zapytań względem wpisane <xref:System.Data.DataSet> obiektów.  
  
## <a name="see-also"></a>Zobacz też  
 [Przykłady LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [Ładowanie danych do zestawu danych](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
