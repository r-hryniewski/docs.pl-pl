---
title: "Podczas ładowania zestawu danych z pliku XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: db507bf4f90d875960408857c7e6b1e3aa145730
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="loading-a-dataset-from-xml"></a><span data-ttu-id="6eae8-102">Podczas ładowania zestawu danych z pliku XML</span><span class="sxs-lookup"><span data-stu-id="6eae8-102">Loading a DataSet from XML</span></span>
<span data-ttu-id="6eae8-103">Zawartość ADO.NET <xref:System.Data.DataSet> mogą być tworzone z strumień XML lub dokument.</span><span class="sxs-lookup"><span data-stu-id="6eae8-103">The contents of an ADO.NET <xref:System.Data.DataSet> can be created from an XML stream or document.</span></span> <span data-ttu-id="6eae8-104">Ponadto w środowisku .NET Framework masz dużą elastyczność w informacjach są ładowane z pliku XML i w jaki sposób schematu lub relacyjne struktury <xref:System.Data.DataSet> jest tworzony.</span><span class="sxs-lookup"><span data-stu-id="6eae8-104">In addition, with the .NET Framework you have great flexibility over what information is loaded from XML, and how the schema or relational structure of the <xref:System.Data.DataSet> is created.</span></span>  
  
 <span data-ttu-id="6eae8-105">Aby wypełnić <xref:System.Data.DataSet> za pomocą danych z pliku XML, użyj **ReadXml** metody <xref:System.Data.DataSet> obiektu.</span><span class="sxs-lookup"><span data-stu-id="6eae8-105">To fill a <xref:System.Data.DataSet> with data from XML, use the **ReadXml** method of the <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="6eae8-106">**ReadXml** metoda odczytuje z pliku, typu stream, lub **XmlReader**i przyjmuje jako argumenty źródło XML oraz opcjonalny **XmlReadMode** argumentu.</span><span class="sxs-lookup"><span data-stu-id="6eae8-106">The **ReadXml** method reads from a file, a stream, or an **XmlReader**, and takes as arguments the source of the XML plus an optional **XmlReadMode** argument.</span></span> <span data-ttu-id="6eae8-107">(Aby uzyskać więcej informacji na temat **XmlReader**, zobacz [NIB: odczytywanie danych XML za pomocą klasy XmlTextReader](http://msdn.microsoft.com/en-us/762c069b-b50c-41b8-936e-39eacfb0d540).) **ReadXml** metoda odczytuje zawartość strumienia XML lub dokument i obciążeń <xref:System.Data.DataSet> z danymi.</span><span class="sxs-lookup"><span data-stu-id="6eae8-107">(For more information about the **XmlReader**, see [NIB: Reading XML Data with XmlTextReader](http://msdn.microsoft.com/en-us/762c069b-b50c-41b8-936e-39eacfb0d540).) The **ReadXml** method reads the contents of the XML stream or document and loads the <xref:System.Data.DataSet> with data.</span></span> <span data-ttu-id="6eae8-108">Spowoduje również utworzenie schemat relacyjny <xref:System.Data.DataSet> w zależności od **XmlReadMode** określone i określa, czy schemat relacyjny już istnieje.</span><span class="sxs-lookup"><span data-stu-id="6eae8-108">It will also create the relational schema of the <xref:System.Data.DataSet> depending on the **XmlReadMode** specified and whether or not a relational schema already exists.</span></span>  
  
 <span data-ttu-id="6eae8-109">W poniższej tabeli opisano opcje **XmlReadMode** argumentu.</span><span class="sxs-lookup"><span data-stu-id="6eae8-109">The following table describes the options for the **XmlReadMode** argument.</span></span>  
  
|<span data-ttu-id="6eae8-110">Opcja</span><span class="sxs-lookup"><span data-stu-id="6eae8-110">Option</span></span>|<span data-ttu-id="6eae8-111">Opis</span><span class="sxs-lookup"><span data-stu-id="6eae8-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="6eae8-112">**Automatycznie**</span><span class="sxs-lookup"><span data-stu-id="6eae8-112">**Auto**</span></span>|<span data-ttu-id="6eae8-113">Domyślnie włączone.</span><span class="sxs-lookup"><span data-stu-id="6eae8-113">This is the default.</span></span> <span data-ttu-id="6eae8-114">Sprawdza kod XML i wybierze najbardziej odpowiednią opcję w następującej kolejności:</span><span class="sxs-lookup"><span data-stu-id="6eae8-114">Examines the XML and chooses the most appropriate option in the following order:</span></span><br /><br /> <span data-ttu-id="6eae8-115">— Jeśli kod XML jest elementu DiffGram **elementu DiffGram** jest używany.</span><span class="sxs-lookup"><span data-stu-id="6eae8-115">-   If the XML is a DiffGram, **DiffGram** is used.</span></span><br /><span data-ttu-id="6eae8-116">-Jeśli <xref:System.Data.DataSet> zawiera schemat lub wbudowany schemat zawiera kod XML **ReadSchema** jest używany.</span><span class="sxs-lookup"><span data-stu-id="6eae8-116">-   If the <xref:System.Data.DataSet> contains a schema or the XML contains an inline schema, **ReadSchema** is used.</span></span><br /><span data-ttu-id="6eae8-117">-Jeśli <xref:System.Data.DataSet> nie zawiera schemat i plik XML nie zawiera schemat wbudowany **InferSchema** jest używany.</span><span class="sxs-lookup"><span data-stu-id="6eae8-117">-   If the <xref:System.Data.DataSet> does not contain a schema and the XML does not contain an inline schema, **InferSchema** is used.</span></span><br /><br /> <span data-ttu-id="6eae8-118">Jeśli znasz format odczytywanego pliku XML, aby uzyskać najlepszą wydajność zaleca się ustawienie jawnego **XmlReadMode**, zamiast niż zaakceptować **automatycznie** domyślne.</span><span class="sxs-lookup"><span data-stu-id="6eae8-118">If you know the format of the XML being read, for best performance it is recommended that you set an explicit **XmlReadMode**, rather than accept the **Auto** default.</span></span>|  
|<span data-ttu-id="6eae8-119">**ReadSchema**</span><span class="sxs-lookup"><span data-stu-id="6eae8-119">**ReadSchema**</span></span>|<span data-ttu-id="6eae8-120">Odczytuje wszystkie wbudowanego schematu i ładuje danych i schematu.</span><span class="sxs-lookup"><span data-stu-id="6eae8-120">Reads any inline schema and loads the data and schema.</span></span><br /><br /> <span data-ttu-id="6eae8-121">Jeśli <xref:System.Data.DataSet> już zawiera schemat, nowe tabele są dodawane z wbudowanego schematu istniejący schemat w <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6eae8-121">If the <xref:System.Data.DataSet> already contains a schema, new tables are added from the inline schema to the existing schema in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6eae8-122">Jeśli wszystkie tabele w wbudowany schemat już istnieje w <xref:System.Data.DataSet>, jest zgłaszany wyjątek.</span><span class="sxs-lookup"><span data-stu-id="6eae8-122">If any tables in the inline schema already exist in the <xref:System.Data.DataSet>, an exception is thrown.</span></span> <span data-ttu-id="6eae8-123">Nie można zmodyfikować schemat istniejących przy użyciu tabeli **XmlReadMode.ReadSchema**.</span><span class="sxs-lookup"><span data-stu-id="6eae8-123">You will not be able to modify the schema of an existing table using **XmlReadMode.ReadSchema**.</span></span><br /><br /> <span data-ttu-id="6eae8-124">Jeśli <xref:System.Data.DataSet> nie zawiera schematu, a nie Brak schemat wbudowany, nie są odczytywane dane.</span><span class="sxs-lookup"><span data-stu-id="6eae8-124">If the <xref:System.Data.DataSet> does not contain a schema, and there is no inline schema, no data is read.</span></span><br /><br /> <span data-ttu-id="6eae8-125">Wbudowany schemat można zdefiniować przy użyciu schematu (XSD) języka definicji schematu XML.</span><span class="sxs-lookup"><span data-stu-id="6eae8-125">Inline schema can be defined using XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="6eae8-126">Aby uzyskać informacje na temat pisania wbudowanego schematu XML Schema, zobacz [wyprowadzanie struktury relacyjne zestawu danych z schematu XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="6eae8-126">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>|  
|<span data-ttu-id="6eae8-127">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="6eae8-127">**IgnoreSchema**</span></span>|<span data-ttu-id="6eae8-128">Ignoruje wszystkie wbudowanego schematu i ładuje dane do istniejącego <xref:System.Data.DataSet> schematu.</span><span class="sxs-lookup"><span data-stu-id="6eae8-128">Ignores any inline schema and loads the data into the existing <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="6eae8-129">Dane, które nie pasuje do istniejącego schematu zostaną odrzucone.</span><span class="sxs-lookup"><span data-stu-id="6eae8-129">Any data that does not match the existing schema is discarded.</span></span> <span data-ttu-id="6eae8-130">Jeśli schemat nie istnieje w <xref:System.Data.DataSet>, jest załadowane żadne dane.</span><span class="sxs-lookup"><span data-stu-id="6eae8-130">If no schema exists in the <xref:System.Data.DataSet>, no data is loaded.</span></span><br /><br /> <span data-ttu-id="6eae8-131">Jeśli dane są elementu DiffGram **IgnoreSchema** ma te same funkcje co **elementu DiffGram** *.*</span><span class="sxs-lookup"><span data-stu-id="6eae8-131">If the data is a DiffGram, **IgnoreSchema** has the same functionality as **DiffGram** *.*</span></span>|  
|<span data-ttu-id="6eae8-132">**InferSchema**</span><span class="sxs-lookup"><span data-stu-id="6eae8-132">**InferSchema**</span></span>|<span data-ttu-id="6eae8-133">Ignoruje wszystkie wbudowanego schematu i wnioskuje schemat na strukturze danych XML, a następnie ładuje dane.</span><span class="sxs-lookup"><span data-stu-id="6eae8-133">Ignores any inline schema and infers the schema per the structure of the XML data, then loads the data.</span></span><br /><br /> <span data-ttu-id="6eae8-134">Jeśli <xref:System.Data.DataSet> już zawiera schemat, bieżący schemat jest rozszerzony przez dodawanie kolumn do istniejących tabel.</span><span class="sxs-lookup"><span data-stu-id="6eae8-134">If the <xref:System.Data.DataSet> already contains a schema, the current schema is extended by adding columns to existing tables.</span></span> <span data-ttu-id="6eae8-135">Dodatkowe tabele nie zostanie dodany, jeśli nie istnieją tabele.</span><span class="sxs-lookup"><span data-stu-id="6eae8-135">Extra tables will not be added if there are not existing tables.</span></span> <span data-ttu-id="6eae8-136">Jeśli wnioskowany tabela już istnieje z różnych przestrzeni nazw lub kolumn wnioskowany powodują konflikt z istniejących kolumn, jest zgłaszany wyjątek.</span><span class="sxs-lookup"><span data-stu-id="6eae8-136">An exception is thrown if an inferred table already exists with a different namespace, or if any inferred columns conflict with existing columns.</span></span><br /><br /> <span data-ttu-id="6eae8-137">Aby uzyskać szczegółowe informacje o tym, jak **ReadXmlSchema** wnioskuje schemat dokumentu XML, zobacz temat [wnioskowanie struktury zestawu danych relacyjnych z pliku XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6eae8-137">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span></span>|  
|<span data-ttu-id="6eae8-138">**Elementu DiffGram**</span><span class="sxs-lookup"><span data-stu-id="6eae8-138">**DiffGram**</span></span>|<span data-ttu-id="6eae8-139">Odczytuje elementu DiffGram i dodaje je do bieżącego schematu.</span><span class="sxs-lookup"><span data-stu-id="6eae8-139">Reads a DiffGram and adds the data to the current schema.</span></span> <span data-ttu-id="6eae8-140">**Elementu DiffGram** scala nowe wiersze z istniejących wierszy, jeśli takie same wartości unikatowego identyfikatora.</span><span class="sxs-lookup"><span data-stu-id="6eae8-140">**DiffGram** merges new rows with existing rows where the unique identifier values match.</span></span> <span data-ttu-id="6eae8-141">Zobacz "Scalanie danych z pliku XML" na końcu tego tematu.</span><span class="sxs-lookup"><span data-stu-id="6eae8-141">See "Merging Data from XML" at the end of this topic.</span></span> <span data-ttu-id="6eae8-142">Aby uzyskać więcej informacji o DataSets, zobacz [DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span><span class="sxs-lookup"><span data-stu-id="6eae8-142">For more information about DiffGrams, see [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span></span>|  
|<span data-ttu-id="6eae8-143">**Fragment**</span><span class="sxs-lookup"><span data-stu-id="6eae8-143">**Fragment**</span></span>|<span data-ttu-id="6eae8-144">Nadal odczytywania wielu fragmenty XML, aż do osiągnięcia końca strumienia.</span><span class="sxs-lookup"><span data-stu-id="6eae8-144">Continues reading multiple XML fragments until the end of the stream is reached.</span></span> <span data-ttu-id="6eae8-145">Fragmenty zgodnych <xref:System.Data.DataSet> schematu są dołączane do odpowiednich tabel.</span><span class="sxs-lookup"><span data-stu-id="6eae8-145">Fragments that match the <xref:System.Data.DataSet> schema are appended to the appropriate tables.</span></span> <span data-ttu-id="6eae8-146">Fragmenty, które nie odpowiadają <xref:System.Data.DataSet> schematu zostaną odrzucone.</span><span class="sxs-lookup"><span data-stu-id="6eae8-146">Fragments that do not match the <xref:System.Data.DataSet> schema are discarded.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="6eae8-147">W przypadku przekazania **XmlReader** do **ReadXml** będącego pozycjonowane częścią sposób w dokumencie XML **ReadXml** odczyta do następnego węzła elementu i będzie traktować który jako katalogu głównego Element Odczyt do końca tylko węzeł elementu.</span><span class="sxs-lookup"><span data-stu-id="6eae8-147">If you pass an **XmlReader** to **ReadXml** that is positioned part of the way into an XML document, **ReadXml** will read to the next element node and will treat that as the root element, reading until the end of the element node only.</span></span> <span data-ttu-id="6eae8-148">Nie dotyczy Jeśli określisz **XmlReadMode.Fragment**.</span><span class="sxs-lookup"><span data-stu-id="6eae8-148">This does not apply if you specify **XmlReadMode.Fragment**.</span></span>  
  
## <a name="dtd-entities"></a><span data-ttu-id="6eae8-149">DTD jednostek</span><span class="sxs-lookup"><span data-stu-id="6eae8-149">DTD Entities</span></span>  
 <span data-ttu-id="6eae8-150">Jeśli dane XML zawiera jednostki zdefiniowanej w schemacie definicji (DTD) typu dokumentu, będzie zgłaszany wyjątek, jeśli próba załadowania <xref:System.Data.DataSet> przez przekazanie pliku nazwy, strumienia lub bez weryfikacji **XmlReader** do  **ReadXml**.</span><span class="sxs-lookup"><span data-stu-id="6eae8-150">If your XML contains entities defined in a document type definition (DTD) schema, an exception will be thrown if you attempt to load a <xref:System.Data.DataSet> by passing a file name, stream, or non-validating **XmlReader** to **ReadXml**.</span></span> <span data-ttu-id="6eae8-151">Zamiast tego należy utworzyć **elementu XmlValidatingReader**, z **EntityHandling** ustawioną **elementu EntityHandling.ExpandEntities**i przekazywać Twoje  **Elementu XmlValidatingReader** do **ReadXml**.</span><span class="sxs-lookup"><span data-stu-id="6eae8-151">Instead, you must create an **XmlValidatingReader**, with **EntityHandling** set to **EntityHandling.ExpandEntities**, and pass your **XmlValidatingReader** to **ReadXml**.</span></span> <span data-ttu-id="6eae8-152">**Elementu XmlValidatingReader** rozwinie jednostek przed odczytywany przez <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6eae8-152">The **XmlValidatingReader** will expand the entities prior to being read by the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="6eae8-153">W poniższych przykładach kodu przedstawiają sposób załadować <xref:System.Data.DataSet> ze strumienia XML.</span><span class="sxs-lookup"><span data-stu-id="6eae8-153">The following code examples show how to load a <xref:System.Data.DataSet> from an XML stream.</span></span> <span data-ttu-id="6eae8-154">W pierwszym przykładzie pokazano przekazywany do nazwy pliku **ReadXml** metody.</span><span class="sxs-lookup"><span data-stu-id="6eae8-154">The first example shows a file name being passed to the **ReadXml** method.</span></span> <span data-ttu-id="6eae8-155">Drugi przykład przedstawia ciąg, który zawiera XML jest załadować przy użyciu <xref:System.IO.StringReader>.</span><span class="sxs-lookup"><span data-stu-id="6eae8-155">The second example shows a string that contains XML being loaded using a <xref:System.IO.StringReader>.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema);  
```  
  
```vb  
Dim dataSet As DataSet = New DataSet  
Dim dataTable As DataTable = New DataTable("table1")  
dataTable.Columns.Add("col1", Type.GetType("System.String"))  
dataSet.Tables.Add(dataTable)  
  
Dim xmlData As String = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>"  
  
Dim xmlSR As System.IO.StringReader = New System.IO.StringReader(xmlData)  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
DataTable dataTable = new DataTable("table1");  
dataTable.Columns.Add("col1", typeof(string));  
dataSet.Tables.Add(dataTable);  
  
string xmlData = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>";  
  
System.IO.StringReader xmlSR = new System.IO.StringReader(xmlData);  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema);  
```  
  
> [!NOTE]
>  <span data-ttu-id="6eae8-156">Jeśli należy wywołać **ReadXml** załadować bardzo dużych plików, można napotkać niską wydajność.</span><span class="sxs-lookup"><span data-stu-id="6eae8-156">If you call **ReadXml** to load a very large file, you may encounter slow performance.</span></span> <span data-ttu-id="6eae8-157">Aby zapewnić najlepszą wydajność dla **ReadXml**, na dużych plików, należy wywołać <xref:System.Data.DataTable.BeginLoadData%2A> metody dla każdej tabeli w <xref:System.Data.DataSet>, a następnie wywołać **ReadXml**.</span><span class="sxs-lookup"><span data-stu-id="6eae8-157">To ensure best performance for **ReadXml**, on a large file, call the <xref:System.Data.DataTable.BeginLoadData%2A> method for each table in the <xref:System.Data.DataSet>, and then call **ReadXml**.</span></span> <span data-ttu-id="6eae8-158">Na koniec wywołania <xref:System.Data.DataTable.EndLoadData%2A> dla każdej tabeli w <xref:System.Data.DataSet>, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="6eae8-158">Finally, call <xref:System.Data.DataTable.EndLoadData%2A> for each table in the <xref:System.Data.DataSet>, as shown in the following example.</span></span>  
  
```vb  
Dim dataTable As DataTable  
  
For Each dataTable In dataSet.Tables  
   dataTable.BeginLoadData()  
Next  
  
dataSet.ReadXml("file.xml")  
  
For Each dataTable in dataSet.Tables  
   dataTable.EndLoadData()  
Next  
```  
  
```csharp  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.BeginLoadData();  
  
dataSet.ReadXml("file.xml");   
  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.EndLoadData();  
```  
  
> [!NOTE]
>  <span data-ttu-id="6eae8-159">Jeśli schematu XSD dla Twojego <xref:System.Data.DataSet> obejmuje **targetNamespace**, nie można odczytać danych i wyjątków, mogą wystąpić podczas wywoływania metody **ReadXml** załadować <xref:System.Data.DataSet> XML, który zawiera elementy bez kwalifikacji przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="6eae8-159">If the XSD schema for your <xref:System.Data.DataSet> includes a **targetNamespace**, data may not be read, and you may encounter exceptions, when calling **ReadXml** to load the <xref:System.Data.DataSet> with XML that contains elements with no qualifying namespace.</span></span> <span data-ttu-id="6eae8-160">W takim przypadku odczytać niekwalifikowane elementy, ustaw **elementFormDefault** równa "kwalifikowana" schematu XSD.</span><span class="sxs-lookup"><span data-stu-id="6eae8-160">To read unqualified elements in this case, set **elementFormDefault** equal to "qualified" in your XSD schema.</span></span> <span data-ttu-id="6eae8-161">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="6eae8-161">For example:</span></span>  
  
```xml  
<xsd:schema id="customDataSet"   
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"   
  xmlns="http://www.tempuri.org/customDataSet.xsd"   
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a><span data-ttu-id="6eae8-162">Scalanie danych z pliku XML</span><span class="sxs-lookup"><span data-stu-id="6eae8-162">Merging Data from XML</span></span>  
 <span data-ttu-id="6eae8-163">Jeśli <xref:System.Data.DataSet> zawiera już dane, nowych danych z pliku XML jest dodana do danych znajduje się już w <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6eae8-163">If the <xref:System.Data.DataSet> already contains data, the new data from the XML is added to the data already present in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6eae8-164">**ReadXml** nie scalania z pliku XML do <xref:System.Data.DataSet> żadnego wiersza informacji ze zgodnymi kluczami podstawowymi.</span><span class="sxs-lookup"><span data-stu-id="6eae8-164">**ReadXml** does not merge from the XML into the <xref:System.Data.DataSet> any row information with matching primary keys.</span></span> <span data-ttu-id="6eae8-165">Aby zastąpić istniejące informacje wiersza z nowych informacji z pliku XML, użyj **ReadXml** do tworzenia nowego <xref:System.Data.DataSet>, a następnie <xref:System.Data.DataSet.Merge%2A> nowy <xref:System.Data.DataSet> do istniejącego <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6eae8-165">To overwrite existing row information with new information from XML, use **ReadXml** to create a new <xref:System.Data.DataSet>, and then <xref:System.Data.DataSet.Merge%2A> the new <xref:System.Data.DataSet> into the existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6eae8-166">Należy pamiętać, że podczas ładowania elementu DiffGram przy użyciu **ReadXML** z **XmlReadMode** z **elementu DiffGram** będzie scalenie wierszy, które mają ten sam Unikatowy identyfikator.</span><span class="sxs-lookup"><span data-stu-id="6eae8-166">Note that loading a DiffGram using **ReadXML** with an **XmlReadMode** of **DiffGram** will merge rows that have the same unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eae8-167">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6eae8-167">See Also</span></span>  
 <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="6eae8-168">Za pomocą języka XML w zestawie danych</span><span class="sxs-lookup"><span data-stu-id="6eae8-168">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="6eae8-169">DataSets</span><span class="sxs-lookup"><span data-stu-id="6eae8-169">DiffGrams</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 [<span data-ttu-id="6eae8-170">Wyprowadzanie relacyjne struktury zestawu danych z schematu XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="6eae8-170">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="6eae8-171">Wnioskowanie struktury zestawu danych relacyjnych z pliku XML</span><span class="sxs-lookup"><span data-stu-id="6eae8-171">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="6eae8-172">Ładowanie informacji o schemacie zestawu danych z pliku XML</span><span class="sxs-lookup"><span data-stu-id="6eae8-172">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="6eae8-173">Zbiory danych, DataTables i DataViews</span><span class="sxs-lookup"><span data-stu-id="6eae8-173">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="6eae8-174">ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów</span><span class="sxs-lookup"><span data-stu-id="6eae8-174">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)