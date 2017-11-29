---
title: "Tworzenie schematów XML"
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
- cpp
ms.assetid: 8a5ea56c-0140-4b51-8997-875ae6a8e0cb
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e49c2130702fc7df223f2eab0ea0500b1c27b660
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="building-xml-schemas"></a><span data-ttu-id="ee0e5-102">Tworzenie schematów XML</span><span class="sxs-lookup"><span data-stu-id="ee0e5-102">Building XML Schemas</span></span>
<span data-ttu-id="ee0e5-103">Klasy w <xref:System.Xml.Schema?displayProperty=nameWithType> przestrzeń nazw mapowania do struktury zdefiniowane w sieci World Wide Web konsorcjum W3C zalecenie schematu XML i może służyć do tworzenia XML schematów w pamięci.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-103">The classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace map to the structures defined in the World Wide Web Consortium (W3C) XML Schema Recommendation and can be used to build XML schemas in-memory.</span></span>  
  
## <a name="building-an-xml-schema"></a><span data-ttu-id="ee0e5-104">Tworzenie schematu XML</span><span class="sxs-lookup"><span data-stu-id="ee0e5-104">Building an XML Schema</span></span>  
 <span data-ttu-id="ee0e5-105">W kolejnych przykłady kodu interfejsu API SOM jest używany do tworzenia klienta XML schematu w pamięci.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-105">In the code examples that follow, the SOM API is used to build a customer XML schema in-memory.</span></span>  
  
### <a name="creating-element-and-attributes"></a><span data-ttu-id="ee0e5-106">Tworzenie elementów i atrybutów</span><span class="sxs-lookup"><span data-stu-id="ee0e5-106">Creating Element and Attributes</span></span>  
 <span data-ttu-id="ee0e5-107">Przykłady kodu kompilacji klienta schematu od dołu do góry, tworzenie podrzędne elementy, atrybuty i jako odpowiednie typy najpierw, a następnie elementów najwyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-107">The code examples build the customer schema from the bottom up, creating the child elements, attributes, and their corresponding types first, and then the top-level elements.</span></span>  
  
 <span data-ttu-id="ee0e5-108">W poniższym przykładzie kodu `FirstName` i `LastName` elementów, jak również `CustomerId` atrybut schematu klienta są tworzone przy użyciu <xref:System.Xml.Schema.XmlSchemaElement> i <xref:System.Xml.Schema.XmlSchemaAttribute> klasy SOM.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-108">In the following code example, the `FirstName` and `LastName` elements, as well as the `CustomerId` attribute of the customer schema are created using the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAttribute> classes of the SOM.</span></span> <span data-ttu-id="ee0e5-109">Z wyjątkiem <xref:System.Xml.Schema.XmlSchemaElement.Name%2A> właściwości <xref:System.Xml.Schema.XmlSchemaElement> i <xref:System.Xml.Schema.XmlSchemaAttribute> klasy, które odnoszą się do atrybutu "name" `<xs:element />` i `<xs:attribute />` elementy w schemacie XML z wszystkimi innymi atrybutami dozwolona przez schemat (`defaultValue`, `fixedValue`, `form`i tak dalej) ma w odpowiednich właściwościach <xref:System.Xml.Schema.XmlSchemaElement> i <xref:System.Xml.Schema.XmlSchemaAttribute> klasy.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-109">Apart from the <xref:System.Xml.Schema.XmlSchemaElement.Name%2A> properties of the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAttribute> classes, which correspond to the "name" attribute of the `<xs:element />` and `<xs:attribute />` elements in an XML schema, all other attributes allowed by the schema (`defaultValue`, `fixedValue`, `form`, and so on) have corresponding properties in the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAttribute> classes.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#2](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#2)]
 [!code-csharp[XmlSchemaCreateExample#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#2)]
 [!code-vb[XmlSchemaCreateExample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#2)]  
  
### <a name="creating-schema-types"></a><span data-ttu-id="ee0e5-110">Tworzenie typów schematów</span><span class="sxs-lookup"><span data-stu-id="ee0e5-110">Creating Schema Types</span></span>  
 <span data-ttu-id="ee0e5-111">Zawartość elementów i atrybutów zdefiniowano według ich typów.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-111">The content of elements and attributes is defined by their types.</span></span> <span data-ttu-id="ee0e5-112">Tworzenie elementów i atrybutów, których typy są jednego z typów wbudowanego schematu <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> właściwość <xref:System.Xml.Schema.XmlSchemaElement> lub <xref:System.Xml.Schema.XmlSchemaAttribute> klas są konfigurowane przy użyciu odpowiedniego nazwa kwalifikowana za pomocą typu wbudowanego <xref:System.Xml.XmlQualifiedName> klasy.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-112">To create elements and attributes whose types are one of the built-in schema types, the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> or <xref:System.Xml.Schema.XmlSchemaAttribute> classes are set with the corresponding qualified name of the built-in type using the <xref:System.Xml.XmlQualifiedName> class.</span></span> <span data-ttu-id="ee0e5-113">Aby utworzyć typ zdefiniowany przez użytkownika dla elementów i atrybutów, nowy typ prostymi lub złożonymi jest tworzony przy użyciu <xref:System.Xml.Schema.XmlSchemaSimpleType> lub <xref:System.Xml.Schema.XmlSchemaComplexType> klasy.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-113">To create a user-defined type for elements and attributes, a new simple or complex type is created using the <xref:System.Xml.Schema.XmlSchemaSimpleType> or <xref:System.Xml.Schema.XmlSchemaComplexType> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee0e5-114">Do tworzenia bez nazwy prostej lub złożonych typów, które są anonimowe elementami podrzędnymi elementu lub atrybutu (dotyczy tylko proste typy dla atrybutów), ustaw <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> właściwość <xref:System.Xml.Schema.XmlSchemaElement> lub <xref:System.Xml.Schema.XmlSchemaAttribute> klasy bez nazwy typu prostego lub złożonych, zamiast <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> właściwość <xref:System.Xml.Schema.XmlSchemaElement> lub <xref:System.Xml.Schema.XmlSchemaAttribute> klasy.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-114">To create unnamed simple or complex types that are anonymous children of an element or attribute (only simple types apply for attributes), set the <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> or <xref:System.Xml.Schema.XmlSchemaAttribute> classes to the unnamed simple or complex type, instead of the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> or <xref:System.Xml.Schema.XmlSchemaAttribute> classes.</span></span>  
  
 <span data-ttu-id="ee0e5-115">Schematy XML zezwolić na oba anonimowego i nazwane proste typy dziedziczyć przez ograniczenia z innych typów prostych (wbudowanych i zdefiniowanych przez użytkownika) lub wykonywane w formie listy lub union innych typów prostych.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-115">XML schemas allow both anonymous and named simple types to be derived by restriction from other simple types (built-in or user-defined) or constructed as a list or union of other simple types.</span></span> <span data-ttu-id="ee0e5-116"><xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> Klasy jest używany do tworzenia typu prostego ograniczając wbudowane `xs:string` typu.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-116">The <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> class is used to create a simple type by restricting the built-in `xs:string` type.</span></span> <span data-ttu-id="ee0e5-117">Można również użyć <xref:System.Xml.Schema.XmlSchemaSimpleTypeList> lub <xref:System.Xml.Schema.XmlSchemaSimpleTypeUnion> klasy do tworzenia listy lub union.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-117">You can also use the <xref:System.Xml.Schema.XmlSchemaSimpleTypeList> or <xref:System.Xml.Schema.XmlSchemaSimpleTypeUnion> classes to create list or union types.</span></span> <span data-ttu-id="ee0e5-118"><xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A?displayProperty=nameWithType> Właściwość wskazuje, czy jest on ograniczenie typu prostego, lista lub union.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-118">The <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A?displayProperty=nameWithType> property denotes whether it is a simple type restriction, list, or union.</span></span>  
  
 <span data-ttu-id="ee0e5-119">W poniższym przykładzie kodu `FirstName` elementu typem jest typ wbudowany `xs:string`, `LastName` typ elementu jest typem prostym nazwanego jest ograniczeniem typu wbudowanego `xs:string`, z `MaxLength` wartość aspektu 20, i `CustomerId` typ atrybutu jest typu wbudowanego `xs:positiveInteger`.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-119">In the following code example, the `FirstName` element's type is the built-in type `xs:string`, the `LastName` element's type is a named simple type that is a restriction of the built-in type `xs:string`, with a `MaxLength` facet value of 20, and the `CustomerId` attribute's type is the built-in type `xs:positiveInteger`.</span></span> <span data-ttu-id="ee0e5-120">`Customer` Element jest złożone typu anonimowego, w których jest sekwencja z `FirstName` i `LastName` elementów i atrybutów, których zawiera `CustomerId` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-120">The `Customer` element is an anonymous complex type whose particle is the sequence of the `FirstName` and `LastName` elements and whose attributes contains the `CustomerId` attribute.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee0e5-121">Można również użyć <xref:System.Xml.Schema.XmlSchemaChoice> lub <xref:System.Xml.Schema.XmlSchemaAll> klas jako cząstek typu złożonego do replikowania `<xs:choice />` lub `<xs:all />` semantyki.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-121">You can also use the <xref:System.Xml.Schema.XmlSchemaChoice> or <xref:System.Xml.Schema.XmlSchemaAll> classes as the particle of the complex type to replicate `<xs:choice />` or `<xs:all />` semantics.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#3](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#3)]
 [!code-csharp[XmlSchemaCreateExample#3](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#3)]
 [!code-vb[XmlSchemaCreateExample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#3)]  
  
### <a name="creating-and-compiling-schemas"></a><span data-ttu-id="ee0e5-122">Tworzenie i kompilowania schematów</span><span class="sxs-lookup"><span data-stu-id="ee0e5-122">Creating and Compiling Schemas</span></span>  
 <span data-ttu-id="ee0e5-123">Ten punkt, elementy podrzędne i atrybuty, jako odpowiednie typy i najwyższego poziomu `Customer` element zostały utworzone przy użyciu interfejsu API SOM w pamięci.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-123">At this point, the child elements and attributes, their corresponding types, and the top-level `Customer` element have been created in-memory using the SOM API.</span></span> <span data-ttu-id="ee0e5-124">W poniższym przykładzie kodu element schematu jest tworzony przy użyciu <xref:System.Xml.Schema.XmlSchema> klas, elementów najwyższego poziomu i typy są dodawane do go za pomocą <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> właściwości i pełne schematu została skompilowana przy użyciu <xref:System.Xml.Schema.XmlSchemaSet> klasy i zapisywania ich w w konsoli.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-124">In the following code example, the schema element is created using the <xref:System.Xml.Schema.XmlSchema> class, the top-level elements and types are added to it using the <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> property and the complete schema is compiled using the <xref:System.Xml.Schema.XmlSchemaSet> class and written to the console.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#4](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#4)]
 [!code-csharp[XmlSchemaCreateExample#4](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#4)]
 [!code-vb[XmlSchemaCreateExample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#4)]  
  
 <span data-ttu-id="ee0e5-125"><xref:System.Xml.Schema.XmlSchemaSet.Compile%2A?displayProperty=nameWithType> Metoda sprawdza poprawność schematu klienta względem reguły dla schematu XML i udostępnia właściwości po schema kompilacji.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-125">The <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A?displayProperty=nameWithType> method validates the customer schema against the rules for an XML schema and makes post-schema-compilation properties available.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee0e5-126">Wszystkie właściwości po schema kompilacji w interfejsie API SOM różnią się od po-schema-weryfikacji-obiekt typu Infoset.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-126">All post-schema-compilation properties in the SOM API differ from the Post-Schema-Validation-Infoset.</span></span>  
  
 <span data-ttu-id="ee0e5-127"><xref:System.Xml.Schema.ValidationEventHandler> Dodane do <xref:System.Xml.Schema.XmlSchemaSet> jest delegata, który wywołuje metodę wywołania zwrotnego `ValidationCallback` do obsługi schemat sprawdzania poprawności ostrzeżeń i błędów.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-127">The <xref:System.Xml.Schema.ValidationEventHandler> added to the <xref:System.Xml.Schema.XmlSchemaSet> is a delegate that calls the callback method `ValidationCallback` to handle schema validation warnings and errors.</span></span>  
  
 <span data-ttu-id="ee0e5-128">Poniżej znajduje się pełny przykład kodu i schematu klienta wyświetlony w konsoli.</span><span class="sxs-lookup"><span data-stu-id="ee0e5-128">The following is the complete code example, and the customer schema written to the console.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#1)]
 [!code-csharp[XmlSchemaCreateExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#1)]
 [!code-vb[XmlSchemaCreateExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#1)]  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
   <xs:element name="Customer">  
      <xs:complexType>  
         <xs:sequence>  
            <xs:element name="FirstName" type="xs:string" />  
            <xs:element name="LastName" type="tns:LastNameType" />  
         </xs:sequence>  
         <xs:attribute name="CustomerId" type="xs:positiveInteger" use="required" />  
      </xs:complexType>  
   </xs:element>  
   <xs:simpleType name="LastNameType">  
      <xs:restriction base="xs:string">  
         <xs:maxLength value="20" />  
      </xs:restriction>  
   </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee0e5-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ee0e5-129">See Also</span></span>  
 [<span data-ttu-id="ee0e5-130">Omówienie modelu obiektu schematu XML</span><span class="sxs-lookup"><span data-stu-id="ee0e5-130">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)  
 [<span data-ttu-id="ee0e5-131">Odczytywanie i zapisywanie schematy XML</span><span class="sxs-lookup"><span data-stu-id="ee0e5-131">Reading and Writing XML Schemas</span></span>](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)  
 [<span data-ttu-id="ee0e5-132">Przechodzenie przez schematy XML</span><span class="sxs-lookup"><span data-stu-id="ee0e5-132">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)  
 [<span data-ttu-id="ee0e5-133">Edytowanie schematy XML</span><span class="sxs-lookup"><span data-stu-id="ee0e5-133">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)  
 [<span data-ttu-id="ee0e5-134">W tym lub importowanie schematy XML</span><span class="sxs-lookup"><span data-stu-id="ee0e5-134">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)  
 [<span data-ttu-id="ee0e5-135">Zestaw XmlSchemaSet schematu kompilacji</span><span class="sxs-lookup"><span data-stu-id="ee0e5-135">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 [<span data-ttu-id="ee0e5-136">Obiekt typu Infoset schematu po kompilacji</span><span class="sxs-lookup"><span data-stu-id="ee0e5-136">Post-Schema Compilation Infoset</span></span>](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)