---
title: x:ClassModifier — dyrektywa
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 5a3bbd1d4d75c84dda741d382c8dd7568dbb474b
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2018
ms.locfileid: "45749938"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier — dyrektywa
Modyfikuje zachowanie kompilacji XAML podczas `x:Class` jest również udostępniany. W szczególności, zamiast tworzyć częściowym `class` zawierający `Public` (ustawienie domyślne), poziom dostępu podany `x:Class` jest tworzona przy użyciu `NotPublic` poziom dostępu. To zachowanie ma wpływ na poziom dostępu dla klasy w generowanych zestawów.  
  
## <a name="xaml-attribute-usage"></a>Użycie atrybutu języka XAML  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>Wartości XAML  
  
|||  
|-|-|  
|*NotPublic*|Dokładnie taki ciąg znaków do przekazania do określenia <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> a <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> różni się w zależności od używanego języka programowania związane z kodem. Zobacz uwagi.|  
  
## <a name="dependencies"></a>Zależności  
 [x: Class](../../../docs/framework/xaml-services/x-class-directive.md) również musi być podana w tym samym elemencie, a ten element musi być elementem głównym, na stronie. Aby uzyskać więcej informacji, zobacz [ \[MS-XAML\] sekcji 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Uwagi  
 Wartość `x:ClassModifier` w .NET Framework XAML Services użycia zależy od języka programowania. Parametry do użycia zależy od tego, jak każdy język implementuje jego <xref:System.CodeDom.Compiler.CodeDomProvider> i konwertery typu, zwraca go do zdefiniowania znaczenie dla <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> i <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, i czy ten język jest uwzględniana wielkość liter.  
  
-   Dla języka C#, parametry do przekazania do wyznaczenia <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> jest `internal`.  
  
-   Dla programu Microsoft Visual Basic .NET, parametry do przekazania do wyznaczenia <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> jest `Friend`.  
  
-   Aby uzyskać [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], nie istnieje obsługujące kompilowanie XAML; w związku z tym, wartość do przekazania jest nieokreślona.  
  
 Można również określić <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` w języku C# `Public` w języku Visual Basic); Jednakże, określając <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> rzadko jest wykonywana, ponieważ <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> już jest zachowaniem domyślnym.  
  
 Inne wartości z kodu użytkownika równoważne poziomu dostępu do ograniczenia, takie jak `private` w języku C# nie są istotne dla `x:ClassModifier` odwołania zagnieżdżona klasa nie są obsługiwane w XAML i dlatego <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modyfikator ma taki sam skutek.  
  
## <a name="security-notes"></a>Uwagi dotyczące zabezpieczeń  
 Poziom dostępu, zgodnie z deklaracją w `x:ClassModifier` jest nadal podlega procesowi interpretacji przez określonej struktury i ich funkcji. WPF obejmuje funkcje, aby załadować i tworzenie wystąpień typów gdzie `x:ClassModifier` jest `internal`, jeśli z zasobu WPF za pomocą pakietu odwołanie do identyfikatora URI odwołuje się do tej klasy. W wyniku tego przypadku i potencjalnie innych podoba Ci się zaimplementowane przez innych platform, nie należy polegać wyłącznie na `x:ClassModifier` zablokować wszystkie możliwe podczas tworzenia wystąpienia prób.  
  
## <a name="see-also"></a>Zobacz też  
 [x:Class, dyrektywa](../../../docs/framework/xaml-services/x-class-directive.md)  
 [Plik codebehind i XAML w WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [x:FieldModifier, dyrektywa](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)  
 [Zabezpieczenia (WPF)](../../../docs/framework/wpf/security-wpf.md)  
 [Typy migrowane z WPF do System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
