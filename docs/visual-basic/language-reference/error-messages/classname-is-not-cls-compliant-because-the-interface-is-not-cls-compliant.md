---
title: '&#39;&lt;ClassName&gt; &#39; nie jest zgodne ze specyfikacją CLS, ponieważ interfejs &#39; &lt;interfacename&gt; &#39; ją implementuje nie jest zgodne ze specyfikacją CLS'
ms.date: 07/20/2015
f1_keywords:
- bc40029
- vbc40029
helpviewer_keywords:
- BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
ms.openlocfilehash: 4dda0e16a94f43cdb3deeff16fabdd1b10b62526
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588497"
---
# <a name="39ltclassnamegt39-is-not-cls-compliant-because-the-interface-39ltinterfacenamegt39-it-implements-is-not-cls-compliant"></a>&#39;&lt;ClassName&gt; &#39; nie jest zgodne ze specyfikacją CLS, ponieważ interfejs &#39; &lt;interfacename&gt; &#39; ją implementuje nie jest zgodne ze specyfikacją CLS
Klasy lub interfejsu jest oznaczony jako `<CLSCompliant(True)>` po pochodną lub implementuje typu, który jest oznaczony jako `<CLSCompliant(False)>` lub nie jest oznaczony jako.  
  
 Dla klasy lub interfejsu, aby było zgodne z [niezależność od języka i elementy niezależne od języka](../../../standard/language-independence-and-language-independent-components.md) (ze specyfikacją CLS), jej hierarchii dziedziczenia całego muszą być zgodne. Oznacza to, że każdy typ, po którym dziedziczy, bezpośrednio lub pośrednio, muszą być zgodne. Podobnie jeśli klasa implementuje jeden lub więcej interfejsów, ich wszystkie muszą być zgodne w całym ich hierarchii dziedziczenia.  
  
 Po zastosowaniu <xref:System.CLSCompliantAttribute> do elementu programistycznego, ten atrybut zostanie ustawiony `isCompliant` albo parametr `True` lub `False` zgodności lub niezgodności. Nie jest domyślnie dla tego parametru, a należy podać wartość.  
  
 Jeśli nie mają zastosowania <xref:System.CLSCompliantAttribute> do elementu, jest uznawane za niezgodne.  
  
 Domyślnie ten komunikat jest ostrzeżenie. Aby uzyskać informacje na ukrywanie ostrzeżenia lub traktowanie ostrzeżeń jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identyfikator błędu:** BC40029  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
-   Jeśli potrzebujesz zgodności ze specyfikacją CLS, należy zdefiniować tego typu w ramach systemu hierarchii lub wykonania innego dziedziczenia.  
  
-   Jeśli wymagasz, że ten typ pozostają w jego bieżącej hierarchii lub implementacji schemat dziedziczenia, Usuń <xref:System.CLSCompliantAttribute> z jego definicji lub Oznacz go jako `<CLSCompliant(False)>`.  
  
 
