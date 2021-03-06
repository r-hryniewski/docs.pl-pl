---
title: Architektura zorientowane na usługę
description: Architektura Mikrousług .NET dla aplikacji .NET konteneryzowanych | Architektura zorientowane na usługę
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 67560cc93b3d147be36a691af440bb78f2315557
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105008"
---
# <a name="service-oriented-architecture"></a>Architektura zorientowane na usługę 

Zorientowane na usługę architektura (SOA) został termin nadmiernego obciążenia i oznacza różnych rzeczy do innej osoby. Jednak uzyskać punkt odniesienia, SOA oznacza struktury aplikacji przez decomposing go do wielu usług (najczęściej jako usługi HTTP), które mogą być klasyfikowane jako różnych typów, takie jak podsystemów lub warstwy.

Te usługi staje się możliwe wdrożenie jako kontenery Docker, która rozwiązuje problemy z wdrażaniem, ponieważ wszystkie zależności są uwzględnione w obrazie kontenera. Po trzeba skalowanie w górę SOA aplikacji, może być skalowalności i dostępności wyzwania w przypadku wdrażania w oparciu pojedynczego hostów Docker. Jest to gdzie Docker klastrowania lub oprogramowania orchestrator pomoże Ci, zgodnie z objaśnieniem w kolejnych sekcjach, w których opisano wdrożenie podejścia mikrousług.

Kontenery docker są przydatne (ale nie są wymagane) dla tradycyjnych architektury zorientowane na usługę i bardziej zaawansowanych architektury mikrousług.

Mikrousług pochodzi od SOA, ale SOA różni się od architektury mikrousług. Funkcje, takie jak duży brokerzy centralnej, centralnej orchestrators na poziomie organizacji i [magistrali usługi przedsiębiorstwa (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) opisano typowe w SOA. Jednak w większości przypadków przed wzorce w społeczności mikrousługi są to. W rzeczywistości niektóre osoby argumentowało, że "architektury mikrousługi jest SOA wykonywane po prawej".

Ten przewodnik koncentruje się na mikrousług, ponieważ metoda SOA jest przetestowanego mniej niż wymagania i techniki stosowane w przypadku architektury mikrousługi. Jeśli wiesz, jak utworzyć aplikację na podstawie mikrousługi, również należy znać sposób tworzenia aplikacji opartych na usługach prostsze.




>[!div class="step-by-step"]
[Poprzednie](docker-application-state-data.md)
[dalej](microservices-architecture.md)
