---
title: 'Opcje wartości (F #)'
description: 'Więcej informacji na temat typu wartości opcja F #, który jest wersja struktury typu opcji.'
ms.date: 06/16/2018
ms.openlocfilehash: 978bd1713c16f7c050ccb097cb134973d10ef6f5
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185839"
---
# <a name="value-options"></a>Opcje wartości

Typ wartości opcji w F # jest używany podczas przechowywania następujących dwóch przypadkach:

1. Scenariusz jest odpowiedni dla [opcja F #](options.md).
2. Za pomocą struktury zapewnia korzyści wydajności, w tym scenariuszu.

Nie wszystkie scenariusze wrażliwego na wydajność to "rozwiązane" przy użyciu struktury. Należy wziąć pod uwagę dodatkowych kosztów kopiowania podczas korzystania z nich zamiast typów odwołań. Jednak duże F # programy często tworzy wiele opcjonalne typy, które będą działać przy użyciu ścieżek krytycznych, ponieważ struktury czasami może przynieść lepiej ogólną wydajność przez cały okres istnienia programu.

## <a name="definition"></a>Definicja

Wartość opcji jest zdefiniowany jako [sumy Unii](discriminated-unions.md#struct-discriminated-unions) jest podobna do opcji typu odwołania. W ten sposób można traktować ich definicji:

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

Wartość opcji jest zgodny ze strukturalnego równości i porównania. Główną różnicą jest to, że skompilowanych nazwa, nazwa typu i wielkości liter nazwy wskazać, że jest typem wartości.

## <a name="using-value-options"></a>Za pomocą opcji wartość

Podobnie jak używane są opcje wartość [opcje](options.md). `ValueSome` Służy do wskazywania, czy wartość jest obecna, a `ValueNone` jest używany, gdy nie jest wartością:

```fsharp
let tryParseDateTime (s: string) =
    match System.DateTime.TryParse(s) with
    | (true, dt) -> ValueSome dt
    | (false, _) -> ValueNone

let possibleDateString1 = "1990-12-25"
let possibleDateString2 = "This is not a date"

let result1 = tryParseDateTime possibleDateString1
let result2 = tryParseDateTime possibleDateString2

match (result1, result2) with
| ValueSome d1, ValueSome d2 -> printfn "Both are dates!"
| ValueSome d1, ValueNone -> printfn "Only the first is a date!"
| ValueNone, ValueSome d2 -> printfn "Only the second is a date!"
| ValueNone, ValueNone -> printfn "None of them are dates!"
```

Podobnie jak w przypadku [opcje](options.md), Konwencja nazewnictwa dla funkcji, która zwraca `ValueOption` jest poprzedzić go `try`.

## <a name="value-option-properties-and-methods"></a>Wartość opcji właściwości i metody

W tej chwili jest jedną właściwość dla opcji wartości: `Value`. <xref:System.InvalidOperationException> Jest wywoływane, jeśli wartość nie jest obecna, gdy ta właściwość zostanie wywołana.

## <a name="value-option-functions"></a>Wartość opcji funkcji

Obecnie jest jedną funkcję powiązane z modułu dla opcji wartości `defaultValueArg`:

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T 
```

Podobnie jak w przypadku `defaultArg` funkcji `defaultValueArg` zwraca podstawową wartość danej opcji wartość, jeśli istnieje; w przeciwnym razie zwraca określoną wartość domyślną.

W tej chwili nie istnieją żadnych funkcji powiązanych z modułu dla opcji wartości.

## <a name="see-also"></a>Zobacz także

- [Opcje](options.md)
