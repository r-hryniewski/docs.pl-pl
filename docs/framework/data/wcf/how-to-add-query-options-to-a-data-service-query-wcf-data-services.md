---
title: "Porady: Dodawanie opcje zapytania do zapytania usługi danych (usługi danych WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- querying the data service [WCF Data Services]
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: e4258526-557e-4e96-91e1-2175400c7c8f
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7349864e8b191060964a7e716b34a0a7587e8f36
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-add-query-options-to-a-data-service-query-wcf-data-services"></a>Porady: Dodawanie opcje zapytania do zapytania usługi danych (usługi danych WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]Umożliwia to zapytanie usługi danych z aplikacji klienta opartego na programie .NET Framework za pomocą klasy usługi danych wygenerowanego klienta. Najprostsza w tym celu jest utworzenie w wyrażeniu kwerendy języka zapytań zintegrowanym (LINQ) zawiera opcje żądanego zapytania. Można również wywołać szereg metod zapytań LINQ utworzenie równoważne zapytania. Ponadto można użyć <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> metody w celu dodania opcje zapytania do zapytania. W każdym z tych przypadków identyfikator URI, generowany przez klienta zawiera zestaw jednostek żądanego z opcje wybrane zapytanie zastosowane. Aby uzyskać więcej informacji, zobacz [zapytanie usługi danych](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Przykład, w tym temacie korzysta z Northwind przykładowych danych wygenerowany automatycznie i usługi klienta danych usługi klas. Ta usługa i klas danych klienta są tworzone po ukończeniu [szybkiego startu usługi danych WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak utworzyć wyrażenie zapytania LINQ, które zwraca tylko zamówień kosztem transport ponad 30 $ i że zamówień wyniki według daty wysyłki w kolejności malejącej.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinq](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptionslinq)]
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinq](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptionslinq)]  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak utworzenie zapytania LINQ za pomocą metody zapytań LINQ, który jest odpowiednikiem poprzedniego zapytania.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpression](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptionslinqexpression)]
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpression](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptionslinqexpression)]  
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia użycie do <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> metodę w celu utworzenia <xref:System.Data.Services.Client.DataServiceQuery%601> będący odpowiednikiem poprzednich przykładach.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptions)]
 [!code-vb[Astoria Northwind Client#AddQueryOptions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptions)]  
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia użycie `$orderby` opcji zapytania do filtrowania i kolejność zwróciło obiektów zamówień przez właściwość transportu.  
  
 [!code-csharp[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#orderwithfilter)]
 [!code-vb[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#orderwithfilter)]  
  
## <a name="see-also"></a>Zobacz też  
 [Zapytanie usługi danych](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 [Porady: projekt wyników zapytania](../../../../docs/framework/data/wcf/how-to-project-query-results-wcf-data-services.md)