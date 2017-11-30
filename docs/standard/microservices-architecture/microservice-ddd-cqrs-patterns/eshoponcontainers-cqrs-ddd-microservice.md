---
title: "Stosowanie CQRS i CQS podejścia w mikrousługi DDD, w eShopOnContainers"
description: "Architektura Mikrousług .NET dla aplikacji .NET konteneryzowanych | Stosowanie CQRS i CQS podejścia w mikrousługi DDD, w eShopOnContainers"
keywords: "Docker, Mikrousług, ASP.NET, kontenera"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: a2c4429a75ca47d4fbcde868b95e76bc65ea2bef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="applying-cqrs-and-cqs-approaches-in-a-ddd-microservice-in-eshoponcontainers"></a><span data-ttu-id="2198e-104">Stosowanie CQRS i CQS podejścia w mikrousługi DDD, w eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="2198e-104">Applying CQRS and CQS approaches in a DDD microservice in eShopOnContainers</span></span>

<span data-ttu-id="2198e-105">Projekt porządkowania mikrousługi na eShopOnContainers aplikacja referencyjna jest oparta na zasadach CQRS.</span><span class="sxs-lookup"><span data-stu-id="2198e-105">The design of the ordering microservice at the eShopOnContainers reference application is based on CQRS principles.</span></span> <span data-ttu-id="2198e-106">Jednak używa najprostsza metoda po prostu oddzielanie zapytania z poleceniami i dla obu czynności przy użyciu tej samej bazy danych.</span><span class="sxs-lookup"><span data-stu-id="2198e-106">However, it uses the simplest approach, which is just separating the queries from the commands and using the same database for both actions.</span></span>

<span data-ttu-id="2198e-107">Jest użycia tych wzorców i należy koniecznie zwrócić uwagę, że zapytania są idempotentności: niezależnie od tego, ile razy zapytania system, stan systemu nie spowoduje zmiany można nawet korzystają z modelu danych różnych "odczytów" niż logiki transakcyjnej "zapisy" model domeny, mimo że porządkowania mikrousług używa tej samej bazy danych.</span><span class="sxs-lookup"><span data-stu-id="2198e-107">The essence of those patterns, and the important point here, is that queries are idempotent: no matter how many times you query a system, the state of that system will not change You could even use a different “reads” data model than the transactional logic “writes” domain model, although the ordering microservices is using the same database.</span></span> <span data-ttu-id="2198e-108">Dlatego jest uproszczone podejście CQRS.</span><span class="sxs-lookup"><span data-stu-id="2198e-108">Hence this is a simplified CQRS approach.</span></span>

<span data-ttu-id="2198e-109">Z drugiej strony polecenia, które wyzwolić transakcji i aktualizacji danych, Zmień stan w systemie.</span><span class="sxs-lookup"><span data-stu-id="2198e-109">On the other hand, commands, which trigger transactions and data updates, change state in the system.</span></span> <span data-ttu-id="2198e-110">Za pomocą polecenia, musisz należy zachować ostrożność podczas dotyczących złożoności i kiedykolwiek zmiana reguł biznesowych.</span><span class="sxs-lookup"><span data-stu-id="2198e-110">With commands, you need to be careful when dealing with complexity and ever-changing business rules.</span></span> <span data-ttu-id="2198e-111">Jest to, gdy chcesz zastosować DDD technik w celu lepszego modelowanego systemu.</span><span class="sxs-lookup"><span data-stu-id="2198e-111">This is the where you want to apply DDD techniques to have a better modeled system.</span></span>

<span data-ttu-id="2198e-112">Nie można zastosować powszechnie wzorce DDD przedstawionych w tym przewodniku.</span><span class="sxs-lookup"><span data-stu-id="2198e-112">The DDD patterns presented in this guide should not be applied universally.</span></span> <span data-ttu-id="2198e-113">Oni wprowadzić ograniczenia dotyczące projektu.</span><span class="sxs-lookup"><span data-stu-id="2198e-113">They introduce constraints on your design.</span></span> <span data-ttu-id="2198e-114">Ograniczenia te zapewniają korzyści, takich jak wyższej jakości wraz z upływem czasu, szczególnie w przypadku poleceń i innego kodu, który modyfikuje stan systemu.</span><span class="sxs-lookup"><span data-stu-id="2198e-114">Those constraints provide benefits such as higher quality over time, especially in commands and other code that modifies system state.</span></span> <span data-ttu-id="2198e-115">Jednak te ograniczenia zwiększenia złożoności z mniej korzyści za odczytywanie i wykonywanie zapytania na danych.</span><span class="sxs-lookup"><span data-stu-id="2198e-115">However, those constraints add complexity with fewer benefits for reading and querying data.</span></span>

<span data-ttu-id="2198e-116">Jeden taki wzorzec jest wzorcu agregacji więcej omówione w kolejnych sekcjach.</span><span class="sxs-lookup"><span data-stu-id="2198e-116">One such pattern is the Aggregate pattern, which we examine more in later sections.</span></span> <span data-ttu-id="2198e-117">Krótko mówiąc we wzorcu agregacji, są traktowane wiele obiektów domeny jako pojedyncza jednostka wyniku ich relacje w domenie.</span><span class="sxs-lookup"><span data-stu-id="2198e-117">Briefly, in the Aggregate pattern, you treat many domain objects as a single unit as a result of their relationship in the domain.</span></span> <span data-ttu-id="2198e-118">Nie może być zawsze uzyskać korzyści z tego wzorca w zapytaniach; może zwiększyć złożoność logiki kwerendy.</span><span class="sxs-lookup"><span data-stu-id="2198e-118">You might not always gain advantages from this pattern in queries; it can increase the complexity of query logic.</span></span> <span data-ttu-id="2198e-119">Dla zapytań tylko do odczytu nie otrzymasz zalet traktowanie wielu obiektów jako pojedynczy agregacji.</span><span class="sxs-lookup"><span data-stu-id="2198e-119">For read-only queries, you do not get the advantages of treating multiple objects as a single Aggregate.</span></span> <span data-ttu-id="2198e-120">Tylko Pobierz złożoności.</span><span class="sxs-lookup"><span data-stu-id="2198e-120">You only get the complexity.</span></span>

<span data-ttu-id="2198e-121">Jak pokazano na rysunku 9-2, w tym przewodniku sugeruje przy użyciu wzorców DDD tylko w obszarze transakcyjnej/aktualizacji z mikrousługi (jak wyzwalane przez polecenia).</span><span class="sxs-lookup"><span data-stu-id="2198e-121">As shown in Figure 9-2, this guide suggests using DDD patterns only in the transactional/updates area of your microservice (that is, as triggered by commands).</span></span> <span data-ttu-id="2198e-122">Zapytania można wykonać prostsze i musi być oddzielona od po podejście CQRS poleceń.</span><span class="sxs-lookup"><span data-stu-id="2198e-122">Queries can follow a simpler approach and should be separated from commands, following a CQRS approach.</span></span>

<span data-ttu-id="2198e-123">Do wykonania na stronie"zapytania", można wybrać wiele metod z Twojej pełnej wersji ORM, takich jak EF Core, AutoMapper projekcje, procedur składowanych, widoków, zmaterializowanych widoków lub micro ORM.</span><span class="sxs-lookup"><span data-stu-id="2198e-123">For implementing the “queries side”, you can choose between many approaches, from your full-blown ORM like EF Core, AutoMapper projections, stored procedures, views, materialized views or a micro ORM.</span></span>

<span data-ttu-id="2198e-124">W tym przewodniku, jak i w eShopOnContainers (w szczególności porządkowania mikrousługi) wybraliśmy do zaimplementowania prostych zapytań przy użyciu micro ORM, takie jak [Dapper](https://github.com/StackExchange/dapper-dot-net).</span><span class="sxs-lookup"><span data-stu-id="2198e-124">In this guide and in eShopOnContainers (specifically the ordering microservice) we chose to implement straight queries using a micro ORM like [Dapper](https://github.com/StackExchange/dapper-dot-net).</span></span> <span data-ttu-id="2198e-125">Dzięki temu można zaimplementować wszelkie zapytania oparte na instrukcji SQL, aby uzyskać najlepszą wydajność dzięki użyciu światła framework bez nadmiernego obciążenia.</span><span class="sxs-lookup"><span data-stu-id="2198e-125">This lets you implement any query based on SQL statements to get the best performance, thanks to a light framework with very little overhead.</span></span>

<span data-ttu-id="2198e-126">Należy zauważyć, że gdy posłuż się tą metodą, aktualizacje do modelu, które mają wpływ na sposób utrwalone jednostki bazy danych SQL również osobne aktualizacje kwerendy SQL używane przez Dapper lub wszelkie inne oddzielne podejścia (z systemem innym niż EF) do wykonywania zapytania.</span><span class="sxs-lookup"><span data-stu-id="2198e-126">Note that when you use this approach, any updates to your model that impact how entities are persisted to a SQL database also need separate updates to SQL queries used by Dapper or any other separate (non-EF) approaches to querying.</span></span>

## <a name="cqrs-and-ddd-patterns-are-not-top-level-architectures"></a><span data-ttu-id="2198e-127">Wzorce CQRS i DDD nie są architektury najwyższego poziomu</span><span class="sxs-lookup"><span data-stu-id="2198e-127">CQRS and DDD patterns are not top-level architectures</span></span>

<span data-ttu-id="2198e-128">Pamiętać, że CQRS i większość wzorców DDD (na przykład warstwy DDD lub model domeny z wartości zagregowanych) czy nie architektury style, ale tylko architektura wzorce.</span><span class="sxs-lookup"><span data-stu-id="2198e-128">It important to understand that CQRS and most DDD patterns (like DDD layers or a domain model with aggregates) are not architectural styles, but only architecture patterns.</span></span> <span data-ttu-id="2198e-129">Mikrousług, SOA i architektura sterowane zdarzeniami (EDA) to przykłady architektury stylów.</span><span class="sxs-lookup"><span data-stu-id="2198e-129">Microservices, SOA, and event-driven architecture (EDA) are examples of architectural styles.</span></span> <span data-ttu-id="2198e-130">Opisują one systemu z wielu składników, takich jak wiele mikrousług.</span><span class="sxs-lookup"><span data-stu-id="2198e-130">They describe a system of many components, such as many microservices.</span></span> <span data-ttu-id="2198e-131">Wzorce CQRS i DDD opisano coś w jednym systemie lub składnik; w tym przypadku coś wewnątrz mikrousługi.</span><span class="sxs-lookup"><span data-stu-id="2198e-131">CQRS and DDD patterns describe something inside a single system or component; in this case, something inside a microservice.</span></span>

<span data-ttu-id="2198e-132">Ograniczone kontekstów (usług łączności biznesowej) będzie stosować różnych wzorców.</span><span class="sxs-lookup"><span data-stu-id="2198e-132">Different Bounded Contexts (BCs) will employ different patterns.</span></span> <span data-ttu-id="2198e-133">Mają one różne obowiązki i która prowadzi do różnych rozwiązań.</span><span class="sxs-lookup"><span data-stu-id="2198e-133">They have different responsibilities, and that leads to different solutions.</span></span> <span data-ttu-id="2198e-134">Warto akcentowania który wymuszania tego samego wzorca, który wszędzie prowadzi do awarii.</span><span class="sxs-lookup"><span data-stu-id="2198e-134">It is worth emphasizing that forcing the same pattern everywhere leads to failure.</span></span> <span data-ttu-id="2198e-135">Nie używaj wzorce CQRS i DDD wszędzie.</span><span class="sxs-lookup"><span data-stu-id="2198e-135">Do not use CQRS and DDD patterns everywhere.</span></span> <span data-ttu-id="2198e-136">Wiele podsystemów, usług łączności biznesowej lub mikrousług są prostsze i można ją wdrożyć łatwiej przy użyciu usługi simple CRUD lub w inny sposób.</span><span class="sxs-lookup"><span data-stu-id="2198e-136">Many subsystems, BCs, or microservices are simpler and can be implemented more easily using simple CRUD services or using another approach.</span></span>

<span data-ttu-id="2198e-137">Istnieje tylko jedna aplikacja — architektura: Architektura aplikacji systemu lub na trasie projektowania (na przykład architektura mikrousług).</span><span class="sxs-lookup"><span data-stu-id="2198e-137">There is only one application architecture: the architecture of the system or end-to-end application you are designing (for example, the microservices architecture).</span></span> <span data-ttu-id="2198e-138">Jednak projekt każdego ograniczone kontekstu lub mikrousługi tej aplikacji odzwierciedla własne wady i zalety i decyzje dotyczące projektu wewnętrznej na poziomie wzorce architektury.</span><span class="sxs-lookup"><span data-stu-id="2198e-138">However, the design of each Bounded Context or microservice within that application reflects its own tradeoffs and internal design decisions at an architecture patterns level.</span></span> <span data-ttu-id="2198e-139">Nie należy zastosować te same architektury wzory CQRS lub DDD wszędzie.</span><span class="sxs-lookup"><span data-stu-id="2198e-139">Do not try to apply the same architectural patterns like CQRS or DDD everywhere.</span></span>

####  <a name="additional-resources"></a><span data-ttu-id="2198e-140">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2198e-140">Additional resources</span></span>

-   <span data-ttu-id="2198e-141">**Pole Fowler. CQRS**
    [*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)</span><span class="sxs-lookup"><span data-stu-id="2198e-141">**Martin Fowler. CQRS**
[*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)</span></span>

-   <span data-ttu-id="2198e-142">**Małych Gregowi. CQS vs. CQRS**
    [*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)</span><span class="sxs-lookup"><span data-stu-id="2198e-142">**Greg Young. CQS vs. CQRS**
[*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)</span></span>

-   <span data-ttu-id="2198e-143">**Małych Gregowi. Dokumenty CQRS**
    [*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)</span><span class="sxs-lookup"><span data-stu-id="2198e-143">**Greg Young. CQRS Documents**
[*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)</span></span>

-   <span data-ttu-id="2198e-144">**Małych Gregowi. CQRS, zadań, na podstawie UI i źródłem zdarzenia**
    [*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)</span><span class="sxs-lookup"><span data-stu-id="2198e-144">**Greg Young. CQRS, Task Based UIs and Event Sourcing**
[*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)</span></span>

-   <span data-ttu-id="2198e-145">**Udi Dahan. Zawiera wyjaśnienie CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span><span class="sxs-lookup"><span data-stu-id="2198e-145">**Udi Dahan. Clarified CQRS**
[*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span></span>

-   <span data-ttu-id="2198e-146">**CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span><span class="sxs-lookup"><span data-stu-id="2198e-146">**CQRS**
[*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span></span>

-   <span data-ttu-id="2198e-147">**Zdarzenie Sourcing (ES)**
    [*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)</span><span class="sxs-lookup"><span data-stu-id="2198e-147">**Event-Sourcing (ES)**
[*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="2198e-148">[Poprzednie] (apply-simplified-microservice-cqrs-ddd-patterns.md) [dalej] (cqrs mikrousługi reads.md)</span><span class="sxs-lookup"><span data-stu-id="2198e-148">[Previous] (apply-simplified-microservice-cqrs-ddd-patterns.md) [Next] (cqrs-microservice-reads.md)</span></span>