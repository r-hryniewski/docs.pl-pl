---
title: /langversion (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cfe91588471cc8410b25addea8d66a0388c9c5be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="langversion-visual-basic"></a><span data-ttu-id="145bf-102">/langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="145bf-102">/langversion (Visual Basic)</span></span>
<span data-ttu-id="145bf-103">Powoduje, że kompilator, aby zaakceptować tylko składni, który znajduje się w określonej wersji języka Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="145bf-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="145bf-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="145bf-104">Syntax</span></span>  
  
```  
/langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="145bf-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="145bf-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="145bf-106">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="145bf-106">Required.</span></span> <span data-ttu-id="145bf-107">Wersja językowa mają być użyte podczas kompilacji.</span><span class="sxs-lookup"><span data-stu-id="145bf-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="145bf-108">Akceptowane wartości to `9`, `9.0`, `10`, i `10.0`.</span><span class="sxs-lookup"><span data-stu-id="145bf-108">Accepted values are `9`, `9.0`, `10`, and `10.0`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="145bf-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="145bf-109">Remarks</span></span>  
 <span data-ttu-id="145bf-110">`/langversion` Opcja określa, jakie składni akceptuje kompilatora.</span><span class="sxs-lookup"><span data-stu-id="145bf-110">The `/langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="145bf-111">Na przykład możesz określić, że wersja językowa jest 9.0, kompilator generuje błędy składni, który jest prawidłowy tylko w wersji 10.0 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="145bf-111">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="145bf-112">Podczas tworzenia aplikacji, że docelowy różne wersje programu .NET Framework, można użyć tej opcji.</span><span class="sxs-lookup"><span data-stu-id="145bf-112">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="145bf-113">Na przykład jeśli ma być przeznaczona dla programu .NET Framework 3.5, można tę opcję, aby upewnić się, że nie należy używać składni języka w wersji 10.0.</span><span class="sxs-lookup"><span data-stu-id="145bf-113">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="145bf-114">Można ustawić `/langversion` bezpośrednio tylko przy użyciu wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="145bf-114">You can set `/langversion` directly only by using the command line.</span></span> <span data-ttu-id="145bf-115">Aby uzyskać więcej informacji, zobacz [przeznaczonych dla określonej wersji programu .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span><span class="sxs-lookup"><span data-stu-id="145bf-115">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="145bf-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="145bf-116">Example</span></span>  
 <span data-ttu-id="145bf-117">Poniższy kod kompiluje `sample.vb` 9.0 Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="145bf-117">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```  
vbc /langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="145bf-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="145bf-118">See Also</span></span>  
 [<span data-ttu-id="145bf-119">Kompilator w wierszu polecenia programu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="145bf-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="145bf-120">Kompilacja przykładów — wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="145bf-120">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="145bf-121">Przeznaczonych dla określonej wersji platformy .NET</span><span class="sxs-lookup"><span data-stu-id="145bf-121">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)