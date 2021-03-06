---
title: Programowanie dla sieci w .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- Internet
- Internet, .NET Framework Internet services
- Network Resources
ms.assetid: 8d455610-67a0-4fa8-a62f-7747064a9256
ms.openlocfilehash: 1d35951aef3692d82bdfa648df48eb8c1bca88ff
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188082"
---
# <a name="network-programming-in-the-net-framework"></a>Programowanie dla sieci w .NET Framework
Środowisko Microsoft .NET Framework oferuje warstwowe, rozszerzalne i zarządzane wdrożenia usług internetowych, które można szybko i łatwo zintegrować ze swoimi aplikacjami. Aplikacje sieciowe mogą za pomocą podłączanych protokołów automatycznie wykorzystywać nowe protokoły internetowe albo za pośrednictwem zarządzanej implementacji interfejsu gniazd systemu Windows współpracować z siecią na poziomie gniazd.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Wprowadzenie protokołów podłączanych](../../../docs/framework/network-programming/introducing-pluggable-protocols.md)  
 Opis sposobów uzyskiwania dostępu do zasobu internetowego bez względu na protokół dostępu, którego wymaga zasób.  
  
 [Żądanie danych](../../../docs/framework/network-programming/requesting-data.md)  
 Wyjaśnienie, jak za pomocą podłączanych protokołów przekazywać i pobierać dane z zasobów internetowych.  
  
 [Programowanie protokołów podłączanych](../../../docs/framework/network-programming/programming-pluggable-protocols.md)  
 Wyjaśnienie, jak utworzyć pochodne klasy specyficzne dla protokołów w celu zaimplementowania podłączanych protokołów.  
  
 [Korzystanie z protokołów aplikacji](../../../docs/framework/network-programming/using-application-protocols.md)  
 Opis zasad programowania aplikacji wykorzystujących protokoły sieciowe, takie jak TCP, UDP i HTTP.  
  
 [Protokół IPv6](../../../docs/framework/network-programming/internet-protocol-version-6.md)  
 Opis zalet protokołu Internet Protocol w wersji 6 (IPv6) w porównaniu z obecną wersją pakietu Internet Protocol (IPv4), a także mechanizmów adresowania, routingu i automatycznej konfiguracji w protokole IPv6 oraz sposobów włączania i wyłączania protokołu.  
  
 [Konfigurowanie aplikacji internetowych](../../../docs/framework/network-programming/configuring-internet-applications.md)  
 Wyjaśnienie zasad konfigurowania aplikacji internetowych za pomocą plików konfiguracyjnych środowiska .NET Framework.  
  
 [Śledzenie sieci w programie .NET Framework](../../../docs/framework/network-programming/network-tracing.md)  
 Wyjaśnienie, jak za pomocą mechanizmu śledzenia sieci uzyskiwać informacje o wywołaniach metod i ruchu sieciowym generowanym przez zarządzaną aplikację.  
  
 [Zarządzanie pamięcią podręczną dla aplikacji sieciowych](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 W tym artykule opisano sposób użycia buforowania w aplikacjach, które używają <xref:System.Net.WebClient?displayProperty=nameWithType>, <xref:System.Net.WebRequest?displayProperty=nameWithType>, i <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> klasy.  
  
 [Zabezpieczenia w programowaniu sieciowym](../../../docs/framework/network-programming/security-in-network-programming.md)  
 Opis używania standardowych technik zabezpieczania i uwierzytelniania w Internecie.  
  
 [Najlepsze rozwiązania dotyczące klas System.Net](../../../docs/framework/network-programming/best-practices-for-system-net-classes.md)  
 Porady i wskazówki dotyczące optymalnego wykorzystania możliwości aplikacji internetowych.  
  
 [Dostęp do Internetu za pośrednictwem serwera proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 Opis konfigurowania serwerów proxy.  
  
 [NetworkInformation](../../../docs/framework/network-programming/networkinformation.md)  
 Opis sposobów gromadzenia informacji na temat zdarzeń w sieci, zmiany, statystyk i właściwości oraz wyjaśnienie, jak ustalić, czy zdalny host jest osiągalny, za pomocą <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> klasy.  
  
 [Zmiany w przestrzeni nazw System.Uri w wersji 2.0](../../../docs/framework/network-programming/changes-to-the-system-uri-namespace-in-version-2-0.md)  
 W tym artykule opisano kilka zmian <xref:System.Uri?displayProperty=nameWithType> klasy w wersji 2.0 nieprawidłowe zachowanie, zwiększyć użyteczność i poprawić bezpieczeństwo.  
  
 [Obsługa identyfikatorów zasobów międzynarodowych w System.Uri](../../../docs/framework/network-programming/international-resource-identifier-support-in-system-uri.md)  
 Opis ulepszeń <xref:System.Uri?displayProperty=nameWithType> klasy w wersjach 3.5, 3.0 z dodatkiem SP1 i 2.0 z dodatkiem SP1 międzynarodowych identyfikatorów zasobów (IRI) i międzynarodowych nazw domen (IDN).  
  
 [Ulepszenia wydajności gniazda w wersji 3.5](../../../docs/framework/network-programming/socket-performance-enhancements-in-version-3-5.md)  
 Opis zbioru ulepszeń klasy <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> klasy w wersjach 3.5, 3.0 z dodatkiem SP1 i 2.0 z dodatkiem SP1, które zapewniają alternatywny wzorzec asynchroniczny, które mogą być używane przez aplikacje specjalistyczne gniazda o wysokiej wydajności.  
  
 [Protokół PNRP](../../../docs/framework/network-programming/peer-name-resolution-protocol.md)  
 Opis mechanizmu dodanego w wersji 3.5 do obsługi protokołu PNRP (Peer Name Resolution Protocol), bezserwerowego i dynamicznego rejestrowania nazw oraz protokołu rozpoznawania nazw. Te nowe funkcje są obsługiwane przez <xref:System.Net.PeerToPeer?displayProperty=nameWithType> przestrzeni nazw.  
  
 [Współpraca równorzędna](../../../docs/framework/network-programming/peer-to-peer-collaboration.md)  
 Opis mechanizmu dodanego w wersji 3.5 do obsługi współpracy między równorzędnymi urządzeniami w oparciu o protokół PNRP. Te nowe funkcje są obsługiwane przez <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType> przestrzeni nazw.  
  
 [Zmiany w uwierzytelnianiu NTLM dla HttpWebRequest w wersji 3.5 z dodatkiem SP1](../../../docs/framework/network-programming/changes-to-ntlm-authentication-for-httpwebrequest-in-version-3-5-sp1.md)  
 W tym artykule opisano zmiany zabezpieczeń wprowadzone w wersji 3.5 z dodatkiem SP1, które mają wpływ na Windows jak zintegrowane uwierzytelnianie jest obsługiwane przez <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, i pokrewne klasy w przestrzeni nazw System.Net.  
  
 [Zintegrowane uwierzytelnianie systemu Windows z ochroną rozszerzoną](../../../docs/framework/network-programming/integrated-windows-authentication-with-extended-protection.md)  
 Opis rozszerzonej ochrony, które mają wpływ na sposób zintegrowane uwierzytelnianie Windows odbywa się przez <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>, <xref:System.Net.Security.SslStream?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, i pokrewne klasy w <xref:System.Net?displayProperty=nameWithType> i pokrewne przestrzenie nazw.  
  
 [Przechodzenie translatora adresów sieciowych przy użyciu protokołu IPv6 i Teredo](../../../docs/framework/network-programming/nat-traversal-using-ipv6-and-teredo.md)  
 Opis ulepszeń dodanych w <xref:System.Net?displayProperty=nameWithType>, <xref:System.Net.NetworkInformation?displayProperty=nameWithType>, i <xref:System.Net.Sockets?displayProperty=nameWithType> przestrzenie nazw umożliwiają przechodzenie translatora adresów Sieciowych przy użyciu protokołu IPv6 i Teredo.  
  
 [Izolacja sieci dla aplikacji ze sklepu Windows Store](../../../docs/framework/network-programming/network-isolation-for-windows-store-apps.md)  
 Opis wpływu izolacji sieci gdy klasy przestrzeni <xref:System.Net>, <xref:System.Net.Http>, i <xref:System.Net.Http.Headers> przestrzenie nazw są używane w [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplikacji.  
  
 [Przykłady programowania sieciowego](../../../docs/framework/network-programming/network-programming-samples.md)  
 Łącza do pobieralnych sieci przykłady programowania, które używają klas w <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>, <xref:System.Net.Sockets> przestrzeni nazw.  
  
## <a name="reference"></a>Tematy pomocy  
 <xref:System.Net?displayProperty=nameWithType>  
 Prosty interfejs programistyczny dla wielu protokołów używanych obecnie w sieciach. <xref:System.Net.WebRequest?displayProperty=nameWithType> i <xref:System.Net.WebResponse?displayProperty=nameWithType> klasy w tej przestrzeni nazw stanowią podstawę podłączanych protokołów.  
  
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 Określa typy i wyliczenia używane do definiowania zasad buforowania dla zasobów pobranych przy użyciu <xref:System.Net.WebRequest?displayProperty=nameWithType> i <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> klasy.  
  
 <xref:System.Net.Configuration?displayProperty=nameWithType>  
 Klasy, za pomocą których aplikacje programistycznie uzyskują dostęp i aktualizują ustawienia konfiguracyjne w przestrzeni nazw System.Net.  
  
 <xref:System.Net.Http?displayProperty=nameWithType>  
 Klasy tworzące interfejs programistyczny dla nowoczesnych aplikacji wykorzystujących protokół HTTP.  
  
 <xref:System.Net.Http.Headers?displayProperty=nameWithType>  
 Zapewnia obsługę kolekcji nagłówków HTTP używanych przez <xref:System.Net.Http?displayProperty=nameWithType> przestrzeni nazw  
  
 <xref:System.Net.Mail?displayProperty=nameWithType>  
 Klasy do redagowania i wysyłania poczty przy użyciu protokołu SMTP.  
  
 <xref:System.Net.Mime?displayProperty=nameWithType>  
 Definiuje typy, które są używane do reprezentowania nagłówków protokołu dynamicznej konfiguracji hosta (MIME, Multipurpose Internet Mail Exchange) używanych przez klasy w <xref:System.Net.Mail?displayProperty=nameWithType> przestrzeni nazw.  
  
 <xref:System.Net.NetworkInformation?displayProperty=nameWithType>  
 Klasy umożliwiające programistyczne gromadzenie informacji o zdarzeniach, zmianach, statystykach i właściwościach sieci.  
  
 <xref:System.Net.PeerToPeer?displayProperty=nameWithType>  
 Umożliwia zarządzaną implementację protokołu PNRP (Peer Name Resolution Protocol) dla programistów.  
  
 <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType>  
 Umożliwia zarządzaną implementację interfejsu współpracy elementów równorzędnych dla programistów.  
  
 <xref:System.Net.Security?displayProperty=nameWithType>  
 Klasy zapewniające strumienie sieciowe umożliwiające bezpieczną komunikację między hostami.  
  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 Umożliwia zarządzaną implementację interfejsu Windows Sockets (Winsock) dla programistów, którzy muszą wprowadzić mechanizm kontroli dostępu do sieci.  
  
 <xref:System.Net.WebSockets?displayProperty=nameWithType>  
 Umożliwia zarządzaną implementację interfejsu WebSocket dla programistów.  
  
 <xref:System.Uri?displayProperty=nameWithType>  
 Umożliwia reprezentowanie obiektów za pomocą jednolitych identyfikatorów zasobów (URI) oraz łatwy dostęp do elementów identyfikatorów URI.  
  
 <xref:System.Security.Authentication.ExtendedProtection?displayProperty=nameWithType>  
 Umożliwia obsługę uwierzytelniania przy użyciu mechanizmu rozszerzonej ochrony aplikacji.  
  
 <xref:System.Security.Authentication.ExtendedProtection.Configuration?displayProperty=nameWithType>  
 Umożliwia konfigurowanie uwierzytelniania przy użyciu mechanizmu rozszerzonej ochrony aplikacji.  
  
## <a name="see-also"></a>Zobacz też  

 [Transport Layer Security (TLS) najlepsze rozwiązania z programem .NET Framework](../../../docs/framework/network-programming/tls.md)  
 [Programowanie dla sieci — tematy z instrukcjami](../../../docs/framework/network-programming/network-programming-how-to-topics.md)  
 [Przykłady programowania sieciowego](../../../docs/framework/network-programming/network-programming-samples.md)  
 [Przykłady kodu usług sieciowych dla platformy .NET w galerii kodu MSDN](https://code.msdn.microsoft.com/Wiki/View.aspx?ProjectName=nclsamples)  
 [Przykładowe klasy HttpClient](https://go.microsoft.com/fwlink/?LinkId=242550)
