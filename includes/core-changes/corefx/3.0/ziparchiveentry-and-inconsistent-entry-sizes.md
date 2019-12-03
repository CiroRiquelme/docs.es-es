---
ms.openlocfilehash: 9520f8c6b6671917f5694bc602293a00e2dab82d
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568244"
---
### <a name="ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes"></a><span data-ttu-id="5debb-101">ZipArchiveEntry ya no controla los archivos con tamaños de entrada incoherentes</span><span class="sxs-lookup"><span data-stu-id="5debb-101">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>

<span data-ttu-id="5debb-102">Los archivos zip muestran tanto el tamaño comprimido como el tamaño no comprimido en el directorio central y en el encabezado local.</span><span class="sxs-lookup"><span data-stu-id="5debb-102">Zip archives list both compressed size and uncompressed size in the central directory and local header.</span></span>  <span data-ttu-id="5debb-103">Los propios datos de entrada también indican su tamaño.</span><span class="sxs-lookup"><span data-stu-id="5debb-103">The entry data itself also indicates its size.</span></span>  <span data-ttu-id="5debb-104">En .NET Core 2.2 y versiones anteriores, nunca se comprobó la coherencia de estos valores.</span><span class="sxs-lookup"><span data-stu-id="5debb-104">In .NET Core 2.2 and earlier versions, these values were never checked for consistency.</span></span> <span data-ttu-id="5debb-105">A partir de .NET Core 3.0, ahora son.</span><span class="sxs-lookup"><span data-stu-id="5debb-105">Starting with .NET Core 3.0, they now are.</span></span>

#### <a name="change-description"></a><span data-ttu-id="5debb-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="5debb-106">Change description</span></span>

<span data-ttu-id="5debb-107">En .NET Core 2.2 y versiones anteriores, <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> funciona correctamente aunque el encabezado local no concuerde con el encabezado central del archivo zip.</span><span class="sxs-lookup"><span data-stu-id="5debb-107">In .NET Core 2.2 and earlier versions, <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> succeeds even if the local header disagrees with the central header of the zip file.</span></span> <span data-ttu-id="5debb-108">Los datos se descomprimen hasta que se alcanza el final del flujo comprimido, aunque su longitud supere el tamaño de archivo sin comprimir que se muestra en el directorio central/encabezado local.</span><span class="sxs-lookup"><span data-stu-id="5debb-108">Data is decompressed until the end of the compressed stream is reached, even if its length exceeds the uncompressed file size listed in the central directory/local header.</span></span>

<span data-ttu-id="5debb-109">A partir de .NET Core 3.0, el método <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> comprueba que el encabezado local y el encabezado central coinciden en el tamaño comprimido y no comprimido de una entrada.</span><span class="sxs-lookup"><span data-stu-id="5debb-109">Starting with .NET Core 3.0, the <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> method checks that local header and central header agree on compressed and uncompressed sizes of an entry.</span></span>  <span data-ttu-id="5debb-110">Si no coinciden, el método produce una <xref:System.IO.InvalidDataException> si el encabezado local del archivo o el tamaño de la lista de descriptores de datos que no están en desacuerdo con el directorio central del archivo zip.</span><span class="sxs-lookup"><span data-stu-id="5debb-110">If they do not, the method throws an <xref:System.IO.InvalidDataException> if the archive's local header and/or data descriptor list sizes that disagree with the central directory of the zip file.</span></span> <span data-ttu-id="5debb-111">Al leer una entrada, los datos descomprimidos se truncan hasta el tamaño de archivo sin comprimir que se muestra en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="5debb-111">When reading an entry, decompressed data is truncated to the uncompressed file size listed in the header.</span></span>

<span data-ttu-id="5debb-112">Este cambio se realizó para asegurarse de que un <xref:System.IO.Compression.ZipArchiveEntry>representa correctamente el tamaño de sus datos y que solo se lee esa cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="5debb-112">This change was made to ensure that a <xref:System.IO.Compression.ZipArchiveEntry> correctly represents the size of its data and that only that amount of data is read.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5debb-113">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="5debb-113">Version introduced</span></span>

<span data-ttu-id="5debb-114">3.0</span><span class="sxs-lookup"><span data-stu-id="5debb-114">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5debb-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="5debb-115">Recommended action</span></span>

<span data-ttu-id="5debb-116">Vuelva a empaquetar los archivos ZIP que presentan estos problemas.</span><span class="sxs-lookup"><span data-stu-id="5debb-116">Repackage any zip archive that exhibits these problems.</span></span>

#### <a name="category"></a><span data-ttu-id="5debb-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="5debb-117">Category</span></span>

<span data-ttu-id="5debb-118">CoreFX</span><span class="sxs-lookup"><span data-stu-id="5debb-118">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5debb-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5debb-119">Affected APIs</span></span>

- <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.ExtractToDirectory%2A?displayProperty=nameWithType>

<!--

### Affected APIs

`M:System.IO.Compression.ZipArchiveEntry.Open`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A`
`Overload:System.IO.Compression.ZipFile.ExtractToDirectory%2A`

-->