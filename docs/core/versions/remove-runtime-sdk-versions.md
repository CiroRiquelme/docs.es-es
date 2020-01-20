---
title: Eliminación de .NET Core Runtime y el SDK
description: En este artículo se describe cómo determinar las versiones de .NET Core Runtime y el SDK instaladas y, luego, cómo quitarlas en Windows, Mac, and Linux.
ms.date: 12/17/2019
author: billwagner
ms.author: wiwagn
ms.custom: updateeachrelease
ms.openlocfilehash: 8f8dbf7a8730712dc546643a6ef86425a3e19794
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713986"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a><span data-ttu-id="82056-103">Cómo quitar los componentes .NET Core Runtime y SDK</span><span class="sxs-lookup"><span data-stu-id="82056-103">How to remove the .NET Core Runtime and SDK</span></span>

<span data-ttu-id="82056-104">Con el tiempo, a medida que instale versiones actualizadas del runtime y el SDK de .NET Core, es posible que quiera quitar del equipo versiones obsoletas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="82056-104">Over time, as you install updated versions of the .NET Core runtime and SDK, you may want to remove outdated versions of .NET Core from your machine.</span></span> <span data-ttu-id="82056-105">Al quitar versiones anteriores de runtime puede cambiar el runtime elegido para ejecutar aplicaciones de marco compartidas, tal como se detalla en el artículo sobre [selección de la versión de .NET Core](selection.md).</span><span class="sxs-lookup"><span data-stu-id="82056-105">Removing older versions of the runtime may change the runtime chosen to run shared framework applications, as detailed in the article on [.NET Core version selection](selection.md).</span></span>

## <a name="should-i-remove-a-version"></a><span data-ttu-id="82056-106">¿Puedo quitar una versión?</span><span class="sxs-lookup"><span data-stu-id="82056-106">Should I remove a version?</span></span>

<span data-ttu-id="82056-107">Los comportamientos de la [selección de la versión de .NET Core](selection.md) y la compatibilidad de runtime de .NET Core en diferentes actualizaciones permite quitar de forma segura las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="82056-107">The [.NET Core version selection](selection.md) behaviors and the runtime compatibility of .NET Core across updates enables safe removal of previous versions.</span></span> <span data-ttu-id="82056-108">Las actualizaciones de .NET Core Runtime son compatibles con una "banda" de versión principal, como 1.x y 2.x.</span><span class="sxs-lookup"><span data-stu-id="82056-108">.NET Core runtime updates are compatible within a major version 'band' such as 1.x and 2.x.</span></span> <span data-ttu-id="82056-109">Además, normalmente las versiones más recientes del SDK de .NET Core mantienen la capacidad de crear aplicaciones destinadas a versiones anteriores del tiempo de ejecución de una forma compatible.</span><span class="sxs-lookup"><span data-stu-id="82056-109">Additionally, newer releases of the .NET Core SDK generally maintain the ability to build applications that target previous versions of the runtime in a compatible manner.</span></span>

<span data-ttu-id="82056-110">En general, solo se necesita el SDK más reciente y la última versión de revisión de los runtimes necesarios para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="82056-110">In general, you only need the latest SDK and latest patch version of the runtimes required for your application.</span></span> <span data-ttu-id="82056-111">Los casos en los que se conservan versiones anteriores del SDK o de entorno de ejecución incluyen el mantenimiento de aplicaciones basadas en **project.json**.</span><span class="sxs-lookup"><span data-stu-id="82056-111">Instances where keeping older SDK or Runtime versions include maintaining **project.json**-based applications.</span></span> <span data-ttu-id="82056-112">A menos que la aplicación tenga motivos concretos para utilizar SDK o runtimes anteriores, puede quitar las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="82056-112">Unless your application has specific reasons for earlier SDKs or runtimes, you may safely remove older versions.</span></span>

## <a name="determine-what-is-installed"></a><span data-ttu-id="82056-113">Determinación de lo instalado</span><span class="sxs-lookup"><span data-stu-id="82056-113">Determine what is installed</span></span>

<span data-ttu-id="82056-114">A partir de .NET Core 2.1, la CLI de .NET tiene opciones que puede utilizar para enumerar las versiones del SDK y de runtime que están instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="82056-114">Starting with .NET Core 2.1, the .NET CLI has options you can use to list the versions of the SDK and runtime that are installed on your machine.</span></span>  <span data-ttu-id="82056-115">Use [`dotnet --list-sdks`](../tools/dotnet.md#options) para ver la lista de los SDK instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="82056-115">Use [`dotnet --list-sdks`](../tools/dotnet.md#options) to see the list of SDKs installed on your machine.</span></span> <span data-ttu-id="82056-116">Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) para ver la lista de los runtimes instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="82056-116">Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) to see the list of runtimes installed on your machine.</span></span> <span data-ttu-id="82056-117">En el texto siguiente se muestra el resultado típico para Windows, macOS o Linux:</span><span class="sxs-lookup"><span data-stu-id="82056-117">The following text shows typical output for Windows, macOS, or Linux:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[<span data-ttu-id="82056-118">Windows</span><span class="sxs-lookup"><span data-stu-id="82056-118">Windows</span></span>](#tab/windows)

```console
C:\> dotnet --list-sdks
2.1.200-preview-007474 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007480 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007509 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007570 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007576 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007587 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007589 [C:\Program Files\dotnet\sdk]
2.1.200 [C:\Program Files\dotnet\sdk]
2.1.201 [C:\Program Files\dotnet\sdk]
2.1.202 [C:\Program Files\dotnet\sdk]
2.1.300-preview2-008533 [C:\Program Files\dotnet\sdk]
2.1.300 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009063 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009088 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009171 [C:\Program Files\dotnet\sdk]

C:\> dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.0.6 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.7 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.9 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
```

# <a name="linuxtablinux"></a>[<span data-ttu-id="82056-119">Linux</span><span class="sxs-lookup"><span data-stu-id="82056-119">Linux</span></span>](#tab/linux)

```console
$ dotnet --list-sdks
1.0.1 [/usr/share/dotnet/sdk]
1.0.4 [/usr/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/share/dotnet/sdk]
2.0.0 [/usr/share/dotnet/sdk]
2.1.4 [/usr/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/share/dotnet/sdk]
2.1.300 [/usr/share/dotnet/sdk]
2.1.301 [/usr/share/dotnet/sdk]

$ dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
```

# <a name="macostabmacos"></a>[<span data-ttu-id="82056-120">macOS</span><span class="sxs-lookup"><span data-stu-id="82056-120">macOS</span></span>](#tab/macos)

```console
$ dotnet --list-sdks
1.0.1 [/usr/local/share/dotnet/sdk]
1.0.4 [/usr/local/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/local/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/local/share/dotnet/sdk]
2.0.0 [/usr/local/share/dotnet/sdk]
2.1.4 [/usr/local/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/local/share/dotnet/sdk]
2.1.300 [/usr/local/share/dotnet/sdk]
2.1.301 [/usr/local/share/dotnet/sdk]

$ dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

---

## <a name="uninstalling-net-core"></a><span data-ttu-id="82056-121">Desinstalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="82056-121">Uninstalling .NET Core</span></span>

# <a name="windowstabwindows"></a>[<span data-ttu-id="82056-122">Windows</span><span class="sxs-lookup"><span data-stu-id="82056-122">Windows</span></span>](#tab/windows)

<span data-ttu-id="82056-123">.NET Core usa el cuadro de diálogo **Agregar o quitar programas** de Windows para quitar las versiones del runtime de .NET Core y del SDK.</span><span class="sxs-lookup"><span data-stu-id="82056-123">.NET Core uses the Windows **Add/Remove Programs** dialog to remove versions of the .NET Core runtime and SDK.</span></span> <span data-ttu-id="82056-124">En la siguiente ilustración se muestra el cuadro de diálogo **Agregar o quitar programas** con varias versiones del runtime y SDK de .NET instaladas.</span><span class="sxs-lookup"><span data-stu-id="82056-124">The following figure shows the **Add/Remove Programs** dialog with several versions of the .NET runtime and SDK installed.</span></span>

![Agregar o quitar programas para quitar .NET Core](./media/remove-runtime-sdk-versions/programs-and-features.png)

<span data-ttu-id="82056-126">Seleccione las versiones que quiera quitar de su equipo y haga clic en **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="82056-126">Select any versions you want to remove from your machine and click **Uninstall**.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="82056-127">Linux</span><span class="sxs-lookup"><span data-stu-id="82056-127">Linux</span></span>](#tab/linux)

<span data-ttu-id="82056-128">Para desinstalar .NET Core (SDK o runtime) en Linux tiene más opciones.</span><span class="sxs-lookup"><span data-stu-id="82056-128">There are more options to uninstall .NET Core (either SDK or runtime) on Linux.</span></span> <span data-ttu-id="82056-129">La mejor forma de desinstalar .NET Core es repetir la misma acción que se usó para instalarlo.</span><span class="sxs-lookup"><span data-stu-id="82056-129">The best way for you to uninstall .NET Core is to mirror the action you used to install .NET Core.</span></span> <span data-ttu-id="82056-130">Los detalles específicos dependerán de la distribución que elija y del método de instalación.</span><span class="sxs-lookup"><span data-stu-id="82056-130">The specifics depend on your chosen distribution and the installation method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82056-131">Para obtener información sobre las instalaciones y desinstalaciones de .NET Core en Red Hat, consulte la [Guía de introducción a Red Hat](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel).</span><span class="sxs-lookup"><span data-stu-id="82056-131">For Red Hat installations, consult the [Red Hat Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) for information on installing and uninstalling .NET Core.</span></span>

<span data-ttu-id="82056-132">A partir de .NET Core 2.1, no hace falta desinstalar el SDK de .NET Core al actualizarlo mediante un administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="82056-132">Starting with .NET Core 2.1, there's no need to uninstall the .NET Core SDK when upgrading it using a package manager.</span></span> <span data-ttu-id="82056-133">Los comandos `update` o `refresh` del administrador de paquetes quitarán automáticamente la versión anterior tras la instalación correcta de una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="82056-133">The package manager `update` or `refresh` commands will automatically remove the older version upon the successful installation of a newer version.</span></span>

<span data-ttu-id="82056-134">Si ha instalado .NET Core con un administrador de paquetes, use ese mismo administrador de paquetes para desinstalar el SDK o el runtime de .NET.</span><span class="sxs-lookup"><span data-stu-id="82056-134">If you installed .NET Core using a package manager, you use that same package manager to uninstall .NET SDK or runtime.</span></span> <span data-ttu-id="82056-135">Las instalaciones de .NET Core admiten los administradores de paquetes más populares.</span><span class="sxs-lookup"><span data-stu-id="82056-135">.NET Core installations support most popular package managers.</span></span> <span data-ttu-id="82056-136">Consulte la documentación del administrador de paquetes de su distribución para conocer la sintaxis exacta en su entorno:</span><span class="sxs-lookup"><span data-stu-id="82056-136">Consult the documentation for your distribution's package manager for the precise syntax on your environment:</span></span>

- <span data-ttu-id="82056-137">[apt-get(8)](https://linux.die.net/man/8/apt-get) se utiliza en sistemas basados en Debian, incluido Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="82056-137">[apt-get(8)](https://linux.die.net/man/8/apt-get) is used by Debian based systems, including Ubuntu.</span></span>
- <span data-ttu-id="82056-138">[yum(8)](https://linux.die.net/man/8/yum) se utiliza en Fedora, CentOS y Oracle Linux.</span><span class="sxs-lookup"><span data-stu-id="82056-138">[yum(8)](https://linux.die.net/man/8/yum) is used on Fedora, CentOS, and Oracle Linux.</span></span>
- <span data-ttu-id="82056-139">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) se utiliza en openSUSE y SUSE Linux Enterprise Server (SLES).</span><span class="sxs-lookup"><span data-stu-id="82056-139">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) is used on openSUSE and SUSE Linux Enterprise System (SLES).</span></span>
- <span data-ttu-id="82056-140">[DNF(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) se utiliza en Fedora.</span><span class="sxs-lookup"><span data-stu-id="82056-140">[dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) is used on Fedora.</span></span>

<span data-ttu-id="82056-141">En casi todos los casos, el comando para quitar un paquete es `remove`.</span><span class="sxs-lookup"><span data-stu-id="82056-141">In almost all cases, the command to remove a package is `remove`.</span></span>

<span data-ttu-id="82056-142">El nombre del paquete para la instalación del SDK de .NET Core para la mayoría de administradores de paquetes es `dotnet-sdk`, seguido por el número de versión.</span><span class="sxs-lookup"><span data-stu-id="82056-142">The package name for the .NET Core SDK installation for most package managers is `dotnet-sdk`, followed by the version number.</span></span> <span data-ttu-id="82056-143">A partir de la versión 2.1.300 del SDK de .NET Core y de la versión `2.1` del runtime, solo se requieren el primer y el segundo número de versión: por ejemplo, puede hacer referencia a la versión 2.1.300 del SDK de .NET Core como el paquete `dotnet-sdk-2.1`.</span><span class="sxs-lookup"><span data-stu-id="82056-143">Starting with the version 2.1.300 of the .NET Core SDK and version `2.1` of the runtime, only the major and minor version numbers are necessary: for example, the .NET Core SDK version 2.1.300 can be referenced as the package `dotnet-sdk-2.1`.</span></span> <span data-ttu-id="82056-144">Para las versiones anteriores se requiere la cadena de versión completa: por ejemplo, se requeriría `dotnet-sdk-2.1.200` para la versión 2.1.200 del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="82056-144">Prior versions require the entire version string: for example, `dotnet-sdk-2.1.200` would be required for version 2.1.200 of the .NET Core SDK.</span></span>

<span data-ttu-id="82056-145">En los equipos en los que solo se ha instalado el runtime, y no el SDK, el nombre del paquete es `dotnet-runtime-<version>` para .NET Core Runtime y `aspnetcore-runtime-<version>` para la pila de runtime entera.</span><span class="sxs-lookup"><span data-stu-id="82056-145">For machines that have installed only the runtime, and not the SDK, the package name is `dotnet-runtime-<version>` for the .NET Core runtime, and `aspnetcore-runtime-<version>` for the entire runtime stack.</span></span>

<span data-ttu-id="82056-146">Al instalar las versiones de .NET Core anteriores a 2.0 no se desinstaló la aplicación host al desinstalar el SDK mediante el administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="82056-146">.NET Core installations earlier than 2.0 didn't uninstall the host application when the SDK was uninstalled using the package manager.</span></span> <span data-ttu-id="82056-147">Al usar `apt-get`, el comando es:</span><span class="sxs-lookup"><span data-stu-id="82056-147">Using `apt-get`, the command is:</span></span>

```bash
apt-get remove dotnet-host
```

<span data-ttu-id="82056-148">Tenga en cuenta que no hay ninguna versión conectada a `dotnet-host`.</span><span class="sxs-lookup"><span data-stu-id="82056-148">Note that there's no version attached to `dotnet-host`.</span></span>

<span data-ttu-id="82056-149">Si ha realizado la instalación mediante un paquete tarball, debe quitar .NET Core mediante el método manual.</span><span class="sxs-lookup"><span data-stu-id="82056-149">If you installed using a tarball, you must remove .NET Core using the manual method.</span></span>

<span data-ttu-id="82056-150">Debe quitar los SDK y runtimes por separado, quitando el directorio que contiene dicha versión.</span><span class="sxs-lookup"><span data-stu-id="82056-150">You remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="82056-151">Por ejemplo, para quitar el runtime y el SDK 1.0.1, tendrá que usar los siguientes comandos de bash:</span><span class="sxs-lookup"><span data-stu-id="82056-151">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="82056-152">Los directorios primarios para el SDK y runtime se enumeran en el resultado de los comandos `dotnet --list-sdks` y `dotnet --list-runtimes`, como se muestra en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="82056-152">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="82056-153">macOS</span><span class="sxs-lookup"><span data-stu-id="82056-153">macOS</span></span>](#tab/macos)

<span data-ttu-id="82056-154">En Mac, debe quitar los SDK y runtimes por separado, quitando el directorio que contiene dicha versión.</span><span class="sxs-lookup"><span data-stu-id="82056-154">On Mac, you must remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="82056-155">Por ejemplo, para quitar el runtime y el SDK 1.0.1, tendrá que usar los siguientes comandos de bash:</span><span class="sxs-lookup"><span data-stu-id="82056-155">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/local/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="82056-156">Los directorios primarios para el SDK y runtime se enumeran en el resultado de los comandos `dotnet --list-sdks` y `dotnet --list-runtimes`, como se muestra en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="82056-156">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

---

## <a name="net-core-uninstall-tool"></a><span data-ttu-id="82056-157">Herramienta de desinstalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="82056-157">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="82056-158">La [herramienta de desinstalación de .NET Core](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) permite quitar los SDK y los entornos de ejecución de .NET Core de un sistema.</span><span class="sxs-lookup"><span data-stu-id="82056-158">The [.NET Core Uninstall Tool](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="82056-159">Hay una colección de opciones disponible para especificar las versiones que se deben desinstalar.</span><span class="sxs-lookup"><span data-stu-id="82056-159">A collection of options is available to specify which versions should be uninstalled.</span></span>

## <a name="visual-studio-dependency-on-net-core-sdk-versions"></a><span data-ttu-id="82056-160">Dependencia de Visual Studio en versiones de SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="82056-160">Visual Studio dependency on .NET Core SDK versions</span></span>

<span data-ttu-id="82056-161">Antes de la versión 16.3 de Visual Studio 2019, los instaladores de Visual Studio llamaron al instalador de SDK de .NET Core independiente.</span><span class="sxs-lookup"><span data-stu-id="82056-161">Before Visual Studio 2019 version 16.3, Visual Studio installers called the standalone .NET Core SDK installer.</span></span> <span data-ttu-id="82056-162">Como resultado, las versiones del SDK aparecen en el cuadro de diálogo **Agregar o quitar programas** de Windows.</span><span class="sxs-lookup"><span data-stu-id="82056-162">As a result, the SDK versions appear in the Windows **Add/Remove Programs** dialog.</span></span> <span data-ttu-id="82056-163">La eliminación de los SDK de .NET Core que se instalaron con Visual Studio mediante el instalador independiente podría interrumpir Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="82056-163">Removing .NET Core SDKs that were installed by Visual Studio using the standalone installer may break Visual Studio.</span></span> <span data-ttu-id="82056-164">Si Visual Studio tiene problemas después de desinstalar los SDK, ejecute reparar en esa versión específica de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="82056-164">If Visual Studio has problems after you uninstall SDKs, run Repair on that specific version of Visual Studio.</span></span> <span data-ttu-id="82056-165">En la tabla siguiente se muestran algunas de las dependencias de Visual Studio en las versiones de SDK de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="82056-165">The following table shows some of the Visual Studio dependencies on .NET Core SDK versions:</span></span>

| <span data-ttu-id="82056-166">Versión de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="82056-166">Visual Studio version</span></span> | <span data-ttu-id="82056-167">Versión del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="82056-167">.NET Core SDK version</span></span> |
| -- | -- |
| <span data-ttu-id="82056-168">Visual Studio 2019, versión 16.2</span><span class="sxs-lookup"><span data-stu-id="82056-168">Visual Studio 2019 version 16.2</span></span> | <span data-ttu-id="82056-169">SDK de .NET Core 2.2.4xx, 2.1.8xx</span><span class="sxs-lookup"><span data-stu-id="82056-169">.NET Core SDK 2.2.4xx, 2.1.8xx</span></span> |
| <span data-ttu-id="82056-170">Visual Studio 2019, versión 16.1</span><span class="sxs-lookup"><span data-stu-id="82056-170">Visual Studio 2019 version 16.1</span></span> | <span data-ttu-id="82056-171">SDK de .NET Core 2.2.3xx, 2.1.7xx</span><span class="sxs-lookup"><span data-stu-id="82056-171">.NET Core SDK 2.2.3xx, 2.1.7xx</span></span> |
| <span data-ttu-id="82056-172">Visual Studio 2019, versión 16.0</span><span class="sxs-lookup"><span data-stu-id="82056-172">Visual Studio 2019 version 16.0</span></span> | <span data-ttu-id="82056-173">SDK de .NET Core 2.2.2xx, 2.1.6xx</span><span class="sxs-lookup"><span data-stu-id="82056-173">.NET Core SDK 2.2.2xx, 2.1.6xx</span></span> |
| <span data-ttu-id="82056-174">Visual Studio 2017, versión 15.9</span><span class="sxs-lookup"><span data-stu-id="82056-174">Visual Studio 2017 version 15.9</span></span> | <span data-ttu-id="82056-175">SDK de .NET Core 2.2.1xx, 2.1.5xx</span><span class="sxs-lookup"><span data-stu-id="82056-175">.NET Core SDK 2.2.1xx, 2.1.5xx</span></span> |
| <span data-ttu-id="82056-176">Visual Studio 2017, versión 15.8</span><span class="sxs-lookup"><span data-stu-id="82056-176">Visual Studio 2017 version 15.8</span></span> | <span data-ttu-id="82056-177">SDK de .NET Core 2.1.4xx</span><span class="sxs-lookup"><span data-stu-id="82056-177">.NET Core SDK 2.1.4xx</span></span> |

<span data-ttu-id="82056-178">A partir de Visual Studio 2019 16.3, Visual Studio se encarga de su propia copia de la SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="82056-178">Starting with Visual Studio 2019 16.3, Visual Studio is in charge of its own copy of the .NET Core SDK.</span></span> <span data-ttu-id="82056-179">Por ese motivo, ya no verá las versiones del SDK en el cuadro de diálogo **Agregar o quitar programas**.</span><span class="sxs-lookup"><span data-stu-id="82056-179">For that reason, you no longer see those SDK versions in the **Add/Remove Programs** dialog.</span></span>

## <a name="remove-the-nuget-fallback-folder"></a><span data-ttu-id="82056-180">Eliminación de la carpeta de reserva de NuGet</span><span class="sxs-lookup"><span data-stu-id="82056-180">Remove the NuGet fallback folder</span></span>

<span data-ttu-id="82056-181">Antes del SDK de .NET Core 3.0, los instaladores de SDK de .NET Core usaban *NuGetFallbackFolder* para almacenar una memoria caché de paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="82056-181">Before .NET Core 3.0 SDK, the .NET Core SDK installers used the *NuGetFallbackFolder* to store a cache of NuGet packages.</span></span> <span data-ttu-id="82056-182">Esta memoria caché se utilizó durante operaciones como `dotnet restore` o `dotnet build /t:Restore`.</span><span class="sxs-lookup"><span data-stu-id="82056-182">This cache was used during operations such as `dotnet restore` or `dotnet build /t:Restore`.</span></span> <span data-ttu-id="82056-183">`NuGetFallbackFolder` se encuentra en *C:\Archivos de programa\dotnet\sdk* en Windows y en */usr/local/share/dotnet/sdk* en macOS.</span><span class="sxs-lookup"><span data-stu-id="82056-183">The `NuGetFallbackFolder` is located at *C:\Program Files\dotnet\sdk* on Windows and at */usr/local/share/dotnet/sdk* on macOS.</span></span>

<span data-ttu-id="82056-184">Es posible que desee quitar esta carpeta si:</span><span class="sxs-lookup"><span data-stu-id="82056-184">You may want to remove this folder, if:</span></span>

* <span data-ttu-id="82056-185">Solo está desarrollando con el SDK de .NET Core 3.0 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="82056-185">You're only developing using .NET Core 3.0 SDK or later versions.</span></span>
* <span data-ttu-id="82056-186">Está desarrollando con versiones SDK de .NET Core anteriores a la 3.0, pero puede trabajar en línea y las cosas pueden ser más lentas una vez.</span><span class="sxs-lookup"><span data-stu-id="82056-186">You're developing using .NET Core SDK versions earlier than 3.0, but you can work online and things can be slower once.</span></span>

<span data-ttu-id="82056-187">Si desea quitar la carpeta de reserva de NuGet, puede eliminarla, pero necesitará privilegios de administrador para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="82056-187">If you want to remove the NuGet fallback folder, you can delete it, but you'll need admin privileges to do so.</span></span>

<span data-ttu-id="82056-188">No se recomienda eliminar la carpeta *dotnet*.</span><span class="sxs-lookup"><span data-stu-id="82056-188">It's not recommended to delete the *dotnet* folder.</span></span> <span data-ttu-id="82056-189">Si lo hace, se quitarán las herramientas globales que haya instalado previamente.</span><span class="sxs-lookup"><span data-stu-id="82056-189">Doing so would remove any global tools you've previously installed.</span></span> <span data-ttu-id="82056-190">Además, en Windows:</span><span class="sxs-lookup"><span data-stu-id="82056-190">Also, on Windows:</span></span>

- <span data-ttu-id="82056-191">Interrumpirá Visual Studio 2019 versión 16.3 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="82056-191">You'll break Visual Studio 2019 version 16.3 and later versions.</span></span> <span data-ttu-id="82056-192">Puede ejecutar **Reparar** para recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="82056-192">You can run **Repair** to recover.</span></span>
- <span data-ttu-id="82056-193">Si hay SDK de .NET Core entradas en el cuadro de diálogo **Agregar o quitar programas**, se quedarán huérfanas.</span><span class="sxs-lookup"><span data-stu-id="82056-193">If there are .NET Core SDK entries in the **Add/Remove Programs** dialog, they'll be orphaned.</span></span>
