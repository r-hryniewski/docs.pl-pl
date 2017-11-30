---
title: "Porady: wywoływanie procedury operatora (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0abff0a81ebcdacb59b69d0c307bb4aa219906c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="ff00f-102">Porady: wywoływanie procedury operatora (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff00f-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="ff00f-103">Za pomocą symbol operatora w wyrażeniu jest wywoływanie procedury operatora.</span><span class="sxs-lookup"><span data-stu-id="ff00f-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="ff00f-104">W przypadku operatora konwersji, należy wywołać [CType — funkcja](../../../../visual-basic/language-reference/functions/ctype-function.md) można przekonwertować wartości z jednego typu danych.</span><span class="sxs-lookup"><span data-stu-id="ff00f-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="ff00f-105">Procedury operatorów nie zostanie jawnie wywołana.</span><span class="sxs-lookup"><span data-stu-id="ff00f-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="ff00f-106">Po prostu użyć operatora, lub `CType` funkcji w instrukcji przypisania lub wyrażenie, tak samo zwykle użycie operatora.</span><span class="sxs-lookup"><span data-stu-id="ff00f-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="ff00f-107">wykonuje wywołanie procedury operatora.</span><span class="sxs-lookup"><span data-stu-id="ff00f-107"> makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="ff00f-108">Definiowanie operatora w klasie lub strukturze jest również nazywany *przeładowanie* operatora.</span><span class="sxs-lookup"><span data-stu-id="ff00f-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="ff00f-109">Wywoływanie procedury operatora</span><span class="sxs-lookup"><span data-stu-id="ff00f-109">To call an operator procedure</span></span>  
  
1.  <span data-ttu-id="ff00f-110">Symbol operatora należy używać w wyrażeniach w zwykły sposób.</span><span class="sxs-lookup"><span data-stu-id="ff00f-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2.  <span data-ttu-id="ff00f-111">Upewnij się, że typy danych argumenty operacji są odpowiednie dla operatora i we właściwej kolejności.</span><span class="sxs-lookup"><span data-stu-id="ff00f-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="ff00f-112">Operator przyczynia się do wartości wyrażenia zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="ff00f-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="ff00f-113">Wywoływanie procedury operatora konwersji</span><span class="sxs-lookup"><span data-stu-id="ff00f-113">To call a conversion operator procedure</span></span>  
  
1.  <span data-ttu-id="ff00f-114">Użyj `CType` wewnątrz wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="ff00f-114">Use `CType` inside an expression.</span></span>  
  
2.  <span data-ttu-id="ff00f-115">Upewnij się, że typy danych argumenty operacji są odpowiednie do konwersji, a w odpowiedniej kolejności.</span><span class="sxs-lookup"><span data-stu-id="ff00f-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="ff00f-116">`CType`wywołuje procedurę operatora konwersji i zwraca wartość przekonwertowana.</span><span class="sxs-lookup"><span data-stu-id="ff00f-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff00f-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="ff00f-117">Example</span></span>  
 <span data-ttu-id="ff00f-118">Poniższy przykład tworzy dwa <xref:System.TimeSpan> struktury, dodaje je ze sobą i zapisuje wynik w innej <xref:System.TimeSpan> struktury.</span><span class="sxs-lookup"><span data-stu-id="ff00f-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="ff00f-119"><xref:System.TimeSpan> Struktury definiuje operator procedury przeciążenia kilka standardowych operatorów.</span><span class="sxs-lookup"><span data-stu-id="ff00f-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 <span data-ttu-id="ff00f-120">Ponieważ <xref:System.TimeSpan> overloads standardowego `+` operatora, poprzedni przykład wywołuje procedurę operatora podczas obliczania wartości `combinedSpan`.</span><span class="sxs-lookup"><span data-stu-id="ff00f-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="ff00f-121">Przykład wywoływanie procedury operatora konwersacji, zobacz [porady: używanie klasy tego definiuje operatory](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="ff00f-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ff00f-122">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="ff00f-122">Compiling the Code</span></span>  
 <span data-ttu-id="ff00f-123">Upewnij się, że klasy lub struktury, którego używasz definiuje operator, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="ff00f-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff00f-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ff00f-124">See Also</span></span>  
 [<span data-ttu-id="ff00f-125">Procedury operatorów</span><span class="sxs-lookup"><span data-stu-id="ff00f-125">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="ff00f-126">Porady: Definiowanie operatora</span><span class="sxs-lookup"><span data-stu-id="ff00f-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="ff00f-127">Porady: Definiowanie operatora konwersji</span><span class="sxs-lookup"><span data-stu-id="ff00f-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="ff00f-128">Operator — instrukcja</span><span class="sxs-lookup"><span data-stu-id="ff00f-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="ff00f-129">Rozszerzanie</span><span class="sxs-lookup"><span data-stu-id="ff00f-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="ff00f-130">Zawężanie</span><span class="sxs-lookup"><span data-stu-id="ff00f-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="ff00f-131">Structure — instrukcja</span><span class="sxs-lookup"><span data-stu-id="ff00f-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="ff00f-132">Porady: deklarowanie struktury</span><span class="sxs-lookup"><span data-stu-id="ff00f-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="ff00f-133">Konwersje jawne i niejawne</span><span class="sxs-lookup"><span data-stu-id="ff00f-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="ff00f-134">Rozszerzanie i zwężanie konwersji</span><span class="sxs-lookup"><span data-stu-id="ff00f-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)