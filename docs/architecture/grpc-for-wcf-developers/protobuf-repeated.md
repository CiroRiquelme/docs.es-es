---
title: 'Campos repetidos para listas y matrices: gRPC para desarrolladores de WCF'
description: Comprenda cómo protobuf controla las colecciones y cómo se relacionan con las colecciones de .NET.
ms.date: 09/09/2019
ms.openlocfilehash: 16f2b5a54b032f32c8fcb9d572d5284fe589cb01
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542964"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="0dde4-103">Campos repetidos para listas y matrices</span><span class="sxs-lookup"><span data-stu-id="0dde4-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="0dde4-104">Las listas se especifican en el búfer de protocolo (protobuf) mediante la palabra clave de prefijo `repeated`.</span><span class="sxs-lookup"><span data-stu-id="0dde4-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="0dde4-105">En el ejemplo siguiente se muestra cómo crear una lista:</span><span class="sxs-lookup"><span data-stu-id="0dde4-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="0dde4-106">En el código generado, `repeated` campos se representan mediante el tipo genérico `Google.Protobuf.Collections.RepeatedField<T>` en lugar de cualquiera de los tipos de colección .NET integrados.</span><span class="sxs-lookup"><span data-stu-id="0dde4-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span> 

<span data-ttu-id="0dde4-107">El tipo de `RepeatedField<T>` incluye el código necesario para serializar y deserializar la lista en el formato de conexión binaria.</span><span class="sxs-lookup"><span data-stu-id="0dde4-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="0dde4-108">Implementa todas las interfaces de colección estándar de .NET, como <xref:System.Collections.Generic.IList%601> y <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="0dde4-108">It implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="0dde4-109">Por lo tanto, puede usar consultas LINQ o convertirlos en una matriz o una lista fácilmente.</span><span class="sxs-lookup"><span data-stu-id="0dde4-109">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0dde4-110">[Anterior](protobuf-nested-types.md)
>[Siguiente](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="0dde4-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
