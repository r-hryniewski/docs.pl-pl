### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a>Zestawy skompilowane z Regex.CompileToAssembly przerwy między 4.0 i 4.5

|   |   |
|---|---|
|Szczegóły|Jeśli zestaw skompilowanych wyrażeń regularnych został opracowany z .NET Framework 4.5, ale obiektów docelowych programu .NET Framework 4, próba użycia jednego z wyrażeń regularnych, w tym zestaw w systemie przy użyciu programu .NET Framework 4 zainstalowany zgłasza wyjątek.|
|Sugestia|Aby obejść ten problem, wykonaj jedną z następujących czynności:<ul><li>Tworzenie zestawu, który zawiera wyrażeń regularnych, za pomocą programu .NET Framework 4.</li><li>Użyj interpretowanego wyrażenia regularnego.</li></ul>|
|Zakres|Pomocnicza|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|
|Dotyczy interfejsów API|<ul><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType></li></ul>|

