---
title: 'Instrukcje: serializacja obiektu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
ms.openlocfilehash: e4d6e3edb15dbf5ba4b7ec7f8658fec1a618d315
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2018
ms.locfileid: "45748578"
---
# <a name="how-to-serialize-an-object"></a>Instrukcje: serializacja obiektu
Do serializacji obiektu, należy najpierw utworzyć obiekt, który ma być serializowany i ustaw jego właściwości publiczne oraz pól. W tym celu należy określić transportu format, w którym strumień XML mają być przechowywane jako strumień lub jako PLik. Na przykład, jeśli strumień XML musi być zapisany w postaci stałe, Utwórz <xref:System.IO.FileStream> obiektu.  
  
> [!NOTE]
>  Aby uzyskać więcej przykładów serializacji XML, zobacz [przykłady serializacji XML](../../../docs/standard/serialization/examples-of-xml-serialization.md).  
  
### <a name="to-serialize-an-object"></a>Do serializacji obiektu  
  
1.  Utworzenie obiektu i ustaw jego publiczny pola i właściwości.  
  
2.  Budowy <xref:System.Xml.Serialization.XmlSerializer> za pomocą typu obiektu. Aby uzyskać więcej informacji, zobacz <xref:System.Xml.Serialization.XmlSerializer> klasy konstruktorów.  
  
3.  Wywołanie <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> metodę w celu wygenerowania strumień XML lub PLik reprezentacja właściwości publiczne i pola obiektu. Poniższy przykład tworzy plik.  
  
    ```vb  
    Dim myObject As MySerializableClass = New MySerializableClass()  
    ' Insert code to set properties and fields of the object.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To write to a file, create a StreamWriter object.  
    Dim myWriter As StreamWriter = New StreamWriter("myFileName.xml")  
    mySerializer.Serialize(myWriter, myObject)  
    myWriter.Close()  
    ```  
  
    ```csharp  
    MySerializableClass myObject = new MySerializableClass();  
    // Insert code to set properties and fields of the object.  
    XmlSerializer mySerializer = new   
    XmlSerializer(typeof(MySerializableClass));  
    // To write to a file, create a StreamWriter object.  
    StreamWriter myWriter = new StreamWriter("myFileName.xml");  
    mySerializer.Serialize(myWriter, myObject);  
    myWriter.Close();  
    ```  
  
## <a name="see-also"></a>Zobacz także

- [Wprowadzenie do serializacji XML](../../../docs/standard/serialization/introducing-xml-serialization.md)  
- [Instrukcje: Deserializacja obiektu](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
