---
title: FunctionLeave3 (Función)
ms.date: 03/30/2017
api_name:
- FunctionLeave3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3
helpviewer_keywords:
- FunctionLeave3 function [.NET Framework profiling]
ms.assetid: 5d798088-7992-48a0-ae55-d2a7ee31913f
topic_type:
- apiref
ms.openlocfilehash: 32d86f19e9c50694c7d113195e6967645b710666
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866874"
---
# <a name="functionleave3-function"></a>FunctionLeave3 (Función)
Notifica al generador de perfiles que el control se devuelve desde una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a>Parameters  

- `functionOrRemappedID`

  \[en] el identificador de la función de la que se devuelve el control.
  
## <a name="remarks"></a>Notas  
 La función de devolución de llamada `FunctionLeave3` notifica al generador de perfiles cuando se llama a las funciones, pero no admite la inspección del valor devuelto. Use el [método ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 (](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) para registrar su implementación de esta función.  
  
 La función `FunctionLeave3` es una devolución de llamada; debe implementarla. La implementación de debe utilizar el atributo de clase de almacenamiento `__declspec(naked)`.  
  
 El motor de ejecución no guarda ningún registro antes de llamar a esta función.  
  
- En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).  
  
- Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.  
  
 La implementación de `FunctionLeave3` no debe bloquearse porque retrasará la recolección de elementos no utilizados. La implementación no debe intentar una recolección de elementos no utilizados, porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados. Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que `FunctionLeave3` devuelva.  
  
 La función `FunctionLeave3` no debe llamar a código administrado ni producir una asignación de memoria administrada de ninguna manera.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [FunctionEnter3](functionenter3-function.md)
- [FunctionTailcall3](functiontailcall3-function.md)
- [FunctionEnter3WithInfo](functiontailcall3-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [SetFunctionIDMapper2](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)
