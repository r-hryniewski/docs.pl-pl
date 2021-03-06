---
title: -main (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: 2f3c9daf98bfe77ea9462c8126f7a8368016875c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516669"
---
# <a name="-main-c-compiler-options"></a>-main (opcje kompilatora C#)
Ta opcja określa klasę, która zawiera wpis punktu programu, jeśli zawiera więcej niż jednej klasy **Main** metody.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-main:class  
```  
  
## <a name="arguments"></a>Argumenty  
 `class`  
 Typ, który zawiera **Main** metody.  
 Nazwa klasy podana, musi być w pełni kwalifikowana; musi on zawierać pełną przestrzeni nazw z klasą, następuje nazwa klasy. Na przykład, gdy `Main` metoda znajduje się wewnątrz `Program` klasy w `MyApplication.Core` przestrzeni nazw, opcja kompilatora musi być `-main:MyApplication.Core.Program`.
  
## <a name="remarks"></a>Uwagi  
 Jeśli Twoja kompilacja zawiera więcej niż jeden typ o [Main](../../../csharp/programming-guide/main-and-command-args/index.md) metody, można określić, jakiego typu zawiera **Main** metodę, która ma być używany jako punkt wejścia do programu.  
  
 Ta opcja jest do użytku podczas kompilowania pliku .exe.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio  
  
1.  Otwórz projekt **właściwości** strony.  
  
2.  Kliknij przycisk **aplikacji** stronę właściwości.  
  
3.  Modyfikowanie **obiekt początkowy** właściwości.  
  
     Aby programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.  
  
## <a name="example"></a>Przykład  
 Skompilować `t2.cs` i `t3.cs`, określania, **Main** metoda zostanie znaleziony w `Test2`:  
  
```console  
csc t2.cs t3.cs -main:Test2  
```  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](../../../csharp/language-reference/compiler-options/index.md)  
- [Zarządzanie właściwościami projektu i rozwiązania](/visualstudio/ide/managing-project-and-solution-properties)
