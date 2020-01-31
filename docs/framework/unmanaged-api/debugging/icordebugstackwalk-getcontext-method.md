---
title: ICorDebugStackWalk::GetContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
ms.openlocfilehash: 9953d0f3e1a4d4cd935918f0e5721e474453ca7d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791907"
---
# <a name="icordebugstackwalkgetcontext-method"></a><span data-ttu-id="48df4-102">ICorDebugStackWalk::GetContext (Método)</span><span class="sxs-lookup"><span data-stu-id="48df4-102">ICorDebugStackWalk::GetContext Method</span></span>
<span data-ttu-id="48df4-103">Devuelve el contexto del marco actual del objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="48df4-103">Returns the context for the current frame in the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48df4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48df4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48df4-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="48df4-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="48df4-106">de Marcas que indican el contenido solicitado del búfer de contexto (definido en Winnt. h).</span><span class="sxs-lookup"><span data-stu-id="48df4-106">[in] Flags that indicate the requested contents of the context buffer (defined in WinNT.h).</span></span>  
  
 `contextBufSize`  
 <span data-ttu-id="48df4-107">de Tamaño asignado del búfer de contexto.</span><span class="sxs-lookup"><span data-stu-id="48df4-107">[in] The allocated size of the context buffer.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="48df4-108">enuncia Tamaño real del contexto.</span><span class="sxs-lookup"><span data-stu-id="48df4-108">[out] The actual size of the context.</span></span> <span data-ttu-id="48df4-109">Este valor debe ser menor o igual que el tamaño del búfer de contexto.</span><span class="sxs-lookup"><span data-stu-id="48df4-109">This value must be less than or equal to the size of the context buffer.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="48df4-110">enuncia Búfer de contexto.</span><span class="sxs-lookup"><span data-stu-id="48df4-110">[out] The context buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48df4-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="48df4-111">Return Value</span></span>  
 <span data-ttu-id="48df4-112">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="48df4-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="48df4-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48df4-113">HRESULT</span></span>|<span data-ttu-id="48df4-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="48df4-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48df4-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="48df4-115">S_OK</span></span>|<span data-ttu-id="48df4-116">El contexto del marco actual se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="48df4-116">The context for the current frame was successfully returned.</span></span>|  
|<span data-ttu-id="48df4-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="48df4-117">E_FAIL</span></span>|<span data-ttu-id="48df4-118">No se pudo devolver el contexto.</span><span class="sxs-lookup"><span data-stu-id="48df4-118">The context could not be returned.</span></span>|  
|<span data-ttu-id="48df4-119">HRESULT_FROM_WIN32 (BÚFER DE ERROR_INSUFFICIENT)</span><span class="sxs-lookup"><span data-stu-id="48df4-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span></span>|<span data-ttu-id="48df4-120">El búfer de contexto es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="48df4-120">The context buffer is too small.</span></span>|  
|<span data-ttu-id="48df4-121">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="48df4-121">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="48df4-122">El puntero de marco ya está al final de la pila; por lo tanto, no se puede tener acceso a ningún fotograma adicional.</span><span class="sxs-lookup"><span data-stu-id="48df4-122">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="48df4-123">Excepciones</span><span class="sxs-lookup"><span data-stu-id="48df4-123">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48df4-124">Notas</span><span class="sxs-lookup"><span data-stu-id="48df4-124">Remarks</span></span>  
 <span data-ttu-id="48df4-125">Dado que el desenredado solo restaura un subconjunto de los registros, como los registros no volátiles, es posible que el contexto no coincida exactamente con el estado del registro en el momento de la llamada.</span><span class="sxs-lookup"><span data-stu-id="48df4-125">Because unwinding restores only a subset of the registers, such as non-volatile registers, the context may not exactly match the register state at the time of the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48df4-126">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="48df4-126">Requirements</span></span>  
 <span data-ttu-id="48df4-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48df4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48df4-128">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48df4-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48df4-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48df4-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48df4-130">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48df4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48df4-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="48df4-131">See also</span></span>

- [<span data-ttu-id="48df4-132">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="48df4-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="48df4-133">Depuración</span><span class="sxs-lookup"><span data-stu-id="48df4-133">Debugging</span></span>](index.md)
