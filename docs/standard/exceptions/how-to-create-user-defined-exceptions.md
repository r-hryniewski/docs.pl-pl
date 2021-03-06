---
title: 'Porady: tworzenie wyjątków zdefiniowanych przez użytkownika'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- user-defined exceptions
- exceptions, examples
- exceptions, user-defined
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dca313fad896ac1c8eac37c853657bea44a8b777
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2018
ms.locfileid: "44192239"
---
# <a name="how-to-create-user-defined-exceptions"></a>Jak utworzyć wyjątki zdefiniowane przez użytkownika

.NET dostarcza hierarchię klas wyjątków wywodzących się z klasy podstawowej <xref:System.Exception>. Jeśli żaden z wstępnie zdefiniowanych wyjątków nie spełnia Twoich potrzeb, możesz utworzyć własne klasy wyjątków wywodzące się z klasy <xref:System.Exception>.

Tworząc własne wyjątki, zakończ nazwę klasy zdefiniowanego przez siebie wyjątku słowem „Exception” i utwórz trzy wspólne konstruktory, jak pokazano w przykładzie poniżej.  W przykładzie zdefiniowano klasę wyjątku o nazwie `EmployeeListNotFoundException`. Klasa jest pochodną <xref:System.Exception> i zawiera trzy konstruktory.

[!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
[!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
[!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  

> [!NOTE]
> Jeśli używasz komunikacji zdalnej, upewnij się, że metadane zdefiniowane przez użytkownika wyjątków są dostępne na serwerze (strona wywoływana) i dla klienta (obiekt serwera proxy lub strona wywołująca). Aby dowiedzieć się więcej, zobacz [Najlepsze praktyki dotyczące wyjątków](best-practices-for-exceptions.md).

## <a name="see-also"></a>Zobacz także

- [Wyjątki](index.md)
