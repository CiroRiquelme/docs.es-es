---
title: Interfaz ICorDebugBreakpointEnum
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
ms.openlocfilehash: e391a02571481d75ce88ae3f3b2b6421705d661c
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894699"
---
# <a name="icordebugbreakpointenum-interface"></a>Interfaz ICorDebugBreakpointEnum

Implementa los métodos de ICorDebugEnum y enumera las matrices de ICorDebugBreakpoint.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (Método)](icordebugbreakpointenum-next-method.md)|Obtiene el número especificado de `ICorDebugBreakpoint` instancias de la enumeración, comenzando en la posición actual.|  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Interfaces para depuración](debugging-interfaces.md)
