---
title: Jak użyć wyzwalaczy, aby nadać styl zaznaczonym elementom w ListView
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
ms.openlocfilehash: 1741ce84fab1639409a7c834845573239c51cc35
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554914"
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a>Jak użyć wyzwalaczy, aby nadać styl zaznaczonym elementom w ListView
W tym przykładzie pokazano sposób definiowania <xref:System.Windows.Style.Triggers%2A> dla <xref:System.Windows.Controls.ListViewItem> sterowania, aby gdy wartość właściwości <xref:System.Windows.Controls.ListViewItem> zmiany, <xref:System.Windows.Style> z <xref:System.Windows.Controls.ListViewItem> zmianach w odpowiedzi.  
  
## <a name="example"></a>Przykład  
 Jeśli chcesz <xref:System.Windows.Style> z <xref:System.Windows.Controls.ListViewItem> zmiany w odpowiedzi na zmiany właściwości, należy zdefiniować <xref:System.Windows.Style.Triggers%2A> dla <xref:System.Windows.Style> zmienić.  
  
 W poniższym przykładzie zdefiniowano <xref:System.Windows.Trigger> stanowiąca <xref:System.Windows.Controls.Control.Foreground%2A> właściwości <xref:System.Windows.Media.Brushes.Blue%2A> i zmienia <xref:System.Windows.FrameworkElement.Cursor%2A> do wyświetlenia <xref:System.Windows.Input.CursorType.Hand> podczas <xref:System.Windows.UIElement.IsMouseOver%2A> zmiany właściwości `true`.  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 W poniższym przykładzie zdefiniowano <xref:System.Windows.MultiTrigger> stanowiąca <xref:System.Windows.Controls.Control.Foreground%2A> właściwość <xref:System.Windows.Controls.ListViewItem> do <xref:System.Windows.Media.Brushes.Yellow%2A> podczas <xref:System.Windows.Controls.ListViewItem> wybrany element i ma fokus klawiatury.  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Tematy z instrukcjami](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView — omówienie](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [GridView — omówienie](../../../../docs/framework/wpf/controls/gridview-overview.md)
