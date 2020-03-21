---
title: IMetaDataEmit::DeleteToken (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteToken
helpviewer_keywords:
- DeleteToken method [.NET Framework metadata]
- IMetaDataEmit::DeleteToken method [.NET Framework metadata]
ms.assetid: a4926d0a-261b-46b1-9994-82633661a64b
topic_type:
- apiref
ms.openlocfilehash: 3b8aed6522b1c7eb2d8916f71d8a66b367623765
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177603"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="fa369-102">IMetaDataEmit::DeleteToken (Método)</span><span class="sxs-lookup"><span data-stu-id="fa369-102">IMetaDataEmit::DeleteToken Method</span></span>
<span data-ttu-id="fa369-103">Elimina el token especificado del ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="fa369-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa369-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa369-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteToken (
    [in]  mdToken     tkObj
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa369-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa369-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="fa369-106">[en] El token que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="fa369-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa369-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa369-107">Requirements</span></span>  
 <span data-ttu-id="fa369-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa369-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa369-109">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fa369-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa369-110">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa369-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa369-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa369-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa369-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa369-112">See also</span></span>

- [<span data-ttu-id="fa369-113">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa369-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="fa369-114">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa369-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
