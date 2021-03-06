---
title: '&amp;= — Operator (odwołanie w C#)'
ms.date: 07/20/2015
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: f3a6fe20ca89a90b5a64118d73fb39e9a364d1e9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506404"
---
# <a name="amp-operator-c-reference"></a>&amp;= — Operator (odwołanie w C#)
Operator przypisania AND.  
  
## <a name="remarks"></a>Uwagi  
 Wyrażenie używające operatora przypisania `&=`, takie jak  
  
```csharp  
x &= y  
```  
  
 odpowiada wyrażeniu  
  
```csharp  
x = x & y  
```  
  
 z tą różnicą, że `x` jest obliczany tylko raz. [& — Operator](../../../csharp/language-reference/operators/and-operator.md) wykonuje logiczne i operacji na poziomie bitowym operandy typu całkowitego i operator logiczny oraz na `bool` argumentów operacji.  
  
 `&=` Operator nie może zostać przeciążony bezpośrednio, ale typy zdefiniowane przez użytkownika może doprowadzić do przeciążenia pliku binarnego [& — operator](../../../csharp/language-reference/operators/and-operator.md) (zobacz [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Przykład  
 [!code-csharp[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka C#](../../../csharp/language-reference/index.md)  
- [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)  
- [Operatory języka C#](../../../csharp/language-reference/operators/index.md)
