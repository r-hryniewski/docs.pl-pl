---
title: 'Porady: Użyj procedur składowanych mapowane do wielu kształtów wyników'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2b84dfe-7fec-489a-92de-45215cec4518
ms.openlocfilehash: 03a003bd5b09ae19b01dcc9880137661ba6fccae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356799"
---
# <a name="how-to-use-stored-procedures-mapped-for-multiple-result-shapes"></a>Porady: Użyj procedur składowanych mapowane do wielu kształtów wyników
Gdy procedura składowana może zwracać wiele kształtów wynik, zwracany typ nie silnie typizowaną do projekcji pojedynczego kształtu. Mimo że [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] można wygenerować wszystkich typów możliwych projekcji, nie może znać kolejności, w której będą zwracane.  
  
 Natomiast tego scenariusza z procedur składowanych, które powodują powstanie wielu kształtów wynik sekwencyjnie. Aby uzyskać więcej informacji, zobacz [porady: użycie przechowywane procedury mapowane sekwencyjnych kształtów wynik](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md).  
  
 <xref:System.Data.Linq.Mapping.ResultTypeAttribute> Atrybut jest stosowany na procedury składowane, które zwracają wiele typów wyników, aby określić zestaw procedura może zwracać typów.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie kodu SQL kształt wyniku zależy od danych wejściowych (`shape =1` lub `shape = 2`). Nie wiadomo, projekcji, które zostaną zwrócone najpierw.  
  
```  
CREATE PROCEDURE VariableResultShapes(@shape int)  
AS  
if(@shape = 1)  
    select CustomerID, ContactTitle, CompanyName from customers  
else if(@shape = 2)  
    select OrderID, ShipName from orders  
```  
  
 [!code-csharp[DLinqSprox#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#4)]
 [!code-vb[DLinqSprox#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#4)]  
  
## <a name="example"></a>Przykład  
 Należy użyć podobny do następującego kodu, aby wykonać tę procedurę składowaną.  
  
> [!NOTE]
>  Należy użyć <xref:System.Data.Linq.IMultipleResults.GetResult%2A> wzorzec do uzyskania moduł wyliczający prawidłowego typu, na podstawie informacji z procedury składowanej.  
  
 [!code-csharp[DLinqSprox#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#5)]
 [!code-vb[DLinqSprox#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Zobacz też  
 [Procedury składowane](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
