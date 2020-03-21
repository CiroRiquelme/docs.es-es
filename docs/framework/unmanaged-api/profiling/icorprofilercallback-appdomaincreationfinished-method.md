---
title: ICorProfilerCallback::AppDomainCreationFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
ms.openlocfilehash: 8b3f7712436c001e5cd44f214f6edb06390abd41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177077"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="a9853-102">ICorProfilerCallback::AppDomainCreationFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="a9853-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="a9853-103">Notifica al generador de perfiles que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9853-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9853-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9853-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);
```  
  
## <a name="parameters"></a><span data-ttu-id="a9853-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9853-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="a9853-106">\[en] Identifica el dominio que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="a9853-106">\[in] Identifies the domain which has been created.</span></span>

- `hrStatus`

  <span data-ttu-id="a9853-107">\[en] Un HRESULT que indica si la creación del dominio de aplicación se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a9853-107">\[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="a9853-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a9853-108">Remarks</span></span>  
 <span data-ttu-id="a9853-109">El identificador de aplicación no es `AppDomainCreationFinished` válido para ninguna solicitud de información hasta que se llama al método.</span><span class="sxs-lookup"><span data-stu-id="a9853-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="a9853-110">Algunas partes de la carga `AppDomainCreationFinished` del dominio de aplicación pueden continuar después de la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a9853-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="a9853-111">Un error HRESULT in `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="a9853-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="a9853-112">Sin embargo, un `hrStatus` hRESULT correcto en indica solo que la primera parte de la creación del dominio de aplicación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a9853-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9853-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9853-113">Requirements</span></span>  
 <span data-ttu-id="a9853-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9853-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9853-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a9853-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a9853-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9853-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9853-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9853-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9853-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9853-118">See also</span></span>

- [<span data-ttu-id="a9853-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9853-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
