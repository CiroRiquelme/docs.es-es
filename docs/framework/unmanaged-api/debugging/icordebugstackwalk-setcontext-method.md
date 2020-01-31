---
title: ICorDebugStackWalk::SetContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.SetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type:
- apiref
ms.openlocfilehash: 23ad8882ad97e5ceaeb690dfae08a6be55b85f64
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791859"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="7f4b6-102">ICorDebugStackWalk::SetContext (Método)</span><span class="sxs-lookup"><span data-stu-id="7f4b6-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="7f4b6-103">Establece el contexto actual del objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) en un contexto válido para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="7f4b6-103">Sets the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f4b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f4b6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f4b6-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="7f4b6-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="7f4b6-106">de Marca [CorDebugSetContextFlag (](cordebugsetcontextflag-enumeration.md) que indica si el contexto procede del marco activo de la pila o un contexto obtenido al desenredar la pila.</span><span class="sxs-lookup"><span data-stu-id="7f4b6-106">[in] A [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="7f4b6-107">de Tamaño asignado del búfer de `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="7f4b6-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="7f4b6-108">de Búfer de `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="7f4b6-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f4b6-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7f4b6-109">Return Value</span></span>  
 <span data-ttu-id="7f4b6-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="7f4b6-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7f4b6-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7f4b6-111">HRESULT</span></span>|<span data-ttu-id="7f4b6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f4b6-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7f4b6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f4b6-113">S_OK</span></span>|<span data-ttu-id="7f4b6-114">El contexto del objeto `ICorDebugStackWalk` se estableció correctamente.</span><span class="sxs-lookup"><span data-stu-id="7f4b6-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="7f4b6-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7f4b6-115">E_FAIL</span></span>|<span data-ttu-id="7f4b6-116">No se ha establecido el contexto del objeto `ICorDebugStackWalk`.</span><span class="sxs-lookup"><span data-stu-id="7f4b6-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="7f4b6-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7f4b6-117">E_INVALIDARG</span></span>|<span data-ttu-id="7f4b6-118">El contexto es una null.</span><span class="sxs-lookup"><span data-stu-id="7f4b6-118">The context is null.</span></span>|  
|<span data-ttu-id="7f4b6-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="7f4b6-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="7f4b6-120">El búfer de contexto es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="7f4b6-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="7f4b6-121">Excepciones</span><span class="sxs-lookup"><span data-stu-id="7f4b6-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f4b6-122">Notas</span><span class="sxs-lookup"><span data-stu-id="7f4b6-122">Remarks</span></span>  
 <span data-ttu-id="7f4b6-123">Este método no modifica el contexto actual del subproceso.</span><span class="sxs-lookup"><span data-stu-id="7f4b6-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="7f4b6-124">Establecer el contexto actual en un contexto no válido puede producir resultados imprevisibles del rastreador de pila.</span><span class="sxs-lookup"><span data-stu-id="7f4b6-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="7f4b6-125">Puede recuperar una copia bit a bit exacta de este contexto llamando inmediatamente al método [ICorDebugStackWalk:: getContext](icordebugstackwalk-getcontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7f4b6-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f4b6-126">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="7f4b6-126">Requirements</span></span>  
 <span data-ttu-id="7f4b6-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f4b6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f4b6-128">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f4b6-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f4b6-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f4b6-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f4b6-130">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f4b6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f4b6-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f4b6-131">See also</span></span>

- [<span data-ttu-id="7f4b6-132">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7f4b6-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7f4b6-133">Depuración</span><span class="sxs-lookup"><span data-stu-id="7f4b6-133">Debugging</span></span>](index.md)
