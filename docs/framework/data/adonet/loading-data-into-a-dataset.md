---
title: "Podczas ładowania danych do zestawu danych"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: afb05055d67a4430909a657fc0ee90c97d3ebfb0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="d6592-102">Podczas ładowania danych do zestawu danych</span><span class="sxs-lookup"><span data-stu-id="d6592-102">Loading Data Into a DataSet</span></span>
<span data-ttu-id="d6592-103">A <xref:System.Data.DataSet> obiektu najpierw powinno zostać zapełnione przed można zbadać nad nim z [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6592-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="d6592-104">Istnieje kilka różnych sposobów, aby wypełnić <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="d6592-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="d6592-105">Na przykład można użyć [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] w bazie danych i ładuje wyniki do <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="d6592-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="d6592-106">Aby uzyskać więcej informacji, zobacz [LINQ do SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="d6592-106">For more information, see [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="d6592-107">Inny typowy sposób, aby załadować dane <xref:System.Data.DataSet> jest użycie <xref:System.Data.Common.DataAdapter> klasy można pobrać danych z bazy danych.</span><span class="sxs-lookup"><span data-stu-id="d6592-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="d6592-108">Jest to zilustrowane w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="d6592-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6592-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="d6592-109">Example</span></span>  
 <span data-ttu-id="d6592-110">W tym przykładzie użyto <xref:System.Data.Common.DataAdapter> do informacji o sprzedaży z roku 2002, w bazie danych AdventureWorks i ładuje wyniki do <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="d6592-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="d6592-111">Po <xref:System.Data.DataSet> zostały wypełnione, można zapisać zapytania na nim przy użyciu [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6592-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="d6592-112">`FillDataSet` Metoda w tym przykładzie jest używana w przykładowych zapytań w [LINQ do DataSet przykłady](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span><span class="sxs-lookup"><span data-stu-id="d6592-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span></span> <span data-ttu-id="d6592-113">Aby uzyskać więcej informacji, zobacz [zapytań zestawów danych](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="d6592-113">For more information, see [Querying DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="d6592-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d6592-114">See Also</span></span>  
 [<span data-ttu-id="d6592-115">LINQ do DataSet — omówienie</span><span class="sxs-lookup"><span data-stu-id="d6592-115">LINQ to DataSet Overview</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)  
 [<span data-ttu-id="d6592-116">Wykonywanie zapytania zbiory danych</span><span class="sxs-lookup"><span data-stu-id="d6592-116">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [<span data-ttu-id="d6592-117">LINQ do DataSet przykłady</span><span class="sxs-lookup"><span data-stu-id="d6592-117">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)