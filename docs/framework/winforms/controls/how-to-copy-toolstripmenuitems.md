---
title: 'Porady: kopiowanie ToolStripMenuItems'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- menu items [Windows Forms], copying and pasting
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], copying and pasting
ms.assetid: 17ef4207-e92e-4db2-b648-27246e6517ad
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 77f48d7af76cc65092e9045ab76654c96a1a7c02
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-copy-toolstripmenuitems"></a><span data-ttu-id="4f1e3-102">Porady: kopiowanie ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="4f1e3-102">How to: Copy ToolStripMenuItems</span></span>
<span data-ttu-id="4f1e3-103">W czasie projektowania, możesz skopiować cały menu najwyższego poziomu i ich elementy podmenu w inne miejsce na <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-103">At design time, you can copy entire top-level menus and their submenu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="4f1e3-104">Można również skopiować poszczególnych elementów menu między menu najwyższego poziomu lub zmienić jego położenie elementów menu w menu.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-104">You can also copy individual menu items between top-level menus or change the position of menu items within a menu.</span></span>  
  
### <a name="to-copy-a-top-level-menu-and-its-submenu-items-to-another-top-level-location"></a><span data-ttu-id="4f1e3-105">Aby skopiować menu najwyższego poziomu i jego podmenu w innej lokalizacji najwyższego poziomu</span><span class="sxs-lookup"><span data-stu-id="4f1e3-105">To copy a top-level menu and its submenu items to another top-level location</span></span>  
  
1.  <span data-ttu-id="4f1e3-106">Lewym przyciskiem myszy menu, które chcesz skopiować i naciśnij klawisze CTRL + C, lub kliknij prawym przyciskiem myszy menu i wybierz **kopiowania** z menu skrótów.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-106">Left-click the menu that you want to copy and press CTRL+C, or right-click the menu and select **Copy** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="4f1e3-107">Lewym menu najwyższego poziomu, które po zamierzone nowej lokalizacji i naciśnij klawisze CTRL + V lub kliknij prawym przyciskiem myszy element menu najwyższego poziomu, który jest przed zamierzone nowej lokalizacji, a następnie wybierz **Wklej** z menu skrótów.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-107">Left-click the top-level menu that is after the intended new location and press CTRL+V, or right-click the top-level menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="4f1e3-108">Menu, które zostały skopiowane dodaje się przed zaznaczone menu najwyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-108">The menu that you copied is inserted before the selected top-level menu.</span></span>  
  
### <a name="to-copy-a-top-level-menu-and-its-submenu-items-to-a-drop-down-location"></a><span data-ttu-id="4f1e3-109">Aby skopiować menu najwyższego poziomu, a jego podmenu na lokalizację z listy rozwijanej</span><span class="sxs-lookup"><span data-stu-id="4f1e3-109">To copy a top-level menu and its submenu items to a drop-down location</span></span>  
  
1.  <span data-ttu-id="4f1e3-110">Lewym przyciskiem myszy menu, które chcesz przenieść i naciśnij klawisze CTRL + C, lub kliknij prawym przyciskiem myszy menu i wybierz **kopiowania** z menu skrótów.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-110">Left-click the menu that you want to move and press CTRL+C, or right-click the menu and select **Copy** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="4f1e3-111">W menu najwyższego poziomu docelowego lewym przyciskiem myszy element podmenu powyżej zamierzone nowej lokalizacji i naciśnij klawisze CTRL + V lub kliknij prawym przyciskiem myszy element podmenu powyżej zamierzone nowej lokalizacji, a następnie wybierz **Wklej** z menu skrótów.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-111">In the destination top-level menu, left-click the submenu item that is above the intended new location and press CTRL+V, or right-click the submenu item that is above the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="4f1e3-112">Menu, które zostały skopiowane zostanie wstawiony przed elementem wybranym podmenu.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-112">The menu that you copied is inserted before the selected submenu item.</span></span>  
  
### <a name="to-copy-a-submenu-item-to-another-menu"></a><span data-ttu-id="4f1e3-113">Aby skopiować element podmenu do innego menu</span><span class="sxs-lookup"><span data-stu-id="4f1e3-113">To copy a submenu item to another menu</span></span>  
  
1.  <span data-ttu-id="4f1e3-114">Lewym przyciskiem myszy element podmenu, który chcesz skopiować i naciśnij klawisze CTRL + C, lub kliknij prawym przyciskiem myszy element podmenu i wybierz **kopiowania** z menu skrótów.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-114">Left-click the submenu item that you want to copy and press CTRL+C, or right-click the submenu item and choose **Copy** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="4f1e3-115">W lewym przyciskiem myszy menu, która będzie zawierać Wycinanie element podmenu.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-115">Left-click the menu that will contain the submenu item that you cut.</span></span>  
  
3.  <span data-ttu-id="4f1e3-116">Lewym przyciskiem myszy element podmenu przed zamierzone nowej lokalizacji i naciśnij klawisze CTRL + V lub kliknij prawym przyciskiem myszy element podmenu przed zamierzone nowej lokalizacji, a następnie wybierz **Wklej** z menu skrótów.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-116">Left-click the submenu item that is before the intended new location and press CTRL+V, or right-click the submenu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="4f1e3-117">Element podmenu skopiowany zostanie wstawiony przed elementem wybranym podmenu.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-117">The submenu item that you copied is inserted before the selected submenu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f1e3-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4f1e3-118">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="4f1e3-119">Informacje o formancie MenuStrip</span><span class="sxs-lookup"><span data-stu-id="4f1e3-119">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)