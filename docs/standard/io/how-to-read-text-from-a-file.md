---
title: 'Porady: odczyt tekstu z pliku'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
caps.latest.revision: "23"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 026f6ae4dd9aee340d6a9ffb931d0525ae75654a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-text-from-a-file"></a><span data-ttu-id="59fac-102">Porady: odczyt tekstu z pliku</span><span class="sxs-lookup"><span data-stu-id="59fac-102">How to: Read Text from a File</span></span>
<span data-ttu-id="59fac-103">W poniższych przykładach pokazano, jak odczytać tekst synchronicznie i asynchronicznie z pliku tekstowego przy użyciu platformy .NET dla aplikacji komputerowych.</span><span class="sxs-lookup"><span data-stu-id="59fac-103">The following examples show how to read text synchronously and asynchronously from a text file using .NET for desktop apps.</span></span> <span data-ttu-id="59fac-104">W obu przykładach, podczas tworzenia wystąpienia <xref:System.IO.StreamReader> klasy, podaj względna lub bezwzględna ścieżka do pliku.</span><span class="sxs-lookup"><span data-stu-id="59fac-104">In both examples, when you create the instance of the <xref:System.IO.StreamReader> class, you provide the relative or absolute path to the file.</span></span> <span data-ttu-id="59fac-105">W poniższych przykładach założono, że plik o nazwie TestFile.txt znajduje się w folderze aplikacji.</span><span class="sxs-lookup"><span data-stu-id="59fac-105">The following examples assume that the file named TestFile.txt is in the same folder as the application.</span></span>  
  
 <span data-ttu-id="59fac-106">Te przykłady kodu nie dotyczą projektowania aplikacji do Sklepu Windows, ponieważ środowisko wykonawcze systemu Windows oferuje inne typy strumieni odczytujących i zapisujących pliki.</span><span class="sxs-lookup"><span data-stu-id="59fac-106">These code examples do not apply developing for Windows Store Apps because the Windows Runtime provides different streams types reading and writing to files.</span></span> <span data-ttu-id="59fac-107">Przykład pokazujący sposób odczyt tekstu z plików w kontekście aplikacji ze Sklepu Windows, temacie [Szybki Start: Odczyt i zapis plików](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx).</span><span class="sxs-lookup"><span data-stu-id="59fac-107">For an example that shows how to read text from a file within the context of a Windows Store app, see [Quickstart: Reading and writing files](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx).</span></span> <span data-ttu-id="59fac-108">Przykłady sposobu konwersji między .NET Framework i strumieni środowiska wykonawczego systemu Windows można znaleźć [porady: konwertowanie między .NET Framework i strumieni środowiska wykonawczego systemu Windows](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span><span class="sxs-lookup"><span data-stu-id="59fac-108">For examples that show how to convert between .NET Framework streams and Windows runtime streams see [How to: Convert Between .NET Framework Streams and Windows Runtime Streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59fac-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="59fac-109">Example</span></span>  
 <span data-ttu-id="59fac-110">W pierwszym przykładzie pokazano operację odczytu synchronicznego przy użyciu aplikacji konsoli.</span><span class="sxs-lookup"><span data-stu-id="59fac-110">The first example shows a synchronous read operation within a console application.</span></span> <span data-ttu-id="59fac-111">W tym przykładzie plik jest otwarty przy użyciu czytnik strumienia, zawartość jest kopiowana do ciągu i parametry są dane wyjściowe do konsoli.</span><span class="sxs-lookup"><span data-stu-id="59fac-111">In this example, the text file is opened using a stream reader, the contents are copied to a string and string is output to the console.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="59fac-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="59fac-112">Example</span></span>  
 <span data-ttu-id="59fac-113">W drugim przykładzie pokazano operację odczytu asynchronicznego przy użyciu aplikacji programu Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="59fac-113">The second example shows an asynchronous read operation within a Windows Presentation Foundation (WPF) application.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="59fac-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="59fac-114">See Also</span></span>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="59fac-115">Asynchroniczne We/Wy pliku</span><span class="sxs-lookup"><span data-stu-id="59fac-115">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [<span data-ttu-id="59fac-116">NIB: Porady: Tworzenie listy katalogów</span><span class="sxs-lookup"><span data-stu-id="59fac-116">NIB: How to: Create a Directory Listing</span></span>](http://msdn.microsoft.com/en-us/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [<span data-ttu-id="59fac-117">Szybki Start: Odczyt i zapis plików</span><span class="sxs-lookup"><span data-stu-id="59fac-117">Quickstart: Reading and writing files</span></span>](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx)  
 [<span data-ttu-id="59fac-118">Porady: konwertowanie między .NET Framework i strumieni środowiska wykonawczego systemu Windows</span><span class="sxs-lookup"><span data-stu-id="59fac-118">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
 [<span data-ttu-id="59fac-119">Porady: Odczyt i zapis do pliku danych nowo utworzony</span><span class="sxs-lookup"><span data-stu-id="59fac-119">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="59fac-120">Porady: otwieranie i Dołącz do pliku dziennika</span><span class="sxs-lookup"><span data-stu-id="59fac-120">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="59fac-121">Porady: zapisywanie tekstu do pliku</span><span class="sxs-lookup"><span data-stu-id="59fac-121">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="59fac-122">Porady: odczytywanie znaków z ciągu</span><span class="sxs-lookup"><span data-stu-id="59fac-122">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [<span data-ttu-id="59fac-123">Porady: zapisywanie znaków ciągu</span><span class="sxs-lookup"><span data-stu-id="59fac-123">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="59fac-124">Plik i strumienia I-O</span><span class="sxs-lookup"><span data-stu-id="59fac-124">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)