---
title: Procedimiento Instalar un ensamblado en la caché global de ensamblados
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
ms.openlocfilehash: 64878a795a7c5b790c8991064e32b82505685c0c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155568"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="0d5b9-102">Procedimiento Instalar un ensamblado en la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="0d5b9-102">How to: Install an assembly into the global assembly cache</span></span>

<span data-ttu-id="0d5b9-103">La caché global de ensamblados (GAC) almacena los ensamblados que comparten varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0d5b9-103">The global assembly cache (GAC) stores assemblies that several applications share.</span></span> <span data-ttu-id="0d5b9-104">Puede instalar un ensamblado en la [caché global de ensamblados](gac.md) con uno de los componentes siguientes:</span><span class="sxs-lookup"><span data-stu-id="0d5b9-104">Install an assembly into the [global assembly cache](gac.md) with one of the following components:</span></span>

- [<span data-ttu-id="0d5b9-105">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="0d5b9-105">Windows Installer</span></span>](#windows-installer)
- [<span data-ttu-id="0d5b9-106">Herramienta de la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="0d5b9-106">Global Assembly Cache tool</span></span>](#global-assembly-cache-tool)

> [!IMPORTANT]
> <span data-ttu-id="0d5b9-107">Solamente puede instalar ensamblados con nombre seguro en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="0d5b9-107">You can install only strong-named assemblies into the global assembly cache.</span></span> <span data-ttu-id="0d5b9-108">Para obtener información sobre cómo crear un ensamblado de este tipo, vea [Procedimientos para Firmar un ensamblado con un nombre seguro](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="0d5b9-108">For information about how to create a strong-named assembly, see [How to: Sign an assembly with a strong name](../../standard/assembly/sign-strong-name.md).</span></span>

## <a name="windows-installer"></a><span data-ttu-id="0d5b9-109">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="0d5b9-109">Windows Installer</span></span>

<span data-ttu-id="0d5b9-110">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), el motor de instalación de Windows, es la manera recomendada para agregar ensamblados a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="0d5b9-110">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), the Windows installation engine, is the recommended way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="0d5b9-111">Windows Installer proporciona el recuento de referencias de los ensamblados de la caché global de ensamblados, además de otras ventajas.</span><span class="sxs-lookup"><span data-stu-id="0d5b9-111">Windows Installer provides reference counting of assemblies in the global assembly cache and other benefits.</span></span> <span data-ttu-id="0d5b9-112">Para crear un paquete de instalación para Windows Installer, use la [extensión del conjunto de herramientas de WiX para Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).</span><span class="sxs-lookup"><span data-stu-id="0d5b9-112">To create an installer package for Windows Installer, use the [WiX toolset extension for Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).</span></span>

## <a name="global-assembly-cache-tool"></a><span data-ttu-id="0d5b9-113">Herramienta de la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="0d5b9-113">Global Assembly Cache tool</span></span>

<span data-ttu-id="0d5b9-114">Puede usar la [utilidad de la caché global de ensamblados (gacutil.exe) de .NET](../tools/gacutil-exe-gac-tool.md) para agregar ensamblados a la caché global de ensamblados y ver el contenido de esa caché.</span><span class="sxs-lookup"><span data-stu-id="0d5b9-114">You can use the [.NET Global Assembly Cache utility (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0d5b9-115">*Gacutil.exe* solo está pensada para fines de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="0d5b9-115">*Gacutil.exe* is for development purposes only.</span></span> <span data-ttu-id="0d5b9-116">No se usa para instalar ensamblados de producción en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="0d5b9-116">Don't use it to install production assemblies into the global assembly cache.</span></span>

<span data-ttu-id="0d5b9-117">La sintaxis para usar *gacutil.exe* para instalar un ensamblado en la GAC es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d5b9-117">The syntax for using *gacutil.exe* to install an assembly in the GAC is as follows:</span></span>

```cmd
gacutil -i <assembly name>
```

<span data-ttu-id="0d5b9-118">En este comando, *\<nombre del ensamblado>* es el nombre del ensamblado que se va a instalar en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="0d5b9-118">In this command, *\<assembly name>* is the name of the assembly to install in the global assembly cache.</span></span>

<span data-ttu-id="0d5b9-119">Si *gacutil.exe* no se encuentra en la ruta de acceso del sistema, use [Símbolo del sistema para desarrolladores de Visual Studio *\<versión>* ](../tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="0d5b9-119">If *gacutil.exe* isn't in your system path, use the [Developer command prompt for VS *\<version>*](../tools/developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="0d5b9-120">En el ejemplo siguiente se instala un ensamblado con el nombre de archivo *hello.dll* en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="0d5b9-120">The following example installs an assembly with the file name *hello.dll* into the global assembly cache.</span></span>

```cmd
gacutil -i hello.dll
```

> [!NOTE]
> <span data-ttu-id="0d5b9-121">En versiones anteriores de .NET Framework, la extensión *Shfusion.dll* del shell de Windows permitía instalar ensamblados si los arrastraba al Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="0d5b9-121">In earlier versions of the .NET Framework, the *Shfusion.dll* Windows shell extension let you install assemblies by dragging them to File Explorer.</span></span> <span data-ttu-id="0d5b9-122">A partir de .NET Framework 4, *Shfusion.dll* está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="0d5b9-122">Beginning with .NET Framework 4, *Shfusion.dll* is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d5b9-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d5b9-123">See also</span></span>

- [<span data-ttu-id="0d5b9-124">Trabajar con ensamblados y la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="0d5b9-124">Work with assemblies and the global assembly cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="0d5b9-125">Cómo: Quitar un ensamblado de la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="0d5b9-125">How to: Remove an assembly from the global assembly cache</span></span>](how-to-remove-an-assembly-from-the-gac.md)
- [<span data-ttu-id="0d5b9-126">Gacutil.exe (herramienta de la caché global de ensamblados)</span><span class="sxs-lookup"><span data-stu-id="0d5b9-126">Gacutil.exe (Global Assembly Cache tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
- [<span data-ttu-id="0d5b9-127">Cómo: Firmar un ensamblado con un nombre seguro</span><span class="sxs-lookup"><span data-stu-id="0d5b9-127">How to: Sign an assembly with a strong name</span></span>](../../standard/assembly/sign-strong-name.md)
