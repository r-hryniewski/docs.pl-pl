---
title: ORDER BY (jednostka SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0b61572-ecee-41eb-9d7f-74132ec8a26c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b805d4437ffd8d3d56a7cdc599bdda797a763d13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="order-by-entity-sql"></a><span data-ttu-id="85b05-102">ORDER BY (jednostka SQL)</span><span class="sxs-lookup"><span data-stu-id="85b05-102">ORDER BY (Entity SQL)</span></span>
<span data-ttu-id="85b05-103">Określa porządek sortowania używane dla obiektów zwracanych w instrukcji SELECT.</span><span class="sxs-lookup"><span data-stu-id="85b05-103">Specifies the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85b05-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="85b05-104">Syntax</span></span>  
  
```  
[ ORDER BY   
   {  
      order_by_expression [SKIP n] [LIMIT n]  
      [ COLLATE collation_name ]  
      [ ASC | DESC ]  
   }  
   [ ,…n ]   
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="85b05-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="85b05-105">Arguments</span></span>  
 `order_by_expression`  
 <span data-ttu-id="85b05-106">Dowolne wyrażenie prawidłowe zapytanie, określając właściwości do sortowania.</span><span class="sxs-lookup"><span data-stu-id="85b05-106">Any valid query expression specifying a property on which to sort.</span></span> <span data-ttu-id="85b05-107">Można określić wiele wyrażeń sortowania.</span><span class="sxs-lookup"><span data-stu-id="85b05-107">Multiple sort expressions can be specified.</span></span> <span data-ttu-id="85b05-108">Taką sekwencję wyrażeń sortowania w klauzuli ORDER BY definiuje organizacji zestawu wyników posortowane.</span><span class="sxs-lookup"><span data-stu-id="85b05-108">The sequence of the sort expressions in the ORDER BY clause defines the organization of the sorted result set.</span></span>  
  
 <span data-ttu-id="85b05-109">Instrukcji COLLATE {collation_name}</span><span class="sxs-lookup"><span data-stu-id="85b05-109">COLLATE {collation_name}</span></span>  
 <span data-ttu-id="85b05-110">Określa, czy można wykonać operacji ORDER BY, zgodnie z Sortowanie określone w `collation_name`.</span><span class="sxs-lookup"><span data-stu-id="85b05-110">Specifies that the ORDER BY operation should be performed according to the collation specified in `collation_name`.</span></span> <span data-ttu-id="85b05-111">Instrukcji COLLATE ma zastosowanie tylko w przypadku wyrażenia ciągu.</span><span class="sxs-lookup"><span data-stu-id="85b05-111">COLLATE is applicable only for string expressions.</span></span>  
  
 <span data-ttu-id="85b05-112">ASC</span><span class="sxs-lookup"><span data-stu-id="85b05-112">ASC</span></span>  
 <span data-ttu-id="85b05-113">Określa, że wartości w określonej właściwości mają być sortowane w kolejności rosnącej, od najniższej wartości do największej wartości.</span><span class="sxs-lookup"><span data-stu-id="85b05-113">Specifies that the values in the specified property should be sorted in ascending order, from lowest value to highest value.</span></span> <span data-ttu-id="85b05-114">Domyślnie włączone.</span><span class="sxs-lookup"><span data-stu-id="85b05-114">This is the default.</span></span>  
  
 <span data-ttu-id="85b05-115">DESC</span><span class="sxs-lookup"><span data-stu-id="85b05-115">DESC</span></span>  
 <span data-ttu-id="85b05-116">Określa, że wartości w określonej właściwości mają być sortowane w kolejności malejącej, z najwyższą wartością najniższą wartość.</span><span class="sxs-lookup"><span data-stu-id="85b05-116">Specifies that the values in the specified property should be sorted in descending order, from highest value to lowest value.</span></span>  
  
 <span data-ttu-id="85b05-117">LIMIT`n`</span><span class="sxs-lookup"><span data-stu-id="85b05-117">LIMIT `n`</span></span>  
 <span data-ttu-id="85b05-118">Tylko pierwszy `n` zostaną wybrane elementy.</span><span class="sxs-lookup"><span data-stu-id="85b05-118">Only the first `n` items will be selected.</span></span>  
  
 <span data-ttu-id="85b05-119">POMIŃ`n`</span><span class="sxs-lookup"><span data-stu-id="85b05-119">SKIP `n`</span></span>  
 <span data-ttu-id="85b05-120">Pomija pierwszy `n` elementów.</span><span class="sxs-lookup"><span data-stu-id="85b05-120">Skips the first `n` items.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85b05-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="85b05-121">Remarks</span></span>  
 <span data-ttu-id="85b05-122">W klauzuli ORDER BY logicznie jest stosowany do wyniku klauzuli SELECT.</span><span class="sxs-lookup"><span data-stu-id="85b05-122">The ORDER BY clause is logically applied to the result of the SELECT clause.</span></span> <span data-ttu-id="85b05-123">W klauzuli ORDER BY może odwoływać się elementy na liście wyboru przy użyciu ich aliasów.</span><span class="sxs-lookup"><span data-stu-id="85b05-123">The ORDER BY clause can reference items in the select list by using their aliases.</span></span> <span data-ttu-id="85b05-124">W klauzuli ORDER BY, można także odwoływać inne zmienne, które są obecnie w zakresie.</span><span class="sxs-lookup"><span data-stu-id="85b05-124">The ORDER BY clause can also reference other variables that are currently in-scope.</span></span> <span data-ttu-id="85b05-125">Jednak jeśli określono w klauzuli SELECT DISTINCT modyfikatorem klauzuli ORDER BY może odwoływać się tylko aliasy w klauzuli SELECT.</span><span class="sxs-lookup"><span data-stu-id="85b05-125">However, if the SELECT clause has been specified with a DISTINCT modifier, the ORDER BY clause can only reference aliases from the SELECT clause.</span></span>  
  
 `SELECT c AS c1 FROM cs AS c ORDER BY c1.e1, c.e2`  
  
 <span data-ttu-id="85b05-126">Każde wyrażenie w klauzuli ORDER BY musi zwrócić pewien typ, który można porównywać pod kątem nierówności uporządkowanych, (mniejsze lub większe niż i tak dalej).</span><span class="sxs-lookup"><span data-stu-id="85b05-126">Each expression in the ORDER BY clause must evaluate to some type that can be compared for ordered inequality (less than or greater than, and so on).</span></span> <span data-ttu-id="85b05-127">Te typy są zazwyczaj skalarne w nim elementów podstawowych, takich jak liczby, ciągi i daty.</span><span class="sxs-lookup"><span data-stu-id="85b05-127">These types are generally scalar primitives such as numbers, strings, and dates.</span></span> <span data-ttu-id="85b05-128">RowTypes typy można porównywać są również umożliwia porównywanie kolejności.</span><span class="sxs-lookup"><span data-stu-id="85b05-128">RowTypes of comparable types are also order comparable.</span></span>  
  
 <span data-ttu-id="85b05-129">Jeśli kod przechodzi przez uporządkowany zestaw, innych niż dla projekcji najwyższego poziomu, dane wyjściowe nie jest gwarantowana mają ich kolejność zachowane.</span><span class="sxs-lookup"><span data-stu-id="85b05-129">If your code iterates over an ordered set, other than for a top-level projection, the output is not guaranteed to have its order preserved.</span></span>  
  
```  
-- In the following sample, order is guaranteed to be preserved:  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
 <span data-ttu-id="85b05-130">Aby mieć uporządkowanej UNION, UNION ALL, EXCEPT lub INTERSECT operację, należy użyć następującego wzorca:</span><span class="sxs-lookup"><span data-stu-id="85b05-130">To have an ordered UNION, UNION ALL, EXCEPT, or INTERSECT operation, use the following pattern:</span></span>  
  
```  
SELECT ...  
FROM ( UNION/EXCEPT/INTERSECT operation )  
ORDER BY ...  
```  
  
## <a name="restricted-keywords"></a><span data-ttu-id="85b05-131">Ograniczone słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="85b05-131">Restricted keywords</span></span>  
 <span data-ttu-id="85b05-132">Poniższe słowa kluczowe muszą być ujęte w cudzysłów, gdy są używane w `ORDER BY` klauzuli:</span><span class="sxs-lookup"><span data-stu-id="85b05-132">The following keywords must be enclosed in quotation marks when used in an `ORDER BY` clause:</span></span>  
  
-   <span data-ttu-id="85b05-133">KRZYŻOWE</span><span class="sxs-lookup"><span data-stu-id="85b05-133">CROSS</span></span>  
  
-   <span data-ttu-id="85b05-134">PEŁNA</span><span class="sxs-lookup"><span data-stu-id="85b05-134">FULL</span></span>  
  
-   <span data-ttu-id="85b05-135">KLUCZ</span><span class="sxs-lookup"><span data-stu-id="85b05-135">KEY</span></span>  
  
-   <span data-ttu-id="85b05-136">PO LEWEJ</span><span class="sxs-lookup"><span data-stu-id="85b05-136">LEFT</span></span>  
  
-   <span data-ttu-id="85b05-137">KOLEJNOŚĆ</span><span class="sxs-lookup"><span data-stu-id="85b05-137">ORDER</span></span>  
  
-   <span data-ttu-id="85b05-138">ZEWNĘTRZNE</span><span class="sxs-lookup"><span data-stu-id="85b05-138">OUTER</span></span>  
  
-   <span data-ttu-id="85b05-139">PRAWO</span><span class="sxs-lookup"><span data-stu-id="85b05-139">RIGHT</span></span>  
  
-   <span data-ttu-id="85b05-140">WIERSZ</span><span class="sxs-lookup"><span data-stu-id="85b05-140">ROW</span></span>  
  
-   <span data-ttu-id="85b05-141">WARTOŚĆ</span><span class="sxs-lookup"><span data-stu-id="85b05-141">VALUE</span></span>  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="85b05-142">Porządkowanie zapytania zagnieżdżone</span><span class="sxs-lookup"><span data-stu-id="85b05-142">Ordering Nested Queries</span></span>  
 <span data-ttu-id="85b05-143">W ramach jednostki zagnieżdżone wyrażenia mogą umieszczać w dowolnym miejscu kwerendy; kolejność zapytanie zagnieżdżone nie są zachowywane.</span><span class="sxs-lookup"><span data-stu-id="85b05-143">In the Entity Framework, a nested expression can be placed anywhere in the query; the order of a nested query is not preserved.</span></span>  
  
```  
-- The following query will order the results by the last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="example"></a><span data-ttu-id="85b05-144">Przykład</span><span class="sxs-lookup"><span data-stu-id="85b05-144">Example</span></span>  
 <span data-ttu-id="85b05-145">Następujące [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zapytanie używa operatora ORDER BY, aby określić kolejność sortowania użyć obiektów zwracanych w instrukcji SELECT.</span><span class="sxs-lookup"><span data-stu-id="85b05-145">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ORDER BY operator to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="85b05-146">Kwerenda jest oparta na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="85b05-146">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="85b05-147">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="85b05-147">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="85b05-148">Postępuj zgodnie z procedurą w [porady: wykonywanie zapytań tego zwraca wyniki StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="85b05-148">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="85b05-149">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="85b05-149">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ORDERBY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#orderby)]  
  
## <a name="see-also"></a><span data-ttu-id="85b05-150">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="85b05-150">See Also</span></span>  
 [<span data-ttu-id="85b05-151">Wyrażenia zapytań</span><span class="sxs-lookup"><span data-stu-id="85b05-151">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
 [<span data-ttu-id="85b05-152">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="85b05-152">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="85b05-153">POMIŃ</span><span class="sxs-lookup"><span data-stu-id="85b05-153">SKIP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
 [<span data-ttu-id="85b05-154">LIMIT</span><span class="sxs-lookup"><span data-stu-id="85b05-154">LIMIT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
 [<span data-ttu-id="85b05-155">DO GÓRY</span><span class="sxs-lookup"><span data-stu-id="85b05-155">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)