---
title: "SplitContainer — Formant (Formularze systemu Windows)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- splitter windows
- SplitContainer control [Windows Forms]
ms.assetid: 2e36f17f-5c39-4fb4-bb09-7ce3ef823402
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 336243cc4db7039225ba272cac1ba7a3f173f361
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="splitcontainer-control-windows-forms"></a><span data-ttu-id="b866e-102">SplitContainer — Formant (Formularze systemu Windows)</span><span class="sxs-lookup"><span data-stu-id="b866e-102">SplitContainer Control (Windows Forms)</span></span>
<span data-ttu-id="b866e-103">Formularze systemu Windows `SplitContainer` formantu można traktować jako projekt wstępny; jest dwa panele oddzielone ruchomy paska.</span><span class="sxs-lookup"><span data-stu-id="b866e-103">The Windows Forms `SplitContainer` control can be thought of as a composite; it is two panels separated by a movable bar.</span></span> <span data-ttu-id="b866e-104">Gdy wskaźnik myszy znajduje się nad paskiem, kursor zmienia kształt pokazują, że pasek jest ruchomy.</span><span class="sxs-lookup"><span data-stu-id="b866e-104">When the mouse pointer is over the bar, the pointer changes shape to show that the bar is movable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b866e-105">W **przybornika**, to kontrolować zastępuje <xref:System.Windows.Forms.Splitter> formant, który był w poprzedniej wersji programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b866e-105">In the **Toolbox**, this control replaces the <xref:System.Windows.Forms.Splitter> control that was there in the previous version of Visual Studio.</span></span> <span data-ttu-id="b866e-106">`SplitContainer` Formant jest znacznie preferowany nad <xref:System.Windows.Forms.Splitter> formantu.</span><span class="sxs-lookup"><span data-stu-id="b866e-106">The `SplitContainer` control is much preferred over the <xref:System.Windows.Forms.Splitter> control.</span></span> <span data-ttu-id="b866e-107"><xref:System.Windows.Forms.Splitter> Klasy nadal znajduje się w programie .NET Framework w celu zapewnienia zgodności z istniejącymi aplikacjami, ale zdecydowanie zalecamy używania `SplitContainer` kontroli dla nowych projektów.</span><span class="sxs-lookup"><span data-stu-id="b866e-107">The <xref:System.Windows.Forms.Splitter> class is still included in the .NET Framework for compatibility with existing applications, but we strongly encourage you to use the `SplitContainer` control for new projects.</span></span>  
  
 <span data-ttu-id="b866e-108">`SplitContainer` Kontroli umożliwia tworzenie interfejsów użytkownika złożonych; często zaznaczenia w jednym panelu Określa, jakie obiekty są wyświetlane w panelu.</span><span class="sxs-lookup"><span data-stu-id="b866e-108">The `SplitContainer` control lets you create complex user interfaces; often, a selection in one panel determines what objects are shown in the other panel.</span></span> <span data-ttu-id="b866e-109">To rozmieszczenie jest bardzo efektywnym sposobem wyświetlania oraz informacji o przeglądaniu.</span><span class="sxs-lookup"><span data-stu-id="b866e-109">This arrangement is very effective for displaying and browsing information.</span></span> <span data-ttu-id="b866e-110">Dwa panele o umożliwiają agregują informacje w obszarach i paska lub "podziału," ułatwia użytkownikom zmienianie rozmiaru paneli.</span><span class="sxs-lookup"><span data-stu-id="b866e-110">Having two panels allow you to aggregate information in areas, and the bar, or "splitter," makes it easy for users to resize the panels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b866e-111">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="b866e-111">In This Section</span></span>  
 [<span data-ttu-id="b866e-112">Informacje o formancie SplitContainer</span><span class="sxs-lookup"><span data-stu-id="b866e-112">SplitContainer Control Overview</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-overview-windows-forms.md)  
 <span data-ttu-id="b866e-113">Wprowadza `SplitContainer` kontroli oraz opisano typowe właściwości, metod i zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="b866e-113">Introduces the `SplitContainer` control and describes the commonly used properties, methods, and events.</span></span>  
  
 [<span data-ttu-id="b866e-114">Porady: Definiowanie zmieniania rozmiaru i pozycjonowania w podzielonym oknie zachowanie</span><span class="sxs-lookup"><span data-stu-id="b866e-114">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 <span data-ttu-id="b866e-115">Zawiera opis sposobu kontrolowania podziału w `SplitContainer` formantu.</span><span class="sxs-lookup"><span data-stu-id="b866e-115">Describes how to control the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="b866e-116">Porady: Dzielenie okna w poziomie</span><span class="sxs-lookup"><span data-stu-id="b866e-116">How to: Split a Window Horizontally</span></span>](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 <span data-ttu-id="b866e-117">Zawiera opis sposobu kontrolowania orientacji rozdzielacza w `SplitContainer` formantu.</span><span class="sxs-lookup"><span data-stu-id="b866e-117">Describes how to control the orientation of the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="b866e-118">Porady: Tworzenie złożonego interfejsu użytkownika z formularzami systemu Windows</span><span class="sxs-lookup"><span data-stu-id="b866e-118">How to: Create a Multipane User Interface with Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="b866e-119">Tworzy interfejs użytkownika usługa okienku podobny do tego używanego w programie Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="b866e-119">Creates a multi-pane user interface that is similar to the one used in Microsoft Outlook.</span></span>  
  
 <span data-ttu-id="b866e-120">Zobacz też [porady: Dzielenie okna w poziomie przy użyciu narzędzia Projektant](http://msdn.microsoft.com/library/ms233667\(v=vs.110\)), [porady: Tworzenie interfejsu w stylu Eksploratora systemu Windows na formularzu systemu Windows](http://msdn.microsoft.com/library/zh2fe5a5\(v=vs.110\)), [porady: tworzenie Multipane interfejsu użytkownika z Formularze systemu Windows przy użyciu narzędzia Projektant](http://msdn.microsoft.com/library/ms233661\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="b866e-120">Also see [How to: Split a Window Horizontally Using the Designer](http://msdn.microsoft.com/library/ms233667\(v=vs.110\)), [How to: Create a Windows Explorer–Style Interface on a Windows Form](http://msdn.microsoft.com/library/zh2fe5a5\(v=vs.110\)), [How to: Create a Multipane User Interface with Windows Forms Using the Designer](http://msdn.microsoft.com/library/ms233661\(v=vs.110\)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b866e-121">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="b866e-121">Reference</span></span>  
 <span data-ttu-id="b866e-122"><xref:System.Windows.Forms.SplitContainer>klasy</span><span class="sxs-lookup"><span data-stu-id="b866e-122"><xref:System.Windows.Forms.SplitContainer> class</span></span>  
 <span data-ttu-id="b866e-123">Ta klasa opisuje i zawiera łącza do wszystkich jej członków.</span><span class="sxs-lookup"><span data-stu-id="b866e-123">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b866e-124">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="b866e-124">Related Sections</span></span>  
 [<span data-ttu-id="b866e-125">Formanty formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="b866e-125">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 <span data-ttu-id="b866e-126">Zawiera łącza do innych tematów dotyczących kontrolek zaprojektowany specjalnie w celu pracy z formularzami systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="b866e-126">Provides links to topics about the controls designed specifically to work with Windows Forms.</span></span>  
  
 [<span data-ttu-id="b866e-127">Formanty do użycia w formularzach systemu Windows</span><span class="sxs-lookup"><span data-stu-id="b866e-127">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="b866e-128">Zawiera listę wszystkich formanty formularzy systemu Windows, linki do informacji na temat ich użycia.</span><span class="sxs-lookup"><span data-stu-id="b866e-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>