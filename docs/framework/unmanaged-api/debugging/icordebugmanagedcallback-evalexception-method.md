---
title: ICorDebugManagedCallback::EvalException (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalException
helpviewer_keywords:
- EvalException method [.NET Framework debugging]
- ICorDebugManagedCallback::EvalException method [.NET Framework debugging]
ms.assetid: d6036345-18a3-45c1-a302-b1c6f2dced9b
topic_type:
- apiref
ms.openlocfilehash: 3ae93081bd201f745fa47bc01a9c6fcbf6e9f63c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781871"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="39de2-102">ICorDebugManagedCallback::EvalException (Método)</span><span class="sxs-lookup"><span data-stu-id="39de2-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="39de2-103">Notifica al depurador que una evaluación ha finalizado con una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="39de2-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39de2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39de2-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39de2-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="39de2-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="39de2-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que finalizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="39de2-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="39de2-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que finalizó la evaluación.</span><span class="sxs-lookup"><span data-stu-id="39de2-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="39de2-108">de Un puntero a un objeto ICorDebugEval que representa el código que llevó a cabo la evaluación.</span><span class="sxs-lookup"><span data-stu-id="39de2-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39de2-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="39de2-109">Requirements</span></span>  
 <span data-ttu-id="39de2-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39de2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39de2-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39de2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39de2-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39de2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39de2-113">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39de2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39de2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="39de2-114">See also</span></span>

- [<span data-ttu-id="39de2-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="39de2-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
