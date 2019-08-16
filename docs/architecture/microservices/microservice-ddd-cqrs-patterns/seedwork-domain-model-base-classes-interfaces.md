---
title: Seedwork (interfaces y clases base reutilizables para su modelo de dominio)
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Uso del concepto SeedWork como punto de partida para iniciar la implementación de un modelo de dominio orientado a DDD.
ms.date: 10/08/2018
ms.openlocfilehash: 298f79383e477df0cfeeaada5c4657a9274b3df3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68676312"
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a><span data-ttu-id="5ba6b-103">Seedwork (interfaces y clases base reutilizables para su modelo de dominio)</span><span class="sxs-lookup"><span data-stu-id="5ba6b-103">Seedwork (reusable base classes and interfaces for your domain model)</span></span>

<span data-ttu-id="5ba6b-104">La carpeta de soluciones contiene una carpeta *SeedWork*.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-104">The solution folder contains a *SeedWork* folder.</span></span> <span data-ttu-id="5ba6b-105">Esta carpeta contiene las clases base personalizadas que puede usar como base de los objetos de valor y las entidades de dominio.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-105">This folder contains custom base classes that you can use as a base for your domain entities and value objects.</span></span> <span data-ttu-id="5ba6b-106">Use estas clases base para no tener código redundante en la clase de objeto de cada dominio.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-106">Use these base classes so you do not have redundant code in each domain’s object class.</span></span> <span data-ttu-id="5ba6b-107">La carpeta para estos tipos de clases se denomina *SeedWork* y no nombres parecidos como *Marco*.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-107">The folder for these types of classes is called *SeedWork* and not something like *Framework*.</span></span> <span data-ttu-id="5ba6b-108">Se llama *SeedWork* porque la carpeta contiene solo un pequeño subconjunto de clases reutilizables que realmente no se puede considerar un marco.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-108">It's called *SeedWork* because the folder contains just a small subset of reusable classes which cannot really be considered a framework.</span></span> <span data-ttu-id="5ba6b-109">*Seedwork* es un término introducido por [Michael Feathers](https://www.artima.com/forums/flat.jsp?forum=106&thread=8826) y popularizado por [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html), pero esta carpeta también se puede denominar Common, SharedKernel o similar.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-109">*Seedwork* is a term introduced by [Michael Feathers](https://www.artima.com/forums/flat.jsp?forum=106&thread=8826) and popularized by [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) but you could also name that folder Common, SharedKernel, or similar.</span></span>

<span data-ttu-id="5ba6b-110">En la Figura 7-12 se muestran las clases que forman el seedwork del modelo de dominio en el microservicio de pedidos.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-110">Figure 7-12 shows the classes that form the seedwork of the domain model in the ordering microservice.</span></span> <span data-ttu-id="5ba6b-111">Tiene algunas clases base personalizadas, como Entity, ValueObject y Enumeration, además de algunas interfaces.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-111">It has a few custom base classes like Entity, ValueObject, and Enumeration, plus a few interfaces.</span></span> <span data-ttu-id="5ba6b-112">Estas interfaces (IRepository y IUnitOfWork) informan al nivel de infraestructura de lo que requiere implementación.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-112">These interfaces (IRepository and IUnitOfWork) inform the infrastructure layer about what needs to be implemented.</span></span> <span data-ttu-id="5ba6b-113">Estas interfaces también se usan mediante la inserción de dependencias del nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-113">Those interfaces are also used through Dependency Injection from the application layer.</span></span>

![Contenido detallado de la carpeta SeedWork, que contiene interfaces y clases base: Entity.cs, Enumeration.cs, IAggregateRoot.cs, IRepository.cs, IUnitOfWork.cs, y ValueObject.cs](./media/image13.PNG)

<span data-ttu-id="5ba6b-115">**Figura 7-12.**</span><span class="sxs-lookup"><span data-stu-id="5ba6b-115">**Figure 7-12**.</span></span> <span data-ttu-id="5ba6b-116">Un conjunto de muestra de interfaces y clases base "seedwork" del modelo de dominio</span><span class="sxs-lookup"><span data-stu-id="5ba6b-116">A sample set of domain model “seedwork" base classes and interfaces</span></span>

<span data-ttu-id="5ba6b-117">Este es el tipo de reutilización de copiar y pegar que muchos desarrolladores comparten entre proyectos, y no un marco formal.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-117">This is the type of copy and paste reuse that many developers share between projects, not a formal framework.</span></span> <span data-ttu-id="5ba6b-118">Puede tener seedworks en cualquier nivel o biblioteca.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-118">You can have seedworks in any layer or library.</span></span> <span data-ttu-id="5ba6b-119">Pero si el conjunto de clases e interfaces se hace lo suficientemente grande, puede crear una sola biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-119">However, if the set of classes and interfaces gets big enough, you might want to create a single class library.</span></span>

## <a name="the-custom-entity-base-class"></a><span data-ttu-id="5ba6b-120">La clase base de entidad personalizada</span><span class="sxs-lookup"><span data-stu-id="5ba6b-120">The custom Entity base class</span></span>

<span data-ttu-id="5ba6b-121">El código siguiente es un ejemplo de clase base Entity en la que puede colocar código que puede ser utilizado de la misma forma por cualquier entidad de dominio, como el id. de entidad, [operadores de igualdad](~/docs/csharp/language-reference/operators/equality-operators.md), una lista de eventos de dominio por entidad, etc.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-121">The following code is an example of an Entity base class where you can place code that can be used the same way by any domain entity, such as the entity ID, [equality operators](~/docs/csharp/language-reference/operators/equality-operators.md), a domain event list per entity, etc.</span></span>

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

<span data-ttu-id="5ba6b-122">Este código, en el que se utiliza una lista de eventos de dominio por entidad, se describirá en las secciones siguientes, al hablar de los eventos de dominio.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-122">The previous code using a domain event list per entity will be explained in the next sections when focusing on domain events.</span></span>

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a><span data-ttu-id="5ba6b-123">Contratos de repositorio (interfaces) en el nivel de modelo de dominio</span><span class="sxs-lookup"><span data-stu-id="5ba6b-123">Repository contracts (interfaces) in the domain model layer</span></span>

<span data-ttu-id="5ba6b-124">Los contratos de repositorio no son más que interfaces .NET que expresan los requisitos de contrato de los repositorios que se van a utilizar en cada agregado.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-124">Repository contracts are simply .NET interfaces that express the contract requirements of the repositories to be used for each aggregate.</span></span>

<span data-ttu-id="5ba6b-125">Los repositorios en sí, con el código básico de EF Core o cualquier otra dependencia de infraestructura y código (Linq, SQL, etc.), no se deben implementar en el modelo de dominio; los repositorios solo deben implementar las interfaces que defina en el modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-125">The repositories themselves, with EF Core code or any other infrastructure dependencies and code (Linq, SQL, etc.), must not be implemented within the domain model; the repositories should only implement the interfaces you define in the domain model.</span></span>

<span data-ttu-id="5ba6b-126">Otro patrón relacionado con esta práctica (que coloca interfaces de repositorio en el nivel de modelo de dominio) es el patrón de interfaz separada.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-126">A pattern related to this practice (placing the repository interfaces in the domain model layer) is the Separated Interface pattern.</span></span> <span data-ttu-id="5ba6b-127">Como [explica](https://www.martinfowler.com/eaaCatalog/separatedInterface.html) Martin Fowler, "utilice una interfaz separada para definir una interfaz en un paquete e implementarla en otro.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-127">As [explained](https://www.martinfowler.com/eaaCatalog/separatedInterface.html) by Martin Fowler, “Use Separated Interface to define an interface in one package but implement it in another.</span></span> <span data-ttu-id="5ba6b-128">De esta forma, un cliente que necesite la dependencia en la interfaz puede no tener en cuenta para nada la implementación".</span><span class="sxs-lookup"><span data-stu-id="5ba6b-128">This way a client that needs the dependency to the interface can be completely unaware of the implementation.”</span></span>

<span data-ttu-id="5ba6b-129">Seguir el patrón de interfaz separada permite que el nivel de aplicación (en este caso, el proyecto API web para el microservicio) tenga una dependencia en los requisitos definidos en el modelo de dominio, pero no una dependencia directa en el nivel de infraestructura/persistencia.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-129">Following the Separated Interface pattern enables the application layer (in this case, the Web API project for the microservice) to have a dependency on the requirements defined in the domain model, but not a direct dependency to the infrastructure/persistence layer.</span></span> <span data-ttu-id="5ba6b-130">Además, puede usar la inserción de dependencias para aislar la implementación, que se implementa en el nivel de infraestructura/persistencia utilizando repositorios.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-130">In addition, you can use Dependency Injection to isolate the implementation, which is implemented in the infrastructure/ persistence layer using repositories.</span></span>

<span data-ttu-id="5ba6b-131">Por ejemplo, el siguiente ejemplo con la interfaz de IOrderRepository define las operaciones que la clase OrderRepository tendrá que implementar en el nivel de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-131">For example, the following example with the IOrderRepository interface defines what operations the OrderRepository class will need to implement at the infrastructure layer.</span></span> <span data-ttu-id="5ba6b-132">En la implementación actual de la aplicación, el código solo necesita agregar o actualizar los pedidos en la base de datos, puesto que las consultas se dividen siguiendo el enfoque de CQRS simplificado.</span><span class="sxs-lookup"><span data-stu-id="5ba6b-132">In the current implementation of the application, the code just needs to add or update orders to the database, since queries are split following the simplified CQRS approach.</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="5ba6b-133">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5ba6b-133">Additional resources</span></span>

- <span data-ttu-id="5ba6b-134">**Martin Fowler. Separated Interface** (Interfaz independiente).</span><span class="sxs-lookup"><span data-stu-id="5ba6b-134">**Martin Fowler. Separated Interface.**</span></span> \
  <https://www.martinfowler.com/eaaCatalog/separatedInterface.html>

>[!div class="step-by-step"]
><span data-ttu-id="5ba6b-135">[Anterior](net-core-microservice-domain-model.md)
>[Siguiente](implement-value-objects.md)</span><span class="sxs-lookup"><span data-stu-id="5ba6b-135">[Previous](net-core-microservice-domain-model.md)
[Next](implement-value-objects.md)</span></span>