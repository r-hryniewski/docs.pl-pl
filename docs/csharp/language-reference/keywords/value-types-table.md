---
title: Tabela typów wartości (odwołanie w C#)
ms.date: 08/24/2018
helpviewer_keywords:
- value types [C#], table
- types [C#], value types
- types [C#], suffixes
ms.assetid: 67d8f631-b6e3-4d83-9910-5ec497f8c5f3
ms.openlocfilehash: aa37e2237ca0cffe7ff2e64aa53739b6ffafd24a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50182753"
---
# <a name="value-types-table-c-reference"></a>Tabela typów wartości (odwołanie w C#)

W poniższej tabeli przedstawiono typy wartości języka C#.  
  
|Typ wartości|Kategoria|Sufiksem typu|  
|----------------|--------------|-----------------|  
|[bool](bool.md)|Boolean||  
|[byte](byte.md)|Nieoznaczona, numeryczne, [typu całkowitego](integral-types-table.md)||  
|[char](char.md)|Nieoznaczona, numeryczne, [typu całkowitego](integral-types-table.md)||  
|[decimal](decimal.md)|Numeryczne, [zmiennoprzecinkowych](floating-point-types-table.md)|M lub m|  
|[double](double.md)|Numeryczne, [zmiennoprzecinkowych](floating-point-types-table.md)|D lub d|  
|[enum](enum.md)|Wyliczenie||  
|[float](float.md)|Numeryczne, [zmiennoprzecinkowych](floating-point-types-table.md)|F lub f|  
|[int](int.md)|Podpisany, numeryczne, [typu całkowitego](integral-types-table.md)||  
|[long](long.md)|Podpisany, numeryczne, [typu całkowitego](integral-types-table.md)|L lub l|  
|[sbyte](sbyte.md)|Podpisany, numeryczne, [typu całkowitego](integral-types-table.md)||  
|[short](short.md)|Podpisany, numeryczne, [typu całkowitego](integral-types-table.md)||  
|[struct](struct.md)|Struktura zdefiniowanych przez użytkownika||  
|[uint](uint.md)|Nieoznaczona, numeryczne, [typu całkowitego](integral-types-table.md)|U lub u|  
|[ulong](ulong.md)|Nieoznaczona, numeryczne, [typu całkowitego](integral-types-table.md)|UL, Ul, uL, ul, LU, Lu, lU lub lu|  
|[ushort](ushort.md)|Nieoznaczona, numeryczne, [typu całkowitego](integral-types-table.md)||  

## <a name="remarks"></a>Uwagi

Sufiksem typu umożliwia określenie typu literał wartości liczbowych. Na przykład:

```csharp
decimal a = 0.1M;
```

Jeśli [literał numeryczny liczby całkowitej](~/_csharplang/spec/lexical-structure.md#integer-literals) nie sufiks ma pierwszy następujące typy, w których jej wartość może być reprezentowana: `int`, `uint`, `long`, `ulong`.

Jeśli [literał liczby rzeczywistej wartości liczbowych](~/_csharplang/spec/lexical-structure.md#real-literals) nie sufiks jest typu `double`.

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Tabele odwołań dla typów](reference-tables-for-types.md)
- [Tabela wartości domyślnych](default-values-table.md)
- [Typy wartości](value-types.md)
- [Formatowanie tabeli wyników liczbowych](formatting-numeric-results-table.md)
