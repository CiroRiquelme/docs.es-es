---
title: ICorDebugVariableSymbol::SetValue (método)
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
ms.openlocfilehash: 38afd355938ec1beb1dbfd33de36116d25b07b4e
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397072"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a><span data-ttu-id="445e6-102">ICorDebugVariableSymbol::SetValue (método)</span><span class="sxs-lookup"><span data-stu-id="445e6-102">ICorDebugVariableSymbol::SetValue Method</span></span>
<span data-ttu-id="445e6-103">Asigna el valor de una matriz de bytes a una variable.</span><span class="sxs-lookup"><span data-stu-id="445e6-103">Assigns the value of a byte array to a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="445e6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="445e6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="445e6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="445e6-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="445e6-106">[in] Desplazamiento inicial de la variable en la que se va a establecer el valor.</span><span class="sxs-lookup"><span data-stu-id="445e6-106">[in] The starting offset in the variable at which to set the value.</span></span> <span data-ttu-id="445e6-107">Este parámetro se utiliza cuando se escribe en campos de miembro de un objeto.</span><span class="sxs-lookup"><span data-stu-id="445e6-107">This parameter is used when writing to member fields in an object.</span></span>  
  
 `threadID`  
 <span data-ttu-id="445e6-108">[in] Identificador de subproceso del subproceso cuyo contexto debe actualizarse para reflejar el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="445e6-108">[in] The thread identifier of the thread whose context must be updated to reflect the new value.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="445e6-109">[in] Tamaño en bytes del contexto del subproceso.</span><span class="sxs-lookup"><span data-stu-id="445e6-109">[in] The size in bytes of the thread context.</span></span>  
  
 `context`  
 <span data-ttu-id="445e6-110">[in] Contexto del subproceso utilizado para escribir el valor.</span><span class="sxs-lookup"><span data-stu-id="445e6-110">[in] The thread context used to write the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="445e6-111">[in] Tamaño del búfer `pValue` en bytes.</span><span class="sxs-lookup"><span data-stu-id="445e6-111">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="445e6-112">[in] Búfer que contiene el valor que se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="445e6-112">[in] The buffer that contains the value to set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="445e6-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="445e6-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="445e6-114">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="445e6-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="445e6-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="445e6-115">Requirements</span></span>  
 <span data-ttu-id="445e6-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="445e6-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="445e6-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="445e6-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="445e6-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="445e6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="445e6-119">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="445e6-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="445e6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="445e6-120">See also</span></span>

- [<span data-ttu-id="445e6-121">Interfaz ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="445e6-121">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="445e6-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="445e6-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
