---
title: "DateTimePicker — Informacje o formancie [Formularze systemu Windows]"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a97eecc43614c84867e9dbdd527dbebd7dfd426e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="datetimepicker-control-overview-windows-forms"></a><span data-ttu-id="ece4f-102">DateTimePicker — Informacje o formancie [Formularze systemu Windows]</span><span class="sxs-lookup"><span data-stu-id="ece4f-102">DateTimePicker Control Overview (Windows Forms)</span></span>
<span data-ttu-id="ece4f-103">Formularze systemu Windows <xref:System.Windows.Forms.DateTimePicker> formant umożliwia użytkownikowi wybranie pojedynczego elementu z listy daty i godziny.</span><span class="sxs-lookup"><span data-stu-id="ece4f-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control allows the user to select a single item from a list of dates or times.</span></span> <span data-ttu-id="ece4f-104">Gdy jest używany do reprezentowania datę, pojawi się z dwóch części: listy rozwijanej z przedstawiany w tekst i siatki, które pojawia się po kliknięciu Strzałka w dół obok listy.</span><span class="sxs-lookup"><span data-stu-id="ece4f-104">When used to represent a date, it appears in two parts: a drop-down list with a date represented in text, and a grid that appears when you click on the down-arrow next to the list.</span></span> <span data-ttu-id="ece4f-105">Siatka wygląda <xref:System.Windows.Forms.MonthCalendar> formantu, który może służyć do wybierania wielu daty.</span><span class="sxs-lookup"><span data-stu-id="ece4f-105">The grid looks like the <xref:System.Windows.Forms.MonthCalendar> control, which can be used for selecting multiple dates.</span></span> <span data-ttu-id="ece4f-106">Aby uzyskać więcej informacji na temat <xref:System.Windows.Forms.MonthCalendar> sterowania, zobacz [informacje o formancie MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ece4f-106">For more information on the <xref:System.Windows.Forms.MonthCalendar> control, see [MonthCalendar Control Overview](../../../../docs/framework/winforms/controls/monthcalendar-control-overview-windows-forms.md).</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="ece4f-107">Właściwości klucza</span><span class="sxs-lookup"><span data-stu-id="ece4f-107">Key Properties</span></span>  
 <span data-ttu-id="ece4f-108">W razie potrzeby <xref:System.Windows.Forms.DateTimePicker> były wyświetlane jako formant do pobrania lub edytowanie czasów zamiast dat, należy ustawić <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> właściwości `true` i <xref:System.Windows.Forms.DateTimePicker.Format%2A> właściwości <xref:System.Windows.Forms.DateTimePickerFormat.Time>.</span><span class="sxs-lookup"><span data-stu-id="ece4f-108">If you wish the <xref:System.Windows.Forms.DateTimePicker> to appear as a control for picking or editing times instead of dates, set the <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> property to `true` and the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to <xref:System.Windows.Forms.DateTimePickerFormat.Time>.</span></span> <span data-ttu-id="ece4f-109">Aby uzyskać więcej informacji, zobacz [porady: wyświetlanie czasu za pomocą formantu DateTimePicker](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md).</span><span class="sxs-lookup"><span data-stu-id="ece4f-109">For more information see [How to: Display Time with the DateTimePicker Control](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md).</span></span>  
  
 <span data-ttu-id="ece4f-110">Gdy <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> właściwość jest ustawiona na `true`, pole wyboru jest wyświetlany obok wybranej daty w formancie.</span><span class="sxs-lookup"><span data-stu-id="ece4f-110">When the <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> property is set to `true`, a check box is displayed next to the selected date in the control.</span></span> <span data-ttu-id="ece4f-111">Gdy pole wyboru jest zaznaczone, może zostać zaktualizowana wybranej wartości daty i godziny.</span><span class="sxs-lookup"><span data-stu-id="ece4f-111">When the check box is checked, the selected date-time value can be updated.</span></span> <span data-ttu-id="ece4f-112">Jeśli zaznaczenie jest puste, wartość znajduje się niedostępne.</span><span class="sxs-lookup"><span data-stu-id="ece4f-112">When the check box is empty, the value appears unavailable.</span></span>  
  
 <span data-ttu-id="ece4f-113">Kontrolki <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> i <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> właściwości określają zakres dat i godzin.</span><span class="sxs-lookup"><span data-stu-id="ece4f-113">The control's <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> and <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> properties determine the range of dates and times.</span></span> <span data-ttu-id="ece4f-114"><xref:System.Windows.Forms.DateTimePicker.Value%2A> Właściwość zawiera bieżącą datę i godzinę, o których ma ustawioną wartość formantu.</span><span class="sxs-lookup"><span data-stu-id="ece4f-114">The <xref:System.Windows.Forms.DateTimePicker.Value%2A> property contains the current date and time the control is set to.</span></span> <span data-ttu-id="ece4f-115">Aby uzyskać więcej informacji, zobacz [jak: zestaw i zwraca dat za pomocą formantu DateTimePicker formularzy systemu Windows](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md).</span><span class="sxs-lookup"><span data-stu-id="ece4f-115">For details, see [How to: Set and Return Dates with the Windows Forms DateTimePicker Control](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md).</span></span> <span data-ttu-id="ece4f-116">Wartości mogą być wyświetlane w czterech formatów, które są ustawiane przez <xref:System.Windows.Forms.DateTimePicker.Format%2A> właściwości: <xref:System.Windows.Forms.DateTimePickerFormat.Long>, <xref:System.Windows.Forms.DateTimePickerFormat.Short>, <xref:System.Windows.Forms.DateTimePickerFormat.Time>, lub <xref:System.Windows.Forms.DateTimePickerFormat.Custom>.</span><span class="sxs-lookup"><span data-stu-id="ece4f-116">The values can be displayed in four formats, which are set by the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property: <xref:System.Windows.Forms.DateTimePickerFormat.Long>, <xref:System.Windows.Forms.DateTimePickerFormat.Short>, <xref:System.Windows.Forms.DateTimePickerFormat.Time>, or <xref:System.Windows.Forms.DateTimePickerFormat.Custom>.</span></span> <span data-ttu-id="ece4f-117">Jeśli wybrano opcję formatu niestandardowego, należy ustawić <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> odpowiedni ciąg dla właściwości.</span><span class="sxs-lookup"><span data-stu-id="ece4f-117">If a custom format is selected, you must set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to an appropriate string.</span></span> <span data-ttu-id="ece4f-118">Aby uzyskać więcej informacji, zobacz [porady: wyświetlanie daty w formacie niestandardowych za pomocą formantu DateTimePicker formularzy systemu Windows](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md).</span><span class="sxs-lookup"><span data-stu-id="ece4f-118">For details, see [How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ece4f-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ece4f-119">See Also</span></span>  
 [<span data-ttu-id="ece4f-120">Porady: wyświetlanie daty w niestandardowym formacie za pomocą formantu DateTimePicker formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="ece4f-120">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)  
 [<span data-ttu-id="ece4f-121">Porady: Ustawianie i zwracanie dat z systemu Windows formantu DateTimePicker formularzy</span><span class="sxs-lookup"><span data-stu-id="ece4f-121">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)