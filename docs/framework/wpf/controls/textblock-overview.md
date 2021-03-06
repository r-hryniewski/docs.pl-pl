---
title: TextBlock — Przegląd
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], TextBlock
- TextBlock control [WPF]
ms.assetid: 24720bca-341a-4b03-8a6b-7a678023b10a
ms.openlocfilehash: c18ca64a25f436c3ed2ccd9e04316e25bab00a66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556084"
---
# <a name="textblock-overview"></a>TextBlock — Przegląd
<xref:System.Windows.Controls.TextBlock> Kontroli zapewnia elastyczne tekst obsługę [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplikacji. Element jest przeznaczony głównie kierunku basic [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenariusze, które nie wymagają więcej niż jednego akapitu tekstu. Obsługuje wiele właściwości, umożliwiające precyzyjną kontrolę prezentacji, takich jak <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, i <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>. Zawartość tekstu można dodać za pomocą <xref:System.Windows.Controls.TextBlock.Text%2A> właściwości. W przypadku używania w [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], zawartości między otwarcia i zamknięcia tagu niejawnie jest dodawana jako tekstu elementu.  
  
 A <xref:System.Windows.Controls.TextBlock> można wdrożyć elementu bardzo prosty przy użyciu [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[TextBlockSnip_XAML#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip_XAML/CS/default.xaml#2)]  
  
 Podobnie, użycie <xref:System.Windows.Controls.TextBlock> elementu w kodzie jest stosunkowo proste.  
  
 [!code-csharp[TextBlockSnip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip/CSharp/TextBlockSnips.cs#1)]
 [!code-vb[TextBlockSnip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBlockSnip/VisualBasic/TextBlockSnips.vb#1)]  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Controls.Label>
