---
title: "Porady: odczyt z pliku tekstowego (Przewodnik programowania w języku C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2af6102ac6793b4612a6fbc41f8c50189cc24d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="af8cb-102">Porady: odczyt z pliku tekstowego (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="af8cb-102">How to: Read From a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="af8cb-103">Ten przykład odczytuje zawartość pliku tekstowego za pomocą metod statycznych <xref:System.IO.File.ReadAllText%2A> i <xref:System.IO.File.ReadAllLines%2A> z <xref:System.IO.File?displayProperty=nameWithType> klasy.</span><span class="sxs-lookup"><span data-stu-id="af8cb-103">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=nameWithType> class.</span></span>  
  
 <span data-ttu-id="af8cb-104">Na przykład, który używa <xref:System.IO.StreamReader>, zobacz [porady: jeden wiersz pliku tekstowego do odczytu w czasie](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span><span class="sxs-lookup"><span data-stu-id="af8cb-104">For an example that uses <xref:System.IO.StreamReader>, see [How to: Read a Text File One Line at a Time](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af8cb-105">Pliki, które są używane w tym przykładzie są tworzone w temacie [porady: zapis do pliku tekstowego](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span><span class="sxs-lookup"><span data-stu-id="af8cb-105">The files that are used in this example are created in the topic [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="af8cb-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="af8cb-106">Example</span></span>  
 [!code-csharp[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="af8cb-107">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="af8cb-107">Compiling the Code</span></span>  
 <span data-ttu-id="af8cb-108">Skopiuj kod i wklej go w aplikacji konsolowej C#.</span><span class="sxs-lookup"><span data-stu-id="af8cb-108">Copy the code and paste it into a C# console application.</span></span>  
  
 <span data-ttu-id="af8cb-109">Jeśli nie używasz plików tekstowych z [porady: zapis do pliku tekstowego](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), Zastąp argument `ReadAllText` i `ReadAllLines` z odpowiednią ścieżkę i nazwę komputera.</span><span class="sxs-lookup"><span data-stu-id="af8cb-109">If you are not using the text files from [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="af8cb-110">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="af8cb-110">Robust Programming</span></span>  
 <span data-ttu-id="af8cb-111">Następujące warunki mogą spowodować wyjątek:</span><span class="sxs-lookup"><span data-stu-id="af8cb-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="af8cb-112">Plik nie istnieje lub nie istnieje w określonej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="af8cb-112">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="af8cb-113">Sprawdź ścieżkę i pisownię nazwy pliku.</span><span class="sxs-lookup"><span data-stu-id="af8cb-113">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="af8cb-114">Zabezpieczenia.NET Framework</span><span class="sxs-lookup"><span data-stu-id="af8cb-114">.NET Framework Security</span></span>  
 <span data-ttu-id="af8cb-115">Nie należy polegać na nazwę pliku, aby określić zawartość pliku.</span><span class="sxs-lookup"><span data-stu-id="af8cb-115">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="af8cb-116">Na przykład plik `myFile.cs` może nie być pliku źródłowego C#.</span><span class="sxs-lookup"><span data-stu-id="af8cb-116">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af8cb-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="af8cb-117">See Also</span></span>  
 <xref:System.IO?displayProperty=nameWithType>  
 [<span data-ttu-id="af8cb-118">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="af8cb-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="af8cb-119">System plików i rejestr (C# przewodnik programowania w języku)</span><span class="sxs-lookup"><span data-stu-id="af8cb-119">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)