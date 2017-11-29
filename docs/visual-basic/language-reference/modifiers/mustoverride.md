---
title: MustOverride (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a2f7bdba4b01bd307e0c52802509669f772b5eb5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="e0c3c-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0c3c-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="e0c3c-103">Określa, że właściwość lub procedura nie jest zaimplementowana w tej klasie i musi zostać zastąpiony w klasie pochodnej, zanim będzie można go używać.</span><span class="sxs-lookup"><span data-stu-id="e0c3c-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0c3c-104">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e0c3c-104">Remarks</span></span>  
 <span data-ttu-id="e0c3c-105">Można użyć `MustOverride` tylko w instrukcji deklaracji właściwość lub procedura.</span><span class="sxs-lookup"><span data-stu-id="e0c3c-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="e0c3c-106">Właściwość lub procedura, która określa `MustOverride` musi być elementem członkowskim klasy, i muszą być oznaczone jako klasa [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="e0c3c-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="e0c3c-107">Reguły</span><span class="sxs-lookup"><span data-stu-id="e0c3c-107">Rules</span></span>  
  
-   <span data-ttu-id="e0c3c-108">**Deklaracja niekompletne.**</span><span class="sxs-lookup"><span data-stu-id="e0c3c-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="e0c3c-109">Po określeniu `MustOverride`, wszelkie dodatkowe wiersze kodu właściwość lub procedura, nie zostanie podana nie nawet `End Function`, `End Property`, lub `End Sub` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="e0c3c-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
-   <span data-ttu-id="e0c3c-110">**Łączna modyfikatorów.**</span><span class="sxs-lookup"><span data-stu-id="e0c3c-110">**Combined Modifiers.**</span></span> <span data-ttu-id="e0c3c-111">Nie można określić `MustOverride` razem z `NotOverridable`, `Overridable`, lub `Shared` w tej samej deklaracji.</span><span class="sxs-lookup"><span data-stu-id="e0c3c-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
-   <span data-ttu-id="e0c3c-112">**Przesłanianiem i zastępowaniem.**</span><span class="sxs-lookup"><span data-stu-id="e0c3c-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="e0c3c-113">Zarówno przesłanianiem i zastępowaniem ponownego zdefiniowania odziedziczonego elementu, ale są istotne różnice między dwa podejścia.</span><span class="sxs-lookup"><span data-stu-id="e0c3c-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="e0c3c-114">Aby uzyskać więcej informacji, zobacz [przesłanianie w Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="e0c3c-114">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
-   <span data-ttu-id="e0c3c-115">**Alternatywne warunki.**</span><span class="sxs-lookup"><span data-stu-id="e0c3c-115">**Alternate Terms.**</span></span> <span data-ttu-id="e0c3c-116">Element, której nie można użyć z wyjątkiem zastąpienia jest czasami nazywany *czystej wirtualnej* elementu.</span><span class="sxs-lookup"><span data-stu-id="e0c3c-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="e0c3c-117">`MustOverride` Modyfikatora można używać w tych sytuacjach:</span><span class="sxs-lookup"><span data-stu-id="e0c3c-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="e0c3c-118">Function — instrukcja</span><span class="sxs-lookup"><span data-stu-id="e0c3c-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="e0c3c-119">Property — instrukcja</span><span class="sxs-lookup"><span data-stu-id="e0c3c-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="e0c3c-120">Sub — instrukcja</span><span class="sxs-lookup"><span data-stu-id="e0c3c-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e0c3c-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e0c3c-121">See Also</span></span>  
 [<span data-ttu-id="e0c3c-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="e0c3c-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [<span data-ttu-id="e0c3c-123">Możliwym do zastąpienia</span><span class="sxs-lookup"><span data-stu-id="e0c3c-123">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [<span data-ttu-id="e0c3c-124">Zastąpienia</span><span class="sxs-lookup"><span data-stu-id="e0c3c-124">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="e0c3c-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="e0c3c-125">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
 [<span data-ttu-id="e0c3c-126">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="e0c3c-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="e0c3c-127">Przesłanianie w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e0c3c-127">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)