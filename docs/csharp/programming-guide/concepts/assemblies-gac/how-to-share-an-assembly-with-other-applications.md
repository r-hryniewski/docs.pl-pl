---
title: 'Porady: dzielenie się zestawem z innymi aplikacjami (C#)'
ms.date: 07/20/2015
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: a5b20061c759fd914193f24aa123317f13d31dce
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2018
ms.locfileid: "45638399"
---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a>Porady: dzielenie się zestawem z innymi aplikacjami (C#)
Zestawy mogą być prywatne lub udostępnione: domyślnie większości programów proste składają się z zestawu prywatnego, ponieważ nie są przeznaczone do użycia przez inne aplikacje.  
  
 Aby można było dzielenie się zestawem z innymi aplikacjami, muszą być umieszczone w [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).  
  
### <a name="sharing-an-assembly"></a>Współużytkowanie zestawu  
  
1.  Utwórz zestaw. Aby uzyskać więcej informacji, zobacz [tworzenia zestawów](../../../../framework/app-domains/create-assemblies.md).  
  
2.  Do zestawu, należy przypisać silną nazwę. Aby uzyskać więcej informacji, zobacz [porady: podpisywanie zestawu za pomocą silnej nazwy](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
3.  Informacje o wersji należy przypisać do swojego zestawu. Aby uzyskać więcej informacji, zobacz [przechowywanie wersji zestawu](../../../../../docs/framework/app-domains/assembly-versioning.md).  
  
4.  Dodaj zestaw do globalnej pamięci podręcznej zestawów. Aby uzyskać więcej informacji, zobacz [porady: Instalowanie zestawu w globalnej pamięci podręcznej zestawów](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).  
  
5.  Dostęp do typów są zawarte w zestawie z innych aplikacji. Aby uzyskać więcej informacji, zobacz [porady: odwołanie do zestawu Strong-Named](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).  
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../../../../csharp/programming-guide/index.md)  
- [Programowanie za pomocą zestawów](../../../../framework/app-domains/programming-with-assemblies.md)
