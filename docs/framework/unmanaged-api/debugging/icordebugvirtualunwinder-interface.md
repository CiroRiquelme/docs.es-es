---
title: ICorDebugVirtualUnwinder (Interfaz)
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: 065f71e45c2a56dbaa16a45f70958ca3dea80c48
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790825"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="792c6-102">ICorDebugVirtualUnwinder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="792c6-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="792c6-103">Proporciona métodos que ayudan al desenredo de la pila.</span><span class="sxs-lookup"><span data-stu-id="792c6-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="792c6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="792c6-104">Methods</span></span>  
  
|<span data-ttu-id="792c6-105">Método</span><span class="sxs-lookup"><span data-stu-id="792c6-105">Method</span></span>|<span data-ttu-id="792c6-106">Name</span><span class="sxs-lookup"><span data-stu-id="792c6-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="792c6-107">GetContext (método)</span><span class="sxs-lookup"><span data-stu-id="792c6-107">GetContext Method</span></span>](icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="792c6-108">Obtiene el contexto actual de este responsable del desenredado.</span><span class="sxs-lookup"><span data-stu-id="792c6-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="792c6-109">Next (método)</span><span class="sxs-lookup"><span data-stu-id="792c6-109">Next Method</span></span>](icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="792c6-110">Avanza hasta el contexto del llamador.</span><span class="sxs-lookup"><span data-stu-id="792c6-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="792c6-111">Notas</span><span class="sxs-lookup"><span data-stu-id="792c6-111">Remarks</span></span>  
 <span data-ttu-id="792c6-112">Los miembros de la interfaz `ICorDebugVirtualUnwinder` se implementan mediante el depurador para ayudar al desenredo de pila.</span><span class="sxs-lookup"><span data-stu-id="792c6-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="792c6-113">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="792c6-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="792c6-114">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="792c6-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="792c6-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="792c6-115">Requirements</span></span>  
 <span data-ttu-id="792c6-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="792c6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="792c6-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="792c6-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="792c6-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="792c6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="792c6-119">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="792c6-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="792c6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="792c6-120">See also</span></span>

- [<span data-ttu-id="792c6-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="792c6-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="792c6-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="792c6-122">Debugging</span></span>](index.md)
