# [Mikrousługi .NET: architektura konteneryzowanych aplikacji .NET](index.md)
## [Wprowadzenie do kontenerów i platformy Docker](container-docker-introduction/index.md)
### [Co to jest Docker?](container-docker-introduction/docker-defined.md)
### [Terminologia platformy Docker](container-docker-introduction/docker-terminology.md)
### [Kontenery, obrazy i rejestry platformy Docker](container-docker-introduction/docker-containers-images-registries.md)
## [Wybieranie między programami .NET Core i .NET Framework na potrzeby tworzenia kontenerów Docker](net-core-net-framework-containers/index.md)
### [Wskazówki ogólne](net-core-net-framework-containers/general-guidance.md)
### [Kiedy należy wybrać oprogramowanie .NET Core dla kontenerów Docker](net-core-net-framework-containers/net-core-container-scenarios.md)
### [Kiedy należy wybrać oprogramowanie .NET Framework dla kontenerów Docker](net-core-net-framework-containers/net-framework-container-scenarios.md)
### [Tabela decyzji: korzystanie z programu .NET Framework z platformą Docker](net-core-net-framework-containers/container-framework-choice-factors.md)
### [Jakiego systemu operacyjnego należy używać docelowo z kontenerami .NET](net-core-net-framework-containers/net-container-os-targets.md)
### [Oficjalne obrazy Docker w programie .NET](net-core-net-framework-containers/official-net-docker-images.md)
## [Tworzenie aplikacji opartych na kontenerach i mikrousługach](architect-microservice-container-applications/index.md)
### [Umieszczanie aplikacji monolitycznych w kontenerze](architect-microservice-container-applications/containerize-monolithic-applications.md)
### [Stan i dane w aplikacjach platformy Docker](architect-microservice-container-applications/docker-application-state-data.md)
### [Architektura zorientowana na usługi](architect-microservice-container-applications/service-oriented-architecture.md)
### [Architektura mikrousług](architect-microservice-container-applications/microservices-architecture.md)
### [Suwerenność danych przypadająca na mikrousługę](architect-microservice-container-applications/data-sovereignty-per-microservice.md)
### [Architektura logiczna a architektura fizyczna](architect-microservice-container-applications/logical-versus-physical-architecture.md)
### [Problemy i rozwiązania dotyczące rozproszonego zarządzania danymi](architect-microservice-container-applications/distributed-data-management.md)
### [Identyfikowanie ograniczeń modelu domeny dla poszczególnych mikrousług](architect-microservice-container-applications/identify-microservice-domain-model-boundaries.md)
### [Bezpośrednia komunikacja klienta z mikrousługą a wzorzec bramy interfejsu API](architect-microservice-container-applications/direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md)
### [Komunikacja w ramach architektury mikrousługi](architect-microservice-container-applications/communication-in-microservice-architecture.md)
### [Asynchroniczna komunikacja oparta na komunikatach](architect-microservice-container-applications/asynchronous-message-based-communication.md)
### [Tworzenie, rozwijanie i przechowywanie wersji interfejsów API i kontaktów w mikrousługach](architect-microservice-container-applications/maintain-microservice-apis.md)
### [Adresowanie mikrousług i rejestr usług](architect-microservice-container-applications/microservices-addressability-service-registry.md)
### [Tworzenie złożonego interfejsu użytkownika opartego na mikrousługach, w tym kształt graficzny interfejsu użytkownika i układ generowany przez wiele mikrousług](architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md)
### [Odporność i wysoka dostępność w ramach mikrousług](architect-microservice-container-applications/resilient-high-availability-microservices.md)
### [Organizowanie aplikacji mikrousług i aplikacji z wieloma kontenerami w celu zapewnienia wysokiej skalowalności i dostępności](architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)
### [Korzystanie z usługi Azure Service Fabric](architect-microservice-container-applications/using-azure-service-fabric.md)
## [Proces programistyczny dotyczący aplikacji opartych na platformie Docker](docker-application-development-process/index.md)
### [Przepływ pracy tworzenia oprogramowania dla aplikacji platformy Docker](docker-application-development-process/docker-app-development-workflow.md)
## [Wdrażanie aplikacji internetowych .NET Core opartych na jednym kontenerze na hostach z systemem Linux lub Windows Nano Server](net-core-single-containers-linux-windows-server-hosts/index.md)
## [Migrowanie starszych aplikacji monolitycznych .NET Framework do kontenerów systemu Windows](containerize-net-framework-applications/index.md)
## [Projektowanie i tworzenie aplikacji .NET opartych na wielu kontenerach i mikrousługach](multi-container-microservice-net-applications/index.md)
### [Projektowanie aplikacji opartej na mikrousługach](multi-container-microservice-net-applications/microservice-application-design.md)
### [Tworzenie prostej mikrousługi CRUD na podstawie danych](multi-container-microservice-net-applications/data-driven-crud-microservice.md)
### [Definiowanie aplikacji z wieloma kontenerami za pomocą pliku docker-compose.yml](multi-container-microservice-net-applications/multi-container-applications-docker-compose.md)
### [Korzystanie z serwera bazy danych uruchomionego jako kontener](multi-container-microservice-net-applications/database-server-container.md)
### [Implementowanie komunikacji opartej na zdarzeniach między mikrousługami (zdarzenia integracji)](multi-container-microservice-net-applications/integration-event-based-microservice-communications.md)
### [Implementowanie magistrali zdarzeń z oprogramowaniem RabbitMQ na potrzeby środowisk testowych lub deweloperskich](multi-container-microservice-net-applications/rabbitmq-event-bus-development-test-environment.md)
### [Subskrybowanie zdarzeń](multi-container-microservice-net-applications/subscribe-events.md)
### [Testowanie aplikacji internetowych i usług ASP.NET Core](multi-container-microservice-net-applications/test-aspnet-core-services-web-apps.md)
### [Implementowanie zadań w tle w mikrousługach za pomocą interfejsu IHostedService](multi-container-microservice-net-applications/background-tasks-with-ihostedservice.md)
### [Wdrażanie bram interfejsu API za pomocą rozwiązania Ocelot](multi-container-microservice-net-applications/implement-api-gateways-with-ocelot.md)
## [Rozwiązywanie problemów ze złożonościami biznesowymi w mikrousłudze z wzorcami DDD i CQRS](microservice-ddd-cqrs-patterns/index.md)
### [Stosowanie uproszczonych wzorców CQRS i DDD w mikrousługach](microservice-ddd-cqrs-patterns/apply-simplified-microservice-cqrs-ddd-patterns.md)
### [Stosowanie zasad CQRS i CQS w mikrousługach DDD w ramach aplikacji eShopOnContainers](microservice-ddd-cqrs-patterns/eshoponcontainers-cqrs-ddd-microservice.md)
### [Implementowanie odczytów i zapytań w mikrousłudze CQRS](microservice-ddd-cqrs-patterns/cqrs-microservice-reads.md)
### [Projektowanie mikrousługi zorientowanej na wzorzec DDD](microservice-ddd-cqrs-patterns/ddd-oriented-microservice.md)
### [Projektowanie modelu domeny mikrousługi](microservice-ddd-cqrs-patterns/microservice-domain-model.md)
### [Implementowanie modelu domeny mikrousługi za pomocą platformy .NET Core](microservice-ddd-cqrs-patterns/net-core-microservice-domain-model.md)
### [Seedwork (klasy bazowe wielokrotnego użytku i interfejsy na potrzeby modelu domeny)](microservice-ddd-cqrs-patterns/seedwork-domain-model-base-classes-interfaces.md)
### [Implementowanie obiektów wartości](microservice-ddd-cqrs-patterns/implement-value-objects.md)
### [Używanie klas wyliczeń zamiast typów wyliczeń](microservice-ddd-cqrs-patterns/enumeration-classes-over-enum-types.md)
### [Projektowanie reguł weryfikacji w warstwie modelu domeny](microservice-ddd-cqrs-patterns/domain-model-layer-validations.md)
### [Weryfikacja po stronie klienta (weryfikacja w warstwach prezentacji)](microservice-ddd-cqrs-patterns/client-side-validation.md)
### [Zdarzenia w domenie: projektowanie i implementacja](microservice-ddd-cqrs-patterns/domain-events-design-implementation.md)
### [Projektowanie warstwy trwałości infrastruktury](microservice-ddd-cqrs-patterns/infrastructure-persistence-layer-design.md)
### [Implementowanie warstwy trwałości infrastruktury za pomocą programu Entity Framework Core](microservice-ddd-cqrs-patterns/infrastructure-persistence-layer-implemenation-entity-framework-core.md)
### [Korzystanie z baz danych NoSQL jako infrastruktury trwałości](microservice-ddd-cqrs-patterns/nosql-database-persistence-infrastructure.md)
### [Projektowanie warstwy aplikacji mikrousług i internetowego interfejsu API](microservice-ddd-cqrs-patterns/microservice-application-layer-web-api-design.md)
### [Implementowanie warstwy aplikacji mikrousług za pomocą internetowego interfejsu API](microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
## [Implementowanie aplikacji odpornych na błędy](implement-resilient-applications/index.md)
### [Obsługa częściowych niepowodzeń](implement-resilient-applications/handle-partial-failure.md)
### [Strategie dotyczące obsługi częściowych niepowodzeń](implement-resilient-applications/partial-failure-strategies.md)
### [Implementowanie ponownych prób wykonywanych przy użyciu wycofywania wykładniczego](implement-resilient-applications/implement-retries-exponential-backoff.md)
### [Implementowanie odpornych na błędy połączeń SQL w programie Entity Framework Core](implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md)
### [Eksplorowanie ponownych prób niestandardowego wywołania HTTP wykonywanych przy użyciu wycofywania wykładniczego](implement-resilient-applications/explore-custom-http-call-retries-exponential-backoff.md)
### [Używanie elementu HttpClientFactory do implementowania odpornych na błędy żądań HTTP](implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md)
### [Implementowanie ponownych prób wywołania HTTP wykonywanych przy użyciu wycofywania wykładniczego usługi Polly](implement-resilient-applications/implement-http-call-retries-exponential-backoff-polly.md)
### [Implementowanie wzorca wyłącznika](implement-resilient-applications/implement-circuit-breaker-pattern.md)
### [Monitorowanie kondycji](implement-resilient-applications/monitor-app-health.md)
## [Zabezpieczanie mikrousług .NET i aplikacji internetowych](secure-net-microservices-web-applications/index.md)
### [Informacje o autoryzacji w mikrousługach .NET i aplikacjach internetowych](secure-net-microservices-web-applications/authorization-net-microservices-web-applications.md)
### [Bezpieczne przechowywanie kluczy tajnych aplikacji podczas jej tworzenia](secure-net-microservices-web-applications/developer-app-secrets-storage.md)
### [Korzystanie z usługi Azure Key Vault w celu ochrony kluczy tajnych w czasie tworzenia](secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)
## [Kluczowe kwestie do zapamiętania](key-takeaways.md)
