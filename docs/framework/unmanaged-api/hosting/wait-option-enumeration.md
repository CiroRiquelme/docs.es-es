---
title: WAIT_OPTION (Enumeración)
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
ms.openlocfilehash: 9ecfb551b55551e5f6cc7e7e9ffb55e5a96259ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141517"
---
# <a name="wait_option-enumeration"></a>WAIT_OPTION (Enumeración)
Contiene valores que indican la acción que debe realizar un host si una operación solicitada por los bloques de Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|Notifica al host que la tarea se debe reactivar si CLR llama al método [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) .|  
|`WAIT_MSGPUMP`|Notifica al host que debe bombear los mensajes en el subproceso del sistema operativo actual si el subproceso se bloquea. El tiempo de ejecución especifica este valor solo en un subproceso de <xref:System.Threading.ApartmentState.STA>.|  
|`WAIT_NOTINDEADLOCK`|Notifica al host que un host no puede interrumpir la solicitud de sincronización especificada. Es decir, el host no puede devolver `HOST_E_DEADLOCK`.|  
  
## <a name="remarks"></a>Comentarios  
 Los métodos [IHostTaskManager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) y [IHostTaskManager:: switchtotask (](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) toman un parámetro de este tipo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
