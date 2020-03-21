---
title: CorExitProcess (Función)
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
ms.openlocfilehash: 44578595b3cb790570c5359e714bd39c109cf1f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176466"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="02390-102">CorExitProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="02390-102">CorExitProcess Function</span></span>
<span data-ttu-id="02390-103">Cierra el proceso no administrado actual.</span><span class="sxs-lookup"><span data-stu-id="02390-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="02390-104">Esta función ha quedado en desuso en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="02390-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="02390-105">Utilice el [método ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="02390-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02390-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02390-106">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02390-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="02390-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="02390-108">Entero que especifica el código de salida del proceso.</span><span class="sxs-lookup"><span data-stu-id="02390-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02390-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="02390-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="02390-110">A partir de .NET `CorExitProcess` Framework 4, sale de cada tiempo de ejecución iniciado en el proceso, no solo del tiempo de ejecución al que se han enlazado las API heredadas.</span><span class="sxs-lookup"><span data-stu-id="02390-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02390-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02390-111">Requirements</span></span>  
 <span data-ttu-id="02390-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02390-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02390-113">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="02390-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02390-114">**Biblioteca:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="02390-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02390-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02390-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02390-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02390-116">See also</span></span>

- [<span data-ttu-id="02390-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="02390-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
