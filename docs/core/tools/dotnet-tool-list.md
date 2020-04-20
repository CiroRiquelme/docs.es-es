---
title: Comando dotnet tool list
description: El comando dotnet tool list enumera las herramientas de .NET Core que están instaladas en el equipo.
ms.date: 02/14/2020
ms.openlocfilehash: 28f9155407d1238f8b0960b69b34ea329ca0e8e6
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463350"
---
# <a name="dotnet-tool-list"></a>dotnet tool list

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet tool list`: enumera todas las [herramientas de .NET Core](global-tools.md) del tipo especificado actualmente instalado en el equipo.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet tool list` permite enumerar todas las herramientas locales, de ruta de acceso de herramientas y globales de .NET Core que están instaladas en el equipo. El comando enumera el nombre del paquete, la versión instalada y el comando de la herramienta.  Para usar el comando, especifique una de las siguientes opciones:

* Una herramienta global instalada en la ubicación predeterminada. Use la opción `--global`.
* Una herramienta global instalada en una ubicación personalizada. Use la opción `--tool-path`.
* Una herramienta local. Omita las opciones `--global` y `--tool-path`.

**Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.**

## <a name="options"></a>Opciones

- **`-g|--global`**

  Enumera las herramientas globales de los usuarios. No se puede combinar con la opción `--tool-path`. Al omitir `--global` y `--tool-path`, se muestran las herramientas locales.

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`--tool-path <PATH>`**

  Especifica una ubicación personalizada para las herramientas globales. PATH puede ser una ruta absoluta o relativa. No se puede combinar con la opción `--global`. Al omitir `--global` y `--tool-path`, se muestran las herramientas locales.

## <a name="examples"></a>Ejemplos

- **`dotnet tool list -g`**

  Enumera todas las herramientas globales instaladas para todos los usuarios en su equipo (perfil de usuario actual).

- **`dotnet tool list --tool-path c:\global-tools`**

  Enumera las herramientas globales de un directorio específico de Windows.

- **`dotnet tool list --tool-path ~/bin`**

  Enumera las herramientas globales de un directorio específico de Linux/macOS.

- **`dotnet tool list`**

  Enumera todas las herramientas locales disponibles en el directorio actual.

## <a name="see-also"></a>Vea también

- [Herramientas de .NET Core](global-tools.md)
- [Tutorial: Instalación y uso de una herramienta global de .NET Core mediante la CLI de .NET Core](global-tools-how-to-use.md)
- [Tutorial: Instalación y uso de una herramienta local de .NET Core mediante la CLI de .NET Core](local-tools-how-to-use.md)
