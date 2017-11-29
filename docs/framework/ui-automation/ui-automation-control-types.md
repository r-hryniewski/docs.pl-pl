---
title: "Typy formantów automatyzacji interfejsu użytkownika"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AutoGeneratedOrientationPage
helpviewer_keywords:
- UI Automation, control types
- control types, UI Automation
ms.assetid: 261dcc59-3a62-4e40-91dd-63ff9d2241c0
caps.latest.revision: "61"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: e521f07048e37533e052dc8a43fb2c522750f92a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="ui-automation-control-types"></a><span data-ttu-id="973a7-102">Typy kontrolek automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="973a7-102">UI Automation Control Types</span></span>
<span data-ttu-id="973a7-103">**Uwaga** Niniejsza dokumentacja jest przeznaczony dla deweloperów .NET Framework, które chcą korzystać zarządzanej [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="973a7-103">**Note** This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="973a7-104">Aby uzyskać najnowsze informacje o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], zobacz [interfejsu API systemu Windows automatyzacji: automatyzacji interfejsu użytkownika](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="973a7-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="973a7-105">Ta sekcja zawiera informacje dotyczące obsługi typów kontroli w [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="973a7-105">This section contains information about support for control types in [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="973a7-106">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="973a7-106">In This Section</span></span>  
 [<span data-ttu-id="973a7-107">Przegląd typów formantu automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="973a7-107">UI Automation Control Types Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)  
 [<span data-ttu-id="973a7-108">Obsługa automatyzacji interfejsu użytkownika dla formantów typu przycisk</span><span class="sxs-lookup"><span data-stu-id="973a7-108">UI Automation Support for the Button Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-button-control-type.md)  
 [<span data-ttu-id="973a7-109">Obsługa automatyzacji interfejsu użytkownika dla formantów typu kalendarz</span><span class="sxs-lookup"><span data-stu-id="973a7-109">UI Automation Support for the Calendar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-calendar-control-type.md)  
 [<span data-ttu-id="973a7-110">Obsługa automatyzacji interfejsu użytkownika dla typu formantu CheckBox</span><span class="sxs-lookup"><span data-stu-id="973a7-110">UI Automation Support for the CheckBox Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-checkbox-control-type.md)  
 [<span data-ttu-id="973a7-111">Obsługa automatyzacji interfejsu użytkownika dla typu formantu ComboBox</span><span class="sxs-lookup"><span data-stu-id="973a7-111">UI Automation Support for the ComboBox Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-combobox-control-type.md)  
 [<span data-ttu-id="973a7-112">Obsługa automatyzacji interfejsu użytkownika dla typu formantu DataGrid</span><span class="sxs-lookup"><span data-stu-id="973a7-112">UI Automation Support for the DataGrid Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-datagrid-control-type.md)  
 [<span data-ttu-id="973a7-113">Obsługa automatyzacji interfejsu użytkownika dla typu formantu DataItem</span><span class="sxs-lookup"><span data-stu-id="973a7-113">UI Automation Support for the DataItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-dataitem-control-type.md)  
 [<span data-ttu-id="973a7-114">Obsługa automatyzacji interfejsu użytkownika dla formantów typu dokument</span><span class="sxs-lookup"><span data-stu-id="973a7-114">UI Automation Support for the Document Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-document-control-type.md)  
 [<span data-ttu-id="973a7-115">Obsługa automatyzacji interfejsu użytkownika dla formantów typu Edycja</span><span class="sxs-lookup"><span data-stu-id="973a7-115">UI Automation Support for the Edit Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-edit-control-type.md)  
 [<span data-ttu-id="973a7-116">Obsługa automatyzacji interfejsu użytkownika dla formantów typu Grupa</span><span class="sxs-lookup"><span data-stu-id="973a7-116">UI Automation Support for the Group Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-group-control-type.md)  
 [<span data-ttu-id="973a7-117">Obsługa automatyzacji interfejsu użytkownika dla formantów typu Nagłówek</span><span class="sxs-lookup"><span data-stu-id="973a7-117">UI Automation Support for the Header Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-header-control-type.md)  
 [<span data-ttu-id="973a7-118">Obsługa automatyzacji interfejsu użytkownika dla typu formantu HeaderItem</span><span class="sxs-lookup"><span data-stu-id="973a7-118">UI Automation Support for the HeaderItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-headeritem-control-type.md)  
 [<span data-ttu-id="973a7-119">Obsługa automatyzacji interfejsu użytkownika dla formantów typu hiperłącze</span><span class="sxs-lookup"><span data-stu-id="973a7-119">UI Automation Support for the Hyperlink Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-hyperlink-control-type.md)  
 [<span data-ttu-id="973a7-120">Obsługa automatyzacji interfejsu użytkownika dla formantów typu obraz</span><span class="sxs-lookup"><span data-stu-id="973a7-120">UI Automation Support for the Image Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-image-control-type.md)  
 [<span data-ttu-id="973a7-121">Obsługa automatyzacji interfejsu użytkownika dla formantów typu Lista</span><span class="sxs-lookup"><span data-stu-id="973a7-121">UI Automation Support for the List Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-list-control-type.md)  
 [<span data-ttu-id="973a7-122">Obsługa automatyzacji interfejsu użytkownika dla typu formantu ListItem</span><span class="sxs-lookup"><span data-stu-id="973a7-122">UI Automation Support for the ListItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-listitem-control-type.md)  
 [<span data-ttu-id="973a7-123">Obsługa automatyzacji interfejsu użytkownika dla formantów typu Menu</span><span class="sxs-lookup"><span data-stu-id="973a7-123">UI Automation Support for the Menu Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menu-control-type.md)  
 [<span data-ttu-id="973a7-124">Obsługa automatyzacji interfejsu użytkownika dla typu formantu MenuBar</span><span class="sxs-lookup"><span data-stu-id="973a7-124">UI Automation Support for the MenuBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md)  
 [<span data-ttu-id="973a7-125">Obsługa automatyzacji interfejsu użytkownika dla typu formantu MenuItem</span><span class="sxs-lookup"><span data-stu-id="973a7-125">UI Automation Support for the MenuItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menuitem-control-type.md)  
 [<span data-ttu-id="973a7-126">Obsługa automatyzacji interfejsu użytkownika dla formantów typu okienko</span><span class="sxs-lookup"><span data-stu-id="973a7-126">UI Automation Support for the Pane Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-pane-control-type.md)  
 [<span data-ttu-id="973a7-127">Obsługa automatyzacji interfejsu użytkownika dla typu formantu ProgressBar</span><span class="sxs-lookup"><span data-stu-id="973a7-127">UI Automation Support for the ProgressBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-progressbar-control-type.md)  
 [<span data-ttu-id="973a7-128">Obsługa automatyzacji interfejsu użytkownika dla typu formantu RadioButton</span><span class="sxs-lookup"><span data-stu-id="973a7-128">UI Automation Support for the RadioButton Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-radiobutton-control-type.md)  
 [<span data-ttu-id="973a7-129">Obsługa automatyzacji interfejsu użytkownika dla typu formantu ScrollBar</span><span class="sxs-lookup"><span data-stu-id="973a7-129">UI Automation Support for the ScrollBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-scrollbar-control-type.md)  
 [<span data-ttu-id="973a7-130">Obsługa automatyzacji interfejsu użytkownika dla formantów typu Separator</span><span class="sxs-lookup"><span data-stu-id="973a7-130">UI Automation Support for the Separator Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-separator-control-type.md)  
 [<span data-ttu-id="973a7-131">Obsługa automatyzacji interfejsu użytkownika dla formantów typu suwak</span><span class="sxs-lookup"><span data-stu-id="973a7-131">UI Automation Support for the Slider Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-slider-control-type.md)  
 [<span data-ttu-id="973a7-132">Obsługa automatyzacji interfejsu użytkownika dla formantów typu pokrętło</span><span class="sxs-lookup"><span data-stu-id="973a7-132">UI Automation Support for the Spinner Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md)  
 [<span data-ttu-id="973a7-133">Obsługa automatyzacji interfejsu użytkownika dla typu formantu SplitButton</span><span class="sxs-lookup"><span data-stu-id="973a7-133">UI Automation Support for the SplitButton Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-splitbutton-control-type.md)  
 [<span data-ttu-id="973a7-134">Obsługa automatyzacji interfejsu użytkownika dla typu formantu StatusBar</span><span class="sxs-lookup"><span data-stu-id="973a7-134">UI Automation Support for the StatusBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-statusbar-control-type.md)  
 [<span data-ttu-id="973a7-135">Obsługa automatyzacji interfejsu użytkownika dla formantów typu karta</span><span class="sxs-lookup"><span data-stu-id="973a7-135">UI Automation Support for the Tab Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tab-control-type.md)  
 [<span data-ttu-id="973a7-136">Obsługa automatyzacji interfejsu użytkownika dla typu formantu TabItem</span><span class="sxs-lookup"><span data-stu-id="973a7-136">UI Automation Support for the TabItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tabitem-control-type.md)  
 [<span data-ttu-id="973a7-137">Obsługa automatyzacji interfejsu użytkownika dla formantów typu Tabela</span><span class="sxs-lookup"><span data-stu-id="973a7-137">UI Automation Support for the Table Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-table-control-type.md)  
 [<span data-ttu-id="973a7-138">Obsługa automatyzacji interfejsu użytkownika dla formantów typu tekst</span><span class="sxs-lookup"><span data-stu-id="973a7-138">UI Automation Support for the Text Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-text-control-type.md)  
 [<span data-ttu-id="973a7-139">Obsługa automatyzacji interfejsu użytkownika dla formantów typu Miniatura</span><span class="sxs-lookup"><span data-stu-id="973a7-139">UI Automation Support for the Thumb Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-thumb-control-type.md)  
 [<span data-ttu-id="973a7-140">Obsługa automatyzacji interfejsu użytkownika dla typu formantu TitleBar</span><span class="sxs-lookup"><span data-stu-id="973a7-140">UI Automation Support for the TitleBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-titlebar-control-type.md)  
 [<span data-ttu-id="973a7-141">Obsługa automatyzacji interfejsu użytkownika dla typu formantu paska narzędzi</span><span class="sxs-lookup"><span data-stu-id="973a7-141">UI Automation Support for the ToolBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-toolbar-control-type.md)  
 [<span data-ttu-id="973a7-142">Obsługa automatyzacji interfejsu użytkownika dla typu formantu ToolTip</span><span class="sxs-lookup"><span data-stu-id="973a7-142">UI Automation Support for the ToolTip Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tooltip-control-type.md)  
 [<span data-ttu-id="973a7-143">Obsługa automatyzacji interfejsu użytkownika dla typu formantu drzewa</span><span class="sxs-lookup"><span data-stu-id="973a7-143">UI Automation Support for the Tree Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tree-control-type.md)  
 [<span data-ttu-id="973a7-144">Obsługa automatyzacji interfejsu użytkownika dla typu formantu TreeItem</span><span class="sxs-lookup"><span data-stu-id="973a7-144">UI Automation Support for the TreeItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-treeitem-control-type.md)  
 [<span data-ttu-id="973a7-145">Obsługa automatyzacji interfejsu użytkownika dla formantów typu okno</span><span class="sxs-lookup"><span data-stu-id="973a7-145">UI Automation Support for the Window Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-window-control-type.md)  
  
## <a name="reference"></a><span data-ttu-id="973a7-146">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="973a7-146">Reference</span></span>  
 <xref:System.Windows.Automation.ControlType>  
  
## <a name="see-also"></a><span data-ttu-id="973a7-147">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="973a7-147">See Also</span></span>  
 [<span data-ttu-id="973a7-148">Wzorce formantów automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="973a7-148">UI Automation Control Patterns</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns.md)