---
title: ICorPublish::GetProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
ms.openlocfilehash: 0368349e6c6a566cb569738bf3bda40eb9f5de96
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790734"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="4cb53-102">ICorPublish::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="4cb53-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="4cb53-103">Obtiene una instancia de [ICorPublishProcess](icorpublishprocess-interface.md) que representa el proceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="4cb53-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cb53-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4cb53-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cb53-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4cb53-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="4cb53-106">de Identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="4cb53-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="4cb53-107">enuncia Puntero a la dirección de una instancia de `ICorPublishProcess` que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="4cb53-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cb53-108">Notas</span><span class="sxs-lookup"><span data-stu-id="4cb53-108">Remarks</span></span>  
 <span data-ttu-id="4cb53-109">`GetProcess` produce un error si el proceso no existe o no es un proceso administrado que el usuario actual puede depurar.</span><span class="sxs-lookup"><span data-stu-id="4cb53-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cb53-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4cb53-110">Requirements</span></span>  
 <span data-ttu-id="4cb53-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cb53-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cb53-112">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="4cb53-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="4cb53-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cb53-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cb53-114">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cb53-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb53-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cb53-115">See also</span></span>

- [<span data-ttu-id="4cb53-116">ICorPublish (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4cb53-116">ICorPublish Interface</span></span>](icorpublish-interface.md)
