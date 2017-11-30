---
title: "Często używane typy kolekcji"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- collections [.NET Framework], generic
- objects [.NET Framework], grouping in collections
- generics [.NET Framework], collections
- IList interface, grouping data in collections
- IDictionary interface, grouping data in collections
- grouping data in collections, generic collection types
- Collections classes
- generic collections
ms.assetid: f5d4c6a4-0d7b-4944-a9fb-3b12d9ebfd55
caps.latest.revision: "29"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ff8ae4475bde934258e4d3f97451e598a53fb6c5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="commonly-used-collection-types"></a><span data-ttu-id="b70c9-102">Często używane typy kolekcji</span><span class="sxs-lookup"><span data-stu-id="b70c9-102">Commonly Used Collection Types</span></span>
<span data-ttu-id="b70c9-103">Typy kolekcji są typowe przykłady kolekcji danych, takich jak tabele hash, kolejki, stosy, torebki, słowniki i listy.</span><span class="sxs-lookup"><span data-stu-id="b70c9-103">Collection types are the common variations of data collections, such as hash tables, queues, stacks, bags, dictionaries, and lists.</span></span>  
  
 <span data-ttu-id="b70c9-104">Kolekcje są oparte na <xref:System.Collections.ICollection> interfejsu <xref:System.Collections.IList> interfejsu <xref:System.Collections.IDictionary> interfejsu lub ich odpowiedniki ogólnego.</span><span class="sxs-lookup"><span data-stu-id="b70c9-104">Collections are based on the <xref:System.Collections.ICollection> interface, the <xref:System.Collections.IList> interface, the <xref:System.Collections.IDictionary> interface, or their generic counterparts.</span></span> <span data-ttu-id="b70c9-105"><xref:System.Collections.IList> Interfejsu i <xref:System.Collections.IDictionary> interfejsu zarówno pochodne <xref:System.Collections.ICollection> interfejsu; w związku z tym wszystkie kolekcje są oparte na <xref:System.Collections.ICollection> interfejsu bezpośrednio lub pośrednio.</span><span class="sxs-lookup"><span data-stu-id="b70c9-105">The <xref:System.Collections.IList> interface and the <xref:System.Collections.IDictionary> interface are both derived from the <xref:System.Collections.ICollection> interface; therefore, all collections are based on the <xref:System.Collections.ICollection> interface either directly or indirectly.</span></span> <span data-ttu-id="b70c9-106">W kolekcji na podstawie <xref:System.Collections.IList> interfejsu (takich jak <xref:System.Array>, <xref:System.Collections.ArrayList>, lub <xref:System.Collections.Generic.List%601>) lub bezpośrednio na <xref:System.Collections.ICollection> interfejsu (takich jak <xref:System.Collections.Queue>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, <xref:System.Collections.Stack>, <xref:System.Collections.Concurrent.ConcurrentStack%601> lub <xref:System.Collections.Generic.LinkedList%601>), co element zawiera tylko wartości.</span><span class="sxs-lookup"><span data-stu-id="b70c9-106">In collections based on the <xref:System.Collections.IList> interface (such as <xref:System.Array>, <xref:System.Collections.ArrayList>, or <xref:System.Collections.Generic.List%601>) or directly on the <xref:System.Collections.ICollection> interface (such as <xref:System.Collections.Queue>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, <xref:System.Collections.Stack>, <xref:System.Collections.Concurrent.ConcurrentStack%601> or <xref:System.Collections.Generic.LinkedList%601>), every element contains only a value.</span></span> <span data-ttu-id="b70c9-107">W kolekcji na podstawie <xref:System.Collections.IDictionary> interfejsu (takich jak <xref:System.Collections.Hashtable> i <xref:System.Collections.SortedList> klas, <xref:System.Collections.Generic.Dictionary%602> i <xref:System.Collections.Generic.SortedList%602> klasy ogólne), lub <xref:System.Collections.Concurrent.ConcurrentDictionary%602> klas, każdy element zawiera zarówno klucz i wartość.</span><span class="sxs-lookup"><span data-stu-id="b70c9-107">In collections based on the <xref:System.Collections.IDictionary> interface (such as the <xref:System.Collections.Hashtable> and <xref:System.Collections.SortedList> classes, the <xref:System.Collections.Generic.Dictionary%602> and <xref:System.Collections.Generic.SortedList%602> generic classes), or the <xref:System.Collections.Concurrent.ConcurrentDictionary%602> classes, every element contains both a key and a value.</span></span>  <span data-ttu-id="b70c9-108"><xref:System.Collections.ObjectModel.KeyedCollection%602> Klasy jest unikatowa, ponieważ jest listę wartości z kluczami osadzone w wartości, i w związku z tym zachowuje się jak listy i jak słownika.</span><span class="sxs-lookup"><span data-stu-id="b70c9-108">The <xref:System.Collections.ObjectModel.KeyedCollection%602> class is unique because it is a list of values with keys embedded within the values and, therefore, it behaves like a list and like a dictionary.</span></span>  
  
 <span data-ttu-id="b70c9-109">Kolekcje ogólne są najlepsze rozwiązania pod kątem silne wpisywanie.</span><span class="sxs-lookup"><span data-stu-id="b70c9-109">Generic collections are the best solution to strong typing.</span></span> <span data-ttu-id="b70c9-110">Jednak, jeśli język nie obsługuje elementów ogólnych, <xref:System.Collections> przestrzeń nazw zawiera podstawowe kolekcje <xref:System.Collections.CollectionBase>, <xref:System.Collections.ReadOnlyCollectionBase>, i <xref:System.Collections.DictionaryBase>, które są abstrakcyjnych klas podstawowych, które można rozszerzyć, aby utworzyć klasy kolekcji, które są silnie typizowane.</span><span class="sxs-lookup"><span data-stu-id="b70c9-110">However, if your language does not support generics, the <xref:System.Collections> namespace includes base collections, such as <xref:System.Collections.CollectionBase>, <xref:System.Collections.ReadOnlyCollectionBase>, and <xref:System.Collections.DictionaryBase>, which are abstract base classes that can be extended to create collection classes that are strongly typed.</span></span> <span data-ttu-id="b70c9-111">Gdy wymagana jest efektywne kolekcji wielowątkowych dostęp, użyj kolekcje ogólne w <xref:System.Collections.Concurrent> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="b70c9-111">When efficient multi-threaded collection access is required, use the generic collections in the <xref:System.Collections.Concurrent> namespace.</span></span>  
  
 <span data-ttu-id="b70c9-112">Kolekcje mogą się różnić w zależności od sposobu przechowywania elementy, jak są one sortowane realizację wyszukiwania i jak porównań.</span><span class="sxs-lookup"><span data-stu-id="b70c9-112">Collections can vary, depending on how the elements are stored, how they are sorted, how searches are performed, and how comparisons are made.</span></span> <span data-ttu-id="b70c9-113"><xref:System.Collections.Queue> Klasy i <xref:System.Collections.Generic.Queue%601> klasy ogólnej stanowią pierwszy w pierwszym poza listę, gdy <xref:System.Collections.Stack> klasy i <xref:System.Collections.Generic.Stack%601> klasy ogólnej stanowią listę ostatnich w pierwszym poza.</span><span class="sxs-lookup"><span data-stu-id="b70c9-113">The <xref:System.Collections.Queue> class and the <xref:System.Collections.Generic.Queue%601> generic class provide first-in-first-out lists, while the <xref:System.Collections.Stack> class and the <xref:System.Collections.Generic.Stack%601> generic class provide last-in-first-out lists.</span></span> <span data-ttu-id="b70c9-114"><xref:System.Collections.SortedList> Klasy i <xref:System.Collections.Generic.SortedList%602> klasy ogólnej zawiera posortowane wersji <xref:System.Collections.Hashtable> klasy i <xref:System.Collections.Generic.Dictionary%602> klasy ogólnej.</span><span class="sxs-lookup"><span data-stu-id="b70c9-114">The <xref:System.Collections.SortedList> class and the <xref:System.Collections.Generic.SortedList%602> generic class provide sorted versions of the <xref:System.Collections.Hashtable> class and the <xref:System.Collections.Generic.Dictionary%602> generic class.</span></span> <span data-ttu-id="b70c9-115">Elementy <xref:System.Collections.Hashtable> lub <xref:System.Collections.Generic.Dictionary%602> są dostępne tylko za pomocą klucza elementu, ale elementy <xref:System.Collections.SortedList> lub <xref:System.Collections.ObjectModel.KeyedCollection%602> są dostępne przez klucz lub indeks elementu.</span><span class="sxs-lookup"><span data-stu-id="b70c9-115">The elements of a <xref:System.Collections.Hashtable> or a <xref:System.Collections.Generic.Dictionary%602> are accessible only by the key of the element, but the elements of a <xref:System.Collections.SortedList> or a <xref:System.Collections.ObjectModel.KeyedCollection%602> are accessible either by the key or by the index of the element.</span></span> <span data-ttu-id="b70c9-116">Indeksy we wszystkich zbiorach jest liczony od zera, z wyjątkiem <xref:System.Array>, dzięki czemu tablic, które nie są liczony od zera.</span><span class="sxs-lookup"><span data-stu-id="b70c9-116">The indexes in all collections are zero-based, except <xref:System.Array>, which allows arrays that are not zero-based.</span></span>  
  
 <span data-ttu-id="b70c9-117">LINQ do obiektów funkcji pozwala na potrzeby dostępu do obiektów w pamięci, tak długo, jak typ obiektu implementuje zapytań LINQ <xref:System.Collections.IEnumerable> lub <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="b70c9-117">The LINQ to Objects feature allows you to use LINQ queries to access in-memory objects as long as the object type implements <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="b70c9-118">Zapytania LINQ Podaj wspólnego wzorca do uzyskiwania dostępu do danych; zazwyczaj są to zwięzły i bardziej czytelny niż standardowe `foreach` pętli; oraz udostępnia filtrowania, kolejność i grupowanie możliwości.</span><span class="sxs-lookup"><span data-stu-id="b70c9-118">LINQ queries provide a common pattern for accessing data; are typically more concise and readable than standard `foreach` loops; and provide filtering, ordering and grouping capabilities.</span></span> <span data-ttu-id="b70c9-119">Zapytania LINQ także może zwiększyć wydajność.</span><span class="sxs-lookup"><span data-stu-id="b70c9-119">LINQ queries can also improve performance.</span></span> <span data-ttu-id="b70c9-120">Aby uzyskać więcej informacji, zobacz [LINQ do obiektów](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9) i [równoległe LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="b70c9-120">For more information, see [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9) and [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="b70c9-121">Tematy pokrewne</span><span class="sxs-lookup"><span data-stu-id="b70c9-121">Related Topics</span></span>  
  
|<span data-ttu-id="b70c9-122">Tytuł</span><span class="sxs-lookup"><span data-stu-id="b70c9-122">Title</span></span>|<span data-ttu-id="b70c9-123">Opis</span><span class="sxs-lookup"><span data-stu-id="b70c9-123">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b70c9-124">Kolekcje i struktury danych</span><span class="sxs-lookup"><span data-stu-id="b70c9-124">Collections and Data Structures</span></span>](../../../docs/standard/collections/index.md)|<span data-ttu-id="b70c9-125">W tym artykule omówiono różne typy kolekcji dostępne w [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], w tym stosy, kolejek, list, tablic i słowników.</span><span class="sxs-lookup"><span data-stu-id="b70c9-125">Discusses the various collection types available in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], including stacks, queues, lists, arrays, and dictionaries.</span></span>|  
|[<span data-ttu-id="b70c9-126">HashTable typy kolekcji i słowników</span><span class="sxs-lookup"><span data-stu-id="b70c9-126">Hashtable and Dictionary Collection Types</span></span>](../../../docs/standard/collections/hashtable-and-dictionary-collection-types.md)|<span data-ttu-id="b70c9-127">Zawiera opis funkcji typy ogólne i nierodzajowe słownik na podstawie wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="b70c9-127">Describes the features of generic and nongeneric hash-based dictionary types.</span></span>|  
|[<span data-ttu-id="b70c9-128">Sortowane typów kolekcji</span><span class="sxs-lookup"><span data-stu-id="b70c9-128">Sorted Collection Types</span></span>](../../../docs/standard/collections/sorted-collection-types.md)|<span data-ttu-id="b70c9-129">W tym artykule opisano klasy, które zapewniają funkcje sortowania list i zestawów.</span><span class="sxs-lookup"><span data-stu-id="b70c9-129">Describes classes that provide sorting functionality for lists and sets.</span></span>|  
|[<span data-ttu-id="b70c9-130">Typy ogólne</span><span class="sxs-lookup"><span data-stu-id="b70c9-130">Generics</span></span>](../../../docs/standard/generics/index.md)|<span data-ttu-id="b70c9-131">Zawiera opis funkcji ogólne, w tym kolekcje ogólne, delegatów i interfejsami [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b70c9-131">Describes the generics feature, including the generic collections, delegates, and interfaces provided by the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="b70c9-132">Zawiera linki do dokumentacji funkcji języka C#, Visual Basic i Visual C++, a do obsługi technologii, takich jak odbicia.</span><span class="sxs-lookup"><span data-stu-id="b70c9-132">Provides links to feature documentation for C#, Visual Basic, and Visual C++, and to supporting technologies such as reflection.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="b70c9-133">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="b70c9-133">Reference</span></span>  
 <xref:System.Collections?displayProperty=nameWithType>  
  
 <xref:System.Collections.Generic?displayProperty=nameWithType>  
  
 <xref:System.Collections.ICollection?displayProperty=nameWithType>  
  
 <xref:System.Collections.Generic.ICollection%601?displayProperty=nameWithType>  
  
 <xref:System.Collections.IList?displayProperty=nameWithType>  
  
 <xref:System.Collections.Generic.IList%601?displayProperty=nameWithType>  
  
 <xref:System.Collections.IDictionary?displayProperty=nameWithType>  
  
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>