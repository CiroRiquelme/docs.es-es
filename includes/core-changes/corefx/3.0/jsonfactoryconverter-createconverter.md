---
ms.openlocfilehash: 3bce796191e0ebe6dbe4650457abe5a20c383f02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147567"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a><span data-ttu-id="ee2d2-101">Ha cambiado la firma de JsonFactoryConverter.CreateConverter</span><span class="sxs-lookup"><span data-stu-id="ee2d2-101">JsonFactoryConverter.CreateConverter signature changed</span></span>

<span data-ttu-id="ee2d2-102">Para facilitar la composición de las clases <xref:System.Text.Json.Serialization.JsonConverterFactory>, se ha hecho público el método <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> y se le ha dado un segundo argumento de tipo <xref:System.Text.Json.JsonSerializerOptions>.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-102">To facilitate the composition of <xref:System.Text.Json.Serialization.JsonConverterFactory> classes, the <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> method has been made public and given a second argument of type <xref:System.Text.Json.JsonSerializerOptions>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ee2d2-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="ee2d2-103">Change description</span></span>

<span data-ttu-id="ee2d2-104">La firma del método `CreateConverter` en .NET Core antes de la versión 3.0 (versión preliminar 8) era la siguiente:</span><span class="sxs-lookup"><span data-stu-id="ee2d2-104">The signature of the `CreateConverter` method in .NET Core prior to version 3.0 Preview 8 was:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

<span data-ttu-id="ee2d2-105">En .NET Core 3.0 (versión preliminar 8) y en versiones posteriores es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="ee2d2-105">In .NET Core 3.0 Preview 8 and later versions, it is:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

<span data-ttu-id="ee2d2-106">Antes de este cambio, era difícil crear convertidores de generadores sellados, ya que no había ninguna manera fácil de obtener la clase <xref:System.Text.Json.Serialization.JsonConverter%601>.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-106">Before this change, it was difficult to compose sealed factory converters, since there was no easy way to get the <xref:System.Text.Json.Serialization.JsonConverter%601> from it.</span></span> <span data-ttu-id="ee2d2-107">Hacer público el patrón de diseño Factory Method y pasar la clase <xref:System.Text.Json.JsonSerializerOptions> actual permiten una composición mucho más flexible.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-107">Making the factory method public and also passing the current <xref:System.Text.Json.JsonSerializerOptions> allow for much more flexible composition.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ee2d2-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ee2d2-108">Version introduced</span></span>

<span data-ttu-id="ee2d2-109">3.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="ee2d2-109">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ee2d2-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="ee2d2-110">Recommended action</span></span>

<span data-ttu-id="ee2d2-111">Es necesario actualizar y volver a compilar las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-111">Derived classes need to be updated and recompiled.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ee2d2-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ee2d2-112">Affected APIs</span></span>

- <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>

<!-- For tool use only

### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
