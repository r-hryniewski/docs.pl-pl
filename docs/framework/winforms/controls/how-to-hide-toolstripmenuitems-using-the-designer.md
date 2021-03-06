---
title: 'Porady: Ukrywanie ToolStripMenuItems przy użyciu narzędzia Projektant'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 37371269ef9db929573efff0a8e62c86a51b2c35
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523580"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>Porady: Ukrywanie ToolStripMenuItems przy użyciu narzędzia Projektant
Ukrywanie elementów menu jest sposób sterowania interfejsem użytkownika (UI), aplikacji i ograniczyć polecenia użytkownika. Często chcesz ukryć całe menu, gdy wszystkie elementy menu na nim są niedostępne. Przedstawia informacje o przeszkadzał dla użytkownika. Ponadto warto ukryć i Wyłącz menu lub elementu menu, jak samodzielnie ukrywanie nie uniemożliwia użytkownikowi dostęp do poleceń menu przy użyciu klawisza skrótu. Aby uzyskać więcej informacji na temat Wyłączanie elementów menu, zobacz [porady: wyłączanie kontrolki ToolStripMenuItems przy użyciu projektanta](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).  
  
> [!NOTE]
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić swoje ustawienia, wybierz opcję **Import i eksport ustawień** na **narzędzia** menu. Aby uzyskać więcej informacji, zobacz [personalizowanie środowiska IDE programu Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>Aby ukryć menu najwyższego poziomu i jego elementów do podmenu  
  
1.  Wybierz element menu najwyższego poziomu i ustaw jego <xref:System.Windows.Forms.ToolStripItem.Visible%2A> lub <xref:System.Windows.Forms.ToolStripItem.Available%2A> właściwość `false`.  
  
     Po ukryciu element menu najwyższego poziomu wszystkich elementów menu w menu również są ukryte. Po kliknięciu w innym miejscu niż na <xref:System.Windows.Forms.MenuStrip> po ustawieniu <xref:System.Windows.Forms.ToolStripItem.Visible%2A> do `false`, element całego menu najwyższego poziomu i jego elementów podmenu są usuwane z formularza, w związku z tym przedstawiający efekt czasu wykonywania akcji. Aby wyświetlić element ukryty menu najwyższego poziomu w czasie projektowania, kliknij pozycję <xref:System.Windows.Forms.MenuStrip> w **zasobniku składnika**w **konspekt dokumentu**, lub w górnej części siatki właściwości.  
  
> [!NOTE]
>  Rzadko spowoduje ukrycie całe menu z wyjątkiem wielu menu podrzędne w przypadku scalania dokument interfejsu (MDI).  
  
### <a name="to-hide-a-submenu-item"></a>Aby ukryć element podmenu  
  
1.  Wybierz element podmenu, a następnie ustaw jego <xref:System.Windows.Forms.ToolStripItem.Visible%2A> właściwość `false`.  
  
     Po ukryciu elementu podmenu pozostaje widoczna w formularzu w czasie projektowania, aby można go łatwo wybrać dalszej pracy. Zostanie on faktycznie ukryty w czasie wykonywania.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [MenuStrip, kontrolka — omówienie](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [Instrukcje: wyłączanie kontrolki ToolStripMenuItems przy użyciu narzędzia Projektant](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)
