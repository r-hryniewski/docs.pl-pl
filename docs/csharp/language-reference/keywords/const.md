---
title: Const — słowo kluczowe (odwołanie w C#)
ms.date: 07/20/2015
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
ms.openlocfilehash: f586b6d097a8592fd74e92df7886b519d623e478
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513387"
---
# <a name="const-c-reference"></a>const (odwołanie w C#)

Możesz użyć `const` — słowo kluczowe, aby zadeklarować pole stałe lub stałą lokalną. Stałe pola i zmienne lokalne są zmienne i nie może być modyfikowany. Stałe może być liczb, wartości logicznych, ciągi lub odwołanie o wartości null. Nie należy tworzyć stałą do reprezentowania informacje, które chcą zmienić w dowolnym momencie. Na przykład nie używaj pole stałe do przechowywania ceny usługi, numer wersji produktu lub nazwa marki firmy. Te wartości mogą ulec zmianie, a ponieważ kompilatory propagację stałych, inny kod skompilowany przy użyciu bibliotek musi być ponownie kompilowane, aby zobaczyć zmiany. Zobacz też [tylko do odczytu](../../../csharp/language-reference/keywords/readonly.md) — słowo kluczowe. Na przykład:

```csharp
const int x = 0;
public const double gravitationalConstant = 6.673e-11;
private const string productName = "Visual C#";
```

## <a name="remarks"></a>Uwagi

Typ deklaracji stałej Określa typ elementów członkowskich, które wprowadza deklaracja. Inicjator stałą lokalne lub pola stałego musi być wyrażeniem stałym, które mogą być niejawnie konwertowane na typ docelowy.

Wyrażenie stałe jest wyrażeniem, które mogą zostać w pełni oszacowane w czasie kompilacji. Dlatego jedyne możliwe wartości dla stałych o typach odwołania to `string` i odwołanie o wartości null.

W deklaracji stałej można zadeklarować kilka stałych, takich jak:

```csharp
public const double x = 1.0, y = 2.0, z = 3.0;
```

`static` Modyfikator nie jest dozwolony w deklaracji stałej.

Stała może brać udział w wyrażeniu stałym, w następujący sposób:

```csharp
public const int c1 = 5;
public const int c2 = c1 + 100;
```

> [!NOTE]
> [Tylko do odczytu](../../../csharp/language-reference/keywords/readonly.md) — słowo kluczowe różni się od `const` — słowo kluczowe. A `const` pola mogą być inicjowane tylko na deklarację pola. A `readonly` pola mogą być inicjowane w deklaracji lub w konstruktorze. W związku z tym `readonly` pola mogą mieć różne wartości w zależności od używanego konstruktora. Ponadto mimo że `const` pole jest stałą czasu kompilacji `readonly` pole może być używane dla stałych run-time, jak w tym wierszu: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`

## <a name="example"></a>Przykład

[!code-csharp[csrefKeywordsModifiers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#5)]

## <a name="example"></a>Przykład

W tym przykładzie przedstawiono sposób użycia stałych jako zmiennych lokalnych.

[!code-csharp[csrefKeywordsModifiers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#6)]

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../../../csharp/language-reference/index.md)  
- [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)  
- [Słowa kluczowe języka C#](../../../csharp/language-reference/keywords/index.md)  
- [Modyfikatory](../../../csharp/language-reference/keywords/modifiers.md)  
- [readonly](../../../csharp/language-reference/keywords/readonly.md)
