---
title: ICorDebugMDA::GetOSThreadId (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
ms.openlocfilehash: c7ab77e9316023a97d2eafe8bcccc2b45e240cd0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207826"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="ef26a-102">ICorDebugMDA::GetOSThreadId (Método)</span><span class="sxs-lookup"><span data-stu-id="ef26a-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="ef26a-103">Obtiene el identificador del subproceso del sistema operativo (SO) en el que se ejecuta el Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](icordebugmda-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ef26a-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef26a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef26a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef26a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef26a-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="ef26a-106">enuncia Puntero al identificador del subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ef26a-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef26a-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ef26a-107">Remarks</span></span>  
 <span data-ttu-id="ef26a-108">El subproceso del sistema operativo se usa en lugar de una expresión ICorDebugThread para permitir situaciones en las que se desencadena un MDA en un subproceso nativo o en un subproceso administrado que todavía no ha entrado en código administrado.</span><span class="sxs-lookup"><span data-stu-id="ef26a-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef26a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef26a-109">Requirements</span></span>  
 <span data-ttu-id="ef26a-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef26a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef26a-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef26a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef26a-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef26a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef26a-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef26a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef26a-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef26a-114">See also</span></span>

- [<span data-ttu-id="ef26a-115">ICorDebugMDA (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef26a-115">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="ef26a-116">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="ef26a-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
