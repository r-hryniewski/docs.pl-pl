---
title: Punkt wejścia (F#)
description: 'Dowiedz się, jak ustawić punkt wejścia do programu F #, który jest kompilowany jako plik wykonywalny, gdzie formalnie się rozpoczyna wykonywanie.'
ms.date: 05/16/2016
ms.openlocfilehash: 298500931d49c891a7a243295333df3a9f5d413e
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2018
ms.locfileid: "45698396"
---
# <a name="entry-point"></a>Punkt wejścia

W tym temacie opisano metody, która umożliwia ustawianie punktu wejścia do programu F #.

## <a name="syntax"></a>Składnia

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a>Uwagi

W poprzedniej składni *umożliwiają funkcji wiązania* definicję funkcji w `let` powiązania.

Punkt wejścia do programu, który jest kompilowany jako plik wykonywalny jest, gdzie formalnie się rozpoczyna wykonywanie. Określ punkt wejścia do aplikacji F #, stosując `EntryPoint` atrybutu programu `main` funkcji. Tej funkcji (utworzone za pomocą `let` powiązania) musi być ostatniej funkcji ostatniego pliku skompilowany. Ostatnie skompilowanego pliku jest ostatni plik w projekcie lub ostatni plik, który jest przekazywany do wiersza polecenia.

Funkcja punktu wejścia ma typ `string array -> int`. Argumenty dostarczone w wierszu polecenia są przekazywane do `main` funkcji w tablicy ciągów. Pierwszy element tablicy jest pierwszym argumentem; Nazwa pliku wykonywalnego nie znajduje się w tablicy, w przeciwieństwie do innych języków. Wartość zwracana jest używany jako kod zakończenia procesu. Wartość zero wskazuje zwykle sukcesu; niezerowe wartości wskazywać na błąd. Istnieje nie Konwencji szczególne znaczenie wartość różną od zera kody powrotne; znaczenie kody powrotne są specyficzne dla aplikacji.

W poniższym przykładzie pokazano prosty `main` funkcji.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

Kiedy ten kod jest wykonywany przy użyciu wiersza polecenia `EntryPoint.exe 1 2 3`, dane wyjściowe wyglądają następująco.

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a>Niejawne punktu wejścia

Jeśli nie ma programu **punktu wejścia** atrybutu, która wyraźnie wskazuje punkt wejścia, powiązania najwyższego poziomu ostatniego pliku do skompilowania służą jako punkt wejścia.

## <a name="see-also"></a>Zobacz także

- [Funkcje](index.md)
- [Powiązania „let”](let-bindings.md)
