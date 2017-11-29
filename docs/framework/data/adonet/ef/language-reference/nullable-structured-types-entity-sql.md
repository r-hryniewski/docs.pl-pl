---
title: "Typy dopuszczające wartości zerowe strukturalne (jednostki SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ac7405aea459d51154ac25171bc76d637a94bf81
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="nullable-structured-types-entity-sql"></a><span data-ttu-id="aedef-102">Typy dopuszczające wartości zerowe strukturalne (jednostki SQL)</span><span class="sxs-lookup"><span data-stu-id="aedef-102">Nullable Structured Types (Entity SQL)</span></span>
<span data-ttu-id="aedef-103">A `null` wystąpienia typu strukturalnego to wystąpienie nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="aedef-103">A `null` instance of a structured type is an instance that does not exist.</span></span> <span data-ttu-id="aedef-104">To różni się od istniejącego wystąpienia, w którym ma wszystkie właściwości `null` wartości.</span><span class="sxs-lookup"><span data-stu-id="aedef-104">This is different from an existing instance in which all properties have `null` values.</span></span>  
  
 <span data-ttu-id="aedef-105">W tym temacie opisano typy dopuszczające wartości zerowe strukturalnych, w tym typy, które dopuszczają wartości null i które kodu wzorce produktu `null` wystąpień strukturalnych typy dopuszczające wartości zerowe.</span><span class="sxs-lookup"><span data-stu-id="aedef-105">This topic describes the nullable structured types, including which types are nullable and which code patterns produce `null` instances of structured nullable types.</span></span>  
  
## <a name="kinds-of-nullable-structured-types"></a><span data-ttu-id="aedef-106">Typy strukturalne typy dopuszczające wartości zerowe</span><span class="sxs-lookup"><span data-stu-id="aedef-106">Kinds of Nullable Structured Types</span></span>  
 <span data-ttu-id="aedef-107">Istnieją trzy rodzaje typy dopuszczające wartości zerowe struktury:</span><span class="sxs-lookup"><span data-stu-id="aedef-107">There are three kinds of nullable structure types:</span></span>  
  
-   <span data-ttu-id="aedef-108">Typy wierszy.</span><span class="sxs-lookup"><span data-stu-id="aedef-108">Row types.</span></span>  
  
-   <span data-ttu-id="aedef-109">Typy złożone.</span><span class="sxs-lookup"><span data-stu-id="aedef-109">Complex types.</span></span>  
  
-   <span data-ttu-id="aedef-110">Typy jednostek.</span><span class="sxs-lookup"><span data-stu-id="aedef-110">Entity types.</span></span>  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a><span data-ttu-id="aedef-111">Wzorce kodu, które powodują powstanie Null wystąpień typów strukturalnych</span><span class="sxs-lookup"><span data-stu-id="aedef-111">Code Patterns that Produce Null Instances of Structured Types</span></span>  
 <span data-ttu-id="aedef-112">Następujące scenariusze tworzenia `null` wystąpień:</span><span class="sxs-lookup"><span data-stu-id="aedef-112">The following scenarios produce `null` instances:</span></span>  
  
-   <span data-ttu-id="aedef-113">Kształtowania `null` jako typ strukturalny:</span><span class="sxs-lookup"><span data-stu-id="aedef-113">Shaping `null` as a structured type:</span></span>  
  
    ```  
    TREAT (NULL AS StructuredType)  
    ```  
  
-   <span data-ttu-id="aedef-114">Rzutowanie w górę do typem pochodnym typu podstawowego:</span><span class="sxs-lookup"><span data-stu-id="aedef-114">Upcasting of a base type to a derived type:</span></span>  
  
    ```  
    TREAT (BaseType AS DerivedType)  
    ```  
  
-   <span data-ttu-id="aedef-115">Sprzężenie zewnętrzne na fałszywego warunku:</span><span class="sxs-lookup"><span data-stu-id="aedef-115">Outer join on false condition:</span></span>  
  
    ```  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="aedef-116">--lub</span><span class="sxs-lookup"><span data-stu-id="aedef-116">--or</span></span>  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="aedef-117">--lub</span><span class="sxs-lookup"><span data-stu-id="aedef-117">--or</span></span>  
  
    ```  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
-   <span data-ttu-id="aedef-118">Dereferencji `null` odwołania:</span><span class="sxs-lookup"><span data-stu-id="aedef-118">Dereferencing a `null` reference:</span></span>  
  
    ```  
    DEREF(NullRef)  
    ```  
  
-   <span data-ttu-id="aedef-119">Uzyskiwanie ANYELEMENT z pustej kolekcji:</span><span class="sxs-lookup"><span data-stu-id="aedef-119">Obtaining ANYELEMENT from an empty collection:</span></span>  
  
    ```  
    ANYELEMENT(EmptyCollection)  
    ```  
  
-   <span data-ttu-id="aedef-120">Sprawdzanie `null` wystąpień typów strukturalnych:</span><span class="sxs-lookup"><span data-stu-id="aedef-120">Checking for `null` instances of structured types:</span></span>  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine("[NULL]");  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="aedef-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="aedef-121">See Also</span></span>  
 [<span data-ttu-id="aedef-122">Omówienie SQL jednostki</span><span class="sxs-lookup"><span data-stu-id="aedef-122">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)