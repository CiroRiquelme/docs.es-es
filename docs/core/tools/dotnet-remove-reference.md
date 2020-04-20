---
title: Comando dotnet remove reference
description: El comando dotnet remove reference constituye una opción práctica para quitar las referencias entre proyectos.
ms.date: 02/14/2020
ms.openlocfilehash: 92d36bbbde64d806abc8f223c5f08e3f3d79ce9d
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463444"
---
# <a name="dotnet-remove-reference"></a>dotnet remove reference

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores

## <a name="name"></a>Name

`dotnet remove reference`: quita las referencias de proyecto a proyecto.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet remove [<PROJECT>] reference [-f|--framework <FRAMEWORK>] <PROJECT_REFERENCES>

dotnet remove reference -h|--help
```

## <a name="description"></a>Description

El comando `dotnet remove reference` constituye una opción práctica para quitar referencias de proyecto de un proyecto.

## <a name="arguments"></a>Argumentos

`PROJECT`

Archivo de proyecto de destino. Si no se especifica, el comando busca uno en el directorio actual.

`PROJECT_REFERENCES`

Referencias de proyecto a proyecto (P2P) que se van a quitar. Puede especificar uno o varios proyectos. Se admiten [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) en terminales basados en Unix o Linux.

## <a name="options"></a>Opciones

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`-f|--framework <FRAMEWORK>`**

  Quita la referencia solo cuando el destino es un [marco de trabajo](../../standard/frameworks.md) específico.

## <a name="examples"></a>Ejemplos

- Quitar una referencia de proyecto del proyecto especificado:

  ```dotnetcli
  dotnet remove app/app.csproj reference lib/lib.csproj
  ```

- Quitar varias referencias de proyecto del proyecto en el directorio actual:

  ```dotnetcli
  dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- Quitar varias referencias de proyecto con un patrón global en Unix/Linux:

  ```dotnetcli
  dotnet remove app/app.csproj reference **/*.csproj`
  ```
