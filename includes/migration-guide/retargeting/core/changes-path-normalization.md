### <a name="changes-in-path-normalization"></a>Zmiany w ścieżce normalizacji

|   |   |
|---|---|
|Szczegóły|Począwszy od aplikacji .NET Framework 4.6.2 obiektu docelowego, sposób, w którym środowiska uruchomieniowego normalizuje ścieżki została zmieniona. Normalizacji ścieżki pociąga za sobą modyfikowanie ciąg, który określa ścieżkę lub plików, dzięki czemu odpowiada prawidłową ścieżkę na docelowy system operacyjny. Normalizacji zwykle obejmuje:<ul><li>Kanoniczną separatory składnika i katalogu.</li><li>Stosowanie bieżący katalog do ścieżki względnej.</li><li>Ocena względna katalogu (.) lub katalogu nadrzędnego (.) w ścieżce.</li><li>Przycinanie określonych znaków.</li></ul>Począwszy od aplikacji .NET Framework 4.6.2 obiektu docelowego, następujące zmiany w ścieżce normalizacji są domyślnie włączone:<ul><li>Środowisko uruchomieniowe różni się do systemu operacyjnego [GetFullPathName](https://msdn.microsoft.com/library/windows/desktop/aa364963(v=vs.85).aspx) funkcji normalizacji ścieżki.</li><li>Normalizacji nie obejmuje przycinanie końca katalogu segmenty (na przykład miejsca na końcu nazwy katalogu).</li><li>Obsługa składnia ścieżki urządzenia w trybie pełnego zaufania, w tym <code>\\.\</code> and, for file I/O APIs in mscorlib.dll, '\?'.</li><li>The runtime does not validate device syntax paths.</li><li>The use of device syntax to access alternate data streams is supported.</li></ul>These changes improve performance while allowing methods to access previously inaccessible paths. Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.|
|Sugestia|Aplikacje dla środowiska .NET Framework 4.6.2 lub nowszym można zrezygnować z tego zmienić i użyć starszego normalizacji, dodając następujące polecenie, aby <code>&lt;runtime&gt;</code> sekcji pliku konfiguracji aplikacji:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.UseLegacyPathHandling=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Aplikacje, które odnoszą się do platformy .NET Framework 4.6.1 lub wcześniej, ale są uruchomione w programie .NET Framework 4.6.2 lub później włączyć zmiany ścieżki normalizacji, dodając następujący wiersz do <code>&lt;runtime&gt;</code> sekcji pliku .configuration aplikacji:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.UseLegacyPathHandling=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Zakres|Pomocnicza|
|Wersja|4.6.2|
|Typ|Przekierowania|
