---
title: 'Porady: włączanie widoku Tile w formancie ListView formularzy systemu Windows przy użyciu narzędzia Projektant'
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 86645396033ca1c3cfb025ba6db42b726f7e7969
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2018
ms.locfileid: "43862293"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>Porady: włączanie widoku Tile w formancie ListView formularzy systemu Windows przy użyciu narzędzia Projektant
Funkcja widoku kafelków z <xref:System.Windows.Forms.ListView> kontroli umożliwia wizualne równowagi między informacje graficzne i tekstowe. Tekstowe informacje wyświetlane dla elementu w widoku kafelków jest taka sama jak informacji o kolumnie zdefiniowane dla widoku szczegółów. Funkcje widoku kafelków w połączeniu z grupowania lub wstawiania oznaczyć funkcji <xref:System.Windows.Forms.ListView> kontroli.  
  
 Wyświetlanie kafelka używa ikonę 32 x 32 i kilka wierszy tekstu, jak pokazano na poniższej ilustracji.  
  
 ![Widok w kontrolce ListView kafelków](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")  
  
 Kafelek służy do wyświetlania właściwości i metody umożliwiają określenie, które pola kolumny do wyświetlenia dla każdego elementu i zbiorczo kontrolowanie rozmiaru i wyglądu wszystkich elementów w obrębie okna widoku kafelków. W celu uściślenia pierwszy wiersz tekstu we fragmencie jest zawsze nazwę elementu; Nie można zmienić.  
  
 Poniższa procedura wymaga **aplikacji Windows** projektu za pomocą zawierający formularz <xref:System.Windows.Forms.ListView> kontroli. Uzyskać informacji o konfigurowaniu taki projekt, zobacz [jak: Tworzenie projektu aplikacji Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) i [porady: dodawanie formantów do formularzy Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Widoku kafelków jest dostępna tylko na [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] gdy Twoja aplikacja wywołuje <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> metody. W starszych systemach operacyjnych, dowolnego kodu, powiązany z widoku kafelków nie obowiązuje oraz <xref:System.Windows.Forms.ListView> kontrolka wyświetla się w Widok dużych ikon. Aby uzyskać więcej informacji, zobacz <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.  
>   
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić swoje ustawienia, wybierz opcję **Import i eksport ustawień** na **narzędzia** menu. Aby uzyskać więcej informacji, zobacz [personalizowanie środowiska IDE programu Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-tile-view-in-the-designer"></a>Aby ustawić widoku tile w Projektancie  
  
1.  Wybierz <xref:System.Windows.Forms.ListView> kontrolkę w formularzu.  
  
2.  W **właściwości** wybierz <xref:System.Windows.Forms.ListView.View%2A> właściwości i wybierz polecenie **Kafelek**.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Forms.ListView.TileSize%2A>  
 [Funkcje systemu Windows XP i kontrolek formularzy Windows Forms](https://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [ListView, kontrolka — omówienie](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
