---
title: Projektowanie modelu domeny mikrousługi
description: Architektura Mikrousług .NET konteneryzowanych aplikacji .NET | Projektowanie modelu domeny mikrousługi
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/09/2017
ms.openlocfilehash: 9a54679fc28bb2adf803a38fe5e43f67048a4cfd
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50048479"
---
# <a name="designing-a-microservice-domain-model"></a>Projektowanie modelu domeny mikrousługi

*Zdefiniuj jeden model domeny sformatowanego dla poszczególnych mikrousług biznesowych lub ograniczony kontekst*

Celem użytkownika jest, aby utworzyć model pojedynczej domeny spójny dla poszczególnych mikrousług biznesowych lub ograniczony kontekst (BC). Należy pamiętać, jednak, że BC lub mikrousług firmy może czasami składać się z kilka fizycznych usług, które mają model domeny pojedynczej. Model domeny konieczne jest przechwycenie reguły, zachowanie, język biznesowy i ograniczenia pojedynczego ograniczonego kontekstu lub mikrousług firmy, który reprezentuje.

## <a name="the-domain-entity-pattern"></a>Wzorzec jednostka domeny

Jednostki reprezentują obiektów domeny i są zdefiniowane głównie przez ich tożsamości, ciągłość działalności biznesowej i trwałości wraz z upływem czasu, a nie tylko przez atrybuty, które składają się z nimi. Jak wynika z Eric Evans, "obiektu zdefiniowane głównie przez jego tożsamość nosi nazwę jednostki." Jednostki są bardzo ważna w modelu domeny, ponieważ są one base dla modelu. W związku z tym należy zidentyfikować i je uważnie projektować.

*Tożsamość obiektu można krzyżowe w wielu mikrousługach lub ograniczonych kontekstów.*

Ta sama tożsamość (choć nie tej samej jednostki) mogą być modelowane w wielu kontekstach ograniczonych lub mikrousług. Jednakże, nie oznacza, że tej samej jednostki o tej samej logiki i atrybuty mogą być realizowane w wielu kontekstach ograniczonych. Zamiast tego jednostki w każdym kontekście ograniczonych ograniczyć ich atrybuty i zachowaniami służącymi do wymaganych w domenie ten ograniczony kontekst.

Na przykład jednostki nabywcy może być najbardziej atrybutów osoby, które są zdefiniowane w jednostce użytkownika w profilu lub tożsamości mikrousług, włącznie z tożsamością. Ale jednostki nabywcy w mikrousługach szeregowania może być mniej atrybutów, ponieważ określone dane kupujący jest powiązany z procesu zamówień. Kontekst poszczególne mikrousługi lub ograniczony kontekst ma wpływ na jej modelu domeny.

*Jednostki domeny należy zaimplementować zachowanie oprócz atrybutów danych wykonawczych*

Jednostka domeny w DDD musi implementować logikę domeny lub zachowania związane z danymi jednostki (object, dostępne w pamięci). Na przykład jako część klasy jednostki zamówienia konieczne jest posiadanie logiki biznesowej i operacje zaimplementowane jako metody dla zadań, takich jak dodawanie przedmiot zamówienia, sprawdzanie poprawności danych i obliczenia całkowitej. Metody jednostki zajmujemy się invariants i reguł, jednostki, zamiast tych zasad, rozkładają się na warstwie aplikacji.

Rysunek 9-8 przedstawia jednostka domeny, który implementuje nie tylko atrybuty danych, ale operacje lub metody w logice domeny powiązane.

![](./media/image9.png)

**Rysunek 9-8**. Przykładowy projekt jednostka domeny Implementowanie danych oraz zachowania

Oczywiście czasami może być jednostek, które implementuje żadnej logiki jako część klasy jednostki. Przyczyną może być w jednostki podrzędne w ramach agregacji jednostce podrzędnej nie ma jakąkolwiek logikę specjalną, ponieważ większość logiki jest definiowana w głównym agregacji. W przypadku złożonych mikrousług, zawierającego wiele logiki implementowane w klasach usługi zamiast w jednostkach domeny może być należących do modelu domeny anemic szczegółowo opisane w poniższej sekcji.

### <a name="rich-domain-model-versus-anemic-domain-model"></a>Model domeny rozbudowane i model domeny anemic

W jego wpis [AnemicDomainModel](https://martinfowler.com/bliki/AnemicDomainModel.html), Martina Fowlera w tym artykule opisano model domeny anemic w ten sposób:

Podstawowe objaw Anemic modelu domeny to, co najpierw blush wygląda czegoś. Istnieją obiekty, wiele nazwana rzeczowniki w obszarze domeny i te obiekty są połączone za pomocą zaawansowanych relacje i strukturę, która ma modeli domeny true. Catch jest dostarczany, Przyjrzyj się zachowanie, gdy okazuje się, że występuje niewiele wszelkich zachowań tych obiektów, dzięki czemu można je nieco więcej niż zbiory metod pobierających i ustawiających.

Oczywiście, korzystając z modelu domeny anemic te modele danych będą używane w z zestawu obiektów usługi (tradycyjnie nazwane *warstwy biznesowej*) który Przechwyć wszystkie domeny lub logikę biznesową. Warstwy biznesowej znajduje się na podstawie modelu danych i używa modelu danych, podobnie jak dane.

Model domeny anemic jest po prostu procedurach styl projektowania. Obiekty anemic jednostki nie są rzeczywistych obiektów, ponieważ mają zachowanie (metod). Mogą zawierać tylko właściwości danych i dlatego nie jest zorientowany na obiekt. Poprzez umieszczenie wszystkich zachowanie na zewnątrz w obiektach usługi (warstwy biznesowej) zasadniczo na końcu [kodu w postaci spaghetti](https://en.wikipedia.org/wiki/Spaghetti_code) lub [skrypty transakcji](https://martinfowler.com/eaaCatalog/transactionScript.html), i w związku z tym utracić zalety modelu domeny udostępnia.

Niezależnie od tego, jeśli mikrousług lub ograniczony kontekst jest bardzo proste (CRUD usługi), model domeny anemic w formie obiektów jednostek przy użyciu tylko właściwości danych może być wystarczające i może nie być warte Implementowanie wzorców DDD bardziej złożone. W takiej sytuacji będzie po prostu modelu trwałości, ponieważ zostały celowo utworzone jednostki danymi tylko do celów CRUD.

Właśnie dlatego architektur mikrousług są idealne dla wielu architektury podejście w zależności od każdego kontekstu ograniczonego. Na przykład w ramach aplikacji eShopOnContainers, szeregowania mikrousługa implementuje wzorców DDD, ale mikrousług katalogu, który jest prostą usługę CRUD, nie ma.

Niektóre osoby powiedzieć o tym, że model domeny anemic jest zapobieganie wzorca. Tak naprawdę zależy to implementacja. Jeśli mikrousług, tworzona jest prosty wystarczająco (na przykład usługa CRUD), zgodnie z modelu anemic domeny nie jest zapobieganie wzorca. Jednak jeśli zachodzi potrzeba czoła złożoności domeny mikrousług, która ma wiele kolejne zmiany reguł biznesowych, model domeny anemic może być zapobieganie wzorzec dla tego mikrousług lub ograniczone do kontekstu. W takim przypadku projektowania jako zaawansowane modelu przy użyciu jednostek zawierających dane, a także zachowanie, a także wdrażanie dodatkowych wzorców DDD (agregacje, obiekty wartości itp.) może być ogromne korzyści długoterminowe powodzenia takich mikrousług.

#### <a name="additional-resources"></a>Dodatkowe zasoby

-   **DevIQ. Domain Entity**
    [*https://deviq.com/entity/*](https://deviq.com/entity/)

-   **Martina Fowlera. Model domeny**
    [*https://martinfowler.com/eaaCatalog/domainModel.html*](https://martinfowler.com/eaaCatalog/domainModel.html)

-   **Martina Fowlera. Model domeny Anemic**

    <https://martinfowler.com/bliki/AnemicDomainModel.html>

### <a name="the-value-object-pattern"></a>Wzorzec wartość obiektu

Wspomniane Eric Evans ma "wiele obiektów ma koncepcyjny tożsamości. Te obiekty opisują określoną wspólną charakterystykę rzeczy."

Jednostka wymaga tożsamości, ale istnieje wiele obiektów w systemie, które w przeciwnym razie, takich jak wzorzec obiektu wartości. Obiekt wartości jest obiekt z nie pojęciach tożsamości, która opisuje aspekt domeny. Są to obiekty, które wystąpienia do reprezentowania elementów projektu, które tylko dotyczą możesz tymczasowo. Interesujące Cię *co* , nie są *kto* są. Przykłady obejmują liczby i ciągi, ale można też koncepcji wyższego poziomu, takich jak grupy atrybutów.

Coś, co jest jednostką w mikrousługach może być jednostki w innym mikrousług, ponieważ w drugim przypadku ograniczony kontekst może mieć inne znaczenie. Na przykład adres w aplikacji handlu elektronicznego utracić tożsamości, ponieważ może być reprezentowana grupy atrybutów profilu klienta dla osoby lub firmy. W takim przypadku adres powinny być klasyfikowane jako obiekt wartości. Jednak w aplikacji prądu energii elektrycznej adres odbiorcy może być ważne dla domeny biznesowej. Adres musi mieć tożsamości, więc systemów rozliczeniowych, które może być bezpośrednio połączony do adresu. W takim przypadku adres powinny być klasyfikowane jako jednostka domeny.

Osoba mająca imię i nazwisko, zwykle jest jednostką, ponieważ osoba ma tożsamości, nawet wtedy, gdy imię i nazwisko pokrywa się z innego zestawu wartości, np. Jeśli te nazwy odnosi się także do innej osobie.

Obiekty wartości są trudny do zarządzania relacyjnymi bazami danych i ORMs, takie jak EF, natomiast w dokumencie korzystający z bazy danych, które są łatwiejsze do wdrożenia i użycia.

#### <a name="additional-resources"></a>Dodatkowe zasoby

-   **Martina Fowlera. Value — wzorzec obiektu**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)

-   **Obiekt wartości**
    [*https://deviq.com/value-object/*](https://deviq.com/value-object/)

-   **Obiekty wartości w Test-Driven Development**
    [*https://leanpub.com/tdd-ebook/read\#leanpub-auto-value-objects*](https://leanpub.com/tdd-ebook/read#leanpub-auto-value-objects)

-   **Eric Evans. Projektowania opartego na domenie: Co dzień do czynienia złożoności serce oprogramowania.** (Zarezerwuj; zawiera omówienie obiekty wartości) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

### <a name="the-aggregate-pattern"></a>Wzorzec agregacji

Model domeny zawiera klaster jednostek różne dane i procesy, które można kontrolować istotny obszar funkcji, takich jak spełnienia kolejności lub magazynu. Do bardziej szczegółowych DDD jest funkcję agregacji, w tym artykule opisano klastra lub grupy jednostek i zachowań, które mogą być traktowane jako jednostka cohesive.

Zazwyczaj zdefiniujesz agregacją, w oparciu o transakcji, które są potrzebne. Klasycznym przykładem jest zamówienie, zawierający listę elementów w kolejności. Przedmiot zamówienia zwykle jest jednostką. Ale będzie ona jednostce podrzędnej w agregacji kolejność, która będzie również zawierać jednostki zamówienia jego jednostkę główną, zwykle nazywane głównego agregacji.

Identyfikowanie zagregowanych danych może okazać się trudne. Wartość zagregowana jest grupy obiektów, które muszą być zgodne ze sobą, ale nie można po prostu wybierz grupę obiektów i nadaj im etykiety na wartość zagregowana. Musi rozpoczynać się koncepcja domeny i myśleć o jednostek, które są używane w najbardziej typowych transakcje powiązane z związany z tą koncepcją. Te jednostki, które muszą być transakcyjnie spójne to, co stanowi agregację. Myśleć o operacji transakcji jest prawdopodobnie najlepszym sposobem identyfikacji agregacji.

### <a name="the-aggregate-root-or-root-entity-pattern"></a>Wzorzec głównego agregacji lub jednostki głównej

Wartość zagregowana składa się z co najmniej jedną jednostkę: głównego agregacji, nazywane również jednostki głównej lub podstawowej jednostki. Ponadto może mieć wiele podrzędnych jednostek i obiektów wartości wszystkich jednostek i obiektów współpracując do zaimplementowania transakcji i wymagane zachowanie.

Główny agregacji ma na celu zapewnienie spójności agregacji; należy go tylko punkt wejścia dla aktualizacji do agregacji za pomocą metod lub operacji w całkowitym Klasa główna. Należy wprowadzić zmiany do jednostki w ramach agregacji tylko przy użyciu głównego agregacji. Jest ochrona spójności agregacji, biorąc pod uwagę invariants i zasady spójności, może być potrzebnych do wykonania w swojej agregacji. Jeśli zmienisz niezależnie jednostka lub wartość obiektu podrzędnego, głównego agregacji nie upewnij się, że agregacja w prawidłowym stanie. Jest podobna do tabeli za pomocą nie będzie gałęzi. Związane z utrzymaniem spójności jest głównym celem głównego agregacji.

9 rysunek-9, możesz zobaczyć agreguje próbki takich jak kupujący agregacji, która zawiera pojedynczą jednostkę (kupujący w katalogu głównym agregacji). Agregacja kolejności zawiera wiele jednostek i wartość obiektu.

![](./media/image10.png)

**Rysunek 9 – 9**. Przykład wartości zagregowanych z wieloma lub pojedynczego jednostek

Należy zauważyć, że agregacji kupujący może dodatkowe podrzędne jednostki, w zależności od domeny, co w szeregowania mikrousługi w ramach aplikacji eShopOnContainers aplikacji odwołanie. Rysunek 9 – 9 po prostu ilustruje przypadek, w którym kupujący ma pojedynczej jednostki, na przykład agregacji, która zawiera tylko głównego agregacji.

Aby można było obsługiwać separację agregacji i zachować wyraźne granice między nimi, jest dobrym rozwiązaniem w modelu domeny DDD nie zezwala na bezpośrednie Nawigacja pomiędzy agregacje i posiadanie tylko pole klucza obcego (klucz OBCY), zgodnie z implementacją w [ Kolejność modelu domeny mikrousługi](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs) w ramach aplikacji eShopOnContainers. Jednostki zamówienia ma tylko pole klucza Obcego kupujący, ale nie do programu EF Core nawigacji właściwości, jak pokazano w poniższym kodzie:

```csharp
public class Order : Entity, IAggregateRoot
{
    private DateTime _orderDate;
    public Address Address { get; private set; }
    private int? _buyerId; //FK pointing to a different aggregate root
    public OrderStatus OrderStatus { get; private set; }
    private readonly List<OrderItem> _orderItems;
    public IReadOnlyCollection<OrderItem> OrderItems => _orderItems;
    // ... Additional code
}
```

Identyfikowanie i Praca z agregacjami wymaga badania i doświadczenie. Aby uzyskać więcej informacji przejrzyj następującą listę dodatkowych zasobów.

#### <a name="additional-resources"></a>Dodatkowe zasoby

-   **Vaughn Vernon. Efektywnym projektowaniu agregacji - Part I: modelowania jednej wartości zagregowanej**
    [*https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD\_COMMUNITY\_ESSAY\_AGGREGATES\_PART\_1.pdf*](https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_1.pdf)

-   **Vaughn Vernon. Skuteczne agregacji projektu — część II: Wprowadzanie wartości zagregowanych pracują razem**
    [*https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_2.pdf*](https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_2.pdf)

-   **Vaughn Vernon. Skuteczne agregacji projektu — część III: Uzyskiwanie wglądu za pośrednictwem odnajdywania**
    [*https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_3.pdf*](https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_3.pdf)

-   **Sergey Grybniak. Wzorce projektowe taktyczne DDD**
    [*https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part*](https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part)

-   **Chris Leonard. Tworzenie transakcji Mikrousług przy użyciu wartości zagregowanych**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson)

-   **DevIQ. Wzorzec agregacji**
    [*https://deviq.com/aggregate-pattern/*](https://deviq.com/aggregate-pattern/)

>[!div class="step-by-step"]
[Poprzednie](ddd-oriented-microservice.md)
[dalej](net-core-microservice-domain-model.md)
