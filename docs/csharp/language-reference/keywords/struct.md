---
title: struct (odwołanie w C#)
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 46cf0b66a50685a717818fe762ad4f1de36d6156
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185748"
---
# <a name="struct-c-reference"></a>struct (odwołanie w C#)

A `struct` typ jest typem wartości, które jest zazwyczaj używany do hermetyzacji mniejszym grupom powiązanych zmiennych, takich jak współrzędnych prostokąta lub właściwości elementu w magazynie. Poniższy przykład przedstawia deklarację prostą strukturą:

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a>Uwagi

Struktury mogą także zawierać [konstruktory](../../programming-guide/classes-and-structs/constructors.md), [stałe](../../programming-guide/classes-and-structs/constants.md), [pola](../../programming-guide/classes-and-structs/fields.md), [metody](../../programming-guide/classes-and-structs/methods.md), [właściwości](../../programming-guide/classes-and-structs/properties.md), [indeksatory](../../programming-guide/indexers/index.md), [operatory](../../programming-guide/statements-expressions-operators/operators.md), [zdarzenia](../../programming-guide/events/index.md), i [zagnieżdżone typy](../../programming-guide/classes-and-structs/nested-types.md), chociaż Jeśli kilka takich elementów członkowskich są wymagane, możesz należy wziąć pod uwagę klasy jako możliwej do typu Twojej zamiast tego.

Aby uzyskać przykłady, zobacz [przy użyciu struktury](../../programming-guide/classes-and-structs/using-structs.md).

Struktury można zaimplementować interfejs, ale nie może dziedziczyć innej struktury. Z tego powodu składowe struktury nie można zadeklarować jako `protected`.

Aby uzyskać więcej informacji, zobacz [struktury](../../programming-guide/classes-and-structs/structs.md).

## <a name="examples"></a>Przykłady

Aby uzyskać więcej informacji, zobacz [przy użyciu struktury](../../programming-guide/classes-and-structs/using-structs.md).

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać przykłady, zobacz [przy użyciu struktury](../../programming-guide/classes-and-structs/using-structs.md).

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [Tabela wartości domyślnych](default-values-table.md)
- [Tabela typów wbudowanych](built-in-types-table.md)
- [Typy](types.md)
- [Typy wartości](value-types.md)
- [class](class.md)
- [interface](interface.md)
- [Klasy i struktury](../../programming-guide/classes-and-structs/index.md)