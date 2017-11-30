---
title: "Ciąg interpolacji - C#"
description: "Dowiedz się, jak działa interpolacji ciągu w języku C# 6"
keywords: ".NET i .NET core C#, ciąg"
author: mgroves
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f8806f6b-3ac7-4ee6-9b3e-c524d5301ae9
ms.openlocfilehash: ac19d4208da4f8ee6dd3e071ab70dbc41a0cd065
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="string-interpolation-in-c"></a><span data-ttu-id="f1b96-104">Ciąg interpolacji w języku C#</span><span class="sxs-lookup"><span data-stu-id="f1b96-104">String Interpolation in C#</span></span> #

<span data-ttu-id="f1b96-105">Ciąg interpolacji jest sposób symbole zastępcze w ciągu zastępuje wartość zmiennej ciągu.</span><span class="sxs-lookup"><span data-stu-id="f1b96-105">String Interpolation is the way that placeholders in a string are replaced by the value of a string variable.</span></span> <span data-ttu-id="f1b96-106">Przed C# 6, jest sposób, w tym celu `System.String.Format`.</span><span class="sxs-lookup"><span data-stu-id="f1b96-106">Before C# 6, the way to do this is with `System.String.Format`.</span></span> <span data-ttu-id="f1b96-107">To działanie jest zgoda, ale ponieważ używa numeru symbole zastępcze, może być trudniejsze do odczytu i pełniejsze.</span><span class="sxs-lookup"><span data-stu-id="f1b96-107">This works okay, but since it uses numbered placeholders, it can be harder to read and more verbose.</span></span>

<span data-ttu-id="f1b96-108">Inne języki programowania miały interpolacji ciąg wbudowanych w języku jakiś czas.</span><span class="sxs-lookup"><span data-stu-id="f1b96-108">Other programming languages have had string interpolation built into the language for a while.</span></span> <span data-ttu-id="f1b96-109">Na przykład w kodzie PHP:</span><span class="sxs-lookup"><span data-stu-id="f1b96-109">For instance, in PHP:</span></span>

```php
$name = "Jonas";
echo "My name is $name.";
// This will output "My name is Jonas."
```

<span data-ttu-id="f1b96-110">W języku C# 6 koniec zostały tego stylu interpolacji ciągu.</span><span class="sxs-lookup"><span data-stu-id="f1b96-110">In C# 6, we finally have that style of string interpolation.</span></span> <span data-ttu-id="f1b96-111">Można użyć `$` przed ciąg, aby wskazać, że należy zastąpić zmienne/wyrażenia ich wartości.</span><span class="sxs-lookup"><span data-stu-id="f1b96-111">You can use a `$` before a string to indicate that it should substitute variables/expressions for their values.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f1b96-112">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="f1b96-112">Prerequisites</span></span>
<span data-ttu-id="f1b96-113">Należy skonfigurować komputer z usługami .NET core.</span><span class="sxs-lookup"><span data-stu-id="f1b96-113">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="f1b96-114">Instrukcje instalacji można znaleźć na [.NET Core](https://www.microsoft.com/net/core) strony.</span><span class="sxs-lookup"><span data-stu-id="f1b96-114">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="f1b96-115">Można uruchomić tej aplikacji, w systemie Windows, Ubuntu Linux, macOS lub w kontenerze Docker.</span><span class="sxs-lookup"><span data-stu-id="f1b96-115">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="f1b96-116">Należy zainstalować w edytorze kodu dotyczącego elementów ulubionych.</span><span class="sxs-lookup"><span data-stu-id="f1b96-116">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="f1b96-117">Opisy poniżej użyj [Visual Studio Code](https://code.visualstudio.com/) czyli typu open source cross platform edytora.</span><span class="sxs-lookup"><span data-stu-id="f1b96-117">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="f1b96-118">Można jednak użyć dowolnego narzędzia potrafisz.</span><span class="sxs-lookup"><span data-stu-id="f1b96-118">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="f1b96-119">Tworzenie aplikacji</span><span class="sxs-lookup"><span data-stu-id="f1b96-119">Create the Application</span></span>

<span data-ttu-id="f1b96-120">Teraz, po zainstalowaniu wszystkich narzędzi, należy utworzyć nową aplikację platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f1b96-120">Now that you've installed all the tools, create a new .NET Core application.</span></span> <span data-ttu-id="f1b96-121">Aby użyć generatora wiersza polecenia, Utwórz katalog projektu, takie jak `interpolated`i uruchom następujące polecenie w ulubionych powłoki:</span><span class="sxs-lookup"><span data-stu-id="f1b96-121">To use the command line generator, create a directory for your project, such as `interpolated`, and execute the following command in your favorite shell:</span></span>

```
dotnet new console
```

<span data-ttu-id="f1b96-122">To polecenie spowoduje utworzenie projektu podstawowe .NET core z pliku projektu *interpolated.csproj*i pliku kodu źródłowego, *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="f1b96-122">This command will create a barebones .NET core project with a project file, *interpolated.csproj*, and a source code file, *Program.cs*.</span></span> <span data-ttu-id="f1b96-123">Konieczne będzie wykonanie `dotnet restore` do przywrócenia zależności niezbędne do skompilowania tego projektu.</span><span class="sxs-lookup"><span data-stu-id="f1b96-123">You will need to execute `dotnet restore` to restore the dependencies needed to compile this project.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="f1b96-124">Do wykonania programu, należy użyć `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="f1b96-124">To execute the program, use `dotnet run`.</span></span> <span data-ttu-id="f1b96-125">Powinien zostać wyświetlony "tekst Hello, World" dane wyjściowe do konsoli.</span><span class="sxs-lookup"><span data-stu-id="f1b96-125">You should see "Hello, World" output to the console.</span></span>



## <a name="intro-to-string-interpolation"></a><span data-ttu-id="f1b96-126">Wprowadzenie do ciągu interpolacji</span><span class="sxs-lookup"><span data-stu-id="f1b96-126">Intro to String Interpolation</span></span>

<span data-ttu-id="f1b96-127">Z `System.String.Format`, określ "symbole zastępcze" w ciągu, który zastępuje parametrów po ciągu.</span><span class="sxs-lookup"><span data-stu-id="f1b96-127">With `System.String.Format`, you specify "placeholders" in a string that are replaced by the parameters following the string.</span></span> <span data-ttu-id="f1b96-128">Przykład:</span><span class="sxs-lookup"><span data-stu-id="f1b96-128">For instance:</span></span>

[!code-csharp[String.Format example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]  

<span data-ttu-id="f1b96-129">Który dane wyjściowe obejmują "mojej nazwy jest gajów Matt".</span><span class="sxs-lookup"><span data-stu-id="f1b96-129">That will output "My name is Matt Groves".</span></span>

<span data-ttu-id="f1b96-130">W języku C# 6, zamiast `String.Format`, zdefiniuj ciągu interpolowanym dołączając ją z `$` symboli, a następnie za pomocą zmiennych bezpośrednio w ciągu.</span><span class="sxs-lookup"><span data-stu-id="f1b96-130">In C# 6, instead of using `String.Format`, you define an interpolated string by prepending it with the `$` symbol, and then using the variables directly in the string.</span></span> <span data-ttu-id="f1b96-131">Przykład:</span><span class="sxs-lookup"><span data-stu-id="f1b96-131">For instance:</span></span>

[!code-csharp[Interpolation example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]  

<span data-ttu-id="f1b96-132">Nie trzeba używać tylko zmienne.</span><span class="sxs-lookup"><span data-stu-id="f1b96-132">You don't have to use just variables.</span></span> <span data-ttu-id="f1b96-133">Można użyć dowolnego wyrażenia w nawiasach.</span><span class="sxs-lookup"><span data-stu-id="f1b96-133">You can use any expression within the brackets.</span></span> <span data-ttu-id="f1b96-134">Przykład:</span><span class="sxs-lookup"><span data-stu-id="f1b96-134">For instance:</span></span>

[!code-csharp[Interpolation expression example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]  

<span data-ttu-id="f1b96-135">Czy wyjściowy, który:</span><span class="sxs-lookup"><span data-stu-id="f1b96-135">Which would output:</span></span>

```
This is line number 1
This is line number 2
This is line number 3
This is line number 4
This is line number 5
```

## <a name="how-string-interpolation-works"></a><span data-ttu-id="f1b96-136">Jak działa interpolacji ciągu</span><span class="sxs-lookup"><span data-stu-id="f1b96-136">How string interpolation works</span></span>

<span data-ttu-id="f1b96-137">W tle tej składni interpolacji ciągu jest przetłumaczyć String.Format przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="f1b96-137">Behind the scenes, this string interpolation syntax is translated into String.Format by the compiler.</span></span> <span data-ttu-id="f1b96-138">Tak, możesz zrobić [tego samego typu rzeczy wykonaniu przed z String.Format](https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="f1b96-138">So, you can do the [same type of stuff you've done before with String.Format](https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx).</span></span>

<span data-ttu-id="f1b96-139">Na przykład można dodać uzupełniania i formatowania liczbowa:</span><span class="sxs-lookup"><span data-stu-id="f1b96-139">For instance, you can add padding and numeric formatting:</span></span>

[!code-csharp[Interpolation formatting example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]  

<span data-ttu-id="f1b96-140">Powyższe czy dane wyjściowe wyglądać mniej więcej tak:</span><span class="sxs-lookup"><span data-stu-id="f1b96-140">The above would output something like:</span></span>

```
998        5,177.67
999        6,719.30
1000       9,910.61
1001       529.34
1002       1,349.86
1003       2,660.82
1004       6,227.77
```

<span data-ttu-id="f1b96-141">Jeśli nazwa zmiennej nie zostanie znaleziony, błąd w czasie kompilacji zostanie wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="f1b96-141">If a variable name is not found, then a compile time error will be generated.</span></span>

<span data-ttu-id="f1b96-142">Przykład:</span><span class="sxs-lookup"><span data-stu-id="f1b96-142">For instance:</span></span>

```csharp
var animal = "fox";
var localizeMe = $"The {adj} brown {animal} jumped over the lazy {otheranimal}";
var adj = "quick";
Console.WriteLine(localizeMe);
```

<span data-ttu-id="f1b96-143">Kompilacja to spowoduje wyświetlenie błędów:</span><span class="sxs-lookup"><span data-stu-id="f1b96-143">If you compile this, you'll get errors:</span></span>
 
* <span data-ttu-id="f1b96-144">`Cannot use local variable 'adj' before it is declared`- `adj` nie została zadeklarowana zmienna, do *po* ciągu interpolowanym.</span><span class="sxs-lookup"><span data-stu-id="f1b96-144">`Cannot use local variable 'adj' before it is declared` - the `adj` variable wasn't declared until *after* the interpolated string.</span></span>
* <span data-ttu-id="f1b96-145">`The name 'otheranimal' does not exist in the current context`-zmiennej o nazwie `otheranimal` nawet nigdy nie został zadeklarowany.</span><span class="sxs-lookup"><span data-stu-id="f1b96-145">`The name 'otheranimal' does not exist in the current context` - a variable called `otheranimal` was never even declared</span></span>

## <a name="localization-and-internationalization"></a><span data-ttu-id="f1b96-146">Lokalizacja i internacjonalizacji</span><span class="sxs-lookup"><span data-stu-id="f1b96-146">Localization and Internationalization</span></span>

<span data-ttu-id="f1b96-147">Obsługuje ciągu interpolowanym `IFormattable` i `FormattableString`, które mogą być przydatne w przypadku internacjonalizacji.</span><span class="sxs-lookup"><span data-stu-id="f1b96-147">An interpolated string supports `IFormattable` and `FormattableString`, which can be useful for internationalization.</span></span>

<span data-ttu-id="f1b96-148">Domyślnie w ciągu interpolowanym używa bieżącej kultury.</span><span class="sxs-lookup"><span data-stu-id="f1b96-148">By default, an interpolated string uses the current culture.</span></span> <span data-ttu-id="f1b96-149">Aby korzystać z inną kulturę, można rzutować go jako`IFormattable`</span><span class="sxs-lookup"><span data-stu-id="f1b96-149">To use a different culture, you could cast it as `IFormattable`</span></span>

<span data-ttu-id="f1b96-150">Przykład:</span><span class="sxs-lookup"><span data-stu-id="f1b96-150">For instance:</span></span>

[!code-csharp[Interpolation internationalization example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]  

## <a name="conclusion"></a><span data-ttu-id="f1b96-151">Wniosek</span><span class="sxs-lookup"><span data-stu-id="f1b96-151">Conclusion</span></span> 

<span data-ttu-id="f1b96-152">W tym samouczku przedstawiono sposób korzystania z funkcji interpolacji ciągu języka C# 6.</span><span class="sxs-lookup"><span data-stu-id="f1b96-152">In this tutorial, you learned how to use string interpolation features of C# 6.</span></span> <span data-ttu-id="f1b96-153">Zasadniczo jest bardziej zwięzły sposób zapisywania prosty `String.Format` instrukcji z niektórych ostrzeżenia dla bardziej zaawansowanych stosowania.</span><span class="sxs-lookup"><span data-stu-id="f1b96-153">It's basically a more concise way of writing simple `String.Format` statements, with some caveats for more advanced uses of it.</span></span>