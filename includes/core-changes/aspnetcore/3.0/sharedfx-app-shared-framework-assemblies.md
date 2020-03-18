---
ms.openlocfilehash: a8146db1fb54d63d4716b879ce793f7d817cef59
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937291"
---
### <a name="shared-framework-assemblies-removed-from-microsoftaspnetcoreapp"></a><span data-ttu-id="74d47-101">Marco compartido: se han quitado los ensamblados de Microsoft.AspNetCore.App</span><span class="sxs-lookup"><span data-stu-id="74d47-101">Shared framework: Assemblies removed from Microsoft.AspNetCore.App</span></span>

<span data-ttu-id="74d47-102">A partir de ASP.NET Core 3.0, el marco compartido de ASP.NET Core (`Microsoft.AspNetCore.App`) solo contiene ensamblados propios totalmente desarrollados, admitidos y mantenidos por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74d47-102">Starting in ASP.NET Core 3.0, the ASP.NET Core shared framework (`Microsoft.AspNetCore.App`) only contains first-party assemblies that are fully developed, supported, and serviceable by Microsoft.</span></span>

#### <a name="change-description"></a><span data-ttu-id="74d47-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="74d47-103">Change description</span></span>

<span data-ttu-id="74d47-104">Considere el cambio como la redefinición de los límites de la "plataforma" ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="74d47-104">Think of the change as the redefining of boundaries for the ASP.NET Core "platform."</span></span> <span data-ttu-id="74d47-105">[A través de GitHub, cualquier usuario puede compilar el código fuente](https://github.com/dotnet/source-build) del marco compartido y seguirá ofreciendo a las aplicaciones las ventajas existentes de los marcos compartidos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="74d47-105">The shared framework will be [source-buildable by anybody via GitHub](https://github.com/dotnet/source-build) and will continue to offer the existing benefits of .NET Core shared frameworks to your apps.</span></span> <span data-ttu-id="74d47-106">Algunas ventajas son el tamaño de implementación más pequeño, la revisión centralizada y el tiempo de inicio más rápido.</span><span class="sxs-lookup"><span data-stu-id="74d47-106">Some benefits include smaller deployment size, centralized patching, and faster startup time.</span></span>

<span data-ttu-id="74d47-107">Como parte del cambio, en `Microsoft.AspNetCore.App` se han introducido algunos cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="74d47-107">As part of the change, some notable breaking changes are introduced in `Microsoft.AspNetCore.App`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="74d47-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="74d47-108">Version introduced</span></span>

<span data-ttu-id="74d47-109">3.0</span><span class="sxs-lookup"><span data-stu-id="74d47-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="74d47-110">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="74d47-110">Old behavior</span></span>

<span data-ttu-id="74d47-111">Los proyectos hacían referencia a `Microsoft.AspNetCore.App` mediante un elemento `<PackageReference>` en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="74d47-111">Projects referenced `Microsoft.AspNetCore.App` via a `<PackageReference>` element in the project file.</span></span>

<span data-ttu-id="74d47-112">Además, `Microsoft.AspNetCore.App` incluía los subcomponentes siguientes:</span><span class="sxs-lookup"><span data-stu-id="74d47-112">Additionally, `Microsoft.AspNetCore.App` contained the following subcomponents:</span></span>

- <span data-ttu-id="74d47-113">Json.NET (`Newtonsoft.Json`)</span><span class="sxs-lookup"><span data-stu-id="74d47-113">Json.NET (`Newtonsoft.Json`)</span></span>
- <span data-ttu-id="74d47-114">Entity Framework Core (ensamblados con el prefijo `Microsoft.EntityFrameworkCore.`)</span><span class="sxs-lookup"><span data-stu-id="74d47-114">Entity Framework Core (assemblies prefixed with `Microsoft.EntityFrameworkCore.`)</span></span>
- <span data-ttu-id="74d47-115">Roslyn (`Microsoft.CodeAnalysis`)</span><span class="sxs-lookup"><span data-stu-id="74d47-115">Roslyn (`Microsoft.CodeAnalysis`)</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="74d47-116">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="74d47-116">New behavior</span></span>

<span data-ttu-id="74d47-117">Una referencia a `Microsoft.AspNetCore.App` ya no requiere un elemento `<PackageReference>` en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="74d47-117">A reference to `Microsoft.AspNetCore.App` no longer requires a `<PackageReference>` element in the project file.</span></span> <span data-ttu-id="74d47-118">El SDK de .NET Core admite un nuevo elemento denominado `<FrameworkReference>`, que reemplaza el uso de `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="74d47-118">The .NET Core SDK supports a new element called `<FrameworkReference>`, which replaces the use of `<PackageReference>`.</span></span>

<span data-ttu-id="74d47-119">Para obtener más información, vea [dotnet/aspnetcore#3612](https://github.com/dotnet/aspnetcore/issues/3612).</span><span class="sxs-lookup"><span data-stu-id="74d47-119">For more information, see [dotnet/aspnetcore#3612](https://github.com/dotnet/aspnetcore/issues/3612).</span></span>

<span data-ttu-id="74d47-120">Entity Framework Core se distribuye como paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="74d47-120">Entity Framework Core ships as NuGet packages.</span></span> <span data-ttu-id="74d47-121">Este cambio alinea el modelo de envío con el resto de las bibliotecas de acceso a datos de .NET.</span><span class="sxs-lookup"><span data-stu-id="74d47-121">This change aligns the shipping model with all other data access libraries on .NET.</span></span> <span data-ttu-id="74d47-122">Proporciona a Entity Framework Core la ruta más sencilla para continuar con la innovación al tiempo que admite las distintas plataformas .NET.</span><span class="sxs-lookup"><span data-stu-id="74d47-122">It provides Entity Framework Core the simplest path to continue innovating while supporting the various .NET platforms.</span></span> <span data-ttu-id="74d47-123">La exclusión de Entity Framework Core del marco compartido no tiene ningún impacto en su estado como biblioteca desarrollada, admitida y mantenida por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74d47-123">The move of Entity Framework Core out of the shared framework has no impact on its status as a Microsoft-developed, supported, and serviceable library.</span></span> <span data-ttu-id="74d47-124">Continúa bajo la cobertura de la [directiva de compatibilidad de .NET Core](https://www.microsoft.com/net/platform/support-policy).</span><span class="sxs-lookup"><span data-stu-id="74d47-124">The [.NET Core support policy](https://www.microsoft.com/net/platform/support-policy) continues to cover it.</span></span>

<span data-ttu-id="74d47-125">Json.NET y Entity Framework Core siguen funcionando con ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="74d47-125">Json.NET and Entity Framework Core continue to work with ASP.NET Core.</span></span> <span data-ttu-id="74d47-126">Pero no se incluirán en el marco compartido.</span><span class="sxs-lookup"><span data-stu-id="74d47-126">They won't, however, be included in the shared framework.</span></span>

<span data-ttu-id="74d47-127">Para obtener más información, vea [El futuro de JSON en .NET Core 3.0](https://github.com/dotnet/announcements/issues/90).</span><span class="sxs-lookup"><span data-stu-id="74d47-127">For more information, see [The future of JSON in .NET Core 3.0](https://github.com/dotnet/announcements/issues/90).</span></span> <span data-ttu-id="74d47-128">Vea también [la lista completa de archivos binarios](https://github.com/dotnet/aspnetcore/issues/3755) que se han quitado del marco compartido.</span><span class="sxs-lookup"><span data-stu-id="74d47-128">Also see [the complete list of binaries](https://github.com/dotnet/aspnetcore/issues/3755) removed from the shared framework.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="74d47-129">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="74d47-129">Reason for change</span></span>

<span data-ttu-id="74d47-130">Este cambio simplifica el consumo de `Microsoft.AspNetCore.App` y reduce la duplicación entre paquetes NuGet y marcos compartidos.</span><span class="sxs-lookup"><span data-stu-id="74d47-130">This change simplifies the consumption of `Microsoft.AspNetCore.App` and reduces the duplication between NuGet packages and shared frameworks.</span></span>

<span data-ttu-id="74d47-131">Para obtener más información sobre la motivación de este cambio, vea [esta entrada de blog](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="74d47-131">For more information on the motivation for this change, see [this blog post](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="74d47-132">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="74d47-132">Recommended action</span></span>

<span data-ttu-id="74d47-133">No será necesario que los proyectos consuman ensamblados en `Microsoft.AspNetCore.App` como paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="74d47-133">It won't be necessary for projects to consume assemblies in `Microsoft.AspNetCore.App` as NuGet packages.</span></span> <span data-ttu-id="74d47-134">Para simplificar la selección como destino y el uso del marco compartido de ASP.NET Core, ya no se generan muchos paquetes NuGet enviados desde ASP.NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="74d47-134">To simplify the targeting and usage of the ASP.NET Core shared framework, many NuGet packages shipped since ASP.NET Core 1.0 are no longer produced.</span></span> <span data-ttu-id="74d47-135">Las API que proporcionan esos paquetes siguen estando disponibles para las aplicaciones mediante el uso de un elemento `<FrameworkReference>` para `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="74d47-135">The APIs those packages provide are still available to apps by using a `<FrameworkReference>` to `Microsoft.AspNetCore.App`.</span></span> <span data-ttu-id="74d47-136">Entre los ejemplos de API comunes se incluyen Kestrel, MVC y Razor.</span><span class="sxs-lookup"><span data-stu-id="74d47-136">Common API examples include Kestrel, MVC, and Razor.</span></span>

<span data-ttu-id="74d47-137">Este cambio no se aplica a todos los archivos binarios a los que se hace referencia a través de `Microsoft.AspNetCore.App` en ASP.NET Core 2.x.</span><span class="sxs-lookup"><span data-stu-id="74d47-137">This change doesn't apply to all binaries referenced via `Microsoft.AspNetCore.App` in ASP.NET Core 2.x.</span></span> <span data-ttu-id="74d47-138">Entre las excepciones destacables se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="74d47-138">Notable exceptions include:</span></span>

- <span data-ttu-id="74d47-139">Las bibliotecas de `Microsoft.Extensions` que todavía tienen .NET Standard como destino estarán disponibles como paquetes NuGet (vea https://github.com/dotnet/extensions) ).</span><span class="sxs-lookup"><span data-stu-id="74d47-139">`Microsoft.Extensions` libraries that continue to target .NET Standard will be available as NuGet packages (see https://github.com/dotnet/extensions).</span></span>
- <span data-ttu-id="74d47-140">API generadas por el equipo de ASP.NET Core que no forman parte de `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="74d47-140">APIs produced by the ASP.NET Core team that aren't part of `Microsoft.AspNetCore.App`.</span></span> <span data-ttu-id="74d47-141">Por ejemplo, los componentes siguientes están disponibles como paquetes NuGet:</span><span class="sxs-lookup"><span data-stu-id="74d47-141">For example, the following components are available as NuGet packages:</span></span>
  - <span data-ttu-id="74d47-142">Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="74d47-142">Entity Framework Core</span></span>
  - <span data-ttu-id="74d47-143">API que proporcionan integración de terceros</span><span class="sxs-lookup"><span data-stu-id="74d47-143">APIs that provide third-party integration</span></span>
  - <span data-ttu-id="74d47-144">Características experimentales</span><span class="sxs-lookup"><span data-stu-id="74d47-144">Experimental features</span></span>
  - <span data-ttu-id="74d47-145">API con dependencias que no han podido [cumplir los requisitos para ser incluidas en el marco compartido](https://github.com/dotnet/aspnetcore/blob/4e44e5bcbedd961cc0d4f6b846699c7c494f5597/docs/SharedFramework.md)</span><span class="sxs-lookup"><span data-stu-id="74d47-145">APIs with dependencies that couldn't [fulfill the requirements to be in the shared framework](https://github.com/dotnet/aspnetcore/blob/4e44e5bcbedd961cc0d4f6b846699c7c494f5597/docs/SharedFramework.md)</span></span>
- <span data-ttu-id="74d47-146">Extensiones para MVC que mantienen la compatibilidad con Json.NET.</span><span class="sxs-lookup"><span data-stu-id="74d47-146">Extensions to MVC that maintain support for Json.NET.</span></span> <span data-ttu-id="74d47-147">Se proporcionará una API como paquete NuGet para admitir el uso de Json.NET y MVC.</span><span class="sxs-lookup"><span data-stu-id="74d47-147">An API will be provided as a NuGet package to support using Json.NET and MVC.</span></span>
- <span data-ttu-id="74d47-148">El cliente de SignalR para .NET seguirá admitiendo .NET Standard y se enviará como un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="74d47-148">The SignalR .NET client will continue to support .NET Standard and ship as a NuGet package.</span></span> <span data-ttu-id="74d47-149">Está diseñado para usarse en muchos entornos de ejecución de .NET, como Xamarin y UWP.</span><span class="sxs-lookup"><span data-stu-id="74d47-149">It's intended for use on many .NET runtimes, such as Xamarin and UWP.</span></span>

<span data-ttu-id="74d47-150">Para obtener más información, vea [Detección de la generación de paquetes para ensamblados de marco compartido en 3.0](https://github.com/dotnet/aspnetcore/issues/3756).</span><span class="sxs-lookup"><span data-stu-id="74d47-150">For more information, see [Stop producing packages for shared framework assemblies in 3.0](https://github.com/dotnet/aspnetcore/issues/3756).</span></span> <span data-ttu-id="74d47-151">Para obtener información, vea [dotnet/aspnetcore#3757](https://github.com/dotnet/aspnetcore/issues/3757).</span><span class="sxs-lookup"><span data-stu-id="74d47-151">For discussion, see [dotnet/aspnetcore#3757](https://github.com/dotnet/aspnetcore/issues/3757).</span></span>

#### <a name="category"></a><span data-ttu-id="74d47-152">Categoría</span><span class="sxs-lookup"><span data-stu-id="74d47-152">Category</span></span>

<span data-ttu-id="74d47-153">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="74d47-153">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="74d47-154">API afectadas</span><span class="sxs-lookup"><span data-stu-id="74d47-154">Affected APIs</span></span>

- <xref:Microsoft.CodeAnalysis?displayProperty=nameWithType>
- <xref:Microsoft.EntityFrameworkCore?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.CodeAnalysis`
- `N:Microsoft.EntityFrameworkCore`

-->
