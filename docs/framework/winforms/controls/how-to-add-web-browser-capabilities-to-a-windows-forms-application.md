---
title: "Porady: dodawanie funkcji przeglądarki sieci Web do aplikacji systemu Windows"
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
- WebBrowser control [Windows Forms], adding Web browser capabilities to your application
- WebBrowser control [Windows Forms], examples
- Web browsers [.NET Framework], adding to Windows Forms
- examples [Windows Forms], WebBrowser control
- Windows Forms, adding Web browser functionality
ms.assetid: 3871f072-b57a-435b-9976-e5da28df04a7
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4bc8592dd821fdef68c2b77242d9d3f2f2b776bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-web-browser-capabilities-to-a-windows-forms-application"></a><span data-ttu-id="6964d-102">Porady: dodawanie funkcji przeglądarki sieci Web do aplikacji systemu Windows</span><span class="sxs-lookup"><span data-stu-id="6964d-102">How to: Add Web Browser Capabilities to a Windows Forms Application</span></span>
<span data-ttu-id="6964d-103">Z <xref:System.Windows.Forms.WebBrowser> sterowania, można dodać funkcji przeglądarki sieci Web do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6964d-103">With the <xref:System.Windows.Forms.WebBrowser> control, you can add Web browser functionality to your application.</span></span> <span data-ttu-id="6964d-104">Formant działa jak przeglądarki sieci Web domyślnie.</span><span class="sxs-lookup"><span data-stu-id="6964d-104">The control works like a Web browser by default.</span></span> <span data-ttu-id="6964d-105">Po załadowaniu początkowy adres URL przez ustawienie <xref:System.Windows.Forms.WebBrowser.Url%2A> właściwości, można przejść, klikając hiperłącza lub za pomocą skróty klawiaturowe do tyłu i przekazywać je do historii nawigacji.</span><span class="sxs-lookup"><span data-stu-id="6964d-105">After you load an initial URL by setting the <xref:System.Windows.Forms.WebBrowser.Url%2A> property, you can navigate by clicking hyperlinks or by using keyboard shortcuts to move backward and forward through navigation history.</span></span> <span data-ttu-id="6964d-106">Domyślnie można uzyskać dostępu do funkcjonalności przeglądarki dodatkowe za pośrednictwem menu skrótów kliknij prawym przyciskiem myszy.</span><span class="sxs-lookup"><span data-stu-id="6964d-106">By default, you can access additional browser functionality through the right-click shortcut menu.</span></span> <span data-ttu-id="6964d-107">Można również otworzyć nowych dokumentów, przeciągając je w formancie.</span><span class="sxs-lookup"><span data-stu-id="6964d-107">You can also open new documents by dropping them onto the control.</span></span> <span data-ttu-id="6964d-108"><xref:System.Windows.Forms.WebBrowser> Formant ma również kilka właściwości, metod i zdarzeń, które służy do implementowania funkcji interfejsu użytkownika podobne do tych znaleziono w programie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="6964d-108">The <xref:System.Windows.Forms.WebBrowser> control also has several properties, methods, and events that you can use to implement user interface features similar to those found in Internet Explorer.</span></span>  
  
 <span data-ttu-id="6964d-109">Poniższy przykład kodu implementuje paska adresu, przyciski typowe przeglądarki, **pliku** menu, paska stanu i pasek tytułu, który wyświetla bieżący tytuł strony.</span><span class="sxs-lookup"><span data-stu-id="6964d-109">The following code example implements an address bar, typical browser buttons, a **File** menu, a status bar, and a title bar that displays the current page title.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6964d-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="6964d-110">Example</span></span>  
 [!code-cpp[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CPP/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6964d-111">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="6964d-111">Compiling the Code</span></span>  
 <span data-ttu-id="6964d-112">Ten przykład wymaga:</span><span class="sxs-lookup"><span data-stu-id="6964d-112">This example requires:</span></span>  
  
-   <span data-ttu-id="6964d-113">Odwołuje się do `System,``System.Drawing`, i `System.Windows.Forms` zestawów.</span><span class="sxs-lookup"><span data-stu-id="6964d-113">References to the `System,``System.Drawing`, and `System.Windows.Forms` assemblies.</span></span>  
  
 <span data-ttu-id="6964d-114">Informacji dotyczących tworzenia tego przykładu z wiersza polecenia dla [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] lub [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], zobacz [tworzenie z wiersza polecenia](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) lub [kompilowania z wiersza polecenia csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="6964d-114">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="6964d-115">Można także utworzyć tym przykładzie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] przez wklejenie kodu do nowego projektu.</span><span class="sxs-lookup"><span data-stu-id="6964d-115">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="6964d-116">Zobacz też [porady: kompilowanie i uruchamianie pełną Windows formularze kodu przykład za pomocą programu Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="6964d-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6964d-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6964d-117">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 [<span data-ttu-id="6964d-118">WebBrowser — formant</span><span class="sxs-lookup"><span data-stu-id="6964d-118">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)