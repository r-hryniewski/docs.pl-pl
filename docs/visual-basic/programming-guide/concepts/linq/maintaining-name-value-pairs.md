---
title: "Obsługa pary nazwa wartość (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57ac2072-d9f5-432b-84f0-a889c62fd813
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e2743b7ce09db2ec2695c04eeef631a33fa2c289
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="maintaining-namevalue-pairs-visual-basic"></a><span data-ttu-id="521f4-102">Obsługa pary nazwa/wartość (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="521f4-102">Maintaining Name/Value Pairs (Visual Basic)</span></span>
<span data-ttu-id="521f4-103">Wiele aplikacji ma do przechowywania informacji, które najlepiej jest przechowywane jako pary nazwa/wartość.</span><span class="sxs-lookup"><span data-stu-id="521f4-103">Many applications have to maintain information that is best kept as name/value pairs.</span></span> <span data-ttu-id="521f4-104">Informacje te mogą być informacje o konfiguracji lub ustawień globalnych.</span><span class="sxs-lookup"><span data-stu-id="521f4-104">This information might be configuration information or global settings.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="521f4-105">zawiera niektórych metod, które ułatwiają Zachowaj zestaw par nazwa/wartość.</span><span class="sxs-lookup"><span data-stu-id="521f4-105"> contains some methods that make it easy to keep a set of name/value pairs.</span></span> <span data-ttu-id="521f4-106">Możesz zachować informacje jako atrybuty lub zbiór podrzędnych elementów.</span><span class="sxs-lookup"><span data-stu-id="521f4-106">You can either keep the information as attributes or as a set of child elements.</span></span>  
  
 <span data-ttu-id="521f4-107">Jeden różnica między jednoczesnym zachowaniu bezpieczeństwa informacji jako atrybuty lub jako elementy podrzędne jest atrybuty ograniczenia, że może istnieć tylko jeden atrybut o określonej nazwie dla elementu.</span><span class="sxs-lookup"><span data-stu-id="521f4-107">One difference between keeping the information as attributes or as child elements is that attributes have the constraint that there can be only one attribute with a particular name for an element.</span></span> <span data-ttu-id="521f4-108">To ograniczenie nie ma zastosowania do elementów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="521f4-108">This limitation does not apply to child elements.</span></span>  
  
## <a name="setattributevalue-and-setelementvalue"></a><span data-ttu-id="521f4-109">SetAttributeValue i SetElementValue</span><span class="sxs-lookup"><span data-stu-id="521f4-109">SetAttributeValue and SetElementValue</span></span>  
 <span data-ttu-id="521f4-110">Te dwie metody, które ułatwiają utrzymanie par nazwa/wartość są <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> i <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="521f4-110">The two methods that facilitate keeping name/value pairs are <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> and <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span></span> <span data-ttu-id="521f4-111">Te dwie metody mają podobne semantyki.</span><span class="sxs-lookup"><span data-stu-id="521f4-111">These two methods have similar semantics.</span></span>  
  
 <span data-ttu-id="521f4-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A>można dodać, modyfikowanie lub usuwanie atrybutów elementu.</span><span class="sxs-lookup"><span data-stu-id="521f4-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> can add, modify, or remove attributes of an element.</span></span>  
  
-   <span data-ttu-id="521f4-113">Jeśli należy wywołać <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> z nazwą atrybutu, który nie istnieje, metoda tworzy nowy atrybut i dodaje go do określonego elementu.</span><span class="sxs-lookup"><span data-stu-id="521f4-113">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an attribute that does not exist, the method creates a new attribute and adds it to the specified element.</span></span>  
  
-   <span data-ttu-id="521f4-114">Jeśli należy wywołać <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> z nazwą istniejącego atrybutu i niektóre określone zawartości, zawartość atrybutu są zastępowane z określoną zawartością.</span><span class="sxs-lookup"><span data-stu-id="521f4-114">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute and with some specified content, the contents of the attribute are replaced with the specified content.</span></span>  
  
-   <span data-ttu-id="521f4-115">Wywołanie <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> z nazwą istniejącego atrybutu, a następnie określ wartość null dla zawartości, atrybut jest usuwany po swoim obiekcie nadrzędnym.</span><span class="sxs-lookup"><span data-stu-id="521f4-115">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute, and specify null for the content, the attribute is removed from its parent.</span></span>  
  
 <span data-ttu-id="521f4-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A>można dodać, modyfikowanie lub usuwanie elementów podrzędnych danego elementu.</span><span class="sxs-lookup"><span data-stu-id="521f4-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A> can add, modify, or remove child elements of an element.</span></span>  
  
-   <span data-ttu-id="521f4-117">Jeśli należy wywołać <xref:System.Xml.Linq.XElement.SetElementValue%2A> z nazwą elementu podrzędnego, który nie istnieje, metoda tworzy nowy element i dodaje go do określonego elementu.</span><span class="sxs-lookup"><span data-stu-id="521f4-117">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of a child element that does not exist, the method creates a new element and adds it to the specified element.</span></span>  
  
-   <span data-ttu-id="521f4-118">Jeśli należy wywołać <xref:System.Xml.Linq.XElement.SetElementValue%2A> z nazwą istniejącego elementu i niektóre określone zawartości, zawartość elementu są zastępowane z określoną zawartością.</span><span class="sxs-lookup"><span data-stu-id="521f4-118">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element and with some specified content, the contents of the element are replaced with the specified content.</span></span>  
  
-   <span data-ttu-id="521f4-119">Jeśli należy wywołać <xref:System.Xml.Linq.XElement.SetElementValue%2A> z nazwą istniejącego elementu i określ wartość null dla zawartości, element zostanie usunięty z jego elementu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="521f4-119">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element, and specify null for the content, the element is removed from its parent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="521f4-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="521f4-120">Example</span></span>  
 <span data-ttu-id="521f4-121">Poniższy przykład tworzy element bez atrybutów.</span><span class="sxs-lookup"><span data-stu-id="521f4-121">The following example creates an element with no attributes.</span></span> <span data-ttu-id="521f4-122">Następnie używa <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> metodę, aby utworzyć i zachować listę par nazwa/wartość.</span><span class="sxs-lookup"><span data-stu-id="521f4-122">It then uses the <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22)  
root.SetAttributeValue("Left", 20)  
root.SetAttributeValue("Bottom", 122)  
root.SetAttributeValue("Right", 300)  
root.SetAttributeValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
  
' Replace the value of Top.  
root.SetAttributeValue("Top", 10)  
Console.WriteLine(root)  
  
' Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="521f4-123">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="521f4-123">This example produces the following output:</span></span>  
  
```xml  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a><span data-ttu-id="521f4-124">Przykład</span><span class="sxs-lookup"><span data-stu-id="521f4-124">Example</span></span>  
 <span data-ttu-id="521f4-125">Poniższy przykład tworzy element z nie podrzędnych elementów.</span><span class="sxs-lookup"><span data-stu-id="521f4-125">The following example creates an element with no child elements.</span></span> <span data-ttu-id="521f4-126">Następnie używa <xref:System.Xml.Linq.XElement.SetElementValue%2A> metodę, aby utworzyć i zachować listę par nazwa/wartość.</span><span class="sxs-lookup"><span data-stu-id="521f4-126">It then uses the <xref:System.Xml.Linq.XElement.SetElementValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22)  
root.SetElementValue("Left", 20)  
root.SetElementValue("Bottom", 122)  
root.SetElementValue("Right", 300)  
root.SetElementValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Replace the value of Top.  
root.SetElementValue("Top", 10)  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Remove DefaultColor.  
root.SetElementValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="521f4-127">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="521f4-127">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Top>22</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="521f4-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="521f4-128">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
 <xref:System.Xml.Linq.XElement.SetElementValue%2A>  
 [<span data-ttu-id="521f4-129">Modyfikowanie drzew XML (LINQ do XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="521f4-129">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)