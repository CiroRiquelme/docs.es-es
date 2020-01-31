---
title: ICorDebugEnum::Skip (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
ms.openlocfilehash: 5c9049edd6d139bff29d21b65f9c87ec3e6de1a6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782976"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="8f6b6-102">ICorDebugEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="8f6b6-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="8f6b6-103">Mueve el cursor hacia delante en la enumeración el número de elementos especificado.</span><span class="sxs-lookup"><span data-stu-id="8f6b6-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f6b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f6b6-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f6b6-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8f6b6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="8f6b6-106">de Número de elementos por los que se va a desplazar el cursor hacia delante.</span><span class="sxs-lookup"><span data-stu-id="8f6b6-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f6b6-107">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="8f6b6-107">Requirements</span></span>  
 <span data-ttu-id="8f6b6-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f6b6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f6b6-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f6b6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f6b6-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f6b6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f6b6-111">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f6b6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f6b6-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f6b6-112">See also</span></span>

- [<span data-ttu-id="8f6b6-113">ICorDebugEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f6b6-113">ICorDebugEnum Interface</span></span>](icordebugenum-interface1.md)
