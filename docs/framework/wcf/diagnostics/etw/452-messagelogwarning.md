---
title: 452 - MessageLogWarning
ms.date: 03/30/2017
ms.assetid: 22a9f6ea-5b5f-4110-8a4e-9be9c983fbbb
ms.openlocfilehash: 22932c4de7a803307f2ee82adc958a30cf96f198
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757474"
---
# <a name="452---messagelogwarning"></a>452 - MessageLogWarning
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|452|  
|Palabras clave|Solución de problemas, WCFMessageLogging|  
|Nivel|Advertencia|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 Este evento se genera cuando se envía la advertencia del registro de mensajes.  
  
## <a name="message"></a>Mensaje  
 %1  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|data1|`xs:string`||  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
