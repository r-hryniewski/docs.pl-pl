---
title: 'Porady: aranżowanie formularzy podrzędnych MDI'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms [Windows Forms], arranging
- MDI [Windows Forms], arranging child forms
ms.assetid: a0786378-3206-4ccc-898e-7d3b38cc5089
ms.openlocfilehash: d5c0d24ff8a7188a669c218ce8b0dc66ffa56c47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521030"
---
# <a name="how-to-arrange-mdi-child-forms"></a>Porady: aranżowanie formularzy podrzędnych MDI
Często aplikacje będą mieć poleceń menu Akcje, takie jak kafelka, Cascade i Rozmieść, które sterowania układem Otwórz formularzy podrzędnych MDI. Można użyć <xref:System.Windows.Forms.Form.LayoutMdi%2A> metody za pomocą jednego z <xref:System.Windows.Forms.MdiLayout> formularza nadrzędnego wartości wyliczenia do rozmieszczanie formularzy podrzędnych MDI.  
  
 <xref:System.Windows.Forms.MdiLayout> Wartości wyliczenia są wyświetlane formularze podrzędne jako kaskadowych, jak rozmieszczany poziomo czy pionowo lub ikony formularza podrzędnego rozmieszczone wzdłuż dolnej części formularza MDI. Te wartości mają ten sam efekt co polecenia systemu Windows **kaskadowo windows**, **Pokaż okna sąsiadująco**, **wyświetlanie okien skumulowany**, i **wyświetlanie pulpitu** odpowiednio.  
  
 Te metody są często używane jako procedury obsługi zdarzeń, wywoływana przez element menu <xref:System.Windows.Forms.Control.Click> zdarzeń. W ten sposób element menu z tekstem "Kaskadowo" mogą być uwzględnione na okien podrzędnych MDI.  
  
### <a name="to-arrange-child-forms"></a>Aby Rozmieść formularze podrzędne  
  
1.  W metodzie, użyj <xref:System.Windows.Forms.Form.LayoutMdi%2A> metodę, aby ustawić <xref:System.Windows.Forms.MdiLayout> wyliczenia do formularza nadrzędnego MDI. W poniższym przykładzie użyto <xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType> wartość wyliczenia dla okien podrzędnych MDI formularza nadrzędnego (`Form1`). Wyliczenie jest używane w kodzie podczas obsługi zdarzenia <xref:System.Windows.Forms.Control.Click> zdarzenie **Kaskadowo** elementu menu.  
  
    ```vb  
    Protected Sub CascadeWindows_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)  
       Me.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade)  
    End Sub  
    ```  
  
    ```csharp  
    protected void CascadeWindows_Click(object sender, System.EventArgs e){  
       this.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade);  
    }  
    ```  
  
    > [!NOTE]
    >  Można również podzielić windows i windows rozmieszczenie jako ikony, zmieniając <xref:System.Windows.Forms.MdiLayout> wartość wyliczenia używane.  
  
2.  Jeśli używasz programu Visual C#, umieść następujący kod w Konstruktorze formularza, aby zarejestrować program obsługi zdarzeń.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
## <a name="see-also"></a>Zobacz też  
 [Aplikacje interfejsu wielu dokumentów (MDI)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [Instrukcje: tworzenie formularzy nadrzędnych MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Instrukcje: tworzenie formularzy podrzędnych MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Instrukcje: określanie elementu podrzędnego MDI Active](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [Instrukcje: wysyłanie danych do Active MDI Child](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)
