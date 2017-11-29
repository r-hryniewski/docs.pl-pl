---
title: "Obsługa automatyzacji interfejsu użytkownika dla formantów typu miniatura"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control types, Thumb
- UI Automation, Thumb control type
- Thumb control type
ms.assetid: 13636338-e320-4355-b071-ede20a3fb1de
caps.latest.revision: "20"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 80de9fc87acb514bb8bf149d9930217173811012
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ui-automation-support-for-the-thumb-control-type"></a><span data-ttu-id="95674-102">Obsługa automatyzacji interfejsu użytkownika dla kontrolek typu miniatura</span><span class="sxs-lookup"><span data-stu-id="95674-102">UI Automation Support for the Thumb Control Type</span></span>
> [!NOTE]
>  <span data-ttu-id="95674-103">Ta dokumentacja jest przeznaczony dla deweloperów .NET Framework, które chcą korzystać zarządzanej [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="95674-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="95674-104">Aby uzyskać najnowsze informacje o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], zobacz [interfejsu API systemu Windows automatyzacji: automatyzacji interfejsu użytkownika](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="95674-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="95674-105">Ten temat zawiera informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] obsługę formantów typu miniatura.</span><span class="sxs-lookup"><span data-stu-id="95674-105">This topic provides information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] support for the Thumb control type.</span></span> <span data-ttu-id="95674-106">W [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], typu formantu to zestaw warunków, które muszą spełniać formantu, aby można było używać <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> właściwości.</span><span class="sxs-lookup"><span data-stu-id="95674-106">In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], a control type is a set of conditions that a control must meet in order to use the <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> property.</span></span> <span data-ttu-id="95674-107">Takie szczegółowe wytyczne dla [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] struktury drzewa [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] wartości właściwości i wzorce formantu.</span><span class="sxs-lookup"><span data-stu-id="95674-107">The conditions include specific guidelines for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] property values, and control patterns.</span></span>  
  
 <span data-ttu-id="95674-108">Thumb elementy sterujące udostępniają funkcje, które umożliwia kontrolę do przeniesienia (lub przeciągnąć), takie jak przycisk paska przewijania, lub o zmienionym rozmiarze, takie jak okna zmiany rozmiaru elementu widget.</span><span class="sxs-lookup"><span data-stu-id="95674-108">Thumb controls provide the functionality that enables a control to be moved (or dragged), such as a scroll bar button, or resized, such as a window resizing widget.</span></span> <span data-ttu-id="95674-109">Kontrolki Thumb również można zaimplementować jako ruchome obramowań okienka.</span><span class="sxs-lookup"><span data-stu-id="95674-109">Thumb controls can also be implemented as movable borders of panes.</span></span> <span data-ttu-id="95674-110">Należy pamiętać, że nie udostępnia funkcjonalność przeciągania i upuszczania.</span><span class="sxs-lookup"><span data-stu-id="95674-110">Note that it does not provide drag-and-drop functionality.</span></span> <span data-ttu-id="95674-111">Kontrolki Thumb może odbierać myszy fokus, ale zwykle nie fokus klawiatury.</span><span class="sxs-lookup"><span data-stu-id="95674-111">Thumb controls can receive mouse focus but usually not keyboard focus.</span></span> <span data-ttu-id="95674-112">Dewelopera kontrolek musi implementować formantu tak, aby pełnił odpowiednio (można przeciągnąć lub zmiany rozmiaru).</span><span class="sxs-lookup"><span data-stu-id="95674-112">The control developer must implement the control so that it acts appropriately (can be dragged or resized).</span></span>  
  
 <span data-ttu-id="95674-113">Następujące sekcje definiują wymaganych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] struktury, właściwości, wzorce formantów i zdarzeń dla formantów typu Miniatura drzewa.</span><span class="sxs-lookup"><span data-stu-id="95674-113">The following sections define the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, properties, control patterns, and events for the Thumb control type.</span></span> <span data-ttu-id="95674-114">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Wymagania dotyczą wszystkich kontrolek przycisku czy [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], lub [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95674-114">The [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requirements apply to all thumb controls, whether [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], or [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a><span data-ttu-id="95674-115">Struktura drzewa automatyzacji interfejsu użytkownika wymagane</span><span class="sxs-lookup"><span data-stu-id="95674-115">Required UI Automation Tree Structure</span></span>  
 <span data-ttu-id="95674-116">Poniższa tabela przedstawia kontroli i widok zawartości [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] drzewa, które dotyczą przycisku kontrolki i opisano, jakie mogą być zawarte w każdym widoku.</span><span class="sxs-lookup"><span data-stu-id="95674-116">The following table depicts the control view and the content view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree that pertains to thumb controls and describes what can be contained in each view.</span></span> <span data-ttu-id="95674-117">Aby uzyskać więcej informacji na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] drzewa, zobacz [Przegląd drzewa automatyzacji interfejsu użytkownika](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span><span class="sxs-lookup"><span data-stu-id="95674-117">For more information on the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree, see [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span></span>  
  
|<span data-ttu-id="95674-118">Kontrolki widoku</span><span class="sxs-lookup"><span data-stu-id="95674-118">Control View</span></span>|<span data-ttu-id="95674-119">Widok zawartości</span><span class="sxs-lookup"><span data-stu-id="95674-119">Content View</span></span>|  
|------------------|------------------|  
|<span data-ttu-id="95674-120">Thumb</span><span class="sxs-lookup"><span data-stu-id="95674-120">Thumb</span></span>|<span data-ttu-id="95674-121">-Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="95674-121">-   Not applicable</span></span>|  
  
 <span data-ttu-id="95674-122">Kontrolki Thumb są wyświetlane w widoku zawartości nigdy nie, ponieważ istnieją dla jest zmodyfikowany za pomocą myszy.</span><span class="sxs-lookup"><span data-stu-id="95674-122">Thumb controls never appear in Content View because they only exist for being manipulated with a mouse.</span></span> <span data-ttu-id="95674-123">Ich funkcji jest widoczne, ale innego — wzorzec formantu, takie jak Scroll — wzorzec, Przekształć wzorzec lub wzorzec RangeValue dla jest obsługiwany w kontenerze pamięci przenośnej.</span><span class="sxs-lookup"><span data-stu-id="95674-123">Their functionality is exposed though another control pattern, such as Scroll Pattern, Transform Pattern, or RangeValue Pattern, being supported on the Thumb container.</span></span>  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a><span data-ttu-id="95674-124">Właściwości automatyzacji interfejsu użytkownika wymagane</span><span class="sxs-lookup"><span data-stu-id="95674-124">Required UI Automation Properties</span></span>  
 <span data-ttu-id="95674-125">W poniższej tabeli wymieniono [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] właściwości, której wartość lub definicji jest szczególnie istotne przycisku kontrolki.</span><span class="sxs-lookup"><span data-stu-id="95674-125">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties whose value or definition is especially relevant to thumb controls.</span></span> <span data-ttu-id="95674-126">Aby uzyskać więcej informacji na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] właściwości, zobacz [właściwości automatyzacji interfejsu użytkownika dla klientów](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="95674-126">For more information on [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties, see [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="95674-127">Właściwość</span><span class="sxs-lookup"><span data-stu-id="95674-127"> Property</span></span>|<span data-ttu-id="95674-128">Wartość</span><span class="sxs-lookup"><span data-stu-id="95674-128">Value</span></span>|<span data-ttu-id="95674-129">Uwagi</span><span class="sxs-lookup"><span data-stu-id="95674-129">Notes</span></span>|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|<span data-ttu-id="95674-130">Zobacz uwagi.</span><span class="sxs-lookup"><span data-stu-id="95674-130">See notes.</span></span>|<span data-ttu-id="95674-131">Wartość tej właściwości musi być unikatowy w obrębie wszystkich kontrolek w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="95674-131">The value of this property needs to be unique across all controls in an application.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|<span data-ttu-id="95674-132">Zobacz uwagi.</span><span class="sxs-lookup"><span data-stu-id="95674-132">See notes.</span></span>|<span data-ttu-id="95674-133">Prostokąt peryferyjnych zawiera całą formantu.</span><span class="sxs-lookup"><span data-stu-id="95674-133">The outermost rectangle that contains the whole control.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|<span data-ttu-id="95674-134">Zobacz uwagi.</span><span class="sxs-lookup"><span data-stu-id="95674-134">See notes.</span></span>|<span data-ttu-id="95674-135">Żadnego punktu wewnątrz obszaru klienckiego widoczne kontrolki Thumb.</span><span class="sxs-lookup"><span data-stu-id="95674-135">Any point within the visible client area of the Thumb control.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|<span data-ttu-id="95674-136">Zobacz uwagi.</span><span class="sxs-lookup"><span data-stu-id="95674-136">See notes.</span></span>|<span data-ttu-id="95674-137">Formant może przyjmować fokus klawiatury, musi obsługiwać tej właściwości.</span><span class="sxs-lookup"><span data-stu-id="95674-137">If the control can receive keyboard focus, it must support this property.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|`Null`|<span data-ttu-id="95674-138">Kontrolki Thumb nie jest dostępny w zawartości widoku drzewa automatyzacji interfejsu użytkownika, więc nie wymaga nazwy.</span><span class="sxs-lookup"><span data-stu-id="95674-138">The Thumb control is not available in the Content View of the UI Automation tree so it does not require a name.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|<span data-ttu-id="95674-139">Kontrolki Thumb nigdy nie ma etykiety.</span><span class="sxs-lookup"><span data-stu-id="95674-139">Thumb controls never have a label.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|<span data-ttu-id="95674-140">Thumb</span><span class="sxs-lookup"><span data-stu-id="95674-140">Thumb</span></span>|<span data-ttu-id="95674-141">Ta wartość jest taka sama dla wszystkich platform interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="95674-141">This value is the same for all UI frameworks.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|<span data-ttu-id="95674-142">"thumb"</span><span class="sxs-lookup"><span data-stu-id="95674-142">"thumb"</span></span>|<span data-ttu-id="95674-143">Zlokalizowany ciąg odpowiadający Thumb — typ formantu.</span><span class="sxs-lookup"><span data-stu-id="95674-143">Localized string corresponding to the Thumb control type.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|<span data-ttu-id="95674-144">False</span><span class="sxs-lookup"><span data-stu-id="95674-144">False</span></span>|<span data-ttu-id="95674-145">Kontrolki Thumb nigdy nie jest zawartości.</span><span class="sxs-lookup"><span data-stu-id="95674-145">The Thumb control is never content.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|<span data-ttu-id="95674-146">Wartość true</span><span class="sxs-lookup"><span data-stu-id="95674-146">True</span></span>|<span data-ttu-id="95674-147">Kontrolki Thumb zawsze musi być formantem.</span><span class="sxs-lookup"><span data-stu-id="95674-147">The Thumb control must always be a control.</span></span>|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a><span data-ttu-id="95674-148">Wzorce formantów automatyzacji interfejsu użytkownika wymagane</span><span class="sxs-lookup"><span data-stu-id="95674-148">Required UI Automation Control Patterns</span></span>  
 <span data-ttu-id="95674-149">W poniższej tabeli wymieniono [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] kontrolować wzorce wymagane do obsługi przez kontrolki thumb.</span><span class="sxs-lookup"><span data-stu-id="95674-149">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] control patterns required to be supported by thumb controls.</span></span> <span data-ttu-id="95674-150">Aby uzyskać więcej informacji na wzorce formantów, zobacz [Przegląd wzorców formantu automatyzacji interfejsu użytkownika](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).</span><span class="sxs-lookup"><span data-stu-id="95674-150">For more information on control patterns, see [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).</span></span>  
  
|<span data-ttu-id="95674-151">Właściwość wzorzec/wzorzec formantu</span><span class="sxs-lookup"><span data-stu-id="95674-151">Control Pattern/Pattern Property</span></span>|<span data-ttu-id="95674-152">Obsługa i wartości</span><span class="sxs-lookup"><span data-stu-id="95674-152">Support/Value</span></span>|<span data-ttu-id="95674-153">Uwagi</span><span class="sxs-lookup"><span data-stu-id="95674-153">Notes</span></span>|  
|---------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider>|<span data-ttu-id="95674-154">Wymagane</span><span class="sxs-lookup"><span data-stu-id="95674-154">Required</span></span>|<span data-ttu-id="95674-155">Umożliwia kontrolki thumb ma zostać przeniesiona na ekranie.</span><span class="sxs-lookup"><span data-stu-id="95674-155">Enables the thumb control to be moved on the screen.</span></span>|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a><span data-ttu-id="95674-156">Zdarzeń automatyzacji interfejsu użytkownika wymagane</span><span class="sxs-lookup"><span data-stu-id="95674-156">Required UI Automation Events</span></span>  
 <span data-ttu-id="95674-157">W poniższej tabeli wymieniono [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] zdarzenia wymagane obsługiwane przez wszystkie kontrolki thumb.</span><span class="sxs-lookup"><span data-stu-id="95674-157">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] events required to be supported by all thumb controls.</span></span> <span data-ttu-id="95674-158">Aby uzyskać więcej informacji o zdarzeniach, zobacz [Przegląd zdarzeń automatyzacji interfejsu użytkownika](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="95674-158">For more information about events, see [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="95674-159">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="95674-159"> Event</span></span>|<span data-ttu-id="95674-160">Obsługa</span><span class="sxs-lookup"><span data-stu-id="95674-160">Support</span></span>|<span data-ttu-id="95674-161">Uwagi</span><span class="sxs-lookup"><span data-stu-id="95674-161">Notes</span></span>|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<span data-ttu-id="95674-162"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>Zdarzenie zmiany właściwości.</span><span class="sxs-lookup"><span data-stu-id="95674-162"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> property-changed event.</span></span>|<span data-ttu-id="95674-163">Wymagane</span><span class="sxs-lookup"><span data-stu-id="95674-163">Required</span></span>|<span data-ttu-id="95674-164">Brak</span><span class="sxs-lookup"><span data-stu-id="95674-164">None</span></span>|  
|<span data-ttu-id="95674-165"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>Zdarzenie zmiany właściwości.</span><span class="sxs-lookup"><span data-stu-id="95674-165"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> property-changed event.</span></span>|<span data-ttu-id="95674-166">Wymagane</span><span class="sxs-lookup"><span data-stu-id="95674-166">Required</span></span>|<span data-ttu-id="95674-167">Brak</span><span class="sxs-lookup"><span data-stu-id="95674-167">None</span></span>|  
|<span data-ttu-id="95674-168"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>Zdarzenie zmiany właściwości.</span><span class="sxs-lookup"><span data-stu-id="95674-168"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> property-changed event.</span></span>|<span data-ttu-id="95674-169">Wymagane</span><span class="sxs-lookup"><span data-stu-id="95674-169">Required</span></span>|<span data-ttu-id="95674-170">Brak</span><span class="sxs-lookup"><span data-stu-id="95674-170">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|<span data-ttu-id="95674-171">Wymagane</span><span class="sxs-lookup"><span data-stu-id="95674-171">Required</span></span>|<span data-ttu-id="95674-172">Brak</span><span class="sxs-lookup"><span data-stu-id="95674-172">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|<span data-ttu-id="95674-173">Wymagane</span><span class="sxs-lookup"><span data-stu-id="95674-173">Required</span></span>|<span data-ttu-id="95674-174">Brak</span><span class="sxs-lookup"><span data-stu-id="95674-174">None</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95674-175">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="95674-175">See Also</span></span>  
 <xref:System.Windows.Automation.ControlType.Thumb>  
 [<span data-ttu-id="95674-176">Przegląd typów formantu automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="95674-176">UI Automation Control Types Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)  
 [<span data-ttu-id="95674-177">Przegląd automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="95674-177">UI Automation Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-overview.md)