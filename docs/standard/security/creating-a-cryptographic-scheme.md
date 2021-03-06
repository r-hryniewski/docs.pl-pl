---
title: Tworzenie schematu kryptograficznego
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 51d07fadcf359c2b44f22ca9868d0f12e24b80c5
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/08/2018
ms.locfileid: "48873125"
---
# <a name="creating-a-cryptographic-scheme"></a>Tworzenie schematu kryptograficznego
Można łączyć kryptograficznych składników .NET Framework do tworzenia różnych systemów do szyfrowania i odszyfrowywania danych.  
  
 Prosty schemat szyfrowania szyfrowanie i odszyfrowywanie danych może określić następujące czynności:  
  
1.  Każda ze stron generowana jest para kluczy publiczny/prywatny.  
  
2.  Strony wymiany kluczy publicznych.  
  
3.  Każda ze stron generuje klucz tajny dla celów szyfrowania TripleDES, na przykład i szyfruje nowo utworzony klucz przy użyciu klucza publicznego drugiej strony.  
  
4.  Każda strona wysyła dane do drugiego i łączy klucz tajny drugiej strony z własną, w szczególności kolejności, aby utworzyć nowy klucz tajny.  
  
5.  Strony następnie zainicjuj konwersacji za pomocą szyfrowania symetrycznego.  
  
 Tworzenie schematu kryptograficznego nie jest prostym zadaniem.
  
## <a name="see-also"></a>Zobacz także

- [Usługi kryptograficzne](../../../docs/standard/security/cryptographic-services.md)
