---
title: throw (odwołanie w C#)
ms.date: 03/02/2015
f1_keywords:
- throw
- throw_CSharpKeyword
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 831c4cce14e902697d84129e54cc54f07d26b9f3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865039"
---
# <a name="throw-c-reference"></a>throw (odwołanie w C#)
Sygnalizuje zdarzenie wyjątku podczas wykonywania programu.  
  
## <a name="remarks"></a>Uwagi

Składnia `throw` jest:

```csharp
throw [e]
```
gdzie `e` jest wystąpieniem obiektu klasy pochodzącej od <xref:System.Exception?displayProperty=nameWithType>. W poniższym przykładzie użyto `throw` instrukcję, aby zgłosić <xref:System.IndexOutOfRangeException> Jeśli argumentu przekazanego do metody o nazwie `GetNumber` nie odpowiada prawidłowy indeks tablicy wewnętrznego.

[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]  

Następnie za pomocą obiektów wywołujących metodę `try-catch` lub `try-catch-finally` bloku, aby obsłużyć Wyrzucony wyjątek. Poniższy przykład obsługi wyjątku zgłoszonego przez `GetNumber` metody.

[!code-csharp[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]  

## <a name="re-throwing-an-exception"></a>Ponownie zostanie zgłoszony wyjątek

`throw` można również w `catch` bloku, aby można było ponownie zgłosić wyjątek obsłużony w `catch` bloku.  W tym przypadku `throw` nie przyjmuje argumentu operacji wyjątku. Może to być najbardziej przydatne, gdy metoda przekazuje argument z obiekt wywołujący do innej metody w bibliotece, a metoda biblioteki zgłasza wyjątek, który musi być przekazywane do obiektu wywołującego. Na przykład, poniższy przykład generuje ponownie <xref:System.NullReferenceException> zgłaszany podczas próby pobrania pierwszego znaku ciągu niezainicjowany. 

[!code-csharp[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]  

> [!IMPORTANT]
> Można również użyć `throw e` składni `catch` bloku, aby utworzyć wystąpienie nowy wyjątek, który jest przekazywany do obiektu wywołującego. W tym przypadku ślad stosu wyjątku, oryginalnym, który jest dostępny w <xref:System.Exception.StackTrace> właściwości nie są zachowywane.
 
## <a name="the-throw-expression"></a>`throw` Wyrażenia

Począwszy od C# 7.0, `throw` mogą być używane jako wyrażenie, a także instrukcję. Dzięki temu zgłoszenie wyjątku w kontekstach, które były wcześniej obsługiwane. Należą do nich następujące elementy:

- [operator warunkowy](../operators/conditional-operator.md). W poniższym przykładzie użyto `throw` wyrażenie throw <xref:System.ArgumentException> Jeśli metoda jest przekazywana pustą tablicę ciągów. Przed C# 7.0, konieczne są wyświetlane w tę logikę `if` / `else` instrukcji.

   [!code-csharp[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]  
  
- [operator łączenia wartości null](../operators/null-coalescing-operator.md). W poniższym przykładzie `throw` wyrażenie jest używane z operatorem łączenia wartości null do zgłoszenia wyjątku, jeśli ciąg jest przypisany do `Name` właściwość `null`.
 
   [!code-csharp[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]  
 
- wyrażeniem [lambda](../../lambda-expressions.md) lub metody. W poniższym przykładzie pokazano metodę wyrażeniem, które zgłasza <xref:System.InvalidCastException> ponieważ konwersja na <xref:System.DateTime> wartość nie jest obsługiwana.
 
   [!code-csharp[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]  
 
  
## <a name="c-language-specification"></a>Specyfikacja języka C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka C#](../../../csharp/language-reference/index.md)  
- [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)  
- [try-catch](../../../csharp/language-reference/keywords/try-catch.md)  
- [Try, catch i throw instrukcji w języku C++](../../../csharp/language-reference/keywords/try-catch.md)  
- [Słowa kluczowe języka C#](../../../csharp/language-reference/keywords/index.md)  
- [Instrukcje obsługi wyjątków](../../../csharp/language-reference/keywords/exception-handling-statements.md)  
- [Instrukcje: Jawne zgłaszanie wyjątków](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
