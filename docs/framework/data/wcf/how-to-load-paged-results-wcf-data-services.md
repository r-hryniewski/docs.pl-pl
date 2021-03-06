---
title: 'Porady: obciążenia stronicowanej wyników (usługi danych WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: bb786ea4-f3ef-4ad3-9a41-3a0b7feb6a1f
ms.openlocfilehash: 6706ad2eb6821c2c30b5d2482f709ba849b59f32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356593"
---
# <a name="how-to-load-paged-results-wcf-data-services"></a>Porady: obciążenia stronicowanej wyników (usługi danych WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Umożliwia usłudze danych ograniczyć liczbę jednostek, które są zwracane w pojedynczą odpowiedź źródła danych. W takim przypadku końcowy wpis w źródle danych zawiera łącze do następnej strony danych. Identyfikator URI do następnej strony danych można uzyskać przez wywołanie <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A> metody <xref:System.Data.Services.Client.QueryOperationResponse%601>, który jest zwracany, gdy <xref:System.Data.Services.Client.DataServiceQuery%601> jest wykonywana. Identyfikator URI reprezentowany przez ten obiekt jest następnie używany do załadowania następnej strony wyników. Aby uzyskać więcej informacji, zobacz [ładowanie odłożone zawartości](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 Przykład, w tym temacie korzysta z Northwind przykładowych danych wygenerowany automatycznie i usługi klienta danych usługi klas. Ta usługa i klas danych klienta są tworzone po ukończeniu [szybkiego startu usługi danych WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Przykład  
 W tym przykładzie użyto `do…while` pętli załadować `Customers` jednostek z wyników stronicowania z usługi danych.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getcustomerspaged)]
 [!code-vb[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getcustomerspaged)]  
  
## <a name="example"></a>Przykład  
 W tym przykładzie Zwraca powiązane `Orders` jednostek z każdym `Customers` jednostki i używa `do…while` pętli załadować `Customers` strony jednostek i zagnieżdżoną `while` pętli do załadowania strony powiązane `Orders` jednostek z usługi danych .  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getcustomerspagednested)]
 [!code-vb[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getcustomerspagednested)]  
  
## <a name="see-also"></a>Zobacz też  
 [Ładowanie odroczonej zawartości](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)  
 [Instrukcje: Ładowanie powiązanych jednostek](../../../../docs/framework/data/wcf/how-to-load-related-entities-wcf-data-services.md)
