---
title: 'Porady: kotwiczenie formantów na formularzach systemu Windows'
ms.date: 03/30/2017
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
ms.openlocfilehash: c7658eb11e0d9e28c93b0a4b72a248cc42bc705f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2018
ms.locfileid: "43389858"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>Porady: kotwiczenie formantów na formularzach systemu Windows
W przypadku projektowania formularza, który użytkownik może zmienić rozmiar w czasie wykonywania, kontrolek w formularzu należy zmienić rozmiar i odpowiednio zmienić położenie. Aby zmienić rozmiar kontrolki dynamicznej z formularza, można użyć <xref:System.Windows.Forms.Control.Anchor%2A> właściwości kontrolek formularzy Windows Forms. <xref:System.Windows.Forms.Control.Anchor%2A> Właściwość definiuje pozycji zakotwiczenia dla formantu. Gdy formant jest zakotwiczona do formularza i rozmiarów formularza, formant zachowuje odległość między formantem i pozycji zakotwiczenia. Na przykład, jeśli masz <xref:System.Windows.Forms.TextBox> formant, który jest zakotwiczona lewy, prawy i dolną krawędzią formularza, jak rozmiarów formularza <xref:System.Windows.Forms.TextBox> kontrolować zmiany rozmiaru w poziomie, tak, aby utrzymuje tej samej odległości od lewej i prawej strony formularza. Ponadto kontrolka umieszcza się w pionie tak, aby jego lokalizacja jest zawsze tej samej odległości od dolnej krawędzi formularza. Jeśli formant nie jest zakotwiczona rozmiarów formularza, położenie formantu względem krawędzi formularza jest zmieniany.  
  
 <xref:System.Windows.Forms.Control.Anchor%2A> Właściwość wchodzi w interakcję z <xref:System.Windows.Forms.Control.AutoSize%2A> właściwości. Aby uzyskać więcej informacji, zobacz [AutoSize właściwość — omówienie](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
> [!NOTE]
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić swoje ustawienia, wybierz opcję **Import i eksport ustawień** na **narzędzia** menu. Aby uzyskać więcej informacji, zobacz [personalizowanie środowiska IDE programu Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-anchor-a-control-on-a-form"></a>Aby móc zakotwiczyć kontrolki na formularzu  
  
1.  Wybierz formant, który chcesz, aby móc zakotwiczyć.  
  
    > [!NOTE]
    >  Wiele kontrolek można zakotwiczyć jednocześnie, naciskając klawisz CTRL, klikając każdy formant, aby go zaznaczyć, a następnie postępuj zgodnie z pozostałą część tej procedury.  
  
2.  W **właściwości** okna, kliknij strzałkę po prawej stronie <xref:System.Windows.Forms.Control.Anchor%2A> właściwości.  
  
     Zostanie wyświetlony Edytor, pokazujący krzyżyk.  
  
3.  Aby ustawić elementu zakotwiczenia, kliknij lewym górnym rogu, po prawej stronie i dolną sekcję między środowiskami.  
  
     Kontrolki jest zakotwiczona u góry i pozostanie domyślnie.  
  
4.  Aby wyczyścić boku formant, który został zakotwiczone, kliknij ten arm między środowiskami.  
  
5.  Aby zamknąć <xref:System.Windows.Forms.Control.Anchor%2A> Edytor właściwości, kliknij przycisk <xref:System.Windows.Forms.Control.Anchor%2A> ponownie nazwę właściwości.  
  
 Gdy formularz jest wyświetlana w czasie wykonywania, pozostaje osiągniesz idealną pozycję w tej samej odległości od krawędzi formularza zmienia rozmiar kontrolki. Odległość od zakotwiczonej krawędzi zawsze pozostaje taki sam jak odległości określonej, gdy kontrolka jest umieszczany w Windows Forms Designer.  
  
> [!NOTE]
>  Niektóre kontrolki, takie jak <xref:System.Windows.Forms.ComboBox> sterowania, ma ograniczenia do ich wysokość. Zakotwiczanie formantu do dołu formularza lub kontener nie może wymusić kontroli przekroczenie limitu wysokości.  
  
 Musi być dziedziczone formantów `Protected` mogli jest zakotwiczona. Aby zmienić poziom dostępu formantu, ustaw jego `Modifiers` właściwość **właściwości** okna.  
  
## <a name="see-also"></a>Zobacz też  
 [Kontrolki formularzy Windows Forms](../../../../docs/framework/winforms/controls/index.md)  
 [Rozmieszczanie kontrolek na formularzach Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [AutoSize, właściwość — omówienie](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [Instrukcje: dokowanie kontrolek na formularzach Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [Przewodnik: rozmieszczanie kontrolek w formularzach Windows Forms za pomocą kontrolki FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Przewodnik: rozmieszczanie kontrolek w aplikacji Windows Forms za pomocą kontrolki TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Przewodnik: tworzenie kontrolek formularzy Windows Forms z uzupełnieniem, marginesami oraz właściwościami AutoSize](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
