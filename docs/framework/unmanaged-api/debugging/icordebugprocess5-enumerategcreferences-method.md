---
title: ICorDebugProcess5::EnumerateGCReferences (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
ms.openlocfilehash: a97c14d83f99c847bb8569a33e175ab6eb5bccd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178621"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="f2f50-102">ICorDebugProcess5::EnumerateGCReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="f2f50-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="f2f50-103">Obtiene un enumerador para todos los objetos que se van a recopilar como elementos no utilizados en un proceso.</span><span class="sxs-lookup"><span data-stu-id="f2f50-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2f50-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2f50-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2f50-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2f50-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="f2f50-106">[en] Un valor booleano que indica si también se van a enumerar las referencias débiles.</span><span class="sxs-lookup"><span data-stu-id="f2f50-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="f2f50-107">Si `enumerateWeakReferences` `true`es `ppEnum` , el enumerador incluye referencias seguras y referencias débiles.</span><span class="sxs-lookup"><span data-stu-id="f2f50-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="f2f50-108">Si `enumerateWeakReferences` `false`es , el enumerador solo incluye referencias seguras.</span><span class="sxs-lookup"><span data-stu-id="f2f50-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="f2f50-109">[fuera] Puntero a la dirección de un [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) que es un enumerador para los objetos que se van a recopilar como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f2f50-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2f50-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f2f50-110">Remarks</span></span>  
 <span data-ttu-id="f2f50-111">Este método proporciona una manera de determinar la cadena de enraizamiento completa para cualquier objeto administrado en un proceso y se puede usar para determinar por qué un objeto sigue vivo.</span><span class="sxs-lookup"><span data-stu-id="f2f50-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2f50-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2f50-112">Requirements</span></span>  
 <span data-ttu-id="f2f50-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2f50-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2f50-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2f50-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2f50-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2f50-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2f50-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2f50-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2f50-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2f50-117">See also</span></span>

- [<span data-ttu-id="f2f50-118">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2f50-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="f2f50-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f2f50-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
