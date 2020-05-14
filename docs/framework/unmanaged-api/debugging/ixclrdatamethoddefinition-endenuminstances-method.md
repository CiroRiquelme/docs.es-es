---
title: 'IXCLRDataMethodDefinition:: EndEnumInstances (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: febe6766c7a35228820421eee975c777988efd1f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396491"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="6ea79-102">IXCLRDataMethodDefinition:: EndEnumInstances (método)</span><span class="sxs-lookup"><span data-stu-id="6ea79-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="6ea79-103">Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="6ea79-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6ea79-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ea79-104">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="6ea79-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6ea79-105">Parameters</span></span>

`handle`\
<span data-ttu-id="6ea79-106">enuncia Identificador para enumerar las instancias de.</span><span class="sxs-lookup"><span data-stu-id="6ea79-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ea79-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6ea79-107">Remarks</span></span>

<span data-ttu-id="6ea79-108">El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la séptima ranura de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="6ea79-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 7th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6ea79-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ea79-109">Requirements</span></span>

<span data-ttu-id="6ea79-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ea79-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6ea79-111">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="6ea79-111">**Header:** None</span></span>  
<span data-ttu-id="6ea79-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="6ea79-112">**Library:** None</span></span>  
<span data-ttu-id="6ea79-113">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6ea79-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6ea79-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ea79-114">See also</span></span>

- [<span data-ttu-id="6ea79-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="6ea79-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="6ea79-116">Interfaz IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="6ea79-116">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
