---
title: IMetaDataImport::EnumFieldsWithName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFieldsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type:
- apiref
ms.openlocfilehash: bb8b531a884c9d3c2f33aa4aec5c4dbeaafe2b66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177340"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="8d5ed-102">IMetaDataImport::EnumFieldsWithName (Método)</span><span class="sxs-lookup"><span data-stu-id="8d5ed-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="8d5ed-103">Enumera los tokens de FieldDef del tipo especificado con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="8d5ed-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d5ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d5ed-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]  mdTypeDef       cl,
   [in]  LPCWSTR         szName,
   [out] mdFieldDef      rFields[],
   [in]  ULONG           cMax,
   [out] ULONG           *pcTokens
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d5ed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8d5ed-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8d5ed-106">[adentro, fuera] Un puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="8d5ed-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="8d5ed-107">[en] El token del tipo cuyos campos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="8d5ed-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="8d5ed-108">[en] El nombre del campo que limita el ámbito de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="8d5ed-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="8d5ed-109">[fuera] Matriz utilizada para almacenar los tokens FieldDef.</span><span class="sxs-lookup"><span data-stu-id="8d5ed-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8d5ed-110">[in] Tamaño máximo de la matriz `rFields`.</span><span class="sxs-lookup"><span data-stu-id="8d5ed-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8d5ed-111">[fuera] El número real de tokens `rFields`FieldDef devueltos en .</span><span class="sxs-lookup"><span data-stu-id="8d5ed-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d5ed-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8d5ed-112">Remarks</span></span>  
 <span data-ttu-id="8d5ed-113">A diferencia de [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` descarta todos los tokens de campo que no tienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="8d5ed-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d5ed-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8d5ed-114">Return Value</span></span>  
  
|<span data-ttu-id="8d5ed-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8d5ed-115">HRESULT</span></span>|<span data-ttu-id="8d5ed-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d5ed-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8d5ed-117">`EnumFieldsWithName`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="8d5ed-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8d5ed-118">No hay campos que enumerar.</span><span class="sxs-lookup"><span data-stu-id="8d5ed-118">There are no fields to enumerate.</span></span> <span data-ttu-id="8d5ed-119">En ese `pcTokens` caso, es cero.</span><span class="sxs-lookup"><span data-stu-id="8d5ed-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8d5ed-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d5ed-120">Requirements</span></span>  
 <span data-ttu-id="8d5ed-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d5ed-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d5ed-122">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8d5ed-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d5ed-123">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d5ed-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8d5ed-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d5ed-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d5ed-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d5ed-125">See also</span></span>

- [<span data-ttu-id="8d5ed-126">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d5ed-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8d5ed-127">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d5ed-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
