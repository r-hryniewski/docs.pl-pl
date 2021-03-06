---
title: Właściwości formantów formularzy systemu Windows obsługujące dostęp — Wytyczne
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: b466dcf42561d8ced7b224215538a807c94b174b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524491"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a>Właściwości formantów formularzy systemu Windows obsługujące dostęp — Wytyczne
Formanty standardowe przyborniku dla formularzy systemu Windows obsługują wiele wytycznych ułatwień dostępu, w tym udostępnianie fokus klawiatury i udostępnianie elementów ekranu.  
  
## <a name="planning-ahead-for-accessibility"></a>Planowanie wyprzedzeniem ułatwień dostępu  
 Właściwości formantów mogą służyć do obsługi innych dostęp — wytyczne, jak pokazano w poniższej tabeli. Ponadto należy używać menu, aby zapewnić dostęp do funkcji programu.  
  
|Właściwość formantu|Zagadnienia dotyczące ułatwień dostępu|  
|----------------------|--------------------------------------|  
|AccessibleDescription|Opis jest zgłaszane do narzędzi ułatwień dostępu, takich jak czytniki ekranu. Narzędzi ułatwień dostępu są programy specjalistyczne i urządzenia, które pomagają osób niepełnosprawnych komputerów wydajniej wykorzystywać.|  
|AccessibleName|Nazwa przekazywana do narzędzi ułatwień dostępu.|  
|AccessibleRole|Opisuje elementu w interfejsie użytkownika.|  
|TabIndex|Tworzy ścieżkę nawigacyjną za pośrednictwem za pomocą formularza. Jest ważne dla formantów bez etykiet wewnętrznych, takich jak pola tekstowe, ich skojarzone etykiety poprzedzają w kolejności tabulacji.|  
|Tekst|Użyj znaku "&", aby utworzyć klucze dostępu. Za pomocą klawiszy dostępu jest częścią klawiaturę udokumentowaną dostępowi do funkcji.|  
|Rozmiar czcionki|Jeśli rozmiar czcionki nie jest regulowany, następnie go ustawić punkty 10 lub większą. Po ustawieniu formularza rozmiar czcionki, wszystkie formanty, które są następnie dodany do formularza będą miały taki sam rozmiar.|  
|ForeColor|Jeśli ta właściwość ma ustawioną wartość domyślna, preferencje kolorów dla użytkownika będą używane w formularzu.|  
|Kolor tła|Jeśli ta właściwość ma ustawioną wartość domyślna, preferencje kolorów dla użytkownika będą używane w formularzu.|  
|BackgroundImage|Pozostaw pole puste, aby zwiększyć czytelność tekstu tej właściwości.|  
  
## <a name="see-also"></a>Zobacz też  
 [Przewodnik: tworzenie dostępnej aplikacji bazującej na systemie Windows](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)
