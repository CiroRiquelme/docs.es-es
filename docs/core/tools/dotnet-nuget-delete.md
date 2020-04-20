---
title: Comando dotnet nuget delete
description: El comando dotnet-nuget-delete elimina o quita de la lista un paquete del servidor.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 4fa4f24adba251d7872986de4a8b1a63203c36c3
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463581"
---
# <a name="dotnet-nuget-delete"></a>dotnet nuget delete

**Este artículo se aplica a:** ✔️ SDK de .NET Core 1.x y versiones posteriores

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>Name

`dotnet nuget delete`: elimina o quita de la lista un paquete del servidor.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output]
    [--interactive] [-k|--api-key <API_KEY>] [--no-service-endpoint]
    [--non-interactive] [-s|--source <SOURCE>]

dotnet nuget delete -h|--help
```

## <a name="description"></a>Description

El comando `dotnet nuget delete` elimina o quita de la lista un paquete del servidor. Para [nuget.org](https://www.nuget.org/), la acción es quitar de la lista el paquete.

## <a name="arguments"></a>Argumentos

* **`PACKAGE_NAME`**

  Nombre o id. del paquete que se va a eliminar.

* **`PACKAGE_VERSION`**

  Versión del paquete que se va a eliminar.

## <a name="options"></a>Opciones

* **`--force-english-output`**

  Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.

* **`-h|--help`**

  Imprime una corta ayuda para el comando.

* **`--interactive`**

  Permite que el comando se bloquee y requiere una acción manual para operaciones tales como la autenticación. Opción disponible a partir del SDK de .NET Core 2.2.

* **`-k|--api-key <API_KEY>`**

  La clave de API para el servidor.

* **`--no-service-endpoint`**

  No agrega "api/v2/paquete" a la dirección URL de origen. Opción disponible a partir del SDK de .NET Core 2.1.

* **`--non-interactive`**

  No pide confirmaciones o entradas de usuario.

* **`-s|--source <SOURCE>`**

  Especifica la dirección URL del servidor. Las direcciones URL admitidas para nuget.org incluyen `https://www.nuget.org`, `https://www.nuget.org/api/v3` y `https://www.nuget.org/api/v2/package`. Para fuentes privadas, reemplace el nombre de host (por ejemplo, `%hostname%/api/v3`).

## <a name="examples"></a>Ejemplos

* Elimina la versión 1.0 del paquete `Microsoft.AspNetCore.Mvc`:

  ```dotnetcli
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* Elimina la versión 1.0 del paquete `Microsoft.AspNetCore.Mvc`, sin pedir al usuario credenciales u otra información:

  ```dotnetcli
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```
