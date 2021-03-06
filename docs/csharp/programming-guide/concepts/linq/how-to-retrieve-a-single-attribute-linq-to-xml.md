---
title: 'Porady: pobieranie pojedynczego atrybutu (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 1b6b07b9-933f-47e9-874e-e790cab49dc5
ms.openlocfilehash: 7e7da2b63b9b46a23fcdbcbea6a0f499de32cf19
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504999"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-c"></a>Porady: pobieranie pojedynczego atrybutu (LINQ to XML) (C#)
W tym temacie wyjaśniono, jak pobieranie pojedynczego atrybutu elementu, otrzymuje nazwę atrybutu. Jest to przydatne do pisania wyrażeń zapytań, które chcesz znaleźć element, który ma określony atrybut.  
  
 <xref:System.Xml.Linq.XElement.Attribute%2A> Metody <xref:System.Xml.Linq.XElement> klasy zwraca <xref:System.Xml.Linq.XAttribute> o określonej nazwie.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto <xref:System.Xml.Linq.XElement.Attribute%2A> metody.  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 W tym przykładzie wyszukuje wszystkie elementy podrzędne w drzewie o nazwie `Phone`, a następnie znalezienie atrybutu o nazwie `type`.  
  
 Ten kod generuje następujące dane wyjściowe:  
  
```  
home  
work  
```  
  
## <a name="example"></a>Przykład  
 Jeśli chcesz pobrać wartość atrybutu, można rzutować, tak jak w przypadku z <xref:System.Xml.Linq.XElement> obiektów. Poniższy przykład przedstawia to.  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =   
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 Ten kod generuje następujące dane wyjściowe:  
  
```  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] zawiera operatory rzutowania jawnego <xref:System.Xml.Linq.XAttribute> klasy `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`i `GUID?`.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje ten sam kod dla atrybutu, który znajduje się w przestrzeni nazw. Aby uzyskać więcej informacji, zobacz [Praca z przestrzeniami nazw XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement cust = new XElement(aw + "PhoneNumbers",  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "home"),  
        "555-555-5555"),  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants(aw + "Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute(aw + "type"));  
```  
  
 Ten kod generuje następujące dane wyjściowe:  
  
```  
home  
work  
```  
  
## <a name="see-also"></a>Zobacz też

- [LINQ do XML osi (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
