---
title: "Środki zaradcze: Nowy kompilator JIT 64-bitowych"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JIT compiler, 64-bit
- JIT compilation, 64-bit
- RyuJIT compiler
ms.assetid: 0332dabc-72c5-4bdc-8975-20d717802b17
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 091b83cc0d7829c8ff078e6397aa480895b7a115
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="mitigation-new-64-bit-jit-compiler"></a><span data-ttu-id="e38b0-102">Środki zaradcze: Nowy kompilator JIT 64-bitowych</span><span class="sxs-lookup"><span data-stu-id="e38b0-102">Mitigation: New 64-bit JIT Compiler</span></span>
<span data-ttu-id="e38b0-103">Począwszy od programu .NET Framework 4.6 środowiska uruchomieniowego zawiera nowe kompilatora JIT 64-bitowej w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="e38b0-103">Starting with the .NET Framework 4.6, the runtime includes a new 64-bit JIT compiler for just-in-time compilation.</span></span> <span data-ttu-id="e38b0-104">Ta zmiana nie wpływa na kompilacja z kompilatorem JIT 32-bitowych.</span><span class="sxs-lookup"><span data-stu-id="e38b0-104">This change does not affect compilation with the  32-bit JIT compiler.</span></span>  
  
## <a name="unexpected-behavior-or-exceptions"></a><span data-ttu-id="e38b0-105">Nieoczekiwane zachowanie i wyjątków</span><span class="sxs-lookup"><span data-stu-id="e38b0-105">Unexpected behavior or exceptions</span></span>  
 <span data-ttu-id="e38b0-106">W niektórych przypadkach kompilacji przez kompilator JIT 64-bitowych wynikiem wyjątek czasu wykonywania lub zachowania, które nie jest przestrzegana podczas wykonywania kodu skompilowanego przez starszego kompilatora JIT 64-bitowych.</span><span class="sxs-lookup"><span data-stu-id="e38b0-106">In some cases, compilation with the new 64-bit JIT compiler results in a runtime exception or in behavior that is not observed when executing code compiled by the older 64-bit JIT compiler.</span></span> <span data-ttu-id="e38b0-107">Znane różnice są następujące:</span><span class="sxs-lookup"><span data-stu-id="e38b0-107">The known differences include the following:</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e38b0-108">Wszystkie te znane problemy rozwiązano w kompilator 64-bitowych publikowana z programu .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="e38b0-108">All of these known issues have been addressed in the new 64-bit compiler released with the .NET Framework 4.6.2.</span></span> <span data-ttu-id="e38b0-109">Większość rozwiązano także w wersjach usługi .NET Framework 4.6 i 4.6.1, które są dołączone do usługi Windows Update.</span><span class="sxs-lookup"><span data-stu-id="e38b0-109">Most have also been addressed in service releases of the .NET Framework 4.6 and 4.6.1 that are included with Windows Update.</span></span> <span data-ttu-id="e38b0-110">Można wyeliminować te problemy przez zapewnienie im, które danej wersji systemu Windows jest aktualny, albo przez uaktualnienie programu .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="e38b0-110">You can eliminate these issues by ensuring that your version of Windows is up to date, or by upgrading to the .NET Framework 4.6.2.</span></span>  
  
-   <span data-ttu-id="e38b0-111">W niektórych warunkach może zgłaszać rozpakowującej operacji <xref:System.NullReferenceException> w kompilacjach wydania z optymalizacją włączona.</span><span class="sxs-lookup"><span data-stu-id="e38b0-111">Under certain conditions, an unboxing operation may throw a <xref:System.NullReferenceException> in Release builds with optimization turned on.</span></span>  
  
-   <span data-ttu-id="e38b0-112">W niektórych przypadkach może zgłaszać wykonywanie kodu produkcyjnego w treści metody dużych <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="e38b0-112">In some cases, execution of production code in a large method body may throw a <xref:System.StackOverflowException>.</span></span>  
  
-   <span data-ttu-id="e38b0-113">W niektórych warunkach struktury przekazana do metody są traktowane jako typów referencyjnych zamiast typów wartości w wersji kompilacji.</span><span class="sxs-lookup"><span data-stu-id="e38b0-113">Under certain conditions, structures passed to a method are treated as reference types rather than value types in Release builds.</span></span> <span data-ttu-id="e38b0-114">Jednym z przejawy tego problemu jest czy poszczególnych elementów w kolekcji są wyświetlane w kolejności nieoczekiwany.</span><span class="sxs-lookup"><span data-stu-id="e38b0-114">One of the manifestations of this issue is that the individual items in a collection appear in an unexpected order.</span></span>  
  
-   <span data-ttu-id="e38b0-115">W niektórych warunkach porównanie <xref:System.UInt16> wartości z ich wysokobitowe zestawu jest nieprawidłowa, gdy Optymalizacja jest włączona.</span><span class="sxs-lookup"><span data-stu-id="e38b0-115">Under certain conditions, the comparison of <xref:System.UInt16> values with their high bit set is incorrect if optimization is enabled.</span></span>  
  
-   <span data-ttu-id="e38b0-116">W niektórych warunkach, szczególnie gdy inicjowanie tablicy wartości, inicjowania pamięci przez <xref:System.Reflection.Emit.OpCodes.Initblk?displayProperty=nameWithType> instrukcji IL może zainicjować pamięci z niepoprawną wartość.</span><span class="sxs-lookup"><span data-stu-id="e38b0-116">Under certain conditions, particularly when initializing array values, memory initialization by the <xref:System.Reflection.Emit.OpCodes.Initblk?displayProperty=nameWithType> IL instruction may initialize memory with an incorrect value.</span></span> <span data-ttu-id="e38b0-117">Dzięki temu można w nieobsługiwany wyjątek lub nieprawidłowych danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="e38b0-117">This can result either in an unhandled exception or incorrect output.</span></span>  
  
-   <span data-ttu-id="e38b0-118">W niektórych warunkach rzadkich test warunkowy bit może zwrócić nieprawidłowym <xref:System.Boolean> wartość lub zgłosić wyjątek, jeśli jest włączona Optymalizacja kompilatora.</span><span class="sxs-lookup"><span data-stu-id="e38b0-118">Under certain rare conditions, a conditional bit test can return the incorrect <xref:System.Boolean> value or throw an exception if compiler optimizations are enabled.</span></span>  
  
-   <span data-ttu-id="e38b0-119">W niektórych warunkach Jeśli `if` testować warunek przed wprowadzeniem używana jest instrukcja `try` bloku i wyjście z `try` bloku, a tym samym stanie, które są oceniane w `catch` lub `finally` bloku, nowy Kompilator JIT 64-bitowy usuwa `if` warunku z `catch` lub `finally` zablokować, jeśli optymalizuje kod.</span><span class="sxs-lookup"><span data-stu-id="e38b0-119">Under certain conditions, if an `if` statement is used to test for a condition before entering  a `try` block and in the exit from the `try` block, and the same condition is evaluated in the `catch` or `finally` block, the new 64-bit JIT compiler removes the `if` condition from the `catch` or `finally` block when it optimizes code.</span></span> <span data-ttu-id="e38b0-120">W związku z tym kodu wewnątrz `if` instrukcji w `catch` lub `finally` bezwarunkowo wykonaniu bloku.</span><span class="sxs-lookup"><span data-stu-id="e38b0-120">As a result, code inside the `if` statement in the `catch` or `finally` block is executed unconditionally.</span></span>  
  
<a name="General"></a>   
## <a name="mitigation-of-known-issues"></a><span data-ttu-id="e38b0-121">Ograniczenie znane problemy</span><span class="sxs-lookup"><span data-stu-id="e38b0-121">Mitigation of known issues</span></span>  
 <span data-ttu-id="e38b0-122">Jeśli wystąpią problemy z wymienionych powyżej, można rozwiązać je, wykonując jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="e38b0-122">If you encounter the issues listed above, you can address them by doing any of the following:</span></span>  
  
-   <span data-ttu-id="e38b0-123">Uaktualnianie do programu .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="e38b0-123">Upgrade to the .NET Framework 4.6.2.</span></span> <span data-ttu-id="e38b0-124">Kompilator 64-bitowych uwzględnionych w programie .NET Framework 4.6.2 adresów każdego z tych znanych problemów.</span><span class="sxs-lookup"><span data-stu-id="e38b0-124">The new 64-bit compiler included with the .NET Framework 4.6.2 addresses each of these known issues.</span></span>  
  
-   <span data-ttu-id="e38b0-125">Upewnij się, że danej wersji systemu Windows jest aktualny, uruchamiając usługi Windows Update.</span><span class="sxs-lookup"><span data-stu-id="e38b0-125">Ensure that your version of Windows is up to date by running Windows Update.</span></span> <span data-ttu-id="e38b0-126">Usługi aktualizacji programu .NET Framework 4.6 i 4.6.1 dotyczą każdego z tych problemów, z wyjątkiem <xref:System.NullReferenceException> w rozpakowującej operacji.</span><span class="sxs-lookup"><span data-stu-id="e38b0-126">Service updates to the .NET Framework 4.6 and 4.6.1 address each of these issues except the <xref:System.NullReferenceException> in an unboxing operation.</span></span>  
  
-   <span data-ttu-id="e38b0-127">Kompiluj z użyciem starszego kompilatora JIT 64-bitowych.</span><span class="sxs-lookup"><span data-stu-id="e38b0-127">Compile with the older 64-bit JIT compiler.</span></span> <span data-ttu-id="e38b0-128">Zobacz [ograniczenie inne problemy](#Other) sekcji, aby uzyskać więcej informacji na temat sposobu wykonania tego zadania.</span><span class="sxs-lookup"><span data-stu-id="e38b0-128">See the [Mitigation of other issues](#Other) section for more information on how to do this.</span></span>  
  
<a name="Other"></a>   
## <a name="mitigation-of-other-issues"></a><span data-ttu-id="e38b0-129">Ograniczenie inne problemy</span><span class="sxs-lookup"><span data-stu-id="e38b0-129">Mitigation of other issues</span></span>  
 <span data-ttu-id="e38b0-130">Jeśli występują inne różnice w zachowaniu między kodu skompilowanego za pomocą starszego kompilatora 64-bitowe i kompilator JIT 64-bitowych lub debug i release wersje aplikacji, które przez kompilator JIT 64-bitowych są kompilowane, można wykonaj następujące czynności do kompilowania aplikacji za pomocą starszego kompilatora JIT 64-bitowe:</span><span class="sxs-lookup"><span data-stu-id="e38b0-130">If you encounter any other difference in behavior between code compiled with the older 64-bit compiler and the new 64-bit JIT compiler, or between the debug and release versions of your app that are both compiled with the new 64-bit JIT compiler, you can do the following to compile your app with the older 64-bit JIT compiler:</span></span>  
  
-   <span data-ttu-id="e38b0-131">Na poszczególnych aplikacji, co można dodać [ \<useLegacyJit >](../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md) elementu do pliku konfiguracji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e38b0-131">On a per-application basis, you can add the [\<useLegacyJit>](../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md) element to your application's configuration file.</span></span> <span data-ttu-id="e38b0-132">Następujące wyłącza kompilacji przez kompilator JIT 64-bitowe i zamiast tego używa starszej wersji kompilatora JIT 64-bitowych.</span><span class="sxs-lookup"><span data-stu-id="e38b0-132">The following disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
    ```xml  
    <?xml version ="1.0"?>  
    <configuration>  
        <runtime>  
           <useLegacyJit enabled="1" />  
        </runtime>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="e38b0-133">Na podstawie użytkownika, można dodać `REG_DWORD` wartość o nazwie `useLegacyJit` do `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` klucza rejestru.</span><span class="sxs-lookup"><span data-stu-id="e38b0-133">On a per-user basis, you can add a `REG_DWORD` value named `useLegacyJit` to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key of the registry.</span></span> <span data-ttu-id="e38b0-134">Wartość 1 powoduje włączenie starszej wersji 64-bitowej przy użyciu kompilatora JIT; wartość 0 powoduje wyłączenie go i włącza kompilator JIT 64-bitowych.</span><span class="sxs-lookup"><span data-stu-id="e38b0-134">A value of 1 enables the legacy 64-bit JIT compiler; a value of 0 disables it and enables the new 64-bit JIT compiler.</span></span>  
  
-   <span data-ttu-id="e38b0-135">Na poszczególnych komputerach, można dodać `REG_DWORD` wartość o nazwie `useLegacyJit` do `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` klucza rejestru.</span><span class="sxs-lookup"><span data-stu-id="e38b0-135">On a per-machine basis, you can add a `REG_DWORD` value named `useLegacyJit` to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key of the registry.</span></span> <span data-ttu-id="e38b0-136">Wartość 1 powoduje włączenie starszej wersji 64-bitowej przy użyciu kompilatora JIT; wartość 0 powoduje wyłączenie go i włącza kompilator JIT 64-bitowych.</span><span class="sxs-lookup"><span data-stu-id="e38b0-136">A value of 1 enables the legacy 64-bit JIT compiler; a value of 0 disables it and enables the new 64-bit JIT compiler.</span></span>  
  
 <span data-ttu-id="e38b0-137">Można również Daj nam wiedzę na temat problemu przez raportowanie błędów na [Microsoft Connect](https://connect.microsoft.com/VisualStudio).</span><span class="sxs-lookup"><span data-stu-id="e38b0-137">You can also let us know about the problem by reporting a bug on [Microsoft Connect](https://connect.microsoft.com/VisualStudio).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e38b0-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e38b0-138">See Also</span></span>  
 [<span data-ttu-id="e38b0-139">Zmiany środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="e38b0-139">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)  
 [<span data-ttu-id="e38b0-140">\<useLegacyJit > — Element</span><span class="sxs-lookup"><span data-stu-id="e38b0-140">\<useLegacyJit> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md)