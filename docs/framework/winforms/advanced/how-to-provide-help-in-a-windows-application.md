---
title: 'Porady: zapewnianie pomocy w aplikacji Windows'
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
ms.openlocfilehash: 98ed6d4e10d0eb80b99a36172980fcb33186c8ca
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2018
ms.locfileid: "43801245"
---
# <a name="how-to-provide-help-in-a-windows-application"></a>Porady: zapewnianie pomocy w aplikacji Windows
Można również użyć <xref:System.Windows.Forms.HelpProvider> składnika, aby dołączyć tematów pomocy w pliku pomocy do określonych formantów na formularzach Windows Forms. Może to być plik Pomocy HTML lub HTMLHelp 1.x lub większa formatu.  
  
> [!NOTE]
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić swoje ustawienia, wybierz opcję **Import i eksport ustawień** na **narzędzia** menu. Aby uzyskać więcej informacji, zobacz [personalizowanie środowiska IDE programu Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-provide-help"></a>Zapewnienie pomocy  
  
1.  Z **przybornika**, przeciągnij <xref:System.Windows.Forms.HelpProvider> składnika do formularza.  
  
     Składnik będą znajdować się w pasku w dolnej części projektanta Windows Forms.  
  
2.  W **właściwości** oknie <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> właściwość chm, .col lub .htm w pliku pomocy.  
  
3.  Wybierz inny formant na formularzu, a następnie w **właściwości** oknie <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> właściwości.  
  
     Jest to ciąg przekazany przez <xref:System.Windows.Forms.HelpProvider> składnik do pliku pomocy wezwać odpowiedniego tematu Pomocy.  
  
4.  W **właściwości** oknie <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> właściwości na wartość <xref:System.Windows.Forms.HelpNavigator> wyliczenia.  
  
     Określa sposób, w którym **HelpKeyword** właściwość jest przekazywana do systemu pomocy. W poniższej tabeli przedstawiono ustawienia możliwe i ich opisy.  
  
    |Nazwa elementu członkowskiego|Opis|  
    |-----------------|-----------------|  
    |AssociateIndex|Określa, że indeks dla określonego tematu odbywa się w określonym adresie URL.|  
    |Znajdź|Określa, czy są wyświetlane na stronie wyszukiwania określonego adresu URL.|  
    |Indeks|Określa, czy są wyświetlane na indeks określonego adresu URL.|  
    |KeywordIndex|Określa słowo kluczowe do wyszukania i akcję do wykonania w określonym adresie URL.|  
    |TableOfContents|Określa, czy jest wyświetlana tabela zawartość pliku Pomocy HTML 1.0.|  
    |Temat|Określa, czy są wyświetlane na temat odwołuje się określony adres URL.|  
  
 W czasie wykonywania, naciskając klawisz F1 podczas kontroli — dla którego ustawiono **HelpKeyword** i **HelpNavigator** właściwości — ma fokus zostanie otwarty plik pomocy skojarzony z tym <xref:System.Windows.Forms.HelpProvider> składnika.  
  
 Obecnie **HelpNamespace** właściwość obsługuje pliki pomocy w trzech następujących formatów: HTMLHelp 1.x i HTML oraz HTMLHelp w wersji 2.0. W związku z tym, można ustawić **HelpNamespace** właściwości do adresu http://, takich jak strony sieci Web. Jeśli zostanie to zrobione, zostanie otwarty w domyślnej przeglądarce strony sieci Web przy użyciu parametrów określonych w **HelpKeyword** właściwość używana jako zakotwiczenia. Zakotwiczenia jest używana do przechodzenia do określonej części strony HTML.  
  
> [!IMPORTANT]
>  Uważaj sprawdzić wszelkie informacje wysłane przez klienta, zanim użyjesz go w aplikacji. Złośliwi użytkownicy mogą próbować wysyłać ani wstawić skrypt pliku wykonywalnego, instrukcji SQL lub inny kod. Zanim wyświetlić dane wejściowe użytkownika, zapisz go w bazie danych lub pracować z nim Sprawdź, czy nie zawiera informacji o potencjalnie niebezpieczną. Typowym sposobem na sprawdzenie ma użyć wyrażeń regularnych do wyszukiwania słów kluczowych, takich jak "Skrypt" po otrzymaniu danych wejściowych od użytkownika.  
  
 Można również użyć <xref:System.Windows.Forms.HelpProvider> składnika, aby wyświetlić Pomoc podręczną, nawet jeśli jest skonfigurowany do wyświetlania plików pomocy dla formantów na formularzach Windows. Aby uzyskać więcej informacji, zobacz [porady: wyświetlanie wyskakujących pomocy](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Instrukcje: wyświetlanie pomocy podręcznej](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 [Pomoc do kontrolek przy użyciu etykietek narzędzi](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [Integrowanie pomocy użytkownika z formularzami Windows Forms](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [Windows Forms](../../../../docs/framework/winforms/index.md)
