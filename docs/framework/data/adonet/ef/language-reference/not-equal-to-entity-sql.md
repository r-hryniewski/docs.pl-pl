---
title: '! = (Nie jest równa) (jednostka SQL)'
ms.date: 03/30/2017
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
ms.openlocfilehash: 4ed09b0c5f10ef1ac77c4b374619508d714f1dc3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2018
ms.locfileid: "32763699"
---
# <a name="-not-equal-to-entity-sql"></a>! = (Nie jest równa) (jednostka SQL)
Porównuje dwa wyrażenia, aby określić, czy po lewej stronie wyrażenia nie jest równa prawe wyrażenie. ! = (Nie) operator równe jest funkcjonalnym odpowiednikiem < > — operator.  
  
## <a name="syntax"></a>Składnia  
  
```  
expression != expression  
or  
expression <> expression  
```  
  
## <a name="arguments"></a>Argumenty  
 `expression`  
 Dowolne prawidłowe wyrażenie. Oba wyrażenia musi mieć typów danych umożliwiają niejawnej konwersji.  
  
## <a name="result-types"></a>Typy wyników  
 `true` Jeśli po lewej stronie wyrażenia nie jest równa prawe wyrażenie; w przeciwnym razie `false`.  
  
## <a name="example"></a>Przykład  
 Następujące zapytanie SQL jednostki używa! = — operator do porównania dwóch wyrażeń w celu ustalenia, czy po lewej stronie wyrażenia nie jest równa prawe wyrażenie. Kwerenda jest oparta na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1.  Postępuj zgodnie z procedurą w [porady: wykonywanie zapytań tego zwraca wyniki StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not_equals)]  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do jednostki SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
