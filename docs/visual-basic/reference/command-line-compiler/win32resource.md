---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
ms.openlocfilehash: 4ecac4ffe665d724d625aaeb7cc1e008eb13ca54
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50186086"
---
# <a name="-win32resource"></a>-win32resource
Wstawia plik zasobów Win32 w pliku wyjściowym.  
  
## <a name="syntax"></a>Składnia  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a>Argumenty  
 `filename`  
 Nazwa pliku zasobów, aby dodać do pliku wyjściowego. Nazwę pliku należy ująć w znaki cudzysłowu ("") zawiera spację.  
  
## <a name="remarks"></a>Uwagi  
 Plik zasobów Win32 można utworzyć przy użyciu kompilatora zasobów Windows firmy Microsoft (RC).  
  
 Zasób Win32 może zawierać wersji lub informacje mapy bitowej (ikonę), które pomaga w identyfikacji aplikacji na platformie **Eksploratora plików**. Jeśli nie określisz `-win32resource`, kompilator generuje informacje o wersji, w zależności od używanej wersji zestawu. `-win32resource` i `-win32icon` opcje wykluczają się wzajemnie.  
  
 Zobacz [- linkresource — (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) do odwołania [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] pliku zasobów, lub [-zasobów (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) można dołączyć [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] pliku zasobów.  
  
> [!NOTE]
>  `-win32resource` Opcja nie jest dostępne w środowisku programowania Visual Studio; jest dostępna tylko podczas kompilowania kodu w wierszu polecenia.  
  
## <a name="example"></a>Przykład  
 Poniższy kod kompiluje `In.vb` i dołącza plik zasobów Win32 `Rf.res`:  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Kompilator wiersza polecenia programu Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Przykłady kompilacji — wiersze poleceń](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
