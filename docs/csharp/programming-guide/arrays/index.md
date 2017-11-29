---
title: "Tablice (Przewodnik programowania w języku C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
caps.latest.revision: "33"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1cdd319ef6bbb296c7afa5195563b92bdd361f0b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="2e6fb-102">Tablice (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="2e6fb-102">Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="2e6fb-103">W tablicy struktury danych można przechowywać wiele zmiennych tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="2e6fb-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="2e6fb-104">Można zadeklarować tablicy przez określenie typu elementów.</span><span class="sxs-lookup"><span data-stu-id="2e6fb-104">You declare an array by specifying the type of its elements.</span></span>  
  
 `type[] arrayName;`  
  
 <span data-ttu-id="2e6fb-105">Poniższe przykłady tworzenia tablice jednowymiarowe wielowymiarowe i nieregularne:</span><span class="sxs-lookup"><span data-stu-id="2e6fb-105">The following examples create single-dimensional, multidimensional, and jagged arrays:</span></span>  
  
 [!code-csharp[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
## <a name="array-overview"></a><span data-ttu-id="2e6fb-106">Omówienie tablicy</span><span class="sxs-lookup"><span data-stu-id="2e6fb-106">Array Overview</span></span>  
 <span data-ttu-id="2e6fb-107">Tablica ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="2e6fb-107">An array has the following properties:</span></span>  
  
-   <span data-ttu-id="2e6fb-108">Tablica może być [jednowymiarowe](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [wielowymiarowe](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) lub [Jagged](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="2e6fb-108">An array can be [Single-Dimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [Multidimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) or [Jagged](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span></span>  
  
-   <span data-ttu-id="2e6fb-109">Liczba wymiarów i długość każdego wymiaru są wyznaczane podczas tworzenia wystąpienia tablicy.</span><span class="sxs-lookup"><span data-stu-id="2e6fb-109">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="2e6fb-110">Nie można zmienić tych wartości przez cały okres istnienia wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="2e6fb-110">These values can't be changed during the lifetime of the instance.</span></span>  
  
-   <span data-ttu-id="2e6fb-111">Domyślne wartości elementów tablicy liczbowych są ustawione na zero, a elementy odwołań są ustawione na wartość null.</span><span class="sxs-lookup"><span data-stu-id="2e6fb-111">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>  
  
-   <span data-ttu-id="2e6fb-112">Nieregularna tablica jest tablicy tablic, a w związku z tym jej elementy są typy referencyjne i są inicjowane na `null`.</span><span class="sxs-lookup"><span data-stu-id="2e6fb-112">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
-   <span data-ttu-id="2e6fb-113">Tablice są indeksowane zero: tablica o `n` elementów jest indeksowany z `0` do `n-1`.</span><span class="sxs-lookup"><span data-stu-id="2e6fb-113">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>  
  
-   <span data-ttu-id="2e6fb-114">Elementy tablicy może być dowolnego typu, łącznie z typem tablicy.</span><span class="sxs-lookup"><span data-stu-id="2e6fb-114">Array elements can be of any type, including an array type.</span></span>  
  
-   <span data-ttu-id="2e6fb-115">Typy tablicy są [typy referencyjne](../../../csharp/language-reference/keywords/reference-types.md) pochodzi od typu podstawowego abstrakcyjny <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="2e6fb-115">Array types are [reference types](../../../csharp/language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="2e6fb-116">Ponieważ ten typ implementuje <xref:System.Collections.IEnumerable> i <xref:System.Collections.Generic.IEnumerable%601>, można użyć [foreach](../../../csharp/language-reference/keywords/foreach-in.md) iteracji wszystkich tablic w języku C#.</span><span class="sxs-lookup"><span data-stu-id="2e6fb-116">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../../csharp/language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2e6fb-117">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="2e6fb-117">Related Sections</span></span>  
  
-   [<span data-ttu-id="2e6fb-118">Tablice jako obiekty</span><span class="sxs-lookup"><span data-stu-id="2e6fb-118">Arrays as Objects</span></span>](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [<span data-ttu-id="2e6fb-119">Używanie instrukcji foreach z tablicami</span><span class="sxs-lookup"><span data-stu-id="2e6fb-119">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [<span data-ttu-id="2e6fb-120">Przekazywanie tablic jako argumenty</span><span class="sxs-lookup"><span data-stu-id="2e6fb-120">Passing Arrays as Arguments</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
-   [<span data-ttu-id="2e6fb-121">Przekazywanie tablic za pomocą ref i out</span><span class="sxs-lookup"><span data-stu-id="2e6fb-121">Passing Arrays Using ref and out</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)   
  
## <a name="c-language-specification"></a><span data-ttu-id="2e6fb-122">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="2e6fb-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2e6fb-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2e6fb-123">See Also</span></span>  
 [<span data-ttu-id="2e6fb-124">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="2e6fb-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2e6fb-125">Kolekcje</span><span class="sxs-lookup"><span data-stu-id="2e6fb-125">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)  
 [<span data-ttu-id="2e6fb-126">Typ kolekcji tablicy</span><span class="sxs-lookup"><span data-stu-id="2e6fb-126">Array Collection Type</span></span>](http://msdn.microsoft.com/en-us/8a9964de-8941-47b1-a3cf-a01bc88db9e8)