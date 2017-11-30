---
title: "Serializacja na element XmlReader (wywoływanie XSLT) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 4cc3ee03-ef4c-429b-a408-fedd10b728cd
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c18fdb5be02be759b3d24b0112b379ae47cc65c6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="serializing-to-an-xmlreader-invoking-xslt-c"></a><span data-ttu-id="7716b-102">Serializacja na element XmlReader (wywoływanie XSLT) (C#)</span><span class="sxs-lookup"><span data-stu-id="7716b-102">Serializing to an XmlReader (Invoking XSLT) (C#)</span></span>
<span data-ttu-id="7716b-103">Jeśli używasz <xref:System.Xml?displayProperty=nameWithType> możliwości współdziałania [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], można użyć <xref:System.Xml.Linq.XNode.CreateReader%2A> do utworzenia <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="7716b-103">When you use the <xref:System.Xml?displayProperty=nameWithType> interoperability capabilities of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can use <xref:System.Xml.Linq.XNode.CreateReader%2A> to create an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="7716b-104">Moduł odczytujący tego <xref:System.Xml.XmlReader> odczytuje węzły drzewa XML i odpowiednio je przetwarza.</span><span class="sxs-lookup"><span data-stu-id="7716b-104">The module that reads from this <xref:System.Xml.XmlReader> reads the nodes from the XML tree and processes them accordingly.</span></span>  
  
## <a name="invoking-an-xslt-transformation"></a><span data-ttu-id="7716b-105">Wywoływanie transformacji XSLT</span><span class="sxs-lookup"><span data-stu-id="7716b-105">Invoking an XSLT Transformation</span></span>  
 <span data-ttu-id="7716b-106">Jedno możliwe użycie tej metody jest wywoływanie transformację XSLT.</span><span class="sxs-lookup"><span data-stu-id="7716b-106">One possible use for this method is when invoking an XSLT transformation.</span></span> <span data-ttu-id="7716b-107">Można utworzyć drzewa XML, Utwórz <xref:System.Xml.XmlReader> z drzewa XML, Utwórz nowy dokument, a następnie utwórz <xref:System.Xml.XmlWriter> zapis do nowego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="7716b-107">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and then create an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="7716b-108">Następnie można wywołać przekształcenia XSLT, przekazując <xref:System.Xml.XmlReader> i <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="7716b-108">Then, you can invoke the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="7716b-109">Po pomyślnym zakończeniu transformacja, nowe drzewo XML jest wypełniana wyniki przekształcenia.</span><span class="sxs-lookup"><span data-stu-id="7716b-109">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
```csharp  
string xslMarkup = @"<?xml version='1.0'?>  
<xsl:stylesheet xmlns:xsl='http://www.w3.org/1999/XSL/Transform' version='1.0'>  
    <xsl:template match='/Parent'>  
        <Root>  
            <C1>  
            <xsl:value-of select='Child1'/>  
            </C1>  
            <C2>  
            <xsl:value-of select='Child2'/>  
            </C2>  
        </Root>  
    </xsl:template>  
</xsl:stylesheet>";  
  
XDocument xmlTree = new XDocument(  
    new XElement("Parent",  
        new XElement("Child1", "Child1 data"),  
        new XElement("Child2", "Child2 data")  
    )  
);  
  
XDocument newTree = new XDocument();  
using (XmlWriter writer = newTree.CreateWriter()) {  
    // Load the style sheet.  
    XslCompiledTransform xslt = new XslCompiledTransform();  
    xslt.Load(XmlReader.Create(new StringReader(xslMarkup)));  
  
    // Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer);  
}  
  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="7716b-110">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="7716b-110">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7716b-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7716b-111">See Also</span></span>  
 [<span data-ttu-id="7716b-112">Serializacja XML drzew (C#)</span><span class="sxs-lookup"><span data-stu-id="7716b-112">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)