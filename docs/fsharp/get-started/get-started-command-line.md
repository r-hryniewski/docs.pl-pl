---
title: 'Wprowadzenie do F # za pomocą narzędzia wiersza polecenia'
description: 'Dowiedz się, jak tworzenie prostego rozwiązania wielu projektów F # za pomocą interfejsu wiersza polecenia platformy .NET Core w dowolnym systemie operacyjnym (Windows, macOs lub Linux).'
ms.date: 03/26/2018
ms.openlocfilehash: 8a82970f33c8bbe1b8cdd8fb6499b59b16d3cbf3
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2018
ms.locfileid: "45673912"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Wprowadzenie do F # za pomocą interfejsu wiersza polecenia platformy .NET Core

W tym artykule opisano, jak możesz rozpocząć pracę z F # w dowolnym systemie operacyjnym (Windows, macOS lub Linux) przy użyciu interfejsu wiersza polecenia platformy .NET Core. Przechodzi on przez tworzenie rozwiązania wielu projektów za pomocą biblioteki klas, który jest wywoływany przez aplikację konsolową w języku.

## <a name="prerequisites"></a>Wymagania wstępne

Aby rozpocząć, należy zainstalować najnowsze [zestawu .NET Core SDK](https://www.microsoft.com/net/download/).

W tym artykule trzeba wiedzieć, jak za pomocą wiersza polecenia i tekst preferowanego edytora. Jeśli już nie używasz go, [programu Visual Studio Code](get-started-vscode.md) jest świetnym rozwiązaniem jako edytora tekstu w języku F #.

## <a name="build-a-simple-multi-project-solution"></a>Tworzenie prostego rozwiązania wielu projektów

Otwórz wiersz polecenia/terminal i użyj [dotnet nowe](../../core/tools/dotnet-new.md) polecenie, aby utworzyć nowy plik rozwiązania o nazwie `FSNetCore`:

```console
dotnet new sln -o FSNetCore
```

Następującą strukturę katalogów jest generowany po uruchomieniu w poprzednim poleceniu:

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Zapis biblioteki klas

Zmień katalog na *FSNetCore*.

Użyj `dotnet new` polecenia, Utwórz projekt biblioteki klas w **src** folder o nazwie biblioteki.

```console
dotnet new classlib -lang F# -o src/Library
```

Następującą strukturę katalogów jest generowany po uruchomieniu w poprzednim poleceniu:

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Zastąp zawartość `Library.fs` następującym kodem:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

Dodaj pakiet Newtonsoft.Json NuGet do projektu biblioteki.

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Dodaj `Library` projekt `FSNetCore` rozwiązanie przy użyciu [Dodaj dotnet sln](../../core/tools/dotnet-sln.md) polecenia:

```console
dotnet sln add src/Library/Library.fsproj
```

Uruchom `dotnet build` do skompilowania projektu. Nierozwiązane zależności zostaną przywrócone, podczas kompilowania.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Napisz aplikację konsolową, która używa biblioteki klas

Użyj `dotnet new` polecenia, Utwórz aplikację konsolową w **src** folder o nazwie aplikacji.

```console
dotnet new console -lang F# -o src/App
```

Następującą strukturę katalogów jest generowany po uruchomieniu w poprzednim poleceniu:

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        ├── App
        │   ├── App.fsproj
        │   ├── Program.fs
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Zastąp zawartość `Program.fs` pliku następującym kodem:

```fsharp
open System
open Library

[<EntryPoint>]
let main argv =
    printfn "Nice command-line arguments! Here's what JSON.NET has to say about them:"

    argv
    |> Array.map getJsonNetJson
    |> Array.iter (printfn "%s")

    0 // return an integer exit code
```

Dodaj odwołanie do `Library` projektu za pomocą [dotnet Dodaj odwołanie](../../core/tools/dotnet-add-reference.md).

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Dodaj `App` projekt `FSNetCore` rozwiązanie przy użyciu `dotnet sln add` polecenia:

```console
dotnet sln add src/App/App.fsproj
```

Przywracanie zależności NuGet `dotnet restore` ([patrz Uwaga](#dotnet-restore-note)) i uruchom `dotnet build` do skompilowania projektu.

Zmień katalog na `src/App` konsoli projekt i uruchomić projekt, przekazując `Hello World` jako argumenty:

```console
cd src/App
dotnet run Hello World
```

Powinny zostać wyświetlone następujące wyniki:

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>Następne kroki

Następnie zapoznaj się z [samouczek programu F #](../tour.md) Aby dowiedzieć się więcej na temat różnych funkcji języka F #.
