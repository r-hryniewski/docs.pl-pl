---
title: — Element XML i weryfikacja nazwy atrybutu podczas tworzenia nowych węzłów
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 008cf14e63b8458feebf26eaf27be516bb79f933
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216044"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>— Element XML i weryfikacja nazwy atrybutu podczas tworzenia nowych węzłów
XML Document Object Model (DOM) sprawdza poprawność nazwy, podczas tworzenia nowych węzłów elementów lub węzłów atrybutu. Jeśli nazwy zawiera niedozwolone znaki, jest zgłaszany wyjątek. Aby upewnić się, że nazwy są prawidłowe i zakodowany poprawnie, należy użyć **obiekt XmlConvert** klasy do kodowania nazwę i dekodowania go ponownie na poziomie aplikacji. **XmlWriter** posiada metody, które obsługują dodatkową pracę, aby upewnić się, generowany jest poprawnie sformułowany dokument XML.  
  
## <a name="see-also"></a>Zobacz także

- [Model DOM (XML Document Object Model)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
