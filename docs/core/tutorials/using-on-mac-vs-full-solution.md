---
title: Tworzenie kompletnego rozwiązania .NET Core w systemie macOS przy użyciu programu Visual Studio dla komputerów Mac
description: Ten temat przeprowadzi Cię przez tworzenie rozwiązania .NET Core, który zawiera biblioteki wielokrotnego użytku i testy jednostkowe.
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.openlocfilehash: fbbbbc20b45981a41695eac73dcc251ef74a0cb6
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50186021"
---
# <a name="building-a-complete-net-core-solution-on-macos-using-visual-studio-for-mac"></a>Tworzenie kompletnego rozwiązania .NET Core w systemie macOS przy użyciu programu Visual Studio dla komputerów Mac

Visual Studio dla komputerów Mac udostępnia w pełni funkcjonalne rozwoju środowiska IDE (Integrated) do tworzenia aplikacji platformy .NET Core. Ten temat przeprowadzi Cię przez tworzenie rozwiązania .NET Core, który zawiera biblioteki wielokrotnego użytku i testy jednostkowe.

Ten samouczek pokazuje, jak utworzyć aplikację, która akceptuje szukanym wyrazem oraz ciąg tekstowy od użytkownika, zlicza ile razy szukanym wyrazem występuje w ciągu za pomocą innej metody w bibliotece klas i zwraca wynik do użytkownika. Rozwiązanie obejmuje również testów jednostkowych dla biblioteki klas jako wprowadzenie do koncepcji testów jednostkowych. Jeśli wolisz postępuj zgodnie z instrukcjami samouczek z pełny przykład, Pobierz [przykładowe rozwiązanie](https://github.com/dotnet/samples/blob/master/core/tutorials/using-on-mac-vs-full-solution/WordCounter). Aby uzyskać instrukcje pobierania, zobacz [przykłady i samouczki](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

> [!NOTE]
> Twoja opinia jest bardzo ważnych. Istnieją dwa sposoby, możesz przekazywać opinie do zespołu programistycznego w programie Visual Studio dla komputerów Mac:
> * W programie Visual Studio dla komputerów Mac, wybierz **pomocy** > **Zgłoś Problem** z menu lub **Zgłoś Problem** na ekranie powitalnym, który powoduje otwarcie okna zgłoszenia Raport o usterce. Swoje opinie możesz śledzić w portalu [Społeczność deweloperów](https://developercommunity.visualstudio.com/spaces/41/index.html).
> * Aby sugestię, wybierz **pomocy** > **sugestię** z menu lub **sugestię** na ekranie powitalnym, która spowoduje przejście do [ Program Visual Studio dla sieci Web społeczności deweloperów Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).

## <a name="prerequisites"></a>Wymagania wstępne

- Biblioteki OpenSSL (jeśli jest uruchomiony program .NET Core 1.1): zobacz [wymagania wstępne dla platformy .NET Core w systemie Mac](../macos-prerequisites.md) tematu.
- [.NET core SDK 1.1 lub nowszej](https://www.microsoft.com/net/core#macos)
- [Visual Studio 2017 dla komputerów Mac](https://visualstudio.microsoft.com/vs/visual-studio-mac/)

Aby uzyskać więcej informacji na temat wymagań wstępnych, zobacz [wymagania wstępne dla platformy .NET Core w systemie Mac](../../core/macos-prerequisites.md). Aby uzyskać pełne wymagania systemowe programu Visual Studio 2017 dla komputerów Mac, zobacz [Visual Studio 2017 for Mac wymagania systemowe programu](/visualstudio/productinfo/vs2017-system-requirements-mac).

## <a name="building-a-library"></a>Tworzenie biblioteki

1. Na ekranie powitalnym wybierz **nowy projekt**. W **nowy projekt** , okno dialogowe **platformy .NET Core** węzeł **Biblioteka .NET Standard** szablonu. Spowoduje to utworzenie biblioteki .NET Standard, który jest przeznaczony dla platformy .NET Core oraz ewentualne innych implementacji .NET, która obsługuje wersję 2.0 [.NET Standard](../../standard/net-standard.md). Wybierz **dalej**.

   ![Okno dialogowe nowego projektu](./media/using-on-mac-vs-full-solution/vsmacfull01.png)

1. Nadaj projektowi nazwę "TextUtils" (krótka nazwa "Narzędzia tekstowe"), jak i rozwiązania "WordCounter". Pozostaw **Utwórz katalog projektu w katalogu rozwiązania** zaznaczone. Wybierz **tworzenie**.

   ![Okno dialogowe nowego projektu](./media/using-on-mac-vs-full-solution/vsmacfull02.png)

1. W **rozwiązania** pasku bocznym, rozwiń węzeł `TextUtils` węzeł, aby wyświetlić plik klasy, dostarczone przez szablon, *Class1.cs*. Kliknij prawym przyciskiem myszy plik, wybierz **Zmień nazwę** z menu kontekstowego i zmień jego nazwę na *WordCount.cs*. Otwórz plik i Zastąp zawartość następującym kodem:

   [!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/TextUtils/WordCount.cs)]

1. Zapisz plik za pomocą jednej z trzech różnych metod: Użyj skrótu klawiaturowego <kbd> &#8984; </kbd> + <kbd>s</kbd>, wybierz opcję **pliku**  >  **Zapisz** z menu lub kliknij prawym przyciskiem myszy na karcie i wybierz plik **Zapisz** z menu kontekstowego. Na poniższej ilustracji przedstawiono okno środowiska IDE:

   ![Okno IDE TextUtils klasy biblioteki, plik klasy WordCount, Klasa statyczna WordCount i metoda GetWordCount](./media/using-on-mac-vs-full-solution/vsmacfull03.png)

1. Wybierz **błędy** na marginesie w dolnej części okna środowiska IDE, aby otworzyć **błędy** panelu. Wybierz **danych wyjściowych kompilacji** przycisku.

   ![Dolny margines IDE przedstawiający przycisk błędy](./media/using-on-mac-vs-full-solution/vsmacfull03b.png)

1. Wybierz **kompilacji** > **kompilacji wszystkich** z menu.

   Rozwiązanie zostanie skompilowane. Panel danych wyjściowych kompilacji pokazuje, że kompilacja zakończyła się powodzeniem.

   ![Tworzenie panelu błędy z komunikatem pomyślnej kompilacji w okienku danych wyjściowych](./media/using-on-mac-vs-full-solution/vsmacfull04.png)

## <a name="creating-a-test-project"></a>Tworzenie projektu testu

Testy jednostek zapewniają oprogramowania automatyczne, testowane podczas tworzenia i publikowania. Struktura testowania, którego używasz w tym samouczku jest [xUnit (wersja 2.2.0 lub nowszej)](https://xunit.github.io/), która jest instalowana automatycznie podczas projekt testu xUnit jest dodawany do rozwiązania, które w poniższych krokach:

1. W **rozwiązania** pasku bocznym, kliknij prawym przyciskiem myszy `WordCounter` rozwiązań i wybierz pozycję **Dodaj** > **Dodaj nowy projekt**.

1. W **nowy projekt** okno dialogowe, wybierz opcję **testy** z **platformy .NET Core** węzła. Wybierz **projekt testu xUnit** następuje **dalej**.

   ![Okno dialogowe nowego projektu tworzenia projekt testu xUnit](./media/using-on-mac-vs-full-solution/vsmacfull05.png)

1. Nazwa nowego projektu "TestLibrary", a następnie wybierz pozycję **Utwórz**.

   ![Okno dialogowe nowego projektu podanie nazwy projektu](./media/using-on-mac-vs-full-solution/vsmacfull06.png)

1. Aby biblioteka testów do pracy z `WordCount` klasy, Dodaj odwołanie do `TextUtils` projektu. W **rozwiązania** pasku bocznym, kliknij prawym przyciskiem myszy **zależności** w obszarze **TestLibrary**. Wybierz **Edytuj odwołania** z menu kontekstowego.

1. W **Edytuj odwołania** okno dialogowe, wybierz opcję **TextUtils** project **projektów** kartę. Wybierz **OK**.

   ![Okno dialogowe odwołania do edycji](./media/using-on-mac-vs-full-solution/vsmacfull07.png)

1. W **TestLibrary** projektu, Zmień nazwę *UnitTest1.cs* plik *TextUtilsTests.cs*.

1. Otwórz plik i Zastąp kod następujących czynności:

   ```csharp
   using Xunit;
   using TextUtils;
   using System.Diagnostics;

   namespace TestLibrary
   {
       public class TextUtils_GetWordCountShould
       {
           [Fact]
           public void IgnoreCasing()
           {
               var wordCount = WordCount.GetWordCount("Jack", "Jack jack");

               Assert.NotEqual(2, wordCount);
           }
       }
   }
   ```

   Na poniższej ilustracji przedstawiono środowisko IDE z kod testu jednostkowego w miejscu. Należy zwrócić uwagę na `Assert.NotEqual` instrukcji.

   ![Test jednostkowy początkowej do sprawdzenia GetWordCount w głównym oknie środowiska IDE](./media/using-on-mac-vs-full-solution/vsmacfull08.png)

   Należy wprowadzić nowy test nie powiodło się jeden raz upewnij się, że jego testowania logiki jest poprawna. Metoda przekazuje nazwę "Jack" (wielkie litery) i ciąg "Jack" i "jack" (wielkie i małe litery). Jeśli `GetWordCount` metoda działa prawidłowo, zwracana jest liczba dwóch wystąpień z szukanym wyrazem. Aby celowo nie ten test, należy najpierw zaimplementować testu potwierdzające, że dwa wystąpienia szukanym wyrazem "Jack" nie są zwracane przez `GetWordCount` metody. Przejdź do następnego kroku, aby zakończyć niepowodzeniem test celowo.

1. Otwórz **testów jednostkowych** panelu po prawej stronie ekranu.

   ![Panel testów jednostkowych](./media/using-on-mac-vs-full-solution/vsmacfull_UnitTestPanel.png)

1. Kliknij przycisk **Dock** ikonę, aby pozostawić otwarty panel.

   ![Panel testów jednostkowych zadokować ikony](./media/using-on-mac-vs-full-solution/vsmacfull_UnitTestPanelDockIcon.png)

1. Kliknij przycisk **Uruchom wszystkie** przycisku.

   Test wypadnie niepomyślnie, który jest odpowiedni wynik. Metody testowej potwierdza, że dwa wystąpienia `inputString`, "Jack", nie są zwracane z ciągu "Jack jack" udostępniane `GetWordCount` metody. Ponieważ wielkości liter w słowie była brana pod uwagę na zewnątrz `GetWordCount` metody, zwracane są dwa wystąpienia. Potwierdzenie, 2 *nie jest równa* 2 kończy się niepowodzeniem. Jest to prawidłowy wynik, a logika naszym teście jest dobra.

   ![Niepowodzenia testu](./media/using-on-mac-vs-full-solution/vsmacfull09.png)

1. Modyfikowanie `IgnoreCasing` metoda testowa, zmieniając `Assert.NotEqual` do `Assert.Equal`. Zapisz plik za pomocą skrótu klawiaturowego <kbd> &#8984; </kbd> + <kbd>s</kbd>, **pliku** > **Zapisz** z menu lub kliknij prawym przyciskiem myszy kartę pliku i wybraniu **Zapisz** z menu kontekstowego.

   Należy oczekiwać, że `searchWord` "Jack" zwraca dwóch wystąpień z `inputString` "Jack jack" przekazany do `GetWordCount`. Uruchom test ponownie, klikając pozycję **Uruchom testy** znajdujący się w **testów jednostkowych** panel lub **Uruchom ponownie testy** znajdujący się w **wyników testu** panelu w dolnej części ekranu. Test zakończy się pomyślnie. Istnieją dwa wystąpienia "Jack" w ciągu "Jack jack" (bez uwzględnienia wielkości liter) i asercja testu jest `true`.

   ![Przebieg testu](./media/using-on-mac-vs-full-solution/vsmacfull10.png)

1. Testowanie pojedynczych wartości zwracanych z `Fact` to tylko początek co można zrobić za pomocą testów jednostkowych. Inna technika zaawansowane umożliwia przetestowanie kilka wartości, jednocześnie przy użyciu `Theory`. Dodaj następującą metodę do swojej `TextUtils_GetWordCountShould` klasy. Masz dwie metody w klasie, po dodaniu tej metody:

   ```csharp
   [Theory]
   [InlineData(0, "Ting", "Does not appear in the string.")]
   [InlineData(1, "Ting", "Ting appears once.")]
   [InlineData(2, "Ting", "Ting appears twice with Ting.")]
   public void CountInstancesCorrectly(int count,
                                       string searchWord,
                                       string inputString)
   {
       Assert.NotEqual(count, WordCount.GetWordCount(searchWord,
                                                  inputString));
   }
   ```

   `CountInstancesCorrectly` Sprawdza, czy `GetWordCount` metoda liczy się poprawnie. `InlineData` Zapewnia liczbą, szukanym wyrazem oraz ciągu wejściowym, aby sprawdzić. Metoda testowa jest uruchamiane jeden raz dla każdego wiersza danych. Ponownie Pamiętaj, że błąd jest potwierdzające najpierw za pomocą `Assert.NotEqual`nawet wtedy, gdy wiesz, czy liczby w danych są poprawne, i wartości zgodne liczby zwróconych przez `GetWordCount` metody. Wykonywanie kroku celowo niepowodzenie testu może wydawać się marnowania czasu na początku, ale sprawdzanie logiki badania, przełączając ją najpierw jest ważne wyboru na logice testów. Trafisz na metodę testową, która przekazuje, gdy spodziewasz się, aby zakończyć się niepowodzeniem, zostały znaleziono usterkę logikę testu. Jest warte włożonej pracy wykonaj następujący krok, za każdym razem, aby utworzyć metodę testową.

1. Zapisz plik i ponownie uruchom testy. Wielkość liter w wyrazie test zakończy się pomyślnie, ale liczba trzy testy nie powiodą się. Jest to dokładnie, oczekiwać do wykonania.

   ![Niepowodzenia testu](./media/using-on-mac-vs-full-solution/vsmacfull11.png)

1. Modyfikowanie `CountInstancesCorrectly` metoda testowa, zmieniając `Assert.NotEqual` do `Assert.Equal`. Zapisz plik. Ponownie uruchom testy. Kod przechodzi wszystkie testy.

   ![Przebieg testu](./media/using-on-mac-vs-full-solution/vsmacfull12.png)

## <a name="adding-a-console-app"></a>Dodawanie aplikacji konsoli

1. W **rozwiązania** pasku bocznym, kliknij prawym przyciskiem myszy `WordCounter` rozwiązania. Dodaj nową **aplikację Konsolową** projektu, wybierając szablon z **platformy .NET Core** > **aplikacji** szablonów. Wybierz **dalej**. Nadaj projektowi nazwę **WordCounterApp**. Wybierz **Utwórz** do utworzenia projektu w rozwiązaniu.

1. W **rozwiązania** pasku bocznym, kliknij prawym przyciskiem myszy **zależności** nowy węzeł **WordCounterApp** projektu. W **Edytuj odwołania** okno dialogowe, sprawdź **TextUtils** i wybierz **OK**.

1. Otwórz *Program.cs* pliku. Zastąp kod z następujących czynności:

   [!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/WordCounterApp/Program.cs)]

1. Aby uruchomić aplikację w oknie konsoli, zamiast IDE, kliknij prawym przyciskiem myszy `WordCounterApp` projektu, wybierz opcję **opcje**, a następnie otwórz **domyślne** węźle **konfiguracje**. Pole wyboru dla **Uruchom w konsoli zewnętrznej**. Pozostaw **Wstrzymaj dane wyjściowe konsoli** zaznaczoną opcją. To ustawienie powoduje, że aplikacja się w oknie konsoli, w którym można wpisać dane wejściowe na potrzeby `Console.ReadLine` instrukcji. Jeśli pozostawisz aplikacji do uruchamiania w środowisku IDE, może zobaczyć tylko dane wyjściowe `Console.WriteLine` instrukcji. `Console.ReadLine` instrukcje nie działają w IDE **dane wyjściowe aplikacji** panelu.

   ![Okno opcji projektu](./media/using-on-mac-vs-full-solution/vsmacfull13.png)

1. Ponieważ bieżąca wersja programu Visual Studio dla komputerów Mac nie można uruchomić testy, po uruchomieniu rozwiązania, możesz uruchomić aplikację konsoli bezpośrednio. Kliknij prawym przyciskiem myszy `WordCounterApp` projektu, a następnie wybierz **uruchamiania elementu** z menu kontekstowego. Jeśli spróbujesz uruchomić aplikację za pomocą przycisku odtwarzania narzędzie test runner i aplikacja nie uruchomione. Aby uzyskać więcej informacji na temat stanu pracy związane z tym problemem, zobacz [xunit/xamarinstudio.xunit (#60)](https://github.com/xunit/xamarinstudio.xunit/issues/60). Po uruchomieniu aplikacji, podaj wartości szukanym wyrazem oraz ciąg wejściowy po wyświetleniu monitów w oknie konsoli. Aplikacja wskazuje, ile razy szukanym wyrazem występuje w ciągu.

   ![Okno konsoli przedstawiający wyraz oliwki przeszukiwane w ciągu "Iro ate oliwki przez usługi Data lake i oliwki zostały nagraliście." Aplikacja reaguje, "oliwki word search pojawia się 2 razy."](./media/using-on-mac-vs-full-solution/vsmacfull14.png)

1. Ostatnią funkcją, aby zapoznać się z jest debugowania programu Visual Studio dla komputerów Mac. Ustaw punkt przerwania na `Console.WriteLine` instrukcji: Wybierz na lewym marginesie wierszu 23, a zobaczysz czerwone kółko pojawiają się obok wiersza kodu. Alternatywnie, wybierz dowolne miejsce w wierszu kodu, a następnie wybierz pozycję **Uruchom** > **Przełącz punkt przerwania** z menu.

   ![Ustawiono punkt przerwania w wierszu 23, instrukcja elementu Console.WriteLine](./media/using-on-mac-vs-full-solution/vsmacfull15.png)

1. Kliknij prawym przyciskiem myszy `WordCounterApp` projektu. Wybierz **Rozpocznij debugowanie elementu** z menu kontekstowego. Po uruchomieniu aplikacji, wprowadź Wyszukaj słowa "cat" i "dog poszukiwane cat, ale cat poprzedzone znakiem zmiany znaczenia". Aby uzyskać ciąg do wyszukania. Gdy `Console.WriteLine` osiągnięta zostanie instrukcja, przed wykonaniem instrukcji zatrzymuje się wykonywania programu. W **lokalne** karcie, możesz zobaczyć `searchWord`, `inputString`, `wordCount`, i `pluralChar` wartości.

   ![Wykonanie programu został zatrzymany na instrukcji elementu Console.WriteLine z lokalnym oknie wyświetlane wartości od razu, przed wykonaniem instrukcji elementu Console.WriteLine.](./media/using-on-mac-vs-full-solution/vsmacfull16.png)

1. W **bezpośrednie** okienko, wpisz "wordCount = 999;" i naciśnij klawisz Enter. To przypisuje wartość żadnego znaczenia 999 do `wordCount` zmiennej przedstawiający, że podczas debugowania można zastąpić wartości zmiennych.

   ![Nasze punkt przerwania zostaje trafiony. WordCount jest zmieniana na wartość 999 w oknie bezpośrednim](./media/using-on-mac-vs-full-solution/vsmacfull17.png)

1. Na pasku narzędzi kliknij *nadal* strzałki. Spójrz na dane wyjściowe w oknie konsoli. Nieprawidłowa wartość 999 ustawionych podczas Gdybyś debugował aplikacji wysyła raporty.

   ![Kontynuuj przycisk na pasku narzędzi](./media/using-on-mac-vs-full-solution/vsmacfull18.png)

   ![Liczba słów wyszukiwania jest zmieniana na wartość 999 w danych wyjściowych aplikacji](./media/using-on-mac-vs-full-solution/vsmacfull19.png)

## <a name="see-also"></a>Zobacz także

* [Visual Studio 2017 for Mac — informacje o wersji](/visualstudio/releasenotes/vs2017-mac-relnotes)
