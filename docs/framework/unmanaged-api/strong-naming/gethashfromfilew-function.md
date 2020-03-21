---
title: GetHashFromFileW (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
ms.openlocfilehash: 9db583c7064cb910b29e84437f31143dac0d3ec9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175088"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="abf88-102">GetHashFromFileW (Función)</span><span class="sxs-lookup"><span data-stu-id="abf88-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="abf88-103">Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="abf88-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="abf88-104">Esta función ha quedado en desuso.</span><span class="sxs-lookup"><span data-stu-id="abf88-104">This function has been deprecated.</span></span> <span data-ttu-id="abf88-105">Utilice el método [ICLRStrongName::GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="abf88-105">Use the [ICLRStrongName::GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abf88-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abf88-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="abf88-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="abf88-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="abf88-108">[en] El nombre Unicode del archivo que se ha hash.</span><span class="sxs-lookup"><span data-stu-id="abf88-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="abf88-109">[adentro, fuera] El algoritmo que se va a utilizar al generar el hash.</span><span class="sxs-lookup"><span data-stu-id="abf88-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="abf88-110">Los algoritmos válidos son los definidos por Win32 CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="abf88-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="abf88-111">Si `piHashAlg` se establece en 0, se utiliza el algoritmo predeterminado CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="abf88-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="abf88-112">[fuera] Matriz de bytes que contiene el hash generado.</span><span class="sxs-lookup"><span data-stu-id="abf88-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="abf88-113">[en] El tamaño máximo del búfer `pbHash`al que apunta .</span><span class="sxs-lookup"><span data-stu-id="abf88-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="abf88-114">[fuera] El tamaño, en `pbHash`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="abf88-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abf88-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="abf88-115">Remarks</span></span>  
 <span data-ttu-id="abf88-116">Esta función es la misma que [GetHashFromFile](gethashfromfile-function.md), excepto que la especificación de nombre de archivo es Unicode en lugar de ANSI.</span><span class="sxs-lookup"><span data-stu-id="abf88-116">This function is the same as [GetHashFromFile](gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abf88-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="abf88-117">Requirements</span></span>  
 <span data-ttu-id="abf88-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abf88-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abf88-119">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="abf88-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="abf88-120">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="abf88-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="abf88-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abf88-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf88-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="abf88-122">See also</span></span>

- [<span data-ttu-id="abf88-123">Método GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="abf88-123">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="abf88-124">Método GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="abf88-124">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="abf88-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="abf88-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
