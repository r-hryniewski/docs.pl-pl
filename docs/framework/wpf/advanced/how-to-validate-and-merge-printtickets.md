---
title: Jak walidować i scalać PrintTickets
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
ms.openlocfilehash: 37a1c0600b8429158336968507ddc8cfb6d8f98b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485641"
---
# <a name="how-to-validate-and-merge-printtickets"></a>Jak walidować i scalać PrintTickets
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Schematu drukowania](https://go.microsoft.com/fwlink/?LinkId=186397) obejmuje elastyczna i rozszerzalna <xref:System.Printing.PrintCapabilities> i <xref:System.Printing.PrintTicket> elementów. Pierwsza wyszczególniono możliwości drukarki, a jego Określa, jak urządzenia powinny używać tych możliwości w odniesieniu do określonej sekwencji dokumentów, dokument lub pojedynczej strony.  
  
 Typowe sekwencji zadań dla aplikacji, która obsługuje drukowanie byłoby w następujący sposób.  
  
1.  Określ drukarkę możliwości.  
  
2.  Konfigurowanie <xref:System.Printing.PrintTicket> na korzystanie z tych funkcji.  
  
3.  Sprawdź poprawność <xref:System.Printing.PrintTicket>.  
  
 W tym artykule pokazano, jak to zrobić.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie prostego, jesteśmy zainteresowani tylko tego, czy drukarka może obsługiwać dupleksu — drukowania dwustronnego. Główne kroki są następujące.  
  
1.  Pobierz <xref:System.Printing.PrintCapabilities> obiekt z <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> metody.  
  
2.  Test na obecność możliwości, które chcesz. W poniższym przykładzie przetestujemy <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> właściwość <xref:System.Printing.PrintCapabilities> obiektu na obecność możliwość drukowania po obu stronach arkusz papieru, "Włączanie strony" długo po stronie arkusza. Ponieważ <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> jest kolekcją, używamy `Contains` metody <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.  
  
    > [!NOTE]
    >  Ten krok nie jest bezwzględnie konieczne. <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> Metodę poniżej zostanie zaewidencjonowany przez każde żądanie <xref:System.Printing.PrintTicket> z możliwościami drukarki. Jeśli żądana funkcja nie jest obsługiwana przez drukarkę, sterownik drukarki zostanie zastąpiony przez żądanie alternatywnych w <xref:System.Printing.PrintTicket> zwracany przez metodę.  
  
3.  Jeśli drukarka obsługuje dupleksu, przykładowy kod tworzy <xref:System.Printing.PrintTicket> która poprosi o podanie dupleksu. Ale aplikacja nie określa każdej drukarki możliwe ustawienie dostępne w <xref:System.Printing.PrintTicket> elementu. Byłoby marnotrawstwa programisty i godziny programu. Zamiast tego kod ustawia tylko żądanie dupleksu, a następnie scala to <xref:System.Printing.PrintTicket> z istniejącym, w pełni skonfigurowane i sprawdzeniu poprawności <xref:System.Printing.PrintTicket>, w tym przypadku użytkownika domyślnego <xref:System.Printing.PrintTicket>.  
  
4.  W związku z tym przykład wywołuje <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> metody do scalenia z nowej, minimalnymi <xref:System.Printing.PrintTicket> z domyślną użytkownika <xref:System.Printing.PrintTicket>. Spowoduje to zwrócenie <xref:System.Printing.ValidationResult> zawierającego nowe <xref:System.Printing.PrintTicket> jako jeden z jego właściwości.  
  
5.  Następnie testy próbki nowy <xref:System.Printing.PrintTicket> dupleksu żądań. Jeśli tak jest, następnie próbki sprawia, że nowy bilet drukowania domyślny dla użytkownika. Jeśli w kroku 2 powyżej miał pozostawiono i drukarki nie obsługują dupleksu długo po stronie, a następnie spowodowałaby testu `false`. (Zobacz uwagi powyżej).  
  
6.  Ostatnim krokiem istotne jest aby zatwierdzić zmiany <xref:System.Printing.PrintQueue.UserPrintTicket%2A> właściwość <xref:System.Printing.PrintQueue> z <xref:System.Printing.PrintQueue.Commit%2A> metody.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 Dlatego, że możesz szybko przetestować, w tym przykładzie, do końca znajduje się poniżej. Utwórz projekt i przestrzeń nazw, a następnie wklej fragmenty kodu w tym artykule, w bloku przestrzeni nazw.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Printing.PrintCapabilities>  
 <xref:System.Printing.PrintTicket>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [Dokumenty w WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Przegląd drukowania](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Drukuj schematu](https://go.microsoft.com/fwlink/?LinkId=186397)
