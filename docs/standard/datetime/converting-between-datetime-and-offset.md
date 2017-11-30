---
title: "Konwertowanie pomiędzy DateTime i DateTimeOffset"
ms.custom: 
ms.date: 04/10/2017
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
- DateTime structure, converting
- time zones [.NET Framework], conversions
- UTC times, converting
- DateTimeOffset structure, converting
- converting DateTimeOffset and DateTime values
- dates [.NET Framework], converting
- converting times
- Date data type, converting
- local time conversions
ms.assetid: b605ff97-0c45-4c24-833f-4c6a3e8be64c
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35923fb89d6ca2edb3453db61386f0cd23047278
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="converting-between-datetime-and-datetimeoffset"></a><span data-ttu-id="df502-102">Konwertowanie pomiędzy DateTime i DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="df502-102">Converting between DateTime and DateTimeOffset</span></span>

<span data-ttu-id="df502-103">Mimo że <xref:System.DateTimeOffset> struktura zapewnia wysoką świadomości strefy czasowej niż <xref:System.DateTime> struktury <xref:System.DateTime> parametry są najczęściej używane w wywołaniach metody.</span><span class="sxs-lookup"><span data-stu-id="df502-103">Although the <xref:System.DateTimeOffset> structure provides a greater degree of time zone awareness than the <xref:System.DateTime> structure, <xref:System.DateTime> parameters are used more commonly in method calls.</span></span> <span data-ttu-id="df502-104">W związku z tym umożliwia przekonwertowanie <xref:System.DateTimeOffset> wartości do <xref:System.DateTime> wartości i na odwrót jest szczególnie ważne.</span><span class="sxs-lookup"><span data-stu-id="df502-104">Because of this, the ability to convert <xref:System.DateTimeOffset> values to <xref:System.DateTime> values and vice versa is particularly important.</span></span> <span data-ttu-id="df502-105">W tym temacie przedstawiono sposób wykonywania tych konwersji w taki sposób, który zachowuje się jak najwięcej informacji o strefie czasowej, jak to możliwe.</span><span class="sxs-lookup"><span data-stu-id="df502-105">This topic shows how to perform these conversions in a way that preserves as much time zone information as possible.</span></span>

> [!NOTE]
> <span data-ttu-id="df502-106">Zarówno <xref:System.DateTime> i <xref:System.DateTimeOffset> typy mają następujące ograniczenia, gdy reprezentujący razy w strefach czasowych.</span><span class="sxs-lookup"><span data-stu-id="df502-106">Both the <xref:System.DateTime> and the <xref:System.DateTimeOffset> types have some limitations when representing times in time zones.</span></span> <span data-ttu-id="df502-107">Z jego <xref:System.DateTime.Kind%2A> właściwość <xref:System.DateTime> jest w stanie uwzględnić tylko uniwersalny czas koordynowany (UTC) oraz system w lokalnej strefie czasowej.</span><span class="sxs-lookup"><span data-stu-id="df502-107">With its <xref:System.DateTime.Kind%2A> property, <xref:System.DateTime> is able to reflect only Coordinated Universal Time (UTC) and the system's local time zone.</span></span> <span data-ttu-id="df502-108"><xref:System.DateTimeOffset>odzwierciedla przesunięcie raz od czasu UTC, ale nie uwzględnia się, że należy rzeczywiste strefy czasowej, do którego który przesunięcie.</span><span class="sxs-lookup"><span data-stu-id="df502-108"><xref:System.DateTimeOffset> reflects a time's offset from UTC, but it does not reflect the actual time zone to which that offset belongs.</span></span> <span data-ttu-id="df502-109">Aby uzyskać więcej informacji o wartości czasu i pomocy technicznej dla stref czasowych, zobacz [wybór pomiędzy DateTime, DateTimeOffset, TimeSpan i TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="df502-109">For details about time values and support for time zones, see [Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).</span></span>

## <a name="conversions-from-datetime-to-datetimeoffset"></a><span data-ttu-id="df502-110">Konwersje z daty/godziny na DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="df502-110">Conversions from DateTime to DateTimeOffset</span></span>

<span data-ttu-id="df502-111"><xref:System.DateTimeOffset> Struktury udostępnia dwa sposoby równoważne przeprowadzić <xref:System.DateTime> do <xref:System.DateTimeOffset> konwersji, które są odpowiednie dla większości konwersji:</span><span class="sxs-lookup"><span data-stu-id="df502-111">The <xref:System.DateTimeOffset> structure provides two equivalent ways to perform <xref:System.DateTime> to <xref:System.DateTimeOffset> conversion that are suitable for most conversions:</span></span>

* <span data-ttu-id="df502-112"><xref:System.DateTimeOffset.%23ctor%2A> Konstruktora, który tworzy nowy <xref:System.DateTimeOffset> na podstawie obiektu <xref:System.DateTime> wartość.</span><span class="sxs-lookup"><span data-stu-id="df502-112">The <xref:System.DateTimeOffset.%23ctor%2A> constructor, which creates a new <xref:System.DateTimeOffset> object based on a <xref:System.DateTime> value.</span></span>

* <span data-ttu-id="df502-113">Operator niejawnej konwersji, dzięki czemu można przypisać <xref:System.DateTime> do wartości <xref:System.DateTimeOffset> obiektu.</span><span class="sxs-lookup"><span data-stu-id="df502-113">The implicit conversion operator, which allows you to assign a <xref:System.DateTime> value to a <xref:System.DateTimeOffset> object.</span></span>

<span data-ttu-id="df502-114">Dla czasu UTC i lokalnych <xref:System.DateTime> wartości, <xref:System.DateTimeOffset.Offset%2A> właściwość powstałe w ten sposób <xref:System.DateTimeOffset> wartość dokładnie odzwierciedla przesunięcia strefy UTC lub czasu lokalnego.</span><span class="sxs-lookup"><span data-stu-id="df502-114">For UTC and local <xref:System.DateTime> values, the <xref:System.DateTimeOffset.Offset%2A> property of the resulting <xref:System.DateTimeOffset> value accurately reflects the UTC or local time zone offset.</span></span> <span data-ttu-id="df502-115">Na przykład następujący kod konwertuje godzinę UTC na jej odpowiednik <xref:System.DateTimeOffset> wartość.</span><span class="sxs-lookup"><span data-stu-id="df502-115">For example, the following code converts a UTC time to its equivalent <xref:System.DateTimeOffset> value.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

<span data-ttu-id="df502-116">W tym przypadku przesunięcie `utcTime2` zmiennej to 00:00.</span><span class="sxs-lookup"><span data-stu-id="df502-116">In this case, the offset of the `utcTime2` variable is 00:00.</span></span> <span data-ttu-id="df502-117">Podobnie poniższy kod konwertuje czasu lokalnego na jej odpowiednik <xref:System.DateTimeOffset> wartość.</span><span class="sxs-lookup"><span data-stu-id="df502-117">Similarly, the following code converts a local time to its equivalent <xref:System.DateTimeOffset> value.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

<span data-ttu-id="df502-118">Niemniej jednak w przypadku <xref:System.DateTime> wartości, których <xref:System.DateTime.Kind%2A> właściwość jest <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, utworzyć te metody konwersji dwóch <xref:System.DateTimeOffset> wartość, której przesunięcie jest w lokalnej strefie czasowej.</span><span class="sxs-lookup"><span data-stu-id="df502-118">However, for <xref:System.DateTime> values whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, these two conversion methods produce a <xref:System.DateTimeOffset> value whose offset is that of the local time zone.</span></span> <span data-ttu-id="df502-119">Przedstawiono to w poniższym przykładzie, który jest uruchamiany w Stanach Zjednoczonych Pacyficzny standardowa strefy czasowej.</span><span class="sxs-lookup"><span data-stu-id="df502-119">This is shown in the following example, which is run in the U.S. Pacific Standard Time zone.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

<span data-ttu-id="df502-120">Jeśli <xref:System.DateTime> odzwierciedla wartość daty i godziny w coś innego niż lokalnej strefie czasowej lub UTC, możesz przejść do <xref:System.DateTimeOffset> wartości i zachować informacje o strefie czasowej przez wywołanie metody przeciążonej <xref:System.DateTimeOffset.%23ctor%2A> konstruktora.</span><span class="sxs-lookup"><span data-stu-id="df502-120">If the <xref:System.DateTime> value reflects the date and time in something other than the local time zone or UTC, you can convert it to a <xref:System.DateTimeOffset> value and preserve its time zone information by calling the overloaded <xref:System.DateTimeOffset.%23ctor%2A> constructor.</span></span> <span data-ttu-id="df502-121">Na przykład poniższy przykład tworzy <xref:System.DateTimeOffset> obiektów, które odzwierciedla Środkowa (czas standardowy).</span><span class="sxs-lookup"><span data-stu-id="df502-121">For example, the following example instantiates a <xref:System.DateTimeOffset> object that reflects Central Standard Time.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

<span data-ttu-id="df502-122">Drugi parametr tego przeciążenia konstruktora <xref:System.TimeSpan> obiekt, który reprezentuje przesunięcie czasu UTC, powinny zostać pobrane przez wywołanie metody <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> metody odpowiedniej strefy czasowej czasu.</span><span class="sxs-lookup"><span data-stu-id="df502-122">The second parameter to this constructor overload, a <xref:System.TimeSpan> object that represents the time's offset from UTC, should be retrieved by calling the <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> method of the time's corresponding time zone.</span></span> <span data-ttu-id="df502-123">Pojedynczy parametr metody jest <xref:System.DateTime> wartość, która reprezentuje datę i godzinę, który ma zostać przekonwertowany.</span><span class="sxs-lookup"><span data-stu-id="df502-123">The method's single parameter is the <xref:System.DateTime> value that represents the date and time to be converted.</span></span> <span data-ttu-id="df502-124">Jeśli strefa czasowa obsługuje czasu letniego, ten parametr umożliwia metody przesunięcie odpowiednich dla określonej daty i godziny.</span><span class="sxs-lookup"><span data-stu-id="df502-124">If the time zone supports daylight saving time, this parameter allows the method to determine the appropriate offset for that particular date and time.</span></span>

## <a name="conversions-from-datetimeoffset-to-datetime"></a><span data-ttu-id="df502-125">Konwersje z DateTimeOffset DateTime</span><span class="sxs-lookup"><span data-stu-id="df502-125">Conversions from DateTimeOffset to DateTime</span></span>

<span data-ttu-id="df502-126"><xref:System.DateTimeOffset.DateTime%2A> Jest najczęściej używana do wykonywania <xref:System.DateTimeOffset> do <xref:System.DateTime> konwersji.</span><span class="sxs-lookup"><span data-stu-id="df502-126">The <xref:System.DateTimeOffset.DateTime%2A> property is most commonly used to perform <xref:System.DateTimeOffset> to <xref:System.DateTime> conversion.</span></span> <span data-ttu-id="df502-127">Jednak zwraca <xref:System.DateTime> wartości, których <xref:System.DateTime.Kind%2A> właściwość jest <xref:System.DateTimeKind.Unspecified>, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="df502-127">However, it returns a <xref:System.DateTime> value whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Unspecified>, as the following example illustrates.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

<span data-ttu-id="df502-128">Oznacza to, że wszystkie informacje o <xref:System.DateTimeOffset> relacji tej wartości na czas UTC zostaną utracone w procesie konwersji po <xref:System.DateTimeOffset.DateTime%2A> właściwość jest używana.</span><span class="sxs-lookup"><span data-stu-id="df502-128">This means that any information about the <xref:System.DateTimeOffset> value's relationship to UTC is lost by the conversion when the <xref:System.DateTimeOffset.DateTime%2A> property is used.</span></span> <span data-ttu-id="df502-129">Ma to wpływ na <xref:System.DateTimeOffset> wartości, które odpowiadają czasu UTC lub czasu lokalnego systemu, ponieważ <xref:System.DateTimeOffset.DateTime%2A> struktury odzwierciedla tylko tych dwóch stref czasowych w jego <xref:System.DateTime.Kind%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="df502-129">This affects <xref:System.DateTimeOffset> values that correspond to UTC time or to the system's local time because the <xref:System.DateTimeOffset.DateTime%2A> structure reflects only those two time zones in its <xref:System.DateTime.Kind%2A> property.</span></span>

<span data-ttu-id="df502-130">Aby zachować jak najwięcej informacji o strefie czasowej, jak to możliwe, podczas konwertowania <xref:System.DateTimeOffset> do <xref:System.DateTime> wartości, można użyć <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> i <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> właściwości.</span><span class="sxs-lookup"><span data-stu-id="df502-130">To preserve as much time zone information as possible when converting a <xref:System.DateTimeOffset> to a <xref:System.DateTime> value, you can use the <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> and <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> properties.</span></span>

### <a name="converting-a-utc-time"></a><span data-ttu-id="df502-131">Konwertowanie czas UTC</span><span class="sxs-lookup"><span data-stu-id="df502-131">Converting a UTC time</span></span>

<span data-ttu-id="df502-132">Aby wskazać, że przekonwertowanego <xref:System.DateTimeOffset.DateTime%2A> wartość to godzina (UTC), można pobrać wartość <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> właściwości.</span><span class="sxs-lookup"><span data-stu-id="df502-132">To indicate that a converted <xref:System.DateTimeOffset.DateTime%2A> value is the UTC time, you can retrieve the value of the <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="df502-133">Różni się od <xref:System.DateTimeOffset.DateTime%2A> właściwości na dwa sposoby:</span><span class="sxs-lookup"><span data-stu-id="df502-133">It differs from the <xref:System.DateTimeOffset.DateTime%2A> property in two ways:</span></span>

* <span data-ttu-id="df502-134">Zwraca <xref:System.DateTime> wartości, których <xref:System.DateTime.Kind%2A> jest właściwość <xref:System.DateTimeKind.Utc>.</span><span class="sxs-lookup"><span data-stu-id="df502-134">It returns a <xref:System.DateTime> value whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Utc>.</span></span>

* <span data-ttu-id="df502-135">Jeśli <xref:System.DateTimeOffset.Offset%2A> nie jest równa wartości właściwości <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, Konwertuje czas UTC.</span><span class="sxs-lookup"><span data-stu-id="df502-135">If the <xref:System.DateTimeOffset.Offset%2A> property value does not equal <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, it converts the time to UTC.</span></span>

> [!NOTE]
> <span data-ttu-id="df502-136">Jeśli aplikacja wymaga, aby przekonwertować <xref:System.DateTime> wartości jednoznacznie zidentyfikować pojedynczy punkt w czasie, należy rozważyć użycie <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> właściwości, aby zapewnić obsługę wszystkich <xref:System.DateTimeOffset> do <xref:System.DateTime> konwersji.</span><span class="sxs-lookup"><span data-stu-id="df502-136">If your application requires that converted <xref:System.DateTime> values unambiguously identify a single point in time, you should consider using the <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> property to handle all <xref:System.DateTimeOffset> to <xref:System.DateTime> conversions.</span></span>

<span data-ttu-id="df502-137">Poniższy kod używa <xref:System.DateTimeOffset.UtcDateTime%2A> właściwości można przekonwertować <xref:System.DateTimeOffset> wartości, których przesunięcie równe <xref:System.TimeSpan.Zero?displayProperty=nameWithType> do <xref:System.DateTime> wartości.</span><span class="sxs-lookup"><span data-stu-id="df502-137">The following code uses the <xref:System.DateTimeOffset.UtcDateTime%2A> property to convert a <xref:System.DateTimeOffset> value whose offset equals <xref:System.TimeSpan.Zero?displayProperty=nameWithType> to a <xref:System.DateTime> value.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

<span data-ttu-id="df502-138">Poniższy kod używa <xref:System.DateTimeOffset.UtcDateTime%2A> właściwości do realizacji konwersji strefy czasowej i konwersji typu na <xref:System.DateTimeOffset> wartość.</span><span class="sxs-lookup"><span data-stu-id="df502-138">The following code uses the <xref:System.DateTimeOffset.UtcDateTime%2A> property to perform both a time zone conversion and a type conversion on a <xref:System.DateTimeOffset> value.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a><span data-ttu-id="df502-139">Konwertowanie czasu lokalnego</span><span class="sxs-lookup"><span data-stu-id="df502-139">Converting a local time</span></span>

<span data-ttu-id="df502-140">Aby wskazać, że <xref:System.DateTimeOffset> wartość odpowiada czasowi lokalnemu, można przekazać <xref:System.DateTime> wartość zwrócona przez <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> właściwości `static` (`Shared` w języku Visual Basic) <xref:System.DateTime.SpecifyKind%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="df502-140">To indicate that a <xref:System.DateTimeOffset> value represents the local time, you can pass the <xref:System.DateTime> value returned by the <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> property to the `static` (`Shared` in Visual Basic) <xref:System.DateTime.SpecifyKind%2A> method.</span></span> <span data-ttu-id="df502-141">Metoda zwraca wartość daty i godziny przekazywane do niego jako pierwszy parametr, ale ustawia <xref:System.DateTime.Kind%2A> właściwości na wartość określoną przez jego drugi parametr.</span><span class="sxs-lookup"><span data-stu-id="df502-141">The method returns the date and time passed to it as its first parameter, but sets the <xref:System.DateTime.Kind%2A> property to the value specified by its second parameter.</span></span> <span data-ttu-id="df502-142">Poniższy kod używa <xref:System.DateTime.SpecifyKind%2A> metody podczas konwertowania <xref:System.DateTimeOffset> wartość, której przesunięcie odpowiada, który w lokalnej strefie czasowej.</span><span class="sxs-lookup"><span data-stu-id="df502-142">The following code uses the <xref:System.DateTime.SpecifyKind%2A> method when converting a <xref:System.DateTimeOffset> value whose offset corresponds to that of the local time zone.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

<span data-ttu-id="df502-143">Można również użyć <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> właściwości można przekonwertować <xref:System.DateTimeOffset> wartości do lokalnej <xref:System.DateTime> wartość.</span><span class="sxs-lookup"><span data-stu-id="df502-143">You can also use the <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> property to convert a <xref:System.DateTimeOffset> value to a local <xref:System.DateTime> value.</span></span> <span data-ttu-id="df502-144"><xref:System.DateTime.Kind%2A> Właściwości zwracana <xref:System.DateTime> wartość jest <xref:System.DateTimeKind.Local>.</span><span class="sxs-lookup"><span data-stu-id="df502-144">The <xref:System.DateTime.Kind%2A> property of the returned <xref:System.DateTime> value is <xref:System.DateTimeKind.Local>.</span></span> <span data-ttu-id="df502-145">Poniższy kod używa <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> właściwości podczas konwertowania <xref:System.DateTimeOffset> wartość, której przesunięcie odpowiada, który w lokalnej strefie czasowej.</span><span class="sxs-lookup"><span data-stu-id="df502-145">The following code uses the <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> property when converting a <xref:System.DateTimeOffset> value whose offset corresponds to that of the local time zone.</span></span> 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

<span data-ttu-id="df502-146">Po pobraniu <xref:System.DateTime> wartości przy użyciu <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> właściwości, właściwości `get` akcesor najpierw konwertuje <xref:System.DateTimeOffset> wartość na czas UTC, następnie konwertuje go na czas lokalny przez wywołanie metody <xref:System.DateTimeOffset.ToLocalTime%2A> — metoda.</span><span class="sxs-lookup"><span data-stu-id="df502-146">When you retrieve a <xref:System.DateTime> value using the <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> property, the property's `get` accessor first converts the <xref:System.DateTimeOffset> value to UTC, then converts it to local time by calling the <xref:System.DateTimeOffset.ToLocalTime%2A> method.</span></span> <span data-ttu-id="df502-147">Oznacza to, że można pobrać wartości z <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> właściwości, aby dokonać konwersji strefy czasowej w tym samym czasie, aby dokonać konwersji typu.</span><span class="sxs-lookup"><span data-stu-id="df502-147">This means that you can retrieve a value from the <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> property to perform a time zone conversion at the same time that you perform a type conversion.</span></span> <span data-ttu-id="df502-148">Oznacza to również, że strefy czasu lokalnego korekty reguły są stosowane w wykonywaniu konwersji.</span><span class="sxs-lookup"><span data-stu-id="df502-148">It also means that the local time zone's adjustment rules are applied in performing the conversion.</span></span> <span data-ttu-id="df502-149">Poniższy kod przedstawia użycie <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> właściwości do realizacji typu i konwersji strefy czasowej.</span><span class="sxs-lookup"><span data-stu-id="df502-149">The following code illustrates the use of the <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> property to perform both a type and a time zone conversion.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a><span data-ttu-id="df502-150">Metoda konwersji ogólnego przeznaczenia</span><span class="sxs-lookup"><span data-stu-id="df502-150">A general-purpose conversion method</span></span>

<span data-ttu-id="df502-151">W poniższym przykładzie zdefiniowano metodę o nazwie `ConvertFromDateTimeOffset` konwertująca <xref:System.DateTimeOffset> wartości do <xref:System.DateTime> wartości.</span><span class="sxs-lookup"><span data-stu-id="df502-151">The following example defines a method named `ConvertFromDateTimeOffset` that converts <xref:System.DateTimeOffset> values to <xref:System.DateTime> values.</span></span> <span data-ttu-id="df502-152">W oparciu o jego przesunięcie, określa czy <xref:System.DateTimeOffset> wartość czasu UTC, czas lokalny lub innym razem i definiuje zwrócona wartość daty i godziny w <xref:System.DateTime.Kind%2A> właściwości odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="df502-152">Based on its offset, it determines whether the <xref:System.DateTimeOffset> value is a UTC time, a local time, or some other time, and defines the returned date and time value's <xref:System.DateTime.Kind%2A> property accordingly.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

<span data-ttu-id="df502-153">Wykonaj przykładzie wywołuje `ConvertFromDateTimeOffset` metodę, aby przekonwertować <xref:System.DateTimeOffset> wartości, które reprezentują czas UTC, czasu lokalnego, a czas w Stanach Zjednoczonych Strefa Środkowa (czas standardowy).</span><span class="sxs-lookup"><span data-stu-id="df502-153">The follow example calls the `ConvertFromDateTimeOffset` method to convert <xref:System.DateTimeOffset> values that represent a UTC time, a local time, and a time in the U.S. Central Standard Time zone.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

<span data-ttu-id="df502-154">Należy pamiętać, że ten kod sprawia, że dwa założenia, które w zależności od aplikacji i źródłem jego wartości daty i godziny nie zawsze jest nieprawidłowy:</span><span class="sxs-lookup"><span data-stu-id="df502-154">Note that this code makes two assumptions that, depending on the application and the source of its date and time values, may not always be valid:</span></span>

* <span data-ttu-id="df502-155">Przyjęto założenie, że data i godzina wartość, której przesunięcie <xref:System.TimeSpan.Zero?displayProperty=nameWithType> reprezentuje czas UTC.</span><span class="sxs-lookup"><span data-stu-id="df502-155">It assumes that a date and time value whose offset is <xref:System.TimeSpan.Zero?displayProperty=nameWithType> represents UTC.</span></span> <span data-ttu-id="df502-156">W rzeczywistości UTC nie jest czas, w szczególności strefę czasową, ale czas, w odniesieniu do której są standaryzowane razy w strefach czasowych na świecie.</span><span class="sxs-lookup"><span data-stu-id="df502-156">In fact, UTC is not a time in a particular time zone, but the time in relation to which the times in the world's time zones are standardized.</span></span> <span data-ttu-id="df502-157">Strefy czasowe można również mają przesunięcie równe <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="df502-157">Time zones can also have an offset of <xref:System.TimeSpan.Zero>.</span></span>

* <span data-ttu-id="df502-158">Przyjęto założenie, że data i czas, w których przesunięcie equals, który w lokalnej strefie czasowej reprezentuje w lokalnej strefie czasowej.</span><span class="sxs-lookup"><span data-stu-id="df502-158">It assumes that a date and time whose offset equals that of the local time zone represents the local time zone.</span></span> <span data-ttu-id="df502-159">Ponieważ wartości daty i godziny są oddzielone od oryginalnej strefy czasowej, nie może to być sprawa; Data i godzina można muszą pochodzić z innej strefy czasowej z tym samym przesunięcie.</span><span class="sxs-lookup"><span data-stu-id="df502-159">Because date and time values are disassociated from their original time zone, this may not be the case; the date and time can have originated in another time zone with the same offset.</span></span>

## <a name="see-also"></a><span data-ttu-id="df502-160">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="df502-160">See also</span></span>

[<span data-ttu-id="df502-161">Daty, godziny i strefy czasowe</span><span class="sxs-lookup"><span data-stu-id="df502-161">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)