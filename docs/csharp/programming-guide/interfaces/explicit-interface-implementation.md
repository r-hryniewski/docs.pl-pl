---
title: Implementacja interfejsu jawnego (Przewodnik programowania w języku C#)
ms.date: 07/20/2015
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: 4296591875d9843d44a81adfd5937532bcd7fe94
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085822"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a>Implementacja interfejsu jawnego (Przewodnik programowania w języku C#)
Jeśli [klasy](../../../csharp/language-reference/keywords/class.md) implementuje dwa interfejsy, które zawierają element członkowski o tym samym podpisie, a następnie wykonywania tego elementu członkowskiego w klasie spowoduje, że oba interfejsy do użycia tego elementu członkowskiego jako ich implementacji. W poniższym przykładzie, wszystkie wywołania do `Paint` wywołania tej samej metody.  
  
 [!code-csharp[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]  
  
 Jeśli dwa [interfejsu](../../../csharp/language-reference/keywords/interface.md) elementy członkowskie nie wykonuj tę samą funkcję, jednak może to spowodować niepoprawne implementację jeden lub oba interfejsy. Można jawnie implementować składowej interfejsu — tworzenie składowej klasy, która jest wywoływana tylko za pośrednictwem interfejsu i specyficzne dla tego interfejsu. Jest to realizowane za pomocą nazw składowej klasy o nazwie interfejsu i kropką. Na przykład:  
  
 [!code-csharp[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]  
  
 Składowa klasy `IControl.Paint` jest dostępna tylko `IControl` interfejsu, a `ISurface.Paint` jest dostępna tylko `ISurface`. Zarówno implementacje metod są niezależne i nie będzie dostępny bezpośrednio w klasie. Na przykład:  
  
 [!code-csharp[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]  
  
 Jawna implementacja jest również używany do rozpoznawania przypadki, w której dwa interfejsy zadeklarować inne elementy członkowskie o takiej samej nazwie, takie jak właściwości i metody:  
  
 [!code-csharp[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]  
  
 Aby zaimplementować obu interfejsów, klasa ma używać jawnych implementacji P właściwości lub metody P i / lub, aby uniknąć błąd kompilatora. Na przykład:  
  
 [!code-csharp[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]  
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)  
- [Klasy i struktury](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [Interfejsy](../../../csharp/programming-guide/interfaces/index.md)  
- [Dziedziczenie](../../../csharp/programming-guide/classes-and-structs/inheritance.md)
