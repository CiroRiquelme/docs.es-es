---
title: Usar la varianza para los delegados genéricos Func y Action (C#)
ms.date: 07/20/2015
ms.assetid: 1826774f-2b7a-470f-b110-17cfdd6abdae
ms.openlocfilehash: 17f55d594ad4364fd29c8f6e41bd6ad2445b0986
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169797"
---
# <a name="using-variance-for-func-and-action-generic-delegates-c"></a><span data-ttu-id="5ff81-102">Usar la varianza para los delegados genéricos Func y Action (C#)</span><span class="sxs-lookup"><span data-stu-id="5ff81-102">Using Variance for Func and Action Generic Delegates (C#)</span></span>
<span data-ttu-id="5ff81-103">En estos ejemplos se muestra cómo usar la covarianza y la contravarianza en los delegados genéricos `Func` y `Action` para habilitar la reutilización de métodos y proporcionar más flexibilidad en el código.</span><span class="sxs-lookup"><span data-stu-id="5ff81-103">These examples demonstrate how to use covariance and contravariance in the `Func` and `Action` generic delegates to enable reuse of methods and provide more flexibility in your code.</span></span>  
  
 <span data-ttu-id="5ff81-104">Para obtener más información sobre la covarianza y la contravarianza, vea [Varianza en delegados (C#)](./variance-in-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="5ff81-104">For more information about covariance and contravariance, see [Variance in Delegates (C#)](./variance-in-delegates.md).</span></span>  
  
## <a name="using-delegates-with-covariant-type-parameters"></a><span data-ttu-id="5ff81-105">Usar delegados con parámetros de tipo covariante</span><span class="sxs-lookup"><span data-stu-id="5ff81-105">Using Delegates with Covariant Type Parameters</span></span>  
 <span data-ttu-id="5ff81-106">En el ejemplo siguiente se muestran las ventajas de la compatibilidad con la covarianza en los delegados `Func` genéricos.</span><span class="sxs-lookup"><span data-stu-id="5ff81-106">The following example illustrates the benefits of covariance support in the generic `Func` delegates.</span></span> <span data-ttu-id="5ff81-107">El método `FindByTitle` toma un parámetro del tipo `String` y devuelve un objeto del tipo `Employee`.</span><span class="sxs-lookup"><span data-stu-id="5ff81-107">The `FindByTitle` method takes a parameter of the `String` type and returns an object of the `Employee` type.</span></span> <span data-ttu-id="5ff81-108">Pero este método se puede asignar al delegado `Func<String, Person>` porque `Employee` hereda `Person`.</span><span class="sxs-lookup"><span data-stu-id="5ff81-108">However, you can assign this method to the `Func<String, Person>` delegate because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static Employee FindByTitle(String title)  
    {  
        // This is a stub for a method that returns  
        // an employee that has the specified title.  
        return new Employee();  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Func<String, Employee> findEmployee = FindByTitle;  
  
        // The delegate expects a method to return Person,  
        // but you can assign it a method that returns Employee.  
        Func<String, Person> findPerson = FindByTitle;  
  
        // You can also assign a delegate
        // that returns a more derived type
        // to a delegate that returns a less derived type.  
        findPerson = findEmployee;  
  
    }  
}  
```  
  
## <a name="using-delegates-with-contravariant-type-parameters"></a><span data-ttu-id="5ff81-109">Usar delegados con parámetros de tipo contravariante</span><span class="sxs-lookup"><span data-stu-id="5ff81-109">Using Delegates with Contravariant Type Parameters</span></span>  
 <span data-ttu-id="5ff81-110">En el ejemplo siguiente se muestran las ventajas de la compatibilidad con la contravarianza en los delegados `Action` genéricos.</span><span class="sxs-lookup"><span data-stu-id="5ff81-110">The following example illustrates the benefits of contravariance support in the generic `Action` delegates.</span></span> <span data-ttu-id="5ff81-111">El método `AddToContacts` toma un parámetro del tipo `Person`.</span><span class="sxs-lookup"><span data-stu-id="5ff81-111">The `AddToContacts` method takes a parameter of the `Person` type.</span></span> <span data-ttu-id="5ff81-112">Pero este método se puede asignar al delegado `Action<Employee>` porque `Employee` hereda `Person`.</span><span class="sxs-lookup"><span data-stu-id="5ff81-112">However, you can assign this method to the `Action<Employee>` delegate because `Employee` inherits `Person`.</span></span>  
  
```csharp  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static void AddToContacts(Person person)  
    {  
        // This method adds a Person object  
        // to a contact list.  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Action<Person> addPersonToContacts = AddToContacts;  
  
        // The Action delegate expects
        // a method that has an Employee parameter,  
        // but you can assign it a method that has a Person parameter  
        // because Employee derives from Person.  
        Action<Employee> addEmployeeToContacts = AddToContacts;  
  
        // You can also assign a delegate
        // that accepts a less derived parameter to a delegate
        // that accepts a more derived parameter.  
        addEmployeeToContacts = addPersonToContacts;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ff81-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ff81-113">See also</span></span>

- [<span data-ttu-id="5ff81-114">Covarianza y contravarianza (C#)</span><span class="sxs-lookup"><span data-stu-id="5ff81-114">Covariance and Contravariance (C#)</span></span>](./index.md)
- [<span data-ttu-id="5ff81-115">Genéricos</span><span class="sxs-lookup"><span data-stu-id="5ff81-115">Generics</span></span>](../../../../standard/generics/index.md)
