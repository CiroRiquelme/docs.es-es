---
title: Recolección de elementos no utilizados de .NET
ms.date: 04/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET Framework]
- memory, allocating
- common language runtime, garbage collection
- garbage collector
- cleanup operations
- garbage collection
- memory, releasing
- common language runtime, automatic memory management
- automatic memory management
- runtime, automatic memory management
- runtime, garbage collection
- garbage collection, about
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
ms.openlocfilehash: c087deb033a373dd8b3980feb7ec6901c7909569
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102247"
---
# <a name="garbage-collection"></a>Recolección de elementos no utilizados

El recolector de elementos no utilizados de .NET administra la asignación y liberación de la memoria de la aplicación. Cada vez que se crea un objeto nuevo, el Common Language Runtime asigna al objeto memoria del montón administrado. Siempre que haya espacio de direcciones disponible en el montón nativo, el motor en tiempo de ejecución continúa asignando espacio a los objetos nuevos. No obstante, la memoria no es infinita. En ocasiones, el recolector de elementos no utilizados debe realizar una recolección para liberar alguna memoria. El motor de optimización del recolector de elementos no utilizados determina cuál es el mejor momento para realizar una recolección, según las asignaciones que se estén realizando. Cuando el recolector de elementos no utilizados realiza una recolección, comprueba si en el montón administrado hay objetos que la aplicación ya no utiliza y realiza las operaciones necesarias para reclamar su memoria.  
  
## <a name="in-this-section"></a>En esta sección
  
|Title|Descripción|  
|-----------|-----------------|  
|[Fundamentos de la recolección de elementos no utilizados](../../../docs/standard/garbage-collection/fundamentals.md)|Describe cómo funciona la recolección de elementos no utilizados, cómo se asignan los objetos en el montón administrado y otros conceptos básicos.|  
|[Recolección de elementos no utilizados de estación de trabajo y de servidor](workstation-server-gc.md)|Describe las diferencias entre la recolección de elementos no utilizados para aplicaciones cliente y la recolección de elementos no utilizados del servidor para aplicaciones de servidor.|
|[Recolección de elementos no utilizados en segundo plano](background-gc.md)|Describe la recolección de elementos no utilizados en segundo plano, que es la recolección de objetos de generación 0 y 1 mientras se lleva a cabo la recolección de generación 2.|
|[El montón de objetos grandes](large-object-heap.md)|Describe el montón de objetos grandes y cómo se lleva a cabo la recolección de elementos no utilizados de los objetos grandes.|
|[Recolección de elementos no utilizados y rendimiento](../../../docs/standard/garbage-collection/performance.md)|Describe las comprobaciones de rendimiento que se pueden utilizar para diagnosticar los problemas con la recolección de elementos no utilizados y los problemas de rendimiento.|  
|[Colecciones inducidas](../../../docs/standard/garbage-collection/induced.md)|Describe cómo hacer que se produzca una recolección de elementos no utilizados.|  
|[Modos de latencia](../../../docs/standard/garbage-collection/latency.md)|Describe los modos que determinan la tendencia a la intrusión de la recolección de elementos no utilizados.|  
|[Optimización de hospedaje web compartido](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|Describe cómo optimizar la recolección de elementos no utilizados en servidores compartidos entre varios sitios web pequeños.|  
|[Notificaciones de recolección de elementos no utilizados](../../../docs/standard/garbage-collection/notifications.md)|Describe cómo se determina cuándo una recolección de elementos no utilizados completa está próxima y cuándo se ha completado.|  
|[Supervisión de recursos de dominio de aplicación](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|Describe cómo supervisar el uso de la CPU y la memoria por un dominio de aplicación.|  
|[Referencias débiles](../../../docs/standard/garbage-collection/weak-references.md)|Describe las características que permiten al recolector de elementos no utilizados recoger un objeto y, mientras tanto, permitir que la aplicación tenga acceso a ese objeto.|  
  
## <a name="reference"></a>Referencia

- <xref:System.GC?displayProperty=nameWithType>  
- <xref:System.GCCollectionMode?displayProperty=nameWithType>  
- <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
- <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a>Vea también

- [Limpieza de recursos no administrados](../../../docs/standard/garbage-collection/unmanaged.md)
