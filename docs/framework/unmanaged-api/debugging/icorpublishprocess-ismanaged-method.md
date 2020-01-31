---
title: ICorPublishProcess::IsManaged (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
ms.openlocfilehash: 68931ba16ea1f8f61176c6d6ed8300e762b61690
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790526"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="7bc7d-102">ICorPublishProcess::IsManaged (Método)</span><span class="sxs-lookup"><span data-stu-id="7bc7d-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="7bc7d-103">Obtiene un valor que indica si se sabe que el proceso al que hace referencia esta [ICorPublishProcess](icorpublishprocess-interface.md) tiene código administrado.</span><span class="sxs-lookup"><span data-stu-id="7bc7d-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bc7d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7bc7d-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bc7d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="7bc7d-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="7bc7d-106">enuncia Un puntero a un valor booleano que indica si el proceso tiene código administrado.</span><span class="sxs-lookup"><span data-stu-id="7bc7d-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="7bc7d-107">El valor es `true` si el proceso tiene código administrado; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="7bc7d-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bc7d-108">Notas</span><span class="sxs-lookup"><span data-stu-id="7bc7d-108">Remarks</span></span>  
 <span data-ttu-id="7bc7d-109">Dado que la versión actual de `ICorPublishProcess` permite el acceso únicamente a los procesos que tienen código administrado, `IsManaged` siempre devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="7bc7d-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bc7d-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="7bc7d-110">Requirements</span></span>  
 <span data-ttu-id="7bc7d-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bc7d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bc7d-112">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="7bc7d-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="7bc7d-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bc7d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bc7d-114">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bc7d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bc7d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bc7d-115">See also</span></span>

- [<span data-ttu-id="7bc7d-116">ICorPublishProcess (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7bc7d-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
