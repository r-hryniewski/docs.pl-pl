---
title: "CheckBox — Style i szablony"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], CheckBox
- templates [WPF], CheckBox
- parts [WPF], CheckBox
- ControlTemplate [WPF], CheckBox
- CheckBox [WPF], styles and templates
- styles [WPF], CheckBox
ms.assetid: bfdaec96-d101-4d3d-864d-c27e6b621d03
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c901d710e96cd111104b9fef2219b157377adc3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="checkbox-styles-and-templates"></a><span data-ttu-id="ac8d1-102">CheckBox — Style i szablony</span><span class="sxs-lookup"><span data-stu-id="ac8d1-102">CheckBox Styles and Templates</span></span>
<span data-ttu-id="ac8d1-103">W tym temacie opisano, style i szablonów dla <xref:System.Windows.Controls.CheckBox> formantu.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.CheckBox> control.</span></span> <span data-ttu-id="ac8d1-104">Można zmodyfikować domyślne <xref:System.Windows.Controls.ControlTemplate> umożliwiają unikatowego wyglądu formantu.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ac8d1-105">Aby uzyskać więcej informacji, zobacz [Dostosowywanie wyglądu formant tworząc ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="ac8d1-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="checkbox-parts"></a><span data-ttu-id="ac8d1-106">Części pola wyboru</span><span class="sxs-lookup"><span data-stu-id="ac8d1-106">CheckBox Parts</span></span>  
 <span data-ttu-id="ac8d1-107"><xref:System.Windows.Controls.CheckBox> Formant nie ma żadnych części o nazwie.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-107">The <xref:System.Windows.Controls.CheckBox> control does not have any named parts.</span></span>  
  
## <a name="checkbox-states"></a><span data-ttu-id="ac8d1-108">Stany pola wyboru</span><span class="sxs-lookup"><span data-stu-id="ac8d1-108">CheckBox States</span></span>  
 <span data-ttu-id="ac8d1-109">W poniższej tabeli wymieniono stany wizualne dla <xref:System.Windows.Controls.CheckBox> formantu.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-109">The following table lists the visual states for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
|<span data-ttu-id="ac8d1-110">Nazwa stanu wizualnego</span><span class="sxs-lookup"><span data-stu-id="ac8d1-110">VisualState Name</span></span>|<span data-ttu-id="ac8d1-111">Nazwa VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="ac8d1-111">VisualStateGroup Name</span></span>|<span data-ttu-id="ac8d1-112">Opis</span><span class="sxs-lookup"><span data-stu-id="ac8d1-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="ac8d1-113">Normalny</span><span class="sxs-lookup"><span data-stu-id="ac8d1-113">Normal</span></span>|<span data-ttu-id="ac8d1-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ac8d1-114">CommonStates</span></span>|<span data-ttu-id="ac8d1-115">Stan domyślny.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-115">The default state.</span></span>|  
|<span data-ttu-id="ac8d1-116">Etykietka wskaźnika myszy</span><span class="sxs-lookup"><span data-stu-id="ac8d1-116">MouseOver</span></span>|<span data-ttu-id="ac8d1-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ac8d1-117">CommonStates</span></span>|<span data-ttu-id="ac8d1-118">Wskaźnik myszy znajduje się nad formantem.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="ac8d1-119">Naciśnięto</span><span class="sxs-lookup"><span data-stu-id="ac8d1-119">Pressed</span></span>|<span data-ttu-id="ac8d1-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ac8d1-120">CommonStates</span></span>|<span data-ttu-id="ac8d1-121">Formant zostanie naciśnięty.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-121">The control is pressed.</span></span>|  
|<span data-ttu-id="ac8d1-122">Wyłączone</span><span class="sxs-lookup"><span data-stu-id="ac8d1-122">Disabled</span></span>|<span data-ttu-id="ac8d1-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ac8d1-123">CommonStates</span></span>|<span data-ttu-id="ac8d1-124">Kontrolka jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-124">The control is disabled.</span></span>|  
|<span data-ttu-id="ac8d1-125">Fokus</span><span class="sxs-lookup"><span data-stu-id="ac8d1-125">Focused</span></span>|<span data-ttu-id="ac8d1-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ac8d1-126">FocusStates</span></span>|<span data-ttu-id="ac8d1-127">Formant ma fokus.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-127">The control has focus.</span></span>|  
|<span data-ttu-id="ac8d1-128">Bez fokusu</span><span class="sxs-lookup"><span data-stu-id="ac8d1-128">Unfocused</span></span>|<span data-ttu-id="ac8d1-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ac8d1-129">FocusStates</span></span>|<span data-ttu-id="ac8d1-130">Formant nie ma fokusa.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="ac8d1-131">Zaznaczone</span><span class="sxs-lookup"><span data-stu-id="ac8d1-131">Checked</span></span>|<span data-ttu-id="ac8d1-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="ac8d1-132">CheckStates</span></span>|<span data-ttu-id="ac8d1-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>jest `true`.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="ac8d1-134">Unchecked</span><span class="sxs-lookup"><span data-stu-id="ac8d1-134">Unchecked</span></span>|<span data-ttu-id="ac8d1-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="ac8d1-135">CheckStates</span></span>|<span data-ttu-id="ac8d1-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>jest `false`.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="ac8d1-137">Nieokreślony</span><span class="sxs-lookup"><span data-stu-id="ac8d1-137">Indeterminate</span></span>|<span data-ttu-id="ac8d1-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="ac8d1-138">CheckStates</span></span>|<span data-ttu-id="ac8d1-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>jest `true`, i <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> jest `null`.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="ac8d1-140">Prawidłowe</span><span class="sxs-lookup"><span data-stu-id="ac8d1-140">Valid</span></span>|<span data-ttu-id="ac8d1-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ac8d1-141">ValidationStates</span></span>|<span data-ttu-id="ac8d1-142">Używa kontrolki <xref:System.Windows.Controls.Validation> klasy i <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> jest dołączona właściwość `false`.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ac8d1-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ac8d1-143">InvalidUnfocused</span></span>|<span data-ttu-id="ac8d1-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ac8d1-144">ValidationStates</span></span>|<span data-ttu-id="ac8d1-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Jest dołączona właściwość `true` ma formant ma fokus.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ac8d1-146">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ac8d1-146">InvalidFocused</span></span>|<span data-ttu-id="ac8d1-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ac8d1-147">ValidationStates</span></span>|<span data-ttu-id="ac8d1-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Jest dołączona właściwość `true` ma formant nie ma fokusa.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="checkbox-controltemplate-example"></a><span data-ttu-id="ac8d1-149">Przykład ControlTemplate wyboru</span><span class="sxs-lookup"><span data-stu-id="ac8d1-149">CheckBox ControlTemplate Example</span></span>  
 <span data-ttu-id="ac8d1-150">Poniższy przykład przedstawia sposób definiowania <xref:System.Windows.Controls.ControlTemplate> dla <xref:System.Windows.Controls.CheckBox> formantu.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#CheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/checkbox.xaml#checkbox)]  
  
 <span data-ttu-id="ac8d1-151">Powyższy przykład korzysta z co najmniej jeden z następujących zasobów.</span><span class="sxs-lookup"><span data-stu-id="ac8d1-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ac8d1-152">Pełny przykład, zobacz [style próbki ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="ac8d1-152">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac8d1-153">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ac8d1-153">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="ac8d1-154">Style formantu i szablony</span><span class="sxs-lookup"><span data-stu-id="ac8d1-154">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="ac8d1-155">Dostosowywanie formantu</span><span class="sxs-lookup"><span data-stu-id="ac8d1-155">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="ac8d1-156">Style i tworzenia szablonów</span><span class="sxs-lookup"><span data-stu-id="ac8d1-156">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="ac8d1-157">Dostosowywanie wyglądu formant tworząc ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="ac8d1-157">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)