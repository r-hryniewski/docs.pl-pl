---
title: -filealign —
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
ms.openlocfilehash: db70749f28592ae6711b6d9544f8704af9416490
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181725"
---
# <a name="-filealign"></a>-filealign —
Określa, gdzie należy wyrównać sekcje pliku wyjściowego.  
  
## <a name="syntax"></a>Składnia  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a>Argumenty  
 `number`  
 Wymagana. Wartość, która określa wyrównanie sekcji w pliku wyjściowym. Prawidłowe wartości to 512, 1024, 2048, 4096 i 8192. Te wartości są w bajtach.  
  
## <a name="remarks"></a>Uwagi  
 Możesz użyć `-filealign` opcję, aby określić wyrównanie sekcji w pliku danych wyjściowych. Sekcje są bloków pamięci ciągłej w pliku przenośny plik wykonywalny (PE), który zawiera kod lub danych. `-filealign` Opcja umożliwia kompilowanie aplikacji za pomocą niestandardowych wyrównanie; Większość programistów nie potrzebuje do użycia tej opcji.  
  
 Każda sekcja jest wyrównany na granicy, która jest wielokrotnością liczby `-filealign` wartość. Nie jest stałą domyślnie. Jeśli `-filealign` nie zostanie określony, kompilator wybiera domyślny w czasie kompilacji.  
  
 Określając rozmiar sekcji, możesz zmienić rozmiar pliku wyjściowego. Modyfikowanie sekcji rozmiaru może być przydatne w przypadku programów, które będą uruchamiane w mniejszych urządzeniach.  
  
> [!NOTE]
>  `-filealign` Opcja nie jest dostępne w środowisku programowania Visual Studio; jest dostępna tylko podczas kompilowania kodu w wierszu polecenia.  
  
## <a name="see-also"></a>Zobacz też  
 [Kompilator wiersza polecenia programu Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
