---
title: "Przy użyciu XSLT do przekształcania drzewo XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3390ca68-c270-4e1d-b64b-6a063a77017c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 18637ecf786c3e44e7a07b5a1ca48cf3c8a4ae35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="using-xslt-to-transform-an-xml-tree-visual-basic"></a><span data-ttu-id="454f4-102">Przy użyciu XSLT do przekształcania drzewo XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="454f4-102">Using XSLT to Transform an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="454f4-103">Można utworzyć drzewa XML, Utwórz <xref:System.Xml.XmlReader> z drzewa XML, Utwórz nowy dokument, a następnie utwórz <xref:System.Xml.XmlWriter> która będzie zapisywała do nowego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="454f4-103">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and create an <xref:System.Xml.XmlWriter> that will write into the new document.</span></span> <span data-ttu-id="454f4-104">Następnie można wywołać przekształcenia XSLT, przekazywanie <xref:System.Xml.XmlReader> i <xref:System.Xml.XmlWriter> do przekształcania.</span><span class="sxs-lookup"><span data-stu-id="454f4-104">Then, you can invoke the XSLT transformation, passing the <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter> to the transformation.</span></span> <span data-ttu-id="454f4-105">Po pomyślnym zakończeniu transformacja, nowe drzewo XML jest wypełniana wyniki transformacji.</span><span class="sxs-lookup"><span data-stu-id="454f4-105">After the transformation successfully completes, the new XML tree is populated with the results of the transform.</span></span>  
  
## <a name="example"></a><span data-ttu-id="454f4-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="454f4-106">Example</span></span>  
  
```vb  
Dim xslMarkup As XDocument = _   
    <?xml version='1.0'?>  
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
    </xsl:stylesheet>  
  
Dim xmlTree As XElement = _   
    <Parent>  
        <Child1>Child1 data</Child1>  
        <Child2>Child2 data</Child2>  
    </Parent>  
  
Dim newTree As XDocument = New XDocument()  
  
Using writer As XmlWriter = newTree.CreateWriter()  
    ' Load the style sheet.  
    Dim xslt As XslCompiledTransform = _  
        New XslCompiledTransform()  
    xslt.Load(xslMarkup.CreateReader())  
  
    ' Execute the transform and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer)  
End Using  
  
Console.WriteLine(newTree)  
```  
  
 <span data-ttu-id="454f4-107">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="454f4-107">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="454f4-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="454f4-108">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.CreateWriter%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XNode.CreateReader%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="454f4-109">Zaawansowane LINQ do XML programowania (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="454f4-109">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)