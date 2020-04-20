---
title: Comando dotnet build-server
description: El comando dotnet build-server interactúa con los servidores que se han iniciado por una compilación.
ms.date: 02/14/2020
ms.openlocfilehash: 882b697c07aac0e20266f3ad4e6c11888a0b7acc
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463721"
---
# <a name="dotnet-build-server"></a>dotnet build-server

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

## <a name="name"></a>Name

`dotnet build-server`: interactúa con servidores iniciados por una compilación.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]

dotnet build-server shutdown -h|--help

dotnet build-server -h|--help
```

## <a name="commands"></a>Comandos

- **`shutdown`**

  Cierra los servidores de la compilación que se inician desde dotnet. De forma predeterminada, se cierran todos los servidores.

## <a name="options"></a>Opciones

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`--msbuild`**

  Cierra el servidor de compilación de MSBuild.

- **`--razor`**

  Cierra el servidor de compilación de Razor.

- **`--vbcscompiler`**

  Cierra el servidor de compilación del compilador de VB/C#.
