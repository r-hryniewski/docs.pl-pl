---
title: /errorreport
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0abe276aaacdeb175c3af7067dffa81448450e22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="errorreport"></a><span data-ttu-id="2784d-102">/errorreport</span><span class="sxs-lookup"><span data-stu-id="2784d-102">/errorreport</span></span>
<span data-ttu-id="2784d-103">Określa sposób [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kompilatora Zgłoś wewnętrzne błędy kompilatora.</span><span class="sxs-lookup"><span data-stu-id="2784d-103">Specifies how the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler should report internal compiler errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2784d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2784d-104">Syntax</span></span>  
  
```  
/errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a><span data-ttu-id="2784d-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2784d-105">Remarks</span></span>  
 <span data-ttu-id="2784d-106">Ta opcja umożliwia dogodny do raportu [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] wewnętrzny błąd kompilatora (ICE) do [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] zespołu w firmie Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2784d-106">This option provides a convenient way to report a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] internal compiler error (ICE) to the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] team at Microsoft.</span></span> <span data-ttu-id="2784d-107">Domyślnie kompilator wysyła żadnych informacji do firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2784d-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="2784d-108">Jednak jeśli wystąpi błąd wewnętrzny kompilatora, ta opcja umożliwia raportowanie błędów firmie Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2784d-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="2784d-109">Informacje te pomogą zidentyfikować przyczynę pracownicy firmy Microsoft i może zwiększyć kolejnej wersji programu [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2784d-109">That information will help Microsoft engineers identify the cause and may help improve the next release of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="2784d-110">Możliwość wysyłania raportów użytkownika zależy od uprawnień zasad komputera i użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2784d-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>  
  
 <span data-ttu-id="2784d-111">W poniższej tabeli przedstawiono wpływ `/errorreport` opcji.</span><span class="sxs-lookup"><span data-stu-id="2784d-111">The following table summarizes the effect of the `/errorreport` option.</span></span>  
  
|<span data-ttu-id="2784d-112">Opcja</span><span class="sxs-lookup"><span data-stu-id="2784d-112">Option</span></span>|<span data-ttu-id="2784d-113">Zachowanie</span><span class="sxs-lookup"><span data-stu-id="2784d-113">Behavior</span></span>|  
|---|---|  
|`prompt`|<span data-ttu-id="2784d-114">Jeśli wystąpi błąd wewnętrzny kompilatora, okno dialogowe pojawia się, dzięki czemu można wyświetlić dokładne dane, które są zbierane przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="2784d-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="2784d-115">Można określić, czy istnieje żadnych poufnych informacji w raporcie o błędzie i podejmowania decyzji od tego, czy do wysłania do firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2784d-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="2784d-116">Jeśli zdecydujesz się wysłać i umożliwienie ustawienia zasad komputera i użytkownika, kompilator wysyła dane do firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2784d-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|  
|`queue`|<span data-ttu-id="2784d-117">Kolejkuje raport o błędzie.</span><span class="sxs-lookup"><span data-stu-id="2784d-117">Queues the error report.</span></span> <span data-ttu-id="2784d-118">Podczas logowania się z uprawnieniami administratora, od czasu ostatniego zalogowania w może raportować zakończą się niepowodzeniem (zostanie nie się monit o wysłanie raportu błędów więcej niż raz na trzy dni).</span><span class="sxs-lookup"><span data-stu-id="2784d-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="2784d-119">Jest to domyślne zachowanie podczas `/errorreport` nie określono opcji.</span><span class="sxs-lookup"><span data-stu-id="2784d-119">This is the default behavior when the `/errorreport` option is not specified.</span></span>|  
|`send`|<span data-ttu-id="2784d-120">Jeśli wystąpi błąd wewnętrzny kompilatora i umożliwienie ustawienia zasad komputera i użytkownika, kompilator wysyła dane do firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2784d-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="2784d-121">Opcja `/errorReport:send` próbuje automatyczne wysyłanie informacji o błędach do firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2784d-121">The option `/errorReport:send` attempts to automatically send error information to Microsoft.</span></span> <span data-ttu-id="2784d-122">Ta opcja jest zależna od rejestru.</span><span class="sxs-lookup"><span data-stu-id="2784d-122">This option depends on the registry.</span></span> <span data-ttu-id="2784d-123">Aby uzyskać więcej informacji na temat ustawiania odpowiednie wartości w rejestrze, zobacz [jak włączyć automatyczne raportowanie błędów w programie Visual Studio 2008 wiersza polecenia narzędzia](http://go.microsoft.com/fwlink/?LinkID=184695).</span><span class="sxs-lookup"><span data-stu-id="2784d-123">For more information about setting the appropriate values in the registry, see [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695).</span></span>|  
|`none`|<span data-ttu-id="2784d-124">Jeśli wystąpi błąd wewnętrzny kompilatora, go nie zostanie zbierane ani wysyłane do firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2784d-124">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|  
  
 <span data-ttu-id="2784d-125">Kompilator wysyła dane, które obejmuje stosu w momencie wystąpienia błędu, obejmujące niektóre kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="2784d-125">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="2784d-126">Jeśli `/errorreport` jest używany z [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opcji, a następnie wysłaniu całego pliku źródłowego.</span><span class="sxs-lookup"><span data-stu-id="2784d-126">If `/errorreport` is used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>  
  
 <span data-ttu-id="2784d-127">Ta opcja jest optymalna dla [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opcja, ponieważ umożliwia pracownicy firmy Microsoft, aby łatwo odtwarzania błędu.</span><span class="sxs-lookup"><span data-stu-id="2784d-127">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2784d-128">`/errorreport` Opcja nie jest dostępne w środowisku programowania Visual Studio; jest dostępna tylko podczas kompilowania kodu w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="2784d-128">The `/errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2784d-129">Przykład</span><span class="sxs-lookup"><span data-stu-id="2784d-129">Example</span></span>  
 <span data-ttu-id="2784d-130">Poniższy kod próbuje skompilować `T2.vb`, jeśli kompilator napotkał błąd wewnętrzny kompilatora, monitów o wysłanie raportu o błędach do firmy Microsoft i.</span><span class="sxs-lookup"><span data-stu-id="2784d-130">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>  
  
```  
vbc /errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2784d-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2784d-131">See Also</span></span>  
 [<span data-ttu-id="2784d-132">Kompilator w wierszu polecenia programu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2784d-132">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="2784d-133">Kompilacja przykładów — wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="2784d-133">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="2784d-134">/ bugreport</span><span class="sxs-lookup"><span data-stu-id="2784d-134">/bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)