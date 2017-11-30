---
title: Odczytywanie dokumentu XML do modelu DOM
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
ms.assetid: a4fb291f-5630-49ba-a49a-5b66c3b71e49
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b8844705b492574443ff4f37de33ccaf1f5fedd7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="reading-an-xml-document-into-the-dom"></a><span data-ttu-id="c5469-102">Odczytywanie dokumentu XML do modelu DOM</span><span class="sxs-lookup"><span data-stu-id="c5469-102">Reading an XML Document into the DOM</span></span>
<span data-ttu-id="c5469-103">Informacje o XML jest do odczytu do pamięci z różnych formatach.</span><span class="sxs-lookup"><span data-stu-id="c5469-103">XML information is read into memory from different formats.</span></span> <span data-ttu-id="c5469-104">Mogą być odczytywane z ciągiem, strumienia, adres URL, czytnika tekstu lub klasy pochodzącej od <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="c5469-104">It can be read from a string, stream, URL, text reader, or a class derived from the <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="c5469-105"><xref:System.Xml.XmlDocument.Load%2A> Metoda powoduje przeniesienie dokumentu do pamięci i ma skonfigurowane przeciążone metody podjąć danych z każdej z różnych formatach.</span><span class="sxs-lookup"><span data-stu-id="c5469-105">The <xref:System.Xml.XmlDocument.Load%2A> method brings the document into memory and has overloaded methods available to take data from each of the different formats.</span></span> <span data-ttu-id="c5469-106">Istnieje również <xref:System.Xml.XmlDocument.LoadXml%2A> metoda odczytuje z ciągu XML.</span><span class="sxs-lookup"><span data-stu-id="c5469-106">There is also a <xref:System.Xml.XmlDocument.LoadXml%2A> method that reads XML from a string.</span></span>  
  
 <span data-ttu-id="c5469-107">Różne <xref:System.Xml.XmlDocument.Load%2A> metody wpływają na węzły, które są tworzone po załadowaniu XML modelu DOM (Document Object).</span><span class="sxs-lookup"><span data-stu-id="c5469-107">Different <xref:System.Xml.XmlDocument.Load%2A> methods affect which nodes are created when the XML Document Object Model (DOM) is loaded.</span></span> <span data-ttu-id="c5469-108">W poniższej tabeli przedstawiono różnice między niektóre <xref:System.Xml.XmlDocument.Load%2A> metody i tematy, które rozwiązują je.</span><span class="sxs-lookup"><span data-stu-id="c5469-108">The following table lists the differences between some of the <xref:System.Xml.XmlDocument.Load%2A> methods and topics that address them.</span></span>  
  
|<span data-ttu-id="c5469-109">Temat</span><span class="sxs-lookup"><span data-stu-id="c5469-109">Subject</span></span>|<span data-ttu-id="c5469-110">Temat</span><span class="sxs-lookup"><span data-stu-id="c5469-110">Topic</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="c5469-111">Tworzenie węzłów biały znak</span><span class="sxs-lookup"><span data-stu-id="c5469-111">Creation of white space nodes</span></span>|<span data-ttu-id="c5469-112">Obiekt używany do załadowania modelu DOM ma wpływ na biały znak i węzły znaczący biały znak wygenerowanych w modelu DOM.</span><span class="sxs-lookup"><span data-stu-id="c5469-112">The object used to load the DOM has an affect on the white space and significant white space nodes generated in the DOM.</span></span> <span data-ttu-id="c5469-113">Aby uzyskać więcej informacji, zobacz [biały znak i znaczący biały znak obsługi podczas ładowania modelu DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="c5469-113">For more information, see [White Space and Significant White Space Handling when Loading the DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span></span>|  
|<span data-ttu-id="c5469-114">Podczas ładowania XML, zaczynając od określonego węzła lub ładowanie całego dokumentu XML</span><span class="sxs-lookup"><span data-stu-id="c5469-114">Loading XML starting from a specific node or loading the entire XML document</span></span>|<span data-ttu-id="c5469-115">Przy użyciu <xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType> danych metody mogą być ładowane z określonego węzła do modelu DOM.</span><span class="sxs-lookup"><span data-stu-id="c5469-115">Using the <xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType> method data can be loaded from a specific node into the DOM.</span></span> <span data-ttu-id="c5469-116">Aby uzyskać więcej informacji, zobacz [ładowanie danych z czytnika](../../../../docs/standard/data/xml/load-data-from-a-reader.md).</span><span class="sxs-lookup"><span data-stu-id="c5469-116">For more information, see [Load Data from a Reader](../../../../docs/standard/data/xml/load-data-from-a-reader.md).</span></span>|  
|<span data-ttu-id="c5469-117">Sprawdzanie poprawności kodu XML, ponieważ jest załadowana.</span><span class="sxs-lookup"><span data-stu-id="c5469-117">Validating the XML as it is loaded</span></span>|<span data-ttu-id="c5469-118">Mogą być sprawdzone danych XML załadowane do modelu DOM, ponieważ jest on załadowany.</span><span class="sxs-lookup"><span data-stu-id="c5469-118">The XML data loaded into the DOM can be validated as it is loaded.</span></span> <span data-ttu-id="c5469-119">Odbywa się przy użyciu sprawdzania poprawności <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="c5469-119">This is accomplished using a validating <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="c5469-120">Aby uzyskać więcej informacji na temat weryfikowania XML, ponieważ jest on załadowany, zobacz [sprawdzania poprawności dokumentu XML w modelu DOM](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="c5469-120">For more information about validating XML as it is loaded, see [Validating an XML Document in the DOM](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md).</span></span>|  
  
 <span data-ttu-id="c5469-121">W poniższym przykładzie przedstawiono XML ładowany z <xref:System.Xml.XmlDocument.LoadXml%2A> — metoda i dane zapisane następnie w pliku tekstowym o nazwie `data.xml`.</span><span class="sxs-lookup"><span data-stu-id="c5469-121">The following example shows XML being loaded with the <xref:System.Xml.XmlDocument.LoadXml%2A> method and the data subsequently saved to a text file called `data.xml`.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
        ' Create the XmlDocument.  
        Dim doc As New XmlDocument()  
        doc.LoadXml(("<book genre='novel' ISBN='1-861001-57-5'>" & _  
                    "<title>Pride And Prejudice</title>" & _  
                    "</book>"))  
        ' Save the document to a file.  
        doc.Save("data.xml")  
    End Sub 'Main  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    public static void Main()  
    {  
        // Create the XmlDocument.  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5'>" +  
                    "<title>Pride And Prejudice</title>" +  
                    "</book>");  
  
        // Save the document to a file.  
        doc.Save("data.xml");  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5469-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c5469-122">See Also</span></span>  
 [<span data-ttu-id="c5469-123">Modelu obiektu dokumentu XML modelu DOM)</span><span class="sxs-lookup"><span data-stu-id="c5469-123">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)