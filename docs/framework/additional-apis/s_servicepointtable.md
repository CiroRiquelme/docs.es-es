---
title: ServicePointManager. s_ServicePointTable campo
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
ms.openlocfilehash: 272a0c113fd70d804c763ba0e7e6e9a4a4ee04ce
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214919"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="e8ee3-102">ServicePointManager. s\_campo ServicePointTable</span><span class="sxs-lookup"><span data-stu-id="e8ee3-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="e8ee3-103">`ServicePointManager.s_ServicePointTable` es una <xref:System.Collections.Hashtable> que contiene la lista de conexiones HTTP activas (<xref:System.Net.ServicePoint>s) en el <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="e8ee3-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="e8ee3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8ee3-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="e8ee3-105">El campo `ServicePointManager.s_ServicePointTable` es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="e8ee3-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="e8ee3-106">Microsoft no admite el uso de este campo en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="e8ee3-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e8ee3-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8ee3-107">Requirements</span></span>

<span data-ttu-id="e8ee3-108">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="e8ee3-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="e8ee3-109">**Ensamblado:** Sistema (en System. dll)</span><span class="sxs-lookup"><span data-stu-id="e8ee3-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="e8ee3-110">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="e8ee3-110">**.NET Framework versions:** Available since 2.0.</span></span>
