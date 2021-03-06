---
title: Typy odwołań (odwołanie w C#)
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: f99415fc9a2b728917cdf829ffb9e25823a824dd
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/26/2018
ms.locfileid: "47207438"
---
# <a name="reference-types-c-reference"></a>Typy odwołań (odwołanie w C#)

Istnieją dwa rodzaje typów w języku C#: typy referencyjne i typy wartości. W zmiennych typu referencyjnego są przechowywane odwołania do ich danych (obiekty), a zmienne typu wartości zawierają bezpośrednio swoje dane. W przypadku typów referencyjnych dwie zmienne mogą odwoływać się do jednego obiektu, a więc operacje wykonane na jednej zmiennych mogą mieć wpływ na obiekt, do którego odwołuje się druga zmienna. Z typami wartości każda zmienna ma własną kopię danych i nie jest możliwe dla operacji na jednej zmiennej miały wpływ na inne (z wyjątkiem w przypadku właściwości w ref i out zmiennych parametrów; zobacz [w](in-parameter-modifier.md), [ref](ref.md) i [się](out-parameter-modifier.md) modyfikator parametrów).

 Do deklarowania typów referencyjnych są używane następujące słowa kluczowe:

- [class](class.md)

- [interface](interface.md)

- [delegate](delegate.md)

 W języku C# są także dostępne następujące wbudowane typy referencyjne:

- [dynamic](dynamic.md)

- [object](object.md)

- [string](string.md)

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../../../csharp/language-reference/index.md)
- [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [Typy](types.md)
- [Typy wartości](value-types.md)