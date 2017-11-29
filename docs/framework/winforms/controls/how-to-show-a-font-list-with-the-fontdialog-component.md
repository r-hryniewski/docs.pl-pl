---
title: "Porady: pokazywanie listy czcionek przy użyciu składnika FontDialog"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 781daeb43a952ef25e73edd577fa17c61b02b426
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a><span data-ttu-id="0d405-102">Porady: pokazywanie listy czcionek przy użyciu składnika FontDialog</span><span class="sxs-lookup"><span data-stu-id="0d405-102">How to: Show a Font List with the FontDialog Component</span></span>
<span data-ttu-id="0d405-103">[FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md) składnika umożliwia użytkownikom wybierz czcionkę, a także zmienić aspektów wyświetlanej takie jak wagi i rozmiaru.</span><span class="sxs-lookup"><span data-stu-id="0d405-103">The [FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md) component allows users to select a font, as well as change its display aspects, such as its weight and size.</span></span>  
  
 <span data-ttu-id="0d405-104">Czcionka zaznaczona w oknie dialogowym jest zwracany w <xref:System.Windows.Forms.FontDialog.Font%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="0d405-104">The font selected in the dialog box is returned in the <xref:System.Windows.Forms.FontDialog.Font%2A> property.</span></span> <span data-ttu-id="0d405-105">W związku z tym wykorzystaniu czcionki wybrane przez użytkownika jest tak proste, jak odczytywania właściwości.</span><span class="sxs-lookup"><span data-stu-id="0d405-105">Thus, taking advantage of the font selected by the user is as easy as reading a property.</span></span>  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a><span data-ttu-id="0d405-106">Aby wybrać właściwości czcionki przy użyciu składnika FontDialog</span><span class="sxs-lookup"><span data-stu-id="0d405-106">To select font properties using the FontDialog Component</span></span>  
  
1.  <span data-ttu-id="0d405-107">Wyświetlać przy użyciu — okno dialogowe <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="0d405-107">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2.  <span data-ttu-id="0d405-108">Użyj <xref:System.Windows.Forms.DialogResult> właściwości, aby określić sposób zamknięcia okna dialogowego.</span><span class="sxs-lookup"><span data-stu-id="0d405-108">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3.  <span data-ttu-id="0d405-109">Użyj <xref:System.Windows.Forms.FontDialog.Font%2A> właściwości można ustawić żądanego czcionki.</span><span class="sxs-lookup"><span data-stu-id="0d405-109">Use the <xref:System.Windows.Forms.FontDialog.Font%2A> property to set the desired font.</span></span>  
  
     <span data-ttu-id="0d405-110">W poniższym przykładzie <xref:System.Windows.Forms.Button> formantu <xref:System.Windows.Forms.Control.Click> obsługi zdarzeń otwiera <xref:System.Windows.Forms.FontDialog> składnika.</span><span class="sxs-lookup"><span data-stu-id="0d405-110">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="0d405-111">Gdy czcionki jest wybrany, a użytkownik kliknie **OK**, <xref:System.Windows.Forms.FontDialog.Font%2A> właściwość <xref:System.Windows.Forms.TextBox> formantu, który znajduje się w formularzu ma ustawioną wartość wybranej czcionki.</span><span class="sxs-lookup"><span data-stu-id="0d405-111">When a font is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.FontDialog.Font%2A> property of a <xref:System.Windows.Forms.TextBox> control that is on the form is set to the chosen font.</span></span> <span data-ttu-id="0d405-112">W przykładzie założono formularz zawiera <xref:System.Windows.Forms.Button> kontroli, <xref:System.Windows.Forms.TextBox> kontroli, a <xref:System.Windows.Forms.FontDialog> składnika.</span><span class="sxs-lookup"><span data-stu-id="0d405-112">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a  <xref:System.Windows.Forms.TextBox> control, and a <xref:System.Windows.Forms.FontDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     <span data-ttu-id="0d405-113">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] i [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) umieścić następujący kod w Konstruktorze formularza, aby zarejestrować program obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="0d405-113">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0d405-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0d405-114">See Also</span></span>  
 <xref:System.Windows.Forms.FontDialog>  
 [<span data-ttu-id="0d405-115">Fontdialog — składnik</span><span class="sxs-lookup"><span data-stu-id="0d405-115">FontDialog Component</span></span>](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)