---
title: Zasady nazewnictwa
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], about naming guidelines
- naming guidelines [.NET Framework]
- class library design guidelines [.NET Framework], names
- formatting [.NET Framework], names
- identifiers, class library element names
- names [.NET Framework]
- format naming guidelines [.NET Framework]
ms.assetid: fc076d66-9b5f-42d3-aa65-61d970c794a3
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 40da7449c88eaaba92e34374c002c7e175b2ef16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="naming-guidelines"></a><span data-ttu-id="ff790-102">Zasady nazewnictwa</span><span class="sxs-lookup"><span data-stu-id="ff790-102">Naming Guidelines</span></span>
<span data-ttu-id="ff790-103">Po konwencji nazewnictwa do tworzenia struktury spójny zestaw może być znaczący udział w ramach użyteczność.</span><span class="sxs-lookup"><span data-stu-id="ff790-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="ff790-104">Umożliwia on framework ma być używany przez wielu deweloperów powszechnie rozdzielonych projektów.</span><span class="sxs-lookup"><span data-stu-id="ff790-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="ff790-105">Poza spójności formularza nazwy elementów framework łatwe zrozumienie i muszą zawierać funkcję każdego elementu.</span><span class="sxs-lookup"><span data-stu-id="ff790-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="ff790-106">Celem niniejszego rozdziału jest zapewnienie spójny zestaw konwencji nazewnictwa, który daje w nazwach sensu bezpośredniego deweloperom.</span><span class="sxs-lookup"><span data-stu-id="ff790-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="ff790-107">Mimo że przyjmowania tych konwencji nazewnictwa jak spowodowałoby nazewnictwa bardziej spójne w całym kodzie kodu ogólne wskazówki dotyczące programowania, są wymagane tylko, aby zastosować je do interfejsów API, które są udostępniane publicznie (typy publiczne lub chronione i elementów członkowskich, a jawnie implementowane interfejsy).</span><span class="sxs-lookup"><span data-stu-id="ff790-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff790-108">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="ff790-108">In This Section</span></span>  
 [<span data-ttu-id="ff790-109">Konwencje wielkość liter</span><span class="sxs-lookup"><span data-stu-id="ff790-109">Capitalization Conventions</span></span>](../../../docs/standard/design-guidelines/capitalization-conventions.md)  
 [<span data-ttu-id="ff790-110">Ogólne konwencje nazewnictwa</span><span class="sxs-lookup"><span data-stu-id="ff790-110">General Naming Conventions</span></span>](../../../docs/standard/design-guidelines/general-naming-conventions.md)  
 [<span data-ttu-id="ff790-111">Nazw zestawów i bibliotek DLL</span><span class="sxs-lookup"><span data-stu-id="ff790-111">Names of Assemblies and DLLs</span></span>](../../../docs/standard/design-guidelines/names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="ff790-112">Nazwy przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="ff790-112">Names of Namespaces</span></span>](../../../docs/standard/design-guidelines/names-of-namespaces.md)  
 [<span data-ttu-id="ff790-113">Nazwy klasy, struktury i interfejsy</span><span class="sxs-lookup"><span data-stu-id="ff790-113">Names of Classes, Structs, and Interfaces</span></span>](../../../docs/standard/design-guidelines/names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="ff790-114">Nazwy elementów członkowskich typu</span><span class="sxs-lookup"><span data-stu-id="ff790-114">Names of Type Members</span></span>](../../../docs/standard/design-guidelines/names-of-type-members.md)  
 [<span data-ttu-id="ff790-115">Nazwy parametrów</span><span class="sxs-lookup"><span data-stu-id="ff790-115">Naming Parameters</span></span>](../../../docs/standard/design-guidelines/naming-parameters.md)  
 [<span data-ttu-id="ff790-116">Nadawanie nazw zasobów</span><span class="sxs-lookup"><span data-stu-id="ff790-116">Naming Resources</span></span>](../../../docs/standard/design-guidelines/naming-resources.md)  
 <span data-ttu-id="ff790-117">*Fragmenty © 2005, 2009 Microsoft Corporation. Wszelkie prawa zastrzeżone.*</span><span class="sxs-lookup"><span data-stu-id="ff790-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ff790-118">*Drukowane uprawnieniami wariancji x edukacji, Inc. z [Framework zaleceń dotyczących projektowania: konwencje, Idioms i wzorce dla bibliotek .NET wielokrotnego użytku, wydanie 2](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina i Abrams Brada opublikowane 22 Oct 2008 przez Professional Addison-Wesley jako część serii rozwoju systemu Windows firmy Microsoft.*</span><span class="sxs-lookup"><span data-stu-id="ff790-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff790-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ff790-119">See Also</span></span>  
 [<span data-ttu-id="ff790-120">Wytyczne dotyczące projektowania Framework</span><span class="sxs-lookup"><span data-stu-id="ff790-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)