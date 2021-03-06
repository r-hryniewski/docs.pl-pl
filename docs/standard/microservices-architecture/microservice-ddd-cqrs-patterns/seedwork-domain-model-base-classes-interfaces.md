---
title: Seedwork (klasy bazowe wielokrotnego użytku i interfejsy dla modelu domeny)
description: Architektura Mikrousług .NET konteneryzowanych aplikacji .NET | Seedwork (klasy bazowe wielokrotnego użytku i interfejsy dla modelu domeny)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.openlocfilehash: 7a38d90caab2232c17d8d58ca0c57d5bb56b3ce9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2018
ms.locfileid: "50198401"
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a>Seedwork (klasy bazowe wielokrotnego użytku i interfejsy dla modelu domeny)

Folder rozwiązania zawiera *SeedWork* folderu. *SeedWork* folder zawiera niestandardowe klasy bazowej, która służy jako podstawa dla domen, jednostek i obiektów wartości. Użyj tych klas bazowych, więc nie trzeba nadmiarowy kod w klasie obiektów w każdej domenie. Folder dla tych typów klasy jest nazywany *SeedWork* i nie mielibyśmy mieć czegoś podobnego *Framework*. Jest on nazywany *SeedWork* ponieważ folder zawiera tylko mały podzbiór klasy wielokrotnego użytku, które naprawdę nie należy traktować platformę. *Seedwork* termin wprowadzone przez [Michael Feathers](https://www.artima.com/forums/flat.jsp?forum=106&thread=8826) i spopularyzowany przez [Martina Fowlera](https://martinfowler.com/bliki/Seedwork.html) , ale można też nazwać tego folderu wspólnego, SharedKernel, lub podobne.

Rysunek 9 – 12 zawiera klasy, które tworzą seedwork modelu domeny w mikrousługę szeregowania. Ma ona kilka niestandardowych klas podstawowych, takich jak jednostki, ValueObject i wyliczenia, a także kilka interfejsów. Te interfejsy (IRepository i IUnitOfWork) informuje warstwy infrastruktury o jakie musi zostać wdrożone. Te interfejsy są również używane przez wstrzykiwanie zależności od warstwy aplikacji.

![](./media/image13.PNG)

**Rysunek 9 – 12**. Przykładowy zestaw klas bazowych "seedwork" model domeny i interfejsy

Jest to typ, kopiowanie i wklejanie ponowne używanie wielu deweloperów na udziale między projektami, a nie formalny strukturę. Może mieć seedworks w dowolnej warstwy lub biblioteki. Jednak zestaw klas i interfejsy pobiera wystarczająco duża, można utworzyć bibliotekę pojedynczą klasę.

## <a name="the-custom-entity-base-class"></a>Niestandardowe klasy podstawowej jednostki

Poniższy kod jest przykładem klasy podstawowej jednostki, gdy umieścisz kod, który może być taki sam sposób używany przez wszystkie jednostki domeny, takich jak identyfikator jednostki [Operatory równości](/cpp/cpp/equality-operators-equal-equal-and-exclpt-equal), listy zdarzeń domeny na jednostkę, np.

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE (1.1 and later)
public abstract class Entity
{
    int? _requestedHashCode;
    int _Id;    
    private List<INotification> _domainEvents;
    public virtual int Id 
    {
        get
        {
            return _Id;
        }
        protected set
        {
            _Id = value;
        }
    }

    public List<INotification> DomainEvents => _domainEvents;        
    public void AddDomainEvent(INotification eventItem)
    {
        _domainEvents = _domainEvents ?? new List<INotification>();
        _domainEvents.Add(eventItem);
    }
    public void RemoveDomainEvent(INotification eventItem)
    {
        if (_domainEvents is null) return;
        _domainEvents.Remove(eventItem);
    }

    public bool IsTransient()
    {
        return this.Id == default(Int32);
    }

    public override bool Equals(object obj)
    {
        if (obj == null || !(obj is Entity))
            return false;
        if (Object.ReferenceEquals(this, obj))
            return true;
        if (this.GetType() != obj.GetType())
            return false;
        Entity item = (Entity)obj;
        if (item.IsTransient() || this.IsTransient())
            return false;
        else
            return item.Id == this.Id;
    }

    public override int GetHashCode()
    {
        if (!IsTransient())
        {
            if (!_requestedHashCode.HasValue)
                _requestedHashCode = this.Id.GetHashCode() ^ 31;
            // XOR for random distribution. See:
            // https://blogs.msdn.microsoft.com/ericlippert/2011/02/28/guidelines-and-rules-for-gethashcode/
            return _requestedHashCode.Value;
        }
        else
            return base.GetHashCode();
    }
    public static bool operator ==(Entity left, Entity right)
    {
        if (Object.Equals(left, null))
            return (Object.Equals(right, null));
        else
            return left.Equals(right);
    }
    public static bool operator !=(Entity left, Entity right)
    {
        return !(left == right);
    }
}
```

Poprzedni kod, korzystając z listy zdarzeń domeny na jednostkę zostaną wyjaśnione w kolejnych sekcjach, w przypadku skupienia się na zdarzeń domeny. 

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a>Kontrakty repozytorium (interfejsy) w warstwie modelu domeny

Kontrakty repozytorium są po prostu interfejsy platformy .NET, które wyrażania wymagań kontraktu repozytoriów ma być używany dla każdej agregacji. 

Repozytoria, z kod programem EF Core lub innymi zależności infrastruktury i kodu (Linq, SQL itp.), nie może być realizowana w ramach modelu domeny; repozytoriów tylko powinny implementować interfejsy, które należy zdefiniować. 

Wzorzec związane z tym rozwiązaniem (wprowadzenie do interfejsów repozytorium w warstwie modelu domeny) jest wzorcem rozdzielonych interfejsu. Jako [wyjaśniono](https://www.martinfowler.com/eaaCatalog/separatedInterface.html) Martina fowlera "w użyciu interfejsu oddzielone, aby zdefiniować interfejs w jednym pakietu, ale jej wdrożenia w innej. W ten sposób klient, który wymaga zależności do interfejsu może być całkowicie nieświadome implementacji."

Następującego wzorca rozdzielonych interfejs umożliwia ma zależności od wymagań zdefiniowanych w modelu domeny, ale nie bezpośredniej zależności do infrastruktury/trwałości warstwy aplikacji (w tym przypadku projekt internetowego interfejsu API dla mikrousług) warstwy. Ponadto można użyć wstrzykiwanie zależności do izolowania w celu wykonania, która jest zaimplementowana w infrastrukturze / warstwy trwałości przy użyciu repozytoriów.

Na przykład w poniższym przykładzie, za pomocą interfejsu IOrderRepository zdefiniowano jakie operacje OrderRepository klasy należy zaimplementować w warstwie infrastruktury. W bieżącej implementacji aplikacji kod musi jedynie do dodania lub zaktualizowania zamówienia w bazie danych, ponieważ zapytania są dzielone zgodnie z uproszczone podejście CQRS.

```csharp
// Defined at IOrderRepository.cs
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
        
    void Update(Order order);

    Task<Order> GetAsync(int orderId);
}

// Defined at IRepository.cs (Part of the Domain Seedwork)
public interface IRepository<T> where T : IAggregateRoot
{
    IUnitOfWork UnitOfWork { get; }
}
```

## <a name="additional-resources"></a>Dodatkowe zasoby

-   **Martina Fowlera. Interfejs rozdzielonych.**
    [*https://www.martinfowler.com/eaaCatalog/separatedInterface.html*](https://www.martinfowler.com/eaaCatalog/separatedInterface.html)


>[!div class="step-by-step"]
[Poprzednie](net-core-microservice-domain-model.md)
[dalej](implement-value-objects.md)
