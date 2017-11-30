---
title: 'Porady: strumienia fragmenty XML z element XmlReader (C#)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 4a8f0e45-768a-42e2-bc5f-68bdf0e0a726
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2fe1bc1122900bab6f65db785027add4e0a8e4f7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-c"></a><span data-ttu-id="1c779-102">Porady: strumienia fragmenty XML z element XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="1c779-102">How to: Stream XML Fragments from an XmlReader (C#)</span></span>
<span data-ttu-id="1c779-103">Podczas przetwarzania dużych plików XML, może nie być możliwe do załadowania całego drzewa XML do pamięci.</span><span class="sxs-lookup"><span data-stu-id="1c779-103">When you have to process large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="1c779-104">W tym temacie przedstawiono sposób strumienia fragmenty przy użyciu <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="1c779-104">This topic shows how to stream fragments using an <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="1c779-105">Jedną z najbardziej skutecznych sposobów użycia <xref:System.Xml.XmlReader> odczytać <xref:System.Xml.Linq.XElement> obiektów jest napisanie własnej metody niestandardowe osi.</span><span class="sxs-lookup"><span data-stu-id="1c779-105">One of the most effective ways to use an <xref:System.Xml.XmlReader> to read <xref:System.Xml.Linq.XElement> objects is to write your own custom axis method.</span></span> <span data-ttu-id="1c779-106">Metoda osi takich jak zwykle zwraca kolekcję <xref:System.Collections.Generic.IEnumerable%601> z <xref:System.Xml.Linq.XElement>, jak pokazano w przykładzie w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="1c779-106">An axis method typically returns a collection such as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, as shown in the example in this topic.</span></span> <span data-ttu-id="1c779-107">W metodzie niestandardowych osi, po utworzeniu fragmentu XML przez wywołanie metody <xref:System.Xml.Linq.XNode.ReadFrom%2A> metody zwrócić przy użyciu kolekcji `yield return`.</span><span class="sxs-lookup"><span data-stu-id="1c779-107">In the custom axis method, after you create the XML fragment by calling the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method, return the collection using `yield return`.</span></span> <span data-ttu-id="1c779-108">Zapewnia to wykonanie odroczone semantyki do metody niestandardowe osi.</span><span class="sxs-lookup"><span data-stu-id="1c779-108">This provides deferred execution semantics to your custom axis method.</span></span>  
  
 <span data-ttu-id="1c779-109">Po utworzeniu drzewo XML z <xref:System.Xml.XmlReader> obiektu <xref:System.Xml.XmlReader> musi być umieszczony w elemencie.</span><span class="sxs-lookup"><span data-stu-id="1c779-109">When you create an XML tree from an <xref:System.Xml.XmlReader> object, the <xref:System.Xml.XmlReader> must be positioned on an element.</span></span> <span data-ttu-id="1c779-110"><xref:System.Xml.Linq.XNode.ReadFrom%2A> Nie może zwracać metoda dopóki odczyta tagu zamknięcia elementu.</span><span class="sxs-lookup"><span data-stu-id="1c779-110">The <xref:System.Xml.Linq.XNode.ReadFrom%2A> method does not return until it has read the close tag of the element.</span></span>  
  
 <span data-ttu-id="1c779-111">Jeśli chcesz utworzyć drzewa częściowe, można utworzyć wystąpienia <xref:System.Xml.XmlReader>, umieść czytnik na węźle, który ma zostać przekonwertowany na <xref:System.Xml.Linq.XElement> drzewa, a następnie utwórz <xref:System.Xml.Linq.XElement> obiektu.</span><span class="sxs-lookup"><span data-stu-id="1c779-111">If you want to create a partial tree, you can instantiate an <xref:System.Xml.XmlReader>, position the reader on the node that you want to convert to an <xref:System.Xml.Linq.XElement> tree, and then create the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
 <span data-ttu-id="1c779-112">Temat [porady: strumień fragmenty XML z dostępem do informacji w nagłówku (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) zawiera informacje i przykład dotyczące strumienia bardziej złożonych dokumentu.</span><span class="sxs-lookup"><span data-stu-id="1c779-112">The topic [How to: Stream XML Fragments with Access to Header Information (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) contains information and an example on how to stream a more complex document.</span></span>  
  
 <span data-ttu-id="1c779-113">Temat [porady: wykonaj przesyłania strumieniowego przekształcenie o dużych dokumentów XML (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) zawiera przykład LINQ do XML do transformacji dokumentów XML wyjątkowa przy zachowaniu zużycia pamięci.</span><span class="sxs-lookup"><span data-stu-id="1c779-113">The topic [How to: Perform Streaming Transform of Large XML Documents (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) contains an example of using LINQ to XML to transform extremely large XML documents while maintaining a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c779-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="1c779-114">Example</span></span>  
 <span data-ttu-id="1c779-115">W tym przykładzie tworzy metodę niestandardowych osi.</span><span class="sxs-lookup"><span data-stu-id="1c779-115">This example creates a custom axis method.</span></span> <span data-ttu-id="1c779-116">Odpytywaną przy użyciu [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] zapytania.</span><span class="sxs-lookup"><span data-stu-id="1c779-116">You can query it by using a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query.</span></span> <span data-ttu-id="1c779-117">Metody niestandardowe osi `StreamRootChildDoc`, to metoda, która jest zaprojektowany specjalnie w celu odczytu dokumentu, który zawiera powtarzające się `Child` elementu.</span><span class="sxs-lookup"><span data-stu-id="1c779-117">The custom axis method, `StreamRootChildDoc`, is a method that is designed specifically to read a document that has a repeating `Child` element.</span></span>  
  
```csharp  
static IEnumerable<XElement> StreamRootChildDoc(StringReader stringReader)  
{  
    using (XmlReader reader = XmlReader.Create(stringReader))  
    {  
        reader.MoveToContent();  
        // Parse the file and display each of the nodes.  
        while (reader.Read())  
        {  
            switch (reader.NodeType)  
            {  
                case XmlNodeType.Element:  
                    if (reader.Name == "Child") {  
                        XElement el = XElement.ReadFrom(reader) as XElement;  
                        if (el != null)  
                            yield return el;  
                    }  
                    break;  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    string markup = @"<Root>  
      <Child Key=""01"">  
        <GrandChild>aaa</GrandChild>  
      </Child>  
      <Child Key=""02"">  
        <GrandChild>bbb</GrandChild>  
      </Child>  
      <Child Key=""03"">  
        <GrandChild>ccc</GrandChild>  
      </Child>  
    </Root>";  
  
    IEnumerable<string> grandChildData =  
        from el in StreamRootChildDoc(new StringReader(markup))  
        where (int)el.Attribute("Key") > 1  
        select (string)el.Element("GrandChild");  
  
    foreach (string str in grandChildData) {  
        Console.WriteLine(str);  
    }  
}  
```  
  
 <span data-ttu-id="1c779-118">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1c779-118">This example produces the following output:</span></span>  
  
```  
bbb  
ccc  
```  
  
 <span data-ttu-id="1c779-119">W tym przykładzie dokument źródłowy jest bardzo mała.</span><span class="sxs-lookup"><span data-stu-id="1c779-119">In this example, the source document is very small.</span></span> <span data-ttu-id="1c779-120">Jednak nawet wtedy, gdy było miliony `Child` elementów, w tym przykładzie nadal będzie miał zużycie pamięci.</span><span class="sxs-lookup"><span data-stu-id="1c779-120">However, even if there were millions of `Child` elements, this example would still have a small memory footprint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c779-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1c779-121">See Also</span></span>  
 [<span data-ttu-id="1c779-122">Analiza kodu XML (C#)</span><span class="sxs-lookup"><span data-stu-id="1c779-122">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)