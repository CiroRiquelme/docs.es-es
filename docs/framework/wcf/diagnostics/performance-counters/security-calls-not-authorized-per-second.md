---
title: Llamadas de seguridad no autorizadas por segundo
ms.date: 03/30/2017
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
ms.openlocfilehash: 2986ba241ef9b6c110a4742f77320469cdf5f07a
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163935"
---
# <a name="security-calls-not-authorized-per-second"></a>Llamadas de seguridad no autorizadas por segundo
Nombre del contador: llamadas de seguridad no autorizadas por segundo.  
  
## <a name="description"></a>Descripción  
 El número de llamadas que no pudieron autorizarse en esta operación en un segundo.  
  
 Este contador se incrementa cuando el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> devuelve `false`. Indica que el mensaje entrante es de un usuario válido y que está debidamente protegido, pero dicho usuario no está autorizado a realizar tareas específicas.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
