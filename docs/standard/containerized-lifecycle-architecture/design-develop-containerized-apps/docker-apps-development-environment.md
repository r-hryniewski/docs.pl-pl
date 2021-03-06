---
title: Środowisko projektowe dla aplikacji Docker
description: Cykl życia aplikacji konteneryzowanych Docker z platformy firmy Microsoft i narzędzia
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 3da7816127982c3657129561975eed6d1f5aad5a
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104510"
---
# <a name="development-environment-for-docker-apps"></a>Środowisko projektowe dla aplikacji Docker

## <a name="development-tools-choices-ide-or-editor"></a>Opcje narzędzi programistycznych: IDE lub edytora

Niezależnie Jeśli wolisz pełne i wydajne środowiska IDE lub edytora nieskomplikowane i elastyczne, firma Microsoft ma będzie po przejściu tworzenia aplikacji Docker.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code i Docker interfejsu wiersza polecenia (narzędzia wieloplatformowe dla komputerów Mac, Linux i Windows)

Jeśli wolisz edytorze niewielka, między platformami obsługi żadnego języka programowania, można użyć programu Visual Studio Code i interfejsu wiersza polecenia Docker. Te produkty zapewniają proste, ale niezawodne środowisko, co jest szczególnie ważne dla usprawnienie przepływu pracy deweloperów. Instalując "Docker dla komputerów Mac" lub "Docker dla systemu Windows" (development environment), Docker deweloperzy mogą używać jednego interfejsu wiersza polecenia Docker, aby tworzyć aplikacje systemu Windows lub Linux (środowisko uruchomieniowe). Ponadto w Visual Studio Code obsługuje rozszerzenia dla Docker z technologii IntelliSense dla Dockerfiles oraz skrót zadania Docker poleceń w edytorze.

> [!NOTE]
> Aby pobrać program Visual Studio Code, przejdź do <https://code.visualstudio.com/download>.

Aby pobrać Docker dla systemów Mac i systemu Windows, przejdź do <https://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools"></a>Program Visual Studio z narzędziami Docker

Podczas korzystania z programu Visual Studio 2015 można zainstalować dodatkowe narzędzia "Docker Tools for Visual Studio". Dla programu Visual Studio 2017 r narzędzia Docker są wbudowane już. W obu przypadkach można rozwijać, uruchamiania i sprawdzanie poprawności aplikacji bezpośrednio w wybranym środowisku Docker. F5 aplikacji (jeden kontener lub wielu kontenerów) bezpośrednio do Docker hosta z debugowaniem, lub naciśnij klawisze Ctrl + F5, edytowanie i odświeżanie aplikacji bez konieczności odbudować kontenera. Jest to najprostsza i bardziej wydajne wybór dla deweloperów systemu Windows, tworzenie kontenerów Docker dla systemu Linux lub Windows.

> [!NOTE]
> Aby pobrać narzędzia Docker dla programu Visual Studio, przejdź do <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.

## <a name="language-and-framework-choices"></a>Opcje języka i framework

Można programować aplikacje Docker i narzędzi firmy Microsoft z większość nowoczesnych języków. Poniżej przedstawiono listę początkowej, ale nie są ograniczone do niej:

-   Oprogramowanie .NET core i ASP.NET Core
-   Node.js
-   Golang
-   Java
-   Ruby
-   Python

Zasadniczo można użyć dowolnego nowoczesnych języków obsługiwanych przez Docker w systemie Linux lub Windows.


>[!div class="step-by-step"]
[Poprzednie](orchestrate-high-scalability-availability.md)
[dalej](docker-apps-inner-loop-workflow.md)
