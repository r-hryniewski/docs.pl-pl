---
title: 'Porady: lokalizowanie zestawów za pomocą DEVPATH'
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 3a9ae9c60ad7de80d04f16984b3b2fb048421cc2
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452767"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>Porady: lokalizowanie zestawów za pomocą DEVPATH
Deweloperzy mogą chcą upewnij się, że zestaw współużytkowany, które trwają prace działa poprawnie z wieloma aplikacjami. Zamiast ciągle umieszczenie zestawu w globalnej pamięci podręcznej podczas cyklu rozwoju, deweloper można utworzyć zmiennej środowiskowej DEVPATH, który wskazuje na katalog wyjściowy kompilacji dla zestawu.  
  
 Załóżmy na przykład, który jest kompilowany zestaw współużytkowany o nazwie MySharedAssembly i katalog wyjściowy jest C:\MySharedAssembly\Debug. C:\MySharedAssembly\Debug można umieścić w zmiennej DEVPATH. Następnie należy określić [ \<developmentmode — >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) elementu w pliku konfiguracji komputera. Środowisko uruchomieniowe języka wspólnego lokalizowanie zestawów za pomocą DEVPATH zawiera informacje dla tego elementu.  
  
 Zestaw współużytkowany musi być wykrywalny przez środowisko uruchomieniowe.  Aby określić katalog prywatnej rozpoznawania zestawu odwołania do użycia [ \<codeBase > Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) lub [ \<sondowanie > Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) w pliku konfiguracji, zgodnie z opisem w [Określanie lokalizacji zestawu](../../../docs/framework/configure-apps/specify-assembly-location.md).  Możesz również umieścić zestaw w podkatalogu katalogu aplikacji. Aby uzyskać więcej informacji, zobacz [jak środowisko uruchomieniowe lokalizuje zestawy](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
> [!NOTE]
>  Jest to zaawansowana funkcja przeznaczonych tylko w celach deweloperskich.  
  
 Poniższy przykład pokazuje, jak spowodować, że środowisko uruchomieniowe do przeszukania pod kątem zestawów w katalogach określonych przez zmienną środowiskową DEVPATH.  
  
## <a name="example"></a>Przykład  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 To ustawienie, wartość domyślna to false.  
  
> [!NOTE]
>  Użyj tego ustawienia w czasie projektowania. Środowisko wykonawcze nie sprawdza obecności wersje zestawów o silnych nazwach, znaleziono w DEVPATH. Po prostu używa pierwszego zestawu, który odnajdzie.  
  
## <a name="see-also"></a>Zobacz też  
 [Konfigurowanie aplikacji programu .NET Framework](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
