---
title: "Jak powiązać TreeView z danymi, które mają nieokreśloną głębokość"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b16cae3a91eae73a4480484d89bb075862256b25
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>Jak powiązać TreeView z danymi, które mają nieokreśloną głębokość
Może to być razy, jeśli chcesz powiązać <xref:System.Windows.Controls.TreeView> ze źródłem danych, której głębokość nie jest znany.  Taka sytuacja może wystąpić, jeśli dane są cykliczne charakter, takich jak system plików, których foldery mogą zawierać folderów, lub struktura organizacyjna firmy, gdzie pracownicy mają inni jako bezpośrednich podwładnych.  
  
 Źródło danych musi mieć modelu obiektu hierarchicznej. Na przykład `Employee` klasy może zawierać zbiór obiekty pracowników, które mają bezpośrednich podwładnych pracownika. Jeśli dane są reprezentowane w taki sposób, który nie jest hierarchiczne, należy utworzyć hierarchiczną reprezentację danych.  
  
 Podczas ustawiania <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> właściwości i jeśli <xref:System.Windows.Controls.ItemsControl> generuje <xref:System.Windows.Controls.ItemsControl> dla każdego elementu podrzędnego, a następnie podrzędne <xref:System.Windows.Controls.ItemsControl> wykorzystuje takie same <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> jako element nadrzędny. Na przykład jeśli ustawisz <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> właściwość z danymi <xref:System.Windows.Controls.TreeView>, każdy <xref:System.Windows.Controls.TreeViewItem> czyli wygenerowanego używa <xref:System.Windows.DataTemplate> która została przypisana do <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> właściwość <xref:System.Windows.Controls.TreeView>.  
  
 <xref:System.Windows.HierarchicalDataTemplate> Umożliwia określenie <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> dla <xref:System.Windows.Controls.TreeViewItem>, lub <xref:System.Windows.Controls.HeaderedItemsControl>, w szablonie danych. Podczas ustawiania <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType> właściwość, która wartość jest używana, gdy <xref:System.Windows.HierarchicalDataTemplate> została zastosowana. Za pomocą <xref:System.Windows.HierarchicalDataTemplate>, można rekursywnie zestaw <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> dla każdego <xref:System.Windows.Controls.TreeViewItem> w <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie pokazano, jak można powiązać <xref:System.Windows.Controls.TreeView> hierarchiczne dane i użyj <xref:System.Windows.HierarchicalDataTemplate> do określenia <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> dla każdego <xref:System.Windows.Controls.TreeViewItem>.  <xref:System.Windows.Controls.TreeView> Tworzy powiązanie z danymi XML, który reprezentuje pracowników w firmie.  Każdy `Employee` elementu mogą zawierać inne `Employee` elementy, aby wskazać, który zgłasza, do którego. Ponieważ dane są cykliczne, <xref:System.Windows.HierarchicalDataTemplate> mogą być stosowane do każdego poziomu.  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>Zobacz też  
 [Omówienie powiązania danych](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Omówienie tworzenia szablonów danych](../../../../docs/framework/wpf/data/data-templating-overview.md)