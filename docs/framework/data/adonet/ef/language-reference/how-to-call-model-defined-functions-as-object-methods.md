---
title: 'Porady: wywoływanie funkcji definiowanych przez Model jako metod obiektu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33bae8a8-4ed8-4a1f-85d1-c62ff288cc61
ms.openlocfilehash: 290c2f58d0259d5a0df52711f63c48521891ae12
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502084"
---
# <a name="how-to-call-model-defined-functions-as-object-methods"></a>Porady: wywoływanie funkcji definiowanych przez Model jako metod obiektu
W tym temacie opisano sposób wywołania funkcji definiowanych przez model jako metodę na <xref:System.Data.Objects.ObjectContext> obiektu lub metody statycznej na klasę niestandardową. A *funkcja zdefiniowana przez model* jest funkcją, która jest zdefiniowana w modelu koncepcyjnym. Procedury przedstawione w tym temacie opisano sposób wywołać te funkcje bezpośrednio, zamiast wywoływania ich z LINQ do zapytań jednostki. Aby dowiedzieć się, jak wywoływanie funkcji definiowanych przez model w składniku LINQ do jednostek zapytań, zobacz [jak: Call Model-Defined funkcji w zapytaniach](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md).  
  
 Czy wywołania funkcji definiowanych przez model jako <xref:System.Data.Objects.ObjectContext> metody lub jako statyczną metodę na klasę niestandardową, należy najpierw mapowanie metody funkcji definiowanych przez model <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. Jednak gdy należy zdefiniować metodę <xref:System.Data.Objects.ObjectContext> klasy, należy użyć <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> właściwości do udostępnienia dostawcy LINQ, natomiast podczas definiowania metody statycznej na klasę niestandardową, należy użyć <xref:System.Linq.IQueryable.Provider%2A> właściwości do udostępnienia dostawcy LINQ. Aby uzyskać więcej informacji zobacz przykłady, które należy wykonać poniższe procedury.  
  
 Poniższej procedury zapewnienia wysokiego poziomu opisanych wywoływanie funkcji definiowanych przez model jako metodę na <xref:System.Data.Objects.ObjectContext> obiektu oraz metody statycznej na klasę niestandardową. Przykłady, które należy wykonać więcej szczegółowych informacji o krokach w procedurach. W procedurach założono, że zdefiniowano funkcję w modelu koncepcyjnym. Aby uzyskać więcej informacji, zobacz [porady: Definiowanie niestandardowych funkcji w modelu koncepcyjnym](https://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f).  
  
### <a name="to-call-a-model-defined-function-as-a-method-on-an-objectcontext-object"></a>Aby wywołać funkcję definiowanych przez model jako metodę do obiektu ObjectContext  
  
1.  Dodać plik źródłowy rozszerzenie pochodzi od klasy częściowej <xref:System.Data.Objects.ObjectContext> klasy, generowane automatycznie za pomocą narzędzi Entity Framework. Definiowanie klasy zastępczej CLR w pliku źródłowym oddzielne uniemożliwi zmiany są utracone podczas ponownego generowania pliku.  
  
2.  Dodaj wspólnego języka wspólnego (CLR) metodę swoje <xref:System.Data.Objects.ObjectContext> klasę, która wykonuje następujące czynności:  
  
    -   Mapy do funkcji zdefiniowanych w modelu koncepcyjnym. Aby zmapować metody, należy najpierw zastosować <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> do metody. Należy pamiętać, że <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> i <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parametrów atrybutu są odpowiednio nazwę przestrzeni nazw modelu koncepcyjnego i nazwy funkcji w modelu koncepcyjnym. Funkcja rozpoznawania nazw dla programu LINQ jest uwzględniana wielkość liter.  
  
    -   Zwraca wyniki <xref:System.Linq.IQueryProvider.Execute%2A> metodę, która jest zwracana przez <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> właściwości.  
  
3.  Wywołaj metodę jako członka w wystąpieniu <xref:System.Data.Objects.ObjectContext> klasy.  
  
### <a name="to-call-a-model-defined-function-as-static-method-on-a-custom-class"></a>Aby wywołać funkcję definiowanych przez model jako metody statycznej na klasę niestandardową  
  
1.  Dodaj klasę do aplikacji przy użyciu statycznej metody, która wykonuje następujące czynności:  
  
    -   Mapy do funkcji zdefiniowanych w modelu koncepcyjnym. Aby zmapować metody, należy najpierw zastosować <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> do metody. Należy pamiętać, że <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> i <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parametrów atrybutu są odpowiednio nazwę przestrzeni nazw modelu koncepcyjnego i nazwy funkcji w modelu koncepcyjnym.  
  
    -   Akceptuje <xref:System.Linq.IQueryable> argumentu.  
  
    -   Zwraca wyniki <xref:System.Linq.IQueryProvider.Execute%2A> metodę, która jest zwracana przez <xref:System.Linq.IQueryable.Provider%2A> właściwości.  
  
2.  Wywołać metodę jako członek statycznej metody dla niestandardowej klasy  
  
## <a name="example"></a>Przykład  
 **Wywoływanie funkcji definiowanych przez Model jako metodę do obiektu ObjectContext**  
  
 Poniższy przykład pokazuje, jak wywoływanie funkcji definiowanych przez model jako metodę na <xref:System.Data.Objects.ObjectContext> obiektu. W przykładzie użyto [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832).  
  
 Należy wziąć pod uwagę, że modelu koncepcyjnego poniżej:: gettotalsize() zwróciło produktu przychodu dla określonego produktu. (Aby uzyskać informacje dotyczące dodawania funkcji do modelu koncepcyjnego, zobacz [porady: Definiowanie funkcje niestandardowe w modelu koncepcyjnym](https://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f).)  
  
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#4)]  

## <a name="example"></a>Przykład  
 Poniższy kod dodaje metodę `AdventureWorksEntities` klasa, która mapuje do funkcji modelu koncepcyjnego powyżej.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#2)]
 [!code-vb[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#2)]  
  
## <a name="example"></a>Przykład  
 Poniższy kod wywołuje metodę powyżej, aby wyświetlić przychód produktu dla określonego produktu:  
  
 [!code-csharp[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#3)]
 [!code-vb[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#3)]  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje sposób wywołania funkcji definiowanych przez model, które zwraca kolekcję (jako <xref:System.Linq.IQueryable%601> obiektu). Należy wziąć pod uwagę poniższe funkcja modelu koncepcyjnego, która zwraca wszystkie `SalesOrderDetails` identyfikatora danego produktu.  
  
 [!code-xml[DP L2E Methods on ObjectContext#7](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#7)]  
  
## <a name="example"></a>Przykład  
 Poniższy kod dodaje metodę `AdventureWorksEntities` klasa, która mapuje do funkcji modelu koncepcyjnego powyżej.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#8)]
 [!code-vb[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#8)]  
  
## <a name="example"></a>Przykład  
 Poniższy kod wywołuje metodę. Należy pamiętać, że zwrócony <xref:System.Linq.IQueryable%601> zapytania jest dalsze Elegancja do zwrócenia sumy wiersza dla każdego `SalesOrderDetail`.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#9)]
 [!code-vb[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#9)]  
  
## <a name="example"></a>Przykład  
 **Wywoływanie funkcji definiowanych przez Model jako metody statycznej na klasę niestandardową**  
  
 Następny przykład pokazuje, jak wywoływanie funkcji definiowanych przez model jako metody statycznej na klasę niestandardową. W przykładzie użyto [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832).  
  
> [!NOTE]
>  Po wywołaniu funkcji definiowanych przez model jako metody statycznej na klasę niestandardową, funkcji definiowanych przez model musi zaakceptować kolekcji i zwracają agregacji wartości w kolekcji.  
  
 Należy wziąć pod uwagę, że modelu koncepcyjnego poniżej:: gettotalsize() zwróciło przychodu z produktu dla kolekcji szczegóły zamówienia sprzedaży. (Aby uzyskać informacje dotyczące dodawania funkcji do modelu koncepcyjnego, zobacz [porady: Definiowanie funkcje niestandardowe w modelu koncepcyjnym](https://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f).).  
  
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#1)]
  
## <a name="example"></a>Przykład  
 Poniższy kod dodaje klasę do swojej aplikacji, która zawiera statyczne metody, która mapuje do funkcji modelu koncepcyjnego powyżej.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#5)]
 [!code-vb[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#5)]  
  
## <a name="example"></a>Przykład  
 Poniższy kod wywołuje metodę powyżej, aby wyświetlić przychód produktu dla kolekcji szczegóły zamówienia sprzedaży:  
  
 [!code-csharp[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#6)]
 [!code-vb[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#6)]  
  
## <a name="see-also"></a>Zobacz też  
 [Omówienie pliku edmx](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [Zapytania w składniku LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [Wywoływanie funkcji w zapytaniach składnika LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)
