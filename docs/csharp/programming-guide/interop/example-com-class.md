---
title: Klasa COM — Przykład (Przewodnik programowania w języku C#)
ms.date: 07/20/2015
helpviewer_keywords:
- examples [C#], COM classes
- COM, exposing Visual C# objects to
ms.assetid: 6504dea9-ad1c-4993-a794-830fec5270af
ms.openlocfilehash: a77f022b4cf7659d506a7893923ce47270cb8c1b
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2018
ms.locfileid: "45745484"
---
# <a name="example-com-class-c-programming-guide"></a>Klasa COM — Przykład (Przewodnik programowania w języku C#)
Oto przykład klasy, który może narazić jako obiekt COM. Po ten kod został umieszczony w pliku CS i dodane do projektu, ustawić **Zarejestruj dla współdziałania COM** właściwości **True**. Aby uzyskać więcej informacji, zobacz [jak: Zarejestruj składnik COM Interop](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w29wacsy(v=vs.100)).
  
 Udostępnianie obiektów Visual C# dla modelu COM wymaga zadeklarowania interfejsu klasy, interfejsu zdarzenia w razie potrzeby i samej klasy. Elementy członkowskie klasy muszą wykonać następujące czynności, które mają być widoczne dla modelu COM:  
  
-   Klasy muszą być publiczne.  
  
-   Właściwości, metody i zdarzenia muszą być publiczne.  
  
-   Właściwości i metody musi być zadeklarowana w klasie interfejs.  
  
-   Zdarzenia musi być zadeklarowany w zdarzeniu interfejsu.  
  
 Inne publiczne elementy członkowskie klasy, które nie są zadeklarowane za pomocą tych interfejsów nie będą widoczne dla modelu COM, ale będą one widoczne dla innych obiektów .NET Framework.  
  
 Aby udostępnić właściwości i metody dla modelu COM, należy je zadeklarować interfejsu klasy i oznacz je za pomocą `DispId` atrybutu i ich wdrażania w klasie. Kolejność, w której elementy członkowskie są zadeklarowane w interfejsie polega na kolejności, używany dla modelu COM vtable.  
  
 Aby udostępnić zdarzenia z klasy, należy zadeklarować je w interfejsie zdarzeń i oznacz je za pomocą `DispId` atrybutu. Klasy nie powinny implementować ten interfejs.  
  
 Klasa implementuje interfejs klasy; implementuje on więcej niż jeden interfejs, ale pierwszego wdrożenia będzie domyślny interfejs klasy. Implementuje metody i właściwości uwidaczniany w modelu COM w tym miejscu. One musi być oznaczona jako publiczna i musi być zgodna z deklaracji interfejsu klasy. Ponadto należy zadeklarować zdarzenia wygenerowane przez klasę, w tym miejscu. One musi być oznaczona jako publiczna i musi być zgodna z deklaracji zdarzenia interfejsu.  
  
## <a name="example"></a>Przykład  
 [!code-csharp[csProgGuideInterop#8](../../../csharp/programming-guide/interop/codesnippet/CSharp/example-com-class_1.cs)]  
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)  
- [Współdziałanie](../../../csharp/programming-guide/interop/index.md)  
- [Strona kompilacji, Projektant projektu (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp)
