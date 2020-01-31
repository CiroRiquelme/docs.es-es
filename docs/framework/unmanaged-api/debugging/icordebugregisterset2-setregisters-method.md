---
title: ICorDebugRegisterSet2::SetRegisters (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::SetRegisters
helpviewer_keywords:
- ICorDebugRegisterSet2::SetRegisters method [.NET Framework debugging]
- SetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: fe0ac7e7-c9e1-4ec1-9f4e-1c56d63d73ac
topic_type:
- apiref
ms.openlocfilehash: 2dce97db3d209c51270a51ae92e9dce0b6861998
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791994"
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="2fc0d-102">ICorDebugRegisterSet2::SetRegisters (Método)</span><span class="sxs-lookup"><span data-stu-id="2fc0d-102">ICorDebugRegisterSet2::SetRegisters Method</span></span>
<span data-ttu-id="2fc0d-103">`SetRegisters` no se implementa en la versión 2,0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2fc0d-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="2fc0d-104">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="2fc0d-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2fc0d-105">Use las operaciones de nivel superior como [ICorDebugILFrame:: setip](icordebugilframe-setip-method.md) o [ICorDebugNativeFrame:: setip](icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="2fc0d-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fc0d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2fc0d-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="2fc0d-107">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="2fc0d-107">Requirements</span></span>  
 <span data-ttu-id="2fc0d-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fc0d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fc0d-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fc0d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fc0d-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fc0d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fc0d-111">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fc0d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fc0d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fc0d-112">See also</span></span>

- [<span data-ttu-id="2fc0d-113">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2fc0d-113">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="2fc0d-114">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2fc0d-114">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
