---
title: 'Porady: pobieranie pojedynczego atrybutu (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 11b938d7-c011-4048-900e-8b9183c41c94
ms.openlocfilehash: e9e4dce95e9c3202b1cd2a53c186126deac0913c
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332691"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-visual-basic"></a>Porady: pobieranie pojedynczego atrybutu (LINQ to XML) (Visual Basic)
W tym temacie wyjaśniono, jak pobieranie pojedynczego atrybutu elementu, otrzymuje nazwę atrybutu. Jest to przydatne do pisania wyrażeń zapytań, które chcesz znaleźć element, który ma określony atrybut.  
  
 <xref:System.Xml.Linq.XElement.Attribute%2A> Metody <xref:System.Xml.Linq.XElement> klasy zwraca <xref:System.Xml.Linq.XAttribute> o określonej nazwie.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto <xref:System.Xml.Linq.XElement.Attribute%2A> metody.  
  
```vb  
Dim cust As XElement = <PhoneNumbers>  
                           <Phone type="home">555-555-5555</Phone>  
                           <Phone type="work">555-555-6666</Phone>  
                       </PhoneNumbers>  
Dim elList = From el In cust...<Phone>  
For Each e As XElement In elList  
    Console.WriteLine(e.@type)  
Next  
```  
  
 W tym przykładzie wyszukuje wszystkie elementy podrzędne w drzewie o nazwie `Phone`, a następnie znalezienie atrybutu o nazwie `type`.  
  
 Ten kod generuje następujące dane wyjściowe:  
  
```  
home  
work  
```  
  
## <a name="example"></a>Przykład  
 Jeśli chcesz pobrać wartość atrybutu, można rzutować, tak jak w przypadku z <xref:System.Xml.Linq.XElement> obiektów. Poniższy przykład przedstawia to.  
  
```vb  
Dim cust As XElement = <PhoneNumbers>  
                           <Phone type="home">555-555-5555</Phone>  
                           <Phone type="work">555-555-6666</Phone>  
                       </PhoneNumbers>  
Dim elList As IEnumerable(Of XElement) = _  
    From el In cust...<Phone> _  
    Select el  
For Each el As XElement In elList  
    Console.WriteLine(el.@type)  
Next  
```  
  
 Ten kod generuje następujące dane wyjściowe:  
  
```  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] zawiera operatory rzutowania jawnego <xref:System.Xml.Linq.XAttribute> klasy `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`i `GUID?`.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje ten sam kod dla atrybutu, który znajduje się w przestrzeni nazw. Aby uzyskać więcej informacji, zobacz [Praca z przestrzeniami nazw XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim cust As XElement = _  
            <aw:PhoneNumbers>  
                <aw:Phone aw:type="home">555-555-5555</aw:Phone>  
                <aw:Phone aw:type="work">555-555-6666</aw:Phone>  
            </aw:PhoneNumbers>  
        Dim elList As IEnumerable(Of XElement) = _  
            From el In cust...<aw:Phone> _  
            Select el  
        For Each el As XElement In elList  
            Console.WriteLine(el.@aw:type)  
        Next  
    End Sub  
End Module  
```  
  
 Ten kod generuje następujące dane wyjściowe:  
  
```  
home  
work  
```  
  
## <a name="see-also"></a>Zobacz też  
 [LINQ do osi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
