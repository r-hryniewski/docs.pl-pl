---
title: "Porady: wyodrębnianie dnia tygodnia z określonej daty"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [.NET Framework], dates
- DateTime.DayOfWeek property
- DateTime.ToString method
- dates [.NET Framework], retrieving week information
- DateTimeOffset.DayOfWeek property
- dates [.NET Framework], day of week
- Weekday function
- day of week [.NET Framework]
- extracting day of week
- weekday names
- WeekdayName function
- numbers [.NET Framework], day of week
- formatting [.NET Framework], time
- DateTimeOffset.ToString method
- full weekday names
ms.assetid: 1c9bef76-5634-46cf-b91c-9b9eb72091d7
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3accb01eb8c5edb8b3e245020b43c5a94a8bb4cd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-extract-the-day-of-the-week-from-a-specific-date"></a><span data-ttu-id="00a0c-102">Porady: wyodrębnianie dnia tygodnia z określonej daty</span><span class="sxs-lookup"><span data-stu-id="00a0c-102">How to: Extract the Day of the Week from a Specific Date</span></span>
<span data-ttu-id="00a0c-103">.NET Framework ułatwia ustalenie liczby porządkowej dzień tygodnia dla określonej daty i wyświetlić nazwę zlokalizowanej dzień tygodnia dla określonej daty.</span><span class="sxs-lookup"><span data-stu-id="00a0c-103">The .NET Framework makes it easy to determine the ordinal day of the week for a particular date, and to display the localized weekday name for a particular date.</span></span> <span data-ttu-id="00a0c-104">Wartość wyliczenia, która wskazuje dzień tygodnia odpowiadający określonej daty jest dostępna z <xref:System.DateTime.DayOfWeek%2A> lub <xref:System.DateTimeOffset.DayOfWeek%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="00a0c-104">An enumerated value that indicates the day of the week corresponding to a particular date is available from the <xref:System.DateTime.DayOfWeek%2A> or <xref:System.DateTimeOffset.DayOfWeek%2A> property.</span></span> <span data-ttu-id="00a0c-105">Z kolei pobierania nazwy dni tygodnia operacji formatowania, które mogą być wykonywane przez wywołanie metody formatowania, takie jak wartość daty i godziny jest `ToString` metody lub <xref:System.String.Format%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="00a0c-105">In contrast, retrieving the weekday name is a formatting operation that can be performed by calling a formatting method, such as a date and time value's `ToString` method or the <xref:System.String.Format%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="00a0c-106">W tym temacie przedstawiono sposób wykonywania tych operacji formatowania.</span><span class="sxs-lookup"><span data-stu-id="00a0c-106">This topic shows how to perform these formatting operations.</span></span>  
  
### <a name="to-extract-a-number-indicating-the-day-of-the-week-from-a-specific-date"></a><span data-ttu-id="00a0c-107">Aby wyodrębnić liczbę określającą dzień tygodnia z określonej daty</span><span class="sxs-lookup"><span data-stu-id="00a0c-107">To extract a number indicating the day of the week from a specific date</span></span>  
  
1.  <span data-ttu-id="00a0c-108">Jeśli pracujesz z ciągiem znaków reprezentującym datę, należy przekonwertować ciąg do wartości <xref:System.DateTime> lub <xref:System.DateTimeOffset> przy użyciu statycznej metody <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> lub <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="00a0c-108">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="00a0c-109">Użyj <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> lub <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> właściwości do pobrania <xref:System.DayOfWeek> wartość, która wskazuje dzień tygodnia.</span><span class="sxs-lookup"><span data-stu-id="00a0c-109">Use the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> property to retrieve a <xref:System.DayOfWeek> value that indicates the day of the week.</span></span>  
  
3.  <span data-ttu-id="00a0c-110">W razie potrzeby rzutowanie (C#) lub przekonwertować (w języku Visual Basic) <xref:System.DayOfWeek> wartość na liczbę całkowitą.</span><span class="sxs-lookup"><span data-stu-id="00a0c-110">If necessary, cast (in C#) or convert (in Visual Basic) the <xref:System.DayOfWeek> value to an integer.</span></span>  
  
 <span data-ttu-id="00a0c-111">W poniższym przykładzie przedstawiono całkowitą reprezentującą dzień tygodnia z określonej daty.</span><span class="sxs-lookup"><span data-stu-id="00a0c-111">The following example displays an integer that represents the day of the week of a specific date.</span></span>  
  
 [!code-csharp[Formatting.Howto.WeekdayName#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/weekdaynumber7.cs#7)]
 [!code-vb[Formatting.Howto.WeekdayName#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/weekdaynumber7.vb#7)]  
  
### <a name="to-extract-the-abbreviated-weekday-name-from-a-specific-date"></a><span data-ttu-id="00a0c-112">Aby wyodrębnić nazwy skróconej dzień tygodnia z określonej daty</span><span class="sxs-lookup"><span data-stu-id="00a0c-112">To extract the abbreviated weekday name from a specific date</span></span>  
  
1.  <span data-ttu-id="00a0c-113">Jeśli pracujesz z ciągiem znaków reprezentującym datę, należy przekonwertować ciąg do wartości <xref:System.DateTime> lub <xref:System.DateTimeOffset> przy użyciu statycznej metody <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> lub <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="00a0c-113">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="00a0c-114">Można wyodrębnić nazwy skróconej dzień tygodnia bieżącej kultury lub kultury określonej:</span><span class="sxs-lookup"><span data-stu-id="00a0c-114">You can extract the abbreviated weekday name of the current culture or of a specific culture:</span></span>  
  
    1.  <span data-ttu-id="00a0c-115">Aby wyodrębnić nazwy skróconej dzień tygodnia dla bieżącej kultury, należy wywołać wartość daty i godziny <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> lub <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> metody wystąpienia i przekazać ciąg "ddd" jako `format` parametru.</span><span class="sxs-lookup"><span data-stu-id="00a0c-115">To extract the abbreviated weekday name for the current culture, call the date and time value's <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> instance method, and pass the string "ddd" as the `format` parameter.</span></span> <span data-ttu-id="00a0c-116">Poniższy przykład przedstawia wywołanie <xref:System.DateTime.ToString%28System.String%29> metody.</span><span class="sxs-lookup"><span data-stu-id="00a0c-116">The following example illustrates the call to the <xref:System.DateTime.ToString%28System.String%29> method.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/abbrname1.cs#1)]
         [!code-vb[Formatting.Howto.WeekdayName#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/abbrname1.vb#1)]  
  
    2.  <span data-ttu-id="00a0c-117">Aby wyodrębnić nazwy skróconej dzień tygodnia dla określonej kultury, należy wywołać wartość daty i godziny <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> lub <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> metody wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="00a0c-117">To extract the abbreviated weekday name for a specific culture, call the date and time value’s <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="00a0c-118">Przekazać ciąg "ddd" jako `format` parametru.</span><span class="sxs-lookup"><span data-stu-id="00a0c-118">Pass the string "ddd" as the `format` parameter.</span></span> <span data-ttu-id="00a0c-119">Przekaż albo <xref:System.Globalization.CultureInfo> lub <xref:System.Globalization.DateTimeFormatInfo> obiekt, który reprezentuje kultury, których chcesz pobrać jako nazwa dnia tygodnia `provider` parametru.</span><span class="sxs-lookup"><span data-stu-id="00a0c-119">Pass either a <xref:System.Globalization.CultureInfo> or a <xref:System.Globalization.DateTimeFormatInfo> object that represents the culture whose weekday name you want to retrieve as the `provider` parameter.</span></span> <span data-ttu-id="00a0c-120">Poniższy kod ilustruje wywołanie <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> przy użyciu metody <xref:System.Globalization.CultureInfo> obiekt, który reprezentuje fr-FR kultury.</span><span class="sxs-lookup"><span data-stu-id="00a0c-120">The following code illustrates a call to the <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> method using a <xref:System.Globalization.CultureInfo> object that represents the fr-FR culture.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/abbrname2.cs#2)]
         [!code-vb[Formatting.Howto.WeekdayName#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/abbrname2.vb#2)]  
  
### <a name="to-extract-the-full-weekday-name-from-a-specific-date"></a><span data-ttu-id="00a0c-121">Aby wyodrębnić Pełna nazwa dnia tygodnia z określonej daty</span><span class="sxs-lookup"><span data-stu-id="00a0c-121">To extract the full weekday name from a specific date</span></span>  
  
1.  <span data-ttu-id="00a0c-122">Jeśli pracujesz z ciągiem znaków reprezentującym datę, należy przekonwertować ciąg do wartości <xref:System.DateTime> lub <xref:System.DateTimeOffset> przy użyciu statycznej metody <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> lub <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="00a0c-122">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="00a0c-123">Pełna nazwa dnia tygodnia bieżącej kultury lub określoną kulturę można wyodrębnić:</span><span class="sxs-lookup"><span data-stu-id="00a0c-123">You can extract the full weekday name of the current culture or of a specific culture:</span></span>  
  
    1.  <span data-ttu-id="00a0c-124">Aby wyodrębnić nazwy dni tygodnia dla bieżącej kultury, należy wywołać wartość daty i godziny <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> lub <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> metody wystąpienia i przekazać ciąg "dddd" jako `format` parametru.</span><span class="sxs-lookup"><span data-stu-id="00a0c-124">To extract the weekday name for the current culture, call the date and time value’s <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> instance method, and pass the string "dddd" as the `format` parameter.</span></span> <span data-ttu-id="00a0c-125">Poniższy przykład przedstawia wywołanie <xref:System.DateTime.ToString%28System.String%29> metody.</span><span class="sxs-lookup"><span data-stu-id="00a0c-125">The following example illustrates the call to the <xref:System.DateTime.ToString%28System.String%29> method.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/fullname4.cs#4)]
         [!code-vb[Formatting.Howto.WeekdayName#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/fullname4.vb#4)]  
  
    2.  <span data-ttu-id="00a0c-126">Aby wyodrębnić nazwy dni tygodnia dla określonej kultury, należy wywołać wartość daty i godziny <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> lub <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> metody wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="00a0c-126">To extract the weekday name for a specific culture, call the date and time value’s <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="00a0c-127">Przekazać ciąg "dddd" jako `format` parametru.</span><span class="sxs-lookup"><span data-stu-id="00a0c-127">Pass the string "dddd" as the `format` parameter.</span></span> <span data-ttu-id="00a0c-128">Przekaż albo <xref:System.Globalization.CultureInfo> lub <xref:System.Globalization.DateTimeFormatInfo> obiekt, który reprezentuje kultury, których chcesz pobrać jako nazwa dnia tygodnia `provider` parametru.</span><span class="sxs-lookup"><span data-stu-id="00a0c-128">Pass either a <xref:System.Globalization.CultureInfo> or a <xref:System.Globalization.DateTimeFormatInfo> object that represents the culture whose weekday name you want to retrieve as the `provider` parameter.</span></span> <span data-ttu-id="00a0c-129">Poniższy kod ilustruje wywołanie <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> przy użyciu metody <xref:System.Globalization.CultureInfo> obiekt, który reprezentuje es-ES kultury.</span><span class="sxs-lookup"><span data-stu-id="00a0c-129">The following code illustrates a call to the <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> method using a <xref:System.Globalization.CultureInfo> object that represents the es-ES culture.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/fullname5.cs#5)]
         [!code-vb[Formatting.Howto.WeekdayName#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/fullname5.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="00a0c-130">Przykład</span><span class="sxs-lookup"><span data-stu-id="00a0c-130">Example</span></span>  
 <span data-ttu-id="00a0c-131">Wywołania pokazano w przykładzie <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> i <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> właściwości i <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> i <xref:System.DateTimeOffset.ToString%2A?displayProperty=nameWithType> metody, aby pobrać liczbę reprezentującą dzień tygodnia, nazwy skróconej dzień tygodnia i Pełna nazwa dnia tygodnia dla określonej daty.</span><span class="sxs-lookup"><span data-stu-id="00a0c-131">The example illustrates calls to the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> and <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> properties and the <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> and <xref:System.DateTimeOffset.ToString%2A?displayProperty=nameWithType> methods to retrieve the number that represents the day of the week, the abbreviated weekday name, and the full weekday name for a particular date.</span></span>  
  
 [!code-csharp[Formatting.Howto.WeekdayName#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/example6.cs#6)]
 [!code-vb[Formatting.Howto.WeekdayName#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/example6.vb#6)]  
  
 <span data-ttu-id="00a0c-132">Poszczególne języki mogą zapewnić funkcje, których duplikatów lub uzupełniają funkcje udostępniane przez [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00a0c-132">Individual languages may provide functionality that duplicates or supplements the functionality provided by the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="00a0c-133">Na przykład Visual Basic zawiera dwie funkcje:</span><span class="sxs-lookup"><span data-stu-id="00a0c-133">For example, Visual Basic includes two such functions:</span></span>  
  
-   <span data-ttu-id="00a0c-134">`Weekday`, która zwraca liczbę wskazującą dzień tygodnia z określonej daty.</span><span class="sxs-lookup"><span data-stu-id="00a0c-134">`Weekday`, which returns a number that indicates the day of the week of a particular date.</span></span> <span data-ttu-id="00a0c-135">Traktuje wartość porządkową pierwszego dnia tygodnia jedną, podczas gdy <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> właściwości uzna zero.</span><span class="sxs-lookup"><span data-stu-id="00a0c-135">It considers the ordinal value of the first day of the week to be one, whereas the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> property considers it to be zero.</span></span>  
  
-   <span data-ttu-id="00a0c-136">`WeekdayName`, które zwraca nazwę tygodnia w bieżącej kultury, która odpowiada numerowi określonego dnia tygodnia.</span><span class="sxs-lookup"><span data-stu-id="00a0c-136">`WeekdayName`, which returns the name of the week in the current culture that corresponds to a particular weekday number.</span></span>  
  
 <span data-ttu-id="00a0c-137">Poniższy przykład przedstawia użycie Visual Basic `Weekday` i `WeekdayName` funkcji.</span><span class="sxs-lookup"><span data-stu-id="00a0c-137">The following example illustrates the use of the Visual Basic `Weekday` and `WeekdayName` functions.</span></span>  
  
 [!code-vb[Formatting.HowTo.WeekdayName#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/example9.vb#9)]  
  
 <span data-ttu-id="00a0c-138">Umożliwia także wartość zwrócona przez <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> właściwości pobrać nazwy dni tygodnia z określonej daty.</span><span class="sxs-lookup"><span data-stu-id="00a0c-138">You can also use the value returned by the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> property to retrieve the weekday name of a particular date.</span></span> <span data-ttu-id="00a0c-139">Wymaga to tylko wywołania <xref:System.Enum.ToString%2A> metoda <xref:System.DayOfWeek> wartość zwracana przez właściwość.</span><span class="sxs-lookup"><span data-stu-id="00a0c-139">This requires only a call to the <xref:System.Enum.ToString%2A> method on the <xref:System.DayOfWeek> value returned by the property.</span></span> <span data-ttu-id="00a0c-140">Ta technika nie tworzy jednak nazwę zlokalizowanej dzień tygodnia dla bieżącej kultury, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="00a0c-140">However, this technique does not produce a localized weekday name for the current culture, as the following example illustrates.</span></span>  
  
 [!code-csharp[Formatting.HowTo.WeekdayName#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/Howto1.cs#8)]
 [!code-vb[Formatting.HowTo.WeekdayName#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/Howto1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="00a0c-141">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="00a0c-141">See Also</span></span>  
 [<span data-ttu-id="00a0c-142">Wykonywanie operacji formatowania</span><span class="sxs-lookup"><span data-stu-id="00a0c-142">Performing Formatting Operations</span></span>](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [<span data-ttu-id="00a0c-143">Ciągi formatujące standardowa Data i godzina</span><span class="sxs-lookup"><span data-stu-id="00a0c-143">Standard Date and Time Format Strings</span></span>](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)  
 [<span data-ttu-id="00a0c-144">Niestandardowa data i godzina ciągi formatujące</span><span class="sxs-lookup"><span data-stu-id="00a0c-144">Custom Date and Time Format Strings</span></span>](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)