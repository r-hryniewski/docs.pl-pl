---
title: Testowanie jednostek kodu języka Visual Basic w .NET Core za pomocą polecenia dotnet test i NUnit
description: Pojęcia dotyczące jednostek testów platformie .NET Core za pomocą środowisko interaktywne tworzenie rozwiązania języka Visual Basic przykładowe instrukcje krok po kroku przy użyciu narzędzia NUnit.
author: rprouse
ms.date: 10/04/2018
dev_langs:
- vb
ms.openlocfilehash: bed43ac6b6f918b1ee45715101f9142c1add777f
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836929"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-nunit"></a>Biblioteki języka Visual Basic .NET Core za pomocą polecenia dotnet test i NUnit testy jednostkowe

Ten samouczek przeprowadzi Cię przez środowisko interaktywne tworzenie przykładowe rozwiązanie krok po kroku, aby dowiedzieć się więcej pojęcia testów jednostkowych. Jeśli chcesz wykonać kroki samouczka przy użyciu wstępnie utworzone rozwiązania [wyświetlić lub pobrać przykładowy kod](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-nunit/) przed przystąpieniem do wykonywania. Aby uzyskać instrukcje pobierania, zobacz [przykłady i samouczki](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="prerequisites"></a>Wymagania wstępne 
- [.NET core SDK 2.1 (v. 2.1.400)](https://www.microsoft.com/net/download) lub nowszy. 
- Edytor tekstu lub ulubionego edytora kodu.

## <a name="creating-the-source-project"></a>Tworzenie projektu źródłowego

Otwieranie okna powłoki. Utwórz katalog o nazwie *jednostki — testowanie-języka vb — nunit* do przechowywania rozwiązania. Wewnątrz tego nowy katalog uruchom następujące polecenie, aby utworzyć nowy plik rozwiązania dla biblioteki klas i projektu testowego:

```console
dotnet new sln
```

Następnie należy utworzyć *PrimeService* katalogu. Następujące konspektu pokazuje struktury plików do tej pory:

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
```

Wprowadź *PrimeService* bieżącego katalogu i uruchom następujące polecenie, aby utworzyć projekt źródłowy:

```console
dotnet new classlib -lang VB
```

Zmień nazwę *Class1.VB* do *PrimeService.VB*. Aby użyć Programowanie oparte na testach (TDD), należy utworzyć z implementacją niepowodzenie `PrimeService` klasy:

```vb
Imports System

Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

Zmień katalog kopii do *jednostki — testowanie-języka vb — przy użyciu stest* katalogu. Uruchom następujące polecenie, aby dodać projekt biblioteki klas do rozwiązania:

```console
dotnet sln add .\PrimeService\PrimeService.vbproj
```

## <a name="creating-the-test-project"></a>Tworzenie projektu testu

Następnie należy utworzyć *PrimeService.Tests* katalogu. Następujące konspektu przedstawia strukturę katalogów:

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

Wprowadź *PrimeService.Tests* katalogu bieżącego katalogu i Utwórz nowy projekt, używając następującego polecenia:

```console
dotnet new nunit -lang VB
```

[Dotnet nowe](../tools/dotnet-new.md) polecenie tworzy projekt testowy, który używa NUnit jako biblioteka testów. Wygenerowany szablon konfiguruje narzędzie test runner w *PrimeServiceTests.vbproj* pliku:

[!code-xml[Packages](~/samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj#Packages)]

Projekt testowy wymaga innych pakietów, aby utworzyć i uruchomić testy jednostkowe. `dotnet new` w poprzednim kroku należy dodać kartę testu NUnit i NUnit. Teraz Dodaj `PrimeService` biblioteki klas jako inny zależności do projektu. Użyj [ `dotnet add reference` ](../tools/dotnet-add-reference.md) polecenia:

```console
dotnet add reference ../PrimeService/PrimeService.vbproj
```

Widać cały plik w [repozytorium przykładów](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) w witrynie GitHub.

Masz następujące układ ostateczne rozwiązanie:

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeService.Tests.vbproj
```

Wykonaj następujące polecenie w *jednostki — testowanie-języka vb — nunit* katalogu:

```console
dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj
```

## <a name="creating-the-first-test"></a>Tworzenie pierwszego testu

Podejścia TDD wymaga zapisywania niepowodzenie jednego testu, dzięki czemu przekazać, a następnie powtórzyć ten proces. W *PrimeService.Tests* katalogu, zmiana nazwy *UnitTest1.vb* plik *PrimeService_IsPrimeShould.VB* i zastąp jego całą zawartość następującym kodem:

```vb
Imports NUnit.Framework

Namespace PrimeService.Tests
    <TestFixture>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Test>
        Sub ReturnFalseGivenValueOf1()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

`<TestFixture>` Atrybut wskazuje klasę, która zawiera testy. `<Test>` Atrybut oznacza metodę, która jest uruchamiany przez narzędzie test runner. Z *jednostki — testowanie-języka vb — nunit*, wykonaj [ `dotnet test` ](../tools/dotnet-test.md) do kompilacji, testów i biblioteki klas, a następnie uruchom testy. Moduł uruchamiający NUnit zawiera punkt wejścia programu, aby uruchomić testy. `dotnet test` Uruchamia narzędzie test runner, za pomocą projektu testu jednostkowego, który został utworzony.

Test nie powiedzie się. Nie utworzono jeszcze wdrożenia. Należy ten test przez napisanie kodu najprostsza `PrimeService` klasę, która działa:

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first")
End Function
```

W *jednostki — testowanie-języka vb — nunit* katalogu, uruchom `dotnet test` ponownie. `dotnet test` Polecenie uruchamia kompilację dla `PrimeService` projektu i następnie `PrimeService.Tests` projektu. Po utworzeniu obu projektów, działa ten jeden test. Przekazuje on.

## <a name="adding-more-features"></a>Dodawanie większej liczby funkcji

Teraz, gdy wprowadzono jeden przebieg testu, nadszedł czas na zapis więcej. Istnieje kilka innych przypadkach proste dla liczb pierwszych: 0, -1. Możesz dodać te przypadki jako nowe testy za pomocą `<Test>` atrybut, ale który szybko staje się uciążliwe. Istnieją inne atrybuty xUnit, które umożliwiają pisanie zestaw testów podobne.  A `<TestCase>` atrybut reprezentuje zestaw testów, które wykonania tego samego kodu, ale mają różne argumenty wejściowe. Możesz użyć `<TestCase>` atrybutu, aby określić wartości dla tych danych wejściowych.

Zamiast tworzyć nowe testy, mają zastosowanie do utworzenia szereg testów testujące kilka wartości mniejszej niż dwa, czyli najniższy numer pierwsze dwa atrybuty:

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

Uruchom `dotnet test`, i dwa pola spośród wymienionych testów kończyć się niepowodzeniem. Aby wszystkie przebieg testów, należy zmienić `if` klauzuli na początku `Main` method in Class metoda *PrimeServices.cs* pliku:

```vb
if candidate < 2
```

Przejdź do iteracji, dodając więcej testów, więcej teorii i więcej kodu w bibliotece głównej. Masz [ukończoną wersję testy](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) i [pełną implementację biblioteki](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).

Gdy masz utworzoną małych biblioteki i zestaw testów jednostkowych dla tej biblioteki. Tak, aby dodawania nowych pakietów została ze strukturą rozwiązania i testów jest częścią normalnego przepływu pracy. Po skoncentrowany większość czasu i wysiłku niewiele rozwiązywania cele aplikacji.
