---
title: Tworzenie biblioteki klas w języku Visual Basic i .NET Core w programie Visual Studio 2017
description: Dowiedz się, jak utworzyć bibliotekę klas, napisany w języku Visual Basic w programie Visual Studio 2017
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
dev_langs:
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 52bbae330afe4a9ea376c6388a06941f74f6606a
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2018
ms.locfileid: "48035977"
---
# <a name="building-a-class-library-with-visual-basic-and-net-core-in-visual-studio-2017"></a>Tworzenie biblioteki klas w języku Visual Basic i .NET Core w programie Visual Studio 2017

A *biblioteki klas* Określa typy i metody, które są wywoływane przez aplikację. Biblioteka klas, który jest przeznaczony dla .NET Standard 2.0 umożliwia biblioteki można wywoływać za pomocą dowolnego implementacji .NET, która obsługuje daną wersję .NET Standard. Po zakończeniu biblioteki klas, można zdecydować, czy chcesz rozprowadzić go jako składników innych firm lub tego, czy chcesz dołączyć go jako składnik powiązane z jedną lub więcej aplikacji.

> [!NOTE]
> Aby uzyskać listę wersji programu .NET Standard i platform, które obsługują, zobacz [.NET Standard](../../standard/net-standard.md).

W tym temacie utworzysz bibliotekę prostego narzędzia, która zawiera jedną metodę obsługi ciągów. Będzie implementowana jako [— metoda rozszerzenia](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) tak, aby można go wywołać, tak jakby był on członkiem <xref:System.String> klasy.

## <a name="creating-a-class-library-solution"></a>Tworzenie rozwiązania biblioteki klas

Rozpocznij od utworzenia rozwiązania dla Twojego projektu biblioteki klas i jej powiązane projekty. Rozwiązania programu Visual Studio są po prostu służy jako kontener dla jednego lub więcej projektów. Aby utworzyć rozwiązanie:

1. Na pasku menu programu Visual Studio, wybierz **pliku** > **New** > **projektu**.

1. W **nowy projekt** okna dialogowego, rozwiń węzeł **inne typy projektów** , a następnie wybierz węzeł **Visual Studio Solutions**. Nazwij rozwiązanie "ClassLibraryProjects", a następnie wybierz pozycję **OK** przycisku.

   ![Okno dialogowe nowego projektu](./media/library-with-visual-studio/newproject.png)

## <a name="creating-the-class-library-project"></a>Tworzenie projektu biblioteki klas

Utwórz projekt biblioteki klas:

1. W **Eksploratora rozwiązań**, kliknij prawym przyciskiem myszy **ClassLibraryProjects** rozwiązania pliku, a następnie z menu kontekstowego wybierz pozycję **Dodaj** > **New Projekt**.

1. W **Dodaj nowy projekt** okna dialogowego, rozwiń węzeł **języka Visual Basic** węzła, następnie wybierz pozycję **.NET Standard** węzła następuje **biblioteki klas (.NET Standard)**  szablonu projektu. W **nazwa** tekstu wprowadź "StringLibrary" jako nazwę projektu. Wybierz **OK** Aby utworzyć projekt biblioteki klas.

   ![Dodaj okno dialogowe Nowy projekt](./media/vb-library-with-visual-studio/libproject.png)

   W oknie kodu, a następnie zostanie otwarta w środowisku programowania Visual Studio. 
 
   ![Visual Studio okna aplikacji, przedstawiający kod szablonu domyślnego klasy biblioteki](./media/vb-library-with-visual-studio/stringlibrary.png)

1. Sprawdź, czy biblioteka jest przeznaczony dla prawidłowej wersji programu .NET Standard. Kliknij prawym przyciskiem myszy na projekt biblioteki w **Eksploratora rozwiązań** systemu windows, następnie wybierz pozycję **właściwości**. **Platformę docelową** pole tekstowe pokazuje, że firma Microsoft objęci .NET Standard 2.0.

   ![Właściwości projektu biblioteki klas](./media/library-with-visual-studio/properties.png)

1. Również w **właściwości** okno dialogowe, usuń wartość tekstową z **głównej przestrzeni nazw** pola tekstowego. Dla każdego projektu języka Visual Basic automatycznie tworzy przestrzeń nazw, która odnosi się do nazwy projektu, a wszelkie przestrzenie nazw zdefiniowane w plikach kodu źródłowego są nadrzędne tego obszaru nazw. Chcemy określić przestrzeń nazw najwyższego poziomu za pomocą [ `namespace` ](../../visual-basic/language-reference/statements/namespace-statement.md) — słowo kluczowe.
  
1. Zastąp kod w oknie Kod następującym kodem, a następnie zapisz plik:

  [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   Biblioteka klas `UtilityLibraries.StringLibrary`, zawiera metodę o nazwie `StartsWithUpper`, co powoduje zwrócenie <xref:System.Boolean> wartość, która wskazuje, czy bieżące wystąpienie ciągu rozpoczyna się od wielkiej litery. Unicode standard rozróżnia wielkie litery z małych liter. <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> Metoda zwraca `true` Jeśli znak jest wielką literą.

1. Na pasku menu wybierz **kompilacji** > **Kompiluj rozwiązanie**. Projekt powinien być skompilowana bez błędów.

   ![Okienko danych wyjściowych, pokazujący, że kompilacja zakończyła się pomyślnie](./media/library-with-visual-studio/buildsucceeds.png)



## <a name="next-step"></a>Następny krok

Został pomyślnie skompilowany biblioteki. Ponieważ jeszcze nie wywołać dowolną z jego metod, nie wiadomo, czy działa zgodnie z oczekiwaniami. Następnym krokiem w tworzeniu biblioteki jest przetestowanie go za pomocą [projektu testu jednostkowego](testing-library-with-visual-studio.md).
