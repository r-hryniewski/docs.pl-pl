---
title: /keycontainer
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 887e84843201c64f7dd7b056b5e31d5ccd91bf23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="keycontainer"></a><span data-ttu-id="8b028-102">/keycontainer</span><span class="sxs-lookup"><span data-stu-id="8b028-102">/keycontainer</span></span>
<span data-ttu-id="8b028-103">Określa nazwę kontenera kluczy parę kluczy zapewnić silnej nazwy zestawu.</span><span class="sxs-lookup"><span data-stu-id="8b028-103">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b028-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8b028-104">Syntax</span></span>  
  
```  
/keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="8b028-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="8b028-105">Arguments</span></span>  
  
|<span data-ttu-id="8b028-106">Termin</span><span class="sxs-lookup"><span data-stu-id="8b028-106">Term</span></span>|<span data-ttu-id="8b028-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="8b028-107">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="8b028-108">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="8b028-108">Required.</span></span> <span data-ttu-id="8b028-109">Plik kontenera, który zawiera klucz.</span><span class="sxs-lookup"><span data-stu-id="8b028-109">Container file that contains the key.</span></span> <span data-ttu-id="8b028-110">Nazwę pliku należy ująć w cudzysłów (""), jeśli nazwa zawiera spację.</span><span class="sxs-lookup"><span data-stu-id="8b028-110">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b028-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8b028-111">Remarks</span></span>  
 <span data-ttu-id="8b028-112">Kompilator tworzy składnik zabezpieczać przez wstawianie klucza publicznego do manifestu zestawu i podpisywania z kluczem prywatnym zestawie końcowym.</span><span class="sxs-lookup"><span data-stu-id="8b028-112">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="8b028-113">Aby wygenerować plik klucza, wpisz `sn -k``file` w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="8b028-113">To generate a key file, type `sn -k``file` at the command line.</span></span> <span data-ttu-id="8b028-114">`-i` Opcja powoduje zainstalowanie pary kluczy do kontenera.</span><span class="sxs-lookup"><span data-stu-id="8b028-114">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="8b028-115">Aby uzyskać więcej informacji, zobacz [Sn.exe (narzędzie silnej nazwy)](https://msdn.microsoft.com/library/k5b5tt23).</span><span class="sxs-lookup"><span data-stu-id="8b028-115">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
 <span data-ttu-id="8b028-116">Jeśli kompilacji z `/target:module`, nazwa pliku klucza jest przechowywany w module i włączyć do zestawu, który jest tworzony podczas kompilowania zestawu z [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="8b028-116">If you compile with `/target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="8b028-117">Tę opcję można również określić jako atrybut niestandardowy (<xref:System.Reflection.AssemblyKeyNameAttribute>) w kodzie źródłowym dla każdy moduł język pośredni (MSIL) firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b028-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="8b028-118">Można również przekazać do kompilatora z informacjami szyfrowania [/KeyFile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span><span class="sxs-lookup"><span data-stu-id="8b028-118">You can also pass your encryption information to the compiler with [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span></span> <span data-ttu-id="8b028-119">Użyj [/DelaySign](../../../visual-basic/reference/command-line-compiler/delaysign.md) Jeśli chcesz częściowo podpisanych zestawów.</span><span class="sxs-lookup"><span data-stu-id="8b028-119">Use [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="8b028-120">Zobacz [tworzenie i zestawy Using Strong-Named](https://msdn.microsoft.com/library/xwb8f617) Aby uzyskać więcej informacji na temat podpisywania zestawu.</span><span class="sxs-lookup"><span data-stu-id="8b028-120">See [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b028-121">`/keycontainer` Opcja nie jest dostępne w środowisku programowania Visual Studio; jest dostępna tylko podczas kompilowania kodu w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="8b028-121">The `/keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b028-122">Przykład</span><span class="sxs-lookup"><span data-stu-id="8b028-122">Example</span></span>  
 <span data-ttu-id="8b028-123">Poniższy kod tworzy plik źródłowy `Input.vb` i Określa kontener klucza.</span><span class="sxs-lookup"><span data-stu-id="8b028-123">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```  
vbc /keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b028-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8b028-124">See Also</span></span>  
 [<span data-ttu-id="8b028-125">Zestawy i Globalna pamięć podręczna zestawów</span><span class="sxs-lookup"><span data-stu-id="8b028-125">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="8b028-126">Kompilator w wierszu polecenia programu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8b028-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="8b028-127">/ KeyFile</span><span class="sxs-lookup"><span data-stu-id="8b028-127">/keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [<span data-ttu-id="8b028-128">Kompilacja przykładów — wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="8b028-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)