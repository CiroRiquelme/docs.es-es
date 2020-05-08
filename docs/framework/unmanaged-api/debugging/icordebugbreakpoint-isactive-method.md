---
title: ICorDebugBreakpoint::IsActive (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::IsActive
helpviewer_keywords:
- ICorDebugBreakpoint::IsActive method [.NET Framework debugging]
- IsActive method, ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: 06e583d6-d88a-4ff5-bb95-5c48618a461c
topic_type:
- apiref
ms.openlocfilehash: 64a30ca85a75ebd11918ff630daffbb85c97f6dc
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894723"
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="f6788-102">ICorDebugBreakpoint::IsActive (Método)</span><span class="sxs-lookup"><span data-stu-id="f6788-102">ICorDebugBreakpoint::IsActive Method</span></span>
<span data-ttu-id="f6788-103">Obtiene un valor que indica si este `ICorDebugBreakpoint` está activo.</span><span class="sxs-lookup"><span data-stu-id="f6788-103">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6788-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6788-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6788-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f6788-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="f6788-106">enuncia `true` si este punto de interrupción está activo; en caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="f6788-106">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6788-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6788-107">Requirements</span></span>  
 <span data-ttu-id="f6788-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6788-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6788-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6788-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6788-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6788-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6788-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6788-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
