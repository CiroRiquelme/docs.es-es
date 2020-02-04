---
title: Novedades de F# 4,6- F# guía
description: Obtenga información general sobre las nuevas características disponibles en F# 4,6.
ms.date: 11/27/2019
ms.openlocfilehash: 620c1edd8ea212fee306a02d5844b6b322808251
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980397"
---
# <a name="whats-new-in-f-46"></a><span data-ttu-id="6cf31-103">Novedades de F# 4,6</span><span class="sxs-lookup"><span data-stu-id="6cf31-103">What's new in F# 4.6</span></span>

<span data-ttu-id="6cf31-104">F#4,6 agrega varias mejoras en el F# lenguaje.</span><span class="sxs-lookup"><span data-stu-id="6cf31-104">F# 4.6 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="6cf31-105">Primeros pasos</span><span class="sxs-lookup"><span data-stu-id="6cf31-105">Get started</span></span>

<span data-ttu-id="6cf31-106">F#4,6 está disponible en todas las distribuciones de .NET Core y las herramientas de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6cf31-106">F# 4.6 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="6cf31-107">Comience a usar para obtener más información. [ F# ](../get-started/index.md)</span><span class="sxs-lookup"><span data-stu-id="6cf31-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="anonymous-records"></a><span data-ttu-id="6cf31-108">Registros anónimos</span><span class="sxs-lookup"><span data-stu-id="6cf31-108">Anonymous records</span></span>

<span data-ttu-id="6cf31-109">[Los registros anónimos](../language-reference/anonymous-records.md) son un nuevo F# tipo de tipo F# introducido en 4,6.</span><span class="sxs-lookup"><span data-stu-id="6cf31-109">[Anonymous records](../language-reference/anonymous-records.md) are a new kind of F# type introduced in F# 4.6.</span></span> <span data-ttu-id="6cf31-110">Son agregados simples de valores con nombre que no es necesario declarar antes de su uso.</span><span class="sxs-lookup"><span data-stu-id="6cf31-110">They are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="6cf31-111">Puede declararlos como Structs o tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="6cf31-111">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="6cf31-112">Son tipos de referencia de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6cf31-112">They're reference types by default.</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

<span data-ttu-id="6cf31-113">También se pueden declarar como Structs para cuando desee agrupar tipos de valor y funcionen en escenarios con distinción de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="6cf31-113">They can also be declared as structs for when you want to group value types and are operating in performance-sensitive scenarios:</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    struct {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

<span data-ttu-id="6cf31-114">Son bastante eficaces y se pueden usar en numerosos escenarios.</span><span class="sxs-lookup"><span data-stu-id="6cf31-114">They're quite powerful and can be used in numerous scenarios.</span></span> <span data-ttu-id="6cf31-115">Obtenga más información en [registros anónimos](../language-reference/anonymous-records.md).</span><span class="sxs-lookup"><span data-stu-id="6cf31-115">Learn more at [Anonymous records](../language-reference/anonymous-records.md).</span></span>

## <a name="valueoption-functions"></a><span data-ttu-id="6cf31-116">Funciones de ValueOption</span><span class="sxs-lookup"><span data-stu-id="6cf31-116">ValueOption functions</span></span>

<span data-ttu-id="6cf31-117">El tipo ValueOption agregado en F# 4,5 ahora tiene "paridad de función enlazada a módulo" con el tipo de opción.</span><span class="sxs-lookup"><span data-stu-id="6cf31-117">The ValueOption type added in F# 4.5 now has "module-bound function parity" with the Option type.</span></span> <span data-ttu-id="6cf31-118">Algunos de los ejemplos más usados son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6cf31-118">Some of the more commonly-used examples are as follows:</span></span>

```fsharp
// Multiply a value option by 2 if it has  value
let xOpt = ValueSome 99
let result = xOpt |> ValueOption.map (fun v -> v * 2)

// Reverse a string if it exists
let strOpt = ValueSome "Mirror image"
let reverse (str: string) =
    match str with
    | null
    | "" -> ValueNone
    | s ->
        str.ToCharArray()
        |> Array.rev
        |> string
        |> ValueSome

let reversedString = strOpt |> ValueOption.bind reverse
```

<span data-ttu-id="6cf31-119">Esto permite usar ValueOption como opción en escenarios en los que tener un tipo de valor mejora el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="6cf31-119">This allows for ValueOption to be used just like Option in scenarios where having a value type improves performance.</span></span>
