---
title: Nie można przekonwertować typu anonimowego na drzewo wyrażenia, ponieważ zawiera on pole wykorzystywane w inicjowaniu innego pola
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: 2f97a0de74428ce42a088644580a78bf8fd99945
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936805"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a>Nie można przekonwertować typu anonimowego na drzewo wyrażenia, ponieważ zawiera on pole wykorzystywane w inicjowaniu innego pola
Kompilator nie akceptuje konwersja anonimowego na drzewo wyrażenia, po jednej właściwości typu anonimowego służy do inicjowania innej właściwości typu anonimowego. Na przykład w poniższym kodzie `Prop1` jest zadeklarowanych na liście inicjowania i następnie użyta jako wartość początkową dla `Prop2`.  
  
```vb  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 **Identyfikator błędu:** BC36548  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
-   Przypisz wartość początkową dla `Prop1` do zmiennej lokalnej. Przypisz tej zmiennej na wartość oba `Prop1` i `Prop2`, jak pokazano w poniższym kodzie.  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a>Zobacz także

[Typy anonimowe (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
[Drzewa wyrażeń (Visual Basic)](../../programming-guide/concepts/expression-trees/index.md)  
[Porady: Używanie drzew wyrażeń do kompilowania zapytań dynamicznych (Visual Basic)](../../programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md)  