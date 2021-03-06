---
title: 'Porady: otwarcie okna dialogowego'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
ms.openlocfilehash: 29fe8b0d516f20fcc742b91099a30e368dfe4548
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546364"
---
# <a name="how-to-open-a-dialog-box"></a>Porady: otwarcie okna dialogowego
Ten przykład przedstawia sposób otworzyć okno dialogowe.  
  
## <a name="example"></a>Przykład  
 Okno dialogowe jest oknem, która jest otwarta przez utworzenie wystąpienia <xref:System.Windows.Window> i wywoływania <xref:System.Windows.Window.ShowDialog%2A> metody. <xref:System.Windows.Window.ShowDialog%2A> Otwiera okno i nie zwraca, dopóki okno dialogowe Nowy został zamknięty. Okno tego typu jest nazywana *modalne* okna i ogranicza dane wejściowe użytkownika.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a>Zabezpieczenia.NET Framework  
 Wywoływanie <xref:System.Windows.Window.ShowDialog%2A> wymaga uprawnienia do używania wszystkie okna i zdarzenia wejściowe użytkownika bez ograniczeń.  
  
## <a name="see-also"></a>Zobacz też  
 [Zwracanie wyniku okna dialogowego](../../../../docs/framework/wpf/app-development/how-to-return-a-dialog-box-result.md)
