---
title: "Funkcje zewnętrzne (F#)"
description: "Dowiedz się więcej na temat obsługi języka F # na wywoływanie funkcji w kodzie natywnym."
keywords: "Visual f #, f #, funkcjonalności programowania"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c26b6124-ceaa-471c-9dc9-861b4dfa332a
ms.openlocfilehash: 4f525b2b750c2ce42230c61aa0e72f957739b206
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="external-functions"></a><span data-ttu-id="559d6-104">Funkcje zewnętrzne</span><span class="sxs-lookup"><span data-stu-id="559d6-104">External Functions</span></span>

<span data-ttu-id="559d6-105">W tym temacie opisano obsługę języka F # dla wywoływanie funkcji w kodzie natywnym.</span><span class="sxs-lookup"><span data-stu-id="559d6-105">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="559d6-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="559d6-106">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="559d6-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="559d6-107">Remarks</span></span>

<span data-ttu-id="559d6-108">W poprzednich składni *argumenty* reprezentuje argumenty, które są dostarczane do `System.Runtime.InteropServices.DllImportAttribute` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="559d6-108">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="559d6-109">Pierwszy argument jest ciąg reprezentujący nazwę biblioteki DLL zawierającej tej funkcji bez rozszerzenia dll.</span><span class="sxs-lookup"><span data-stu-id="559d6-109">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="559d6-110">Dodatkowe argumenty mogą być dostarczane w każdej publicznej właściwości `System.Runtime.InteropServices.DllImportAttribute` klasy, takie jak konwencję wywołania.</span><span class="sxs-lookup"><span data-stu-id="559d6-110">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="559d6-111">Załóżmy, że masz natywne biblioteki DLL języka C++, która zawiera następujące wyeksportowanej funkcji.</span><span class="sxs-lookup"><span data-stu-id="559d6-111">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="559d6-112">Tę funkcję można wywołać z F # przy użyciu następującego kodu.</span><span class="sxs-lookup"><span data-stu-id="559d6-112">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="559d6-113">Współdziałanie z kodem natywnym jest określany jako *wywołanie platformy* funkcja środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="559d6-113">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="559d6-114">Aby uzyskać więcej informacji, zobacz [współdziałanie z kodem niezarządzanym](https://msdn.microsoft.com/library/sd10k43k.aspx).</span><span class="sxs-lookup"><span data-stu-id="559d6-114">For more information, see [Interoperating with Unmanaged Code](https://msdn.microsoft.com/library/sd10k43k.aspx).</span></span> <span data-ttu-id="559d6-115">Informacje przedstawione w tej sekcji ma zastosowanie do F #.</span><span class="sxs-lookup"><span data-stu-id="559d6-115">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="559d6-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="559d6-116">See Also</span></span>

[<span data-ttu-id="559d6-117">Funkcje</span><span class="sxs-lookup"><span data-stu-id="559d6-117">Functions</span></span>](index.md)