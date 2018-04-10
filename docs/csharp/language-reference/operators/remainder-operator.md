---
title: Operator % (odwołanie w C#)
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 796b4a40347fc5881db27a8a8a28404c7c4e8c5b
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="716cd-102">Operator % (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="716cd-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="716cd-103">Operator reszty (`%`) oblicza resztę po podzieleniu jego pierwszym argumentem przez jego sekundy.</span><span class="sxs-lookup"><span data-stu-id="716cd-103">The remainder operator (`%`) computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="716cd-104">Wszystkie typy liczbowe ma wstępnie zdefiniowane operatory resztę.</span><span class="sxs-lookup"><span data-stu-id="716cd-104">All numeric types have predefined remainder operators.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="716cd-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="716cd-105">Remarks</span></span>  
 <span data-ttu-id="716cd-106">Formuła `a % b` zawsze zwróci wartość z zakresu `(-b, b)`, wyłącznego (nigdy nie może zwrócić `b` lub `-b`), przechowywania znak dzielna.</span><span class="sxs-lookup"><span data-stu-id="716cd-106">The formula `a % b` will always return a value on the range `(-b, b)`, exclusive (it can never return `b` or `-b`), keeping the sign of the dividend.</span></span> <span data-ttu-id="716cd-107">Dla dzielenie liczby całkowitej operator reszty spełnia reguły `a % b = a - (a / b) * b`.</span><span class="sxs-lookup"><span data-stu-id="716cd-107">For integer division, the remainder operator satisfies the rule `a % b = a - (a / b) * b`.</span></span>
  
 <span data-ttu-id="716cd-108">Pozwala to nie należy mylić z canonical modulo, które spełniają reguły podobne, lecz z floored dzielenia i zwraca wartości zakresu `[0, b)`.</span><span class="sxs-lookup"><span data-stu-id="716cd-108">This is not to be confused with canonical modulus, which satisfies a similar rule but with floored division and returns values on the range `[0, b)`.</span></span> <span data-ttu-id="716cd-109">C# nie ma operator modulo kanonicznej.</span><span class="sxs-lookup"><span data-stu-id="716cd-109">C# does not have an operator for canonical modulus.</span></span> <span data-ttu-id="716cd-110">Jednak zachowanie jest takie same dla dywidendy dodatnią.</span><span class="sxs-lookup"><span data-stu-id="716cd-110">However, the behavior is the same for positive dividends.</span></span>
  
 <span data-ttu-id="716cd-111">Typy definiowane przez użytkownika można przeciążać `%` — operator (zobacz [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="716cd-111">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="716cd-112">Jeśli jest przeciążony operator binarny, odpowiedniego operatora przypisania, jeśli taki występuje, jest również niejawnie przeciążona.</span><span class="sxs-lookup"><span data-stu-id="716cd-112">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="716cd-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="716cd-113">Example</span></span>  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/remainder-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="716cd-114">Komentarze</span><span class="sxs-lookup"><span data-stu-id="716cd-114">Comments</span></span>  
 <span data-ttu-id="716cd-115">Należy pamiętać, błędów zaokrąglania skojarzonych z typu double.</span><span class="sxs-lookup"><span data-stu-id="716cd-115">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="716cd-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="716cd-116">See Also</span></span>  
 [<span data-ttu-id="716cd-117">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="716cd-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="716cd-118">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="716cd-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="716cd-119">Operatory języka C#</span><span class="sxs-lookup"><span data-stu-id="716cd-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)