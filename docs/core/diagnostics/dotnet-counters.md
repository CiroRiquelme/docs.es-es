---
title: 'dotnet-counters: .Net Core'
description: Obtenga información sobre cómo instalar y usar la herramienta de línea de comandos dotnet-counter.
ms.date: 02/26/2020
ms.openlocfilehash: dc95297478784ca06fe442a939f8489a40b29da7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147183"
---
# <a name="dotnet-counters"></a>dotnet-counters

**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores

## <a name="install-dotnet-counters"></a>Instalación de dotnet-counters

Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-counters) de `dotnet-counters`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a>Sinopsis

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a>Descripción

`dotnet-counters` es una herramienta de supervisión de rendimiento diseñada para la investigación del rendimiento y la supervisión del estado de primer nivel ad hoc. Puede observar los valores del contador de rendimiento que se publican a través de la API <xref:System.Diagnostics.Tracing.EventCounter>. Por ejemplo, se pueden supervisar rápidamente cosas como el uso de la CPU o la velocidad de las excepciones que se producen en la aplicación .NET Core para ver si hay algo sospechoso antes de profundizar en una investigación de rendimiento más seria mediante `PerfView` o `dotnet-trace`.

## <a name="options"></a>Opciones

- **`--version`**

  Muestra la versión de la utilidad dotnet-counters.

- **`-h|--help`**

  Muestra la ayuda de la línea de comandos.

## <a name="commands"></a>Comandos

| Comando                                             |
| --------------------------------------------------- |
| [dotnet-counters collect](#dotnet-counters-collect) |
| [dotnet-counters list](#dotnet-counters-list)       |
| [dotnet-counters monitor](#dotnet-counters-monitor) |
| [dotnet-counters ps](#dotnet-counters-ps) |

## <a name="dotnet-counters-collect"></a>dotnet-counters collect

Recopila periódicamente los valores de contador seleccionados y los exporta a un formato de archivo especificado para su posterior procesamiento.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list] [--format] [-o|--output]
```

### <a name="options"></a>Opciones

- **`-p|--process-id <PID>`**

  Id. del proceso que se va a supervisar.

- **`--refresh-interval <SECONDS>`**

  Número de segundos de retraso entre la actualización de los contadores mostrados.

- **`counter_list <COUNTERS>`**

  Una lista de contadores separados por espacios. Los contadores pueden ser `provider_name[:counter_name]` especificados. Si `provider_name` se usa sin un elemento `counter_name` calificado, se mostrarán todos los contadores. Para descubrir los nombres del proveedor y del contador, use el comando [dotnet-counters list](#dotnet-counters-list).

- **`--format <csv|json>`**

  El formato que se va a exportar. Actualmente disponibles: csv, json.

- **`-o|--output <output>`**

  Nombre del archivo de salida.

### <a name="examples"></a>Ejemplos

- Recopilación de todos los contadores en un intervalo de actualización de tres segundos y generación de un archivo CSV como salida:

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

## <a name="dotnet-counters-list"></a>dotnet-counters list

Muestra una lista de nombres y descripciones de contador, agrupada por proveedor.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a>Ejemplo

```console
> dotnet-counters list

    Showing well-known counters only. Specific processes may support additional counters.
    System.Runtime
        cpu-usage                    Amount of time the process has utilized the CPU (ms)
        working-set                  Amount of working set used by the process (MB)
        gc-heap-size                 Total heap size reported by the GC (MB)
        gen-0-gc-count               Number of Gen 0 GCs / sec
        gen-1-gc-count               Number of Gen 1 GCs / sec
        gen-2-gc-count               Number of Gen 2 GCs / sec
        exception-count              Number of Exceptions / sec
```

## <a name="dotnet-counters-monitor"></a>dotnet-counters monitor

Muestra la actualización periódica de los valores de los contadores seleccionados.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a>Opciones

- **`-p|--process-id <PID>`**

  Id. del proceso que se va a supervisar.

- **`--refresh-interval <SECONDS>`**

  Número de segundos de retraso entre la actualización de los contadores mostrados.

- **`counter_list <COUNTERS>`**

  Una lista de contadores separados por espacios. Los contadores pueden ser `provider_name[:counter_name]` especificados. Si `provider_name` se usa sin un elemento `counter_name` calificado, se mostrarán todos los contadores. Para descubrir los nombres del proveedor y del contador, use el comando [dotnet-counters list](#dotnet-counters-list).

### <a name="examples"></a>Ejemplos

- Supervisión de todos los contadores de `System.Runtime` con un intervalo de actualización de 3 segundos:

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 System.Runtime

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      Working Set (MB)                            1982
      GC Heap Size (MB)                            811
      Gen 0 GC / second                             20
      Gen 1 GC / second                              4
      Gen 2 GC / second                              1
      Number of Exceptions / sec                     4
  ```

- Supervisión de únicamente el uso de la CPU y el tamaño del montón de GC de `System.Runtime`:

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- Supervisión de los valores `EventCounter` del elemento `EventSource` definido por el usuario. Para obtener más información, consulte [Tutorial: Cómo medir el rendimiento de eventos muy frecuentes con EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
  
## <a name="dotnet-counters-ps"></a>dotnet-counters ps

Muestra una lista de los procesos de dotnet que se pueden supervisar.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a>Ejemplo

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
