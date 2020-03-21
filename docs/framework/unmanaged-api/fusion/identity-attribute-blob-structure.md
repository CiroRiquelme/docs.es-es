---
title: IDENTITY_ATTRIBUTE_BLOB (Estructura)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IDENTITY_ATTRIBUTE_BLOB
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE_BLOB
helpviewer_keywords:
- IDENTITY_ATTRIBUTE_BLOB structure [.NET Framework fusion]
ms.assetid: af14ae5f-d226-47dd-ba90-8fc6e6605d4d
topic_type:
- apiref
ms.openlocfilehash: 8f838d5c812842e2a637065b25182b6a12609231
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176557"
---
# <a name="identity_attribute_blob-structure"></a><span data-ttu-id="0f426-102">IDENTITY_ATTRIBUTE_BLOB (Estructura)</span><span class="sxs-lookup"><span data-stu-id="0f426-102">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>
<span data-ttu-id="0f426-103">Contiene información sobre un único atributo en `DWORD`un ensamblado y consta de tres s.</span><span class="sxs-lookup"><span data-stu-id="0f426-103">Contains information about a single attribute in an assembly, and consists of three `DWORD`s.</span></span> <span data-ttu-id="0f426-104">Cada `DWORD` uno es un desplazamiento en `CurrentIntoBuffer` un búfer de caracteres producido por el método de la interfaz [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md)</span><span class="sxs-lookup"><span data-stu-id="0f426-104">Each `DWORD` is an offset into a character buffer produced by the `CurrentIntoBuffer` method of the [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) interface</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f426-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f426-105">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE_BLOB {  
    DWORD  ofsNamespace;  
    DWORD  ofsName;  
    DWORD  ofsValue;  
}   IDENTITY_ATTRIBUTE_BLOB;  
```  
  
## <a name="members"></a><span data-ttu-id="0f426-106">Members</span><span class="sxs-lookup"><span data-stu-id="0f426-106">Members</span></span>  
  
|<span data-ttu-id="0f426-107">Member</span><span class="sxs-lookup"><span data-stu-id="0f426-107">Member</span></span>|<span data-ttu-id="0f426-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f426-108">Description</span></span>|  
|------------|-----------------|  
|`ofsNamespace`|<span data-ttu-id="0f426-109">El primer desplazamiento en el búfer de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f426-109">The first offset into the character buffer.</span></span> <span data-ttu-id="0f426-110">Este desplazamiento no va seguido del espacio de nombres del atributo, sino de una serie de caracteres nulos.</span><span class="sxs-lookup"><span data-stu-id="0f426-110">This offset is not followed by the attribute's namespace, but by a series of null characters.</span></span> <span data-ttu-id="0f426-111">Por lo tanto, no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="0f426-111">Therefore, it is not used.</span></span>|  
|`ofsName`|<span data-ttu-id="0f426-112">El segundo desplazamiento en el búfer de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f426-112">The second offset into the character buffer.</span></span> <span data-ttu-id="0f426-113">Esta ubicación marca el inicio del nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="0f426-113">This location marks the start of the attribute's name.</span></span>|  
|`ofsValue`|<span data-ttu-id="0f426-114">El tercer desplazamiento en el búfer de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f426-114">The third offset into the character buffer.</span></span> <span data-ttu-id="0f426-115">Esta ubicación marca el inicio del valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="0f426-115">This location marks the start of the attribute's value.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="0f426-116">Muestra</span><span class="sxs-lookup"><span data-stu-id="0f426-116">Sample</span></span>  
 <span data-ttu-id="0f426-117">En el ejemplo siguiente se muestran varios pasos `IDENTITY_ATTRIBUTE_BLOB` básicos, que finalmente dan como resultado una estructura rellenada:</span><span class="sxs-lookup"><span data-stu-id="0f426-117">The following example illustrates several basic steps, which eventually result in a populated `IDENTITY_ATTRIBUTE_BLOB` structure:</span></span>  
  
1. <span data-ttu-id="0f426-118">Obtenga un [IReferenceIdentity](ireferenceidentity-interface.md) para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0f426-118">Obtain an [IReferenceIdentity](ireferenceidentity-interface.md) for the assembly.</span></span>  
  
2. <span data-ttu-id="0f426-119">Llame `IReferenceIdentity::EnumAttributes` al método y obtenga una [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md).</span><span class="sxs-lookup"><span data-stu-id="0f426-119">Call the `IReferenceIdentity::EnumAttributes` method, and obtain an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md).</span></span>  
  
3. <span data-ttu-id="0f426-120">Cree un búfer de caracteres `IDENTITY_ATTRIBUTE_BLOB` y conselle como una estructura.</span><span class="sxs-lookup"><span data-stu-id="0f426-120">Create a character buffer, and cast it as an `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
4. <span data-ttu-id="0f426-121">Llame `CurrentIntoBuffer` al método `IEnumIDENTITY_ATTRIBUTE` de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="0f426-121">Call the `CurrentIntoBuffer` method of the `IEnumIDENTITY_ATTRIBUTE` interface.</span></span> <span data-ttu-id="0f426-122">Este método copia `Namespace` `Name`los `Value` atributos , y en el búfer de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f426-122">This method copies the attributes `Namespace`, `Name`, and `Value` into the character buffer.</span></span> <span data-ttu-id="0f426-123">Los tres desplazamientos a esas cadenas `IDENTITY_ATTRIBUTE_BLOB` estarán disponibles en la estructura.</span><span class="sxs-lookup"><span data-stu-id="0f426-123">The three offsets to those strings will become available in the `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
```cpp  
// EnumAssemblyAttributes.cpp : main project file.  
  
#include "stdafx.h"  
  
#include "fusion.h"  
#include "windows.h"  
#include "stdio.h"  
#include "mscoree.h"  
#include "isolation.h"  
  
typedef HRESULT (__stdcall *PFNGETREF)(LPCWSTR pwzFile, REFIID riid, IUnknown **ppUnk);  
typedef HRESULT (__stdcall *PFNGETAUTH)(IIdentityAuthority **ppIIdentityAuthority);  
  
PFNGETREF                   g_pfnGetAssemblyIdentityFromFile = NULL;  
PFNGETAUTH                  g_pfnGetIdentityAuthority = NULL;  
IUnknown                    *g_pUnk = NULL;  
  
bool Init()  
{  
    HRESULT     hr = S_OK;  
    DWORD       dwSize = 0;  
    bool        bRC = false;  
  
    hr = CorBindToRuntimeEx(NULL, L"wks", 0, CLSID_CorRuntimeHost,  
                           IID_ICorRuntimeHost, (void **)&g_pUnk);  
    if(FAILED(hr)) {  
        printf("Error: Failed to initialize CLR runtime! hr = 0x%0x\n",  
                hr);  
        goto Exit;  
    }  
  
    if (SUCCEEDED(hr)) {  
        hr = GetRealProcAddress("GetAssemblyIdentityFromFile",  
                         (VOID **)&g_pfnGetAssemblyIdentityFromFile);  
    }  
  
    if (SUCCEEDED(hr)) {  
        hr = GetRealProcAddress("GetIdentityAuthority",  
                                (VOID **)&g_pfnGetIdentityAuthority);  
    }  
  
    if (!g_pfnGetAssemblyIdentityFromFile ||
        !g_pfnGetIdentityAuthority)  
    {  
        printf("Error: Cannot get required APIs from fusion.dll!\n");  
        goto Exit;  
    }  
  
    bRC = true;  
  
Exit:  
    return bRC;  
}  
  
void Shutdown()  
{  
    if(g_pUnk) {  
        g_pUnk->Release();  
        g_pUnk = NULL;  
    }  
}  
  
void Usage()  
{  
    printf("EnumAssemblyAttributes: A tool to enumerate the identity
            attributes of a given assembly.\n\n");  
    printf("Usage: EnumAssemblyAttributes AssemblyFilePath\n");  
    printf("\n");  
}  
  
int _cdecl wmain(int argc, LPCWSTR argv[])  
{  
    int     iResult = 1;  
    IUnknown                    *pUnk  = NULL;  
    IReferenceIdentity          *pRef  = NULL;  
    HRESULT                     hr     = S_OK;
    IEnumIDENTITY_ATTRIBUTE     *pEnum = NULL;  
    BYTE                        abData[1024];  
    DWORD                       cbAvailable;  
    DWORD                       cbUsed;  
    IDENTITY_ATTRIBUTE_BLOB     *pBlob;  
  
    if(argc != 2) {  
        Usage();  
        goto Exit;  
    }  
  
    if(!Init()) {  
        printf("Failure initializing EnumIdAttr.\n");  
        goto Exit;  
    }  
  
    hr = g_pfnGetAssemblyIdentityFromFile(argv[1],
                            __uuidof(IReferenceIdentity), &pUnk);  
  
    if (FAILED(hr)) {  
        printf("GetAssemblyIdentityFromFile failed with hr = 0x%x",
                hr);  
        goto Exit;  
    }  
  
    hr = pUnk->QueryInterface(__uuidof(IReferenceIdentity),
                              (void**)&pRef);  
    if (FAILED(hr)) {  
        goto Exit;  
    }  
  
    hr = pRef->EnumAttributes(&pEnum);  
    if (FAILED(hr)) {  
        printf("IReferenceIdentity::EnumAttributes failed with hr =
                0x%x", hr);  
        goto Exit;  
    }  
  
    pBlob = (IDENTITY_ATTRIBUTE_BLOB *)(abData);  
    while (1) {  
        cbAvailable = sizeof(abData);  
        hr = pEnum->CurrentIntoBuffer(cbAvailable, abData, &cbUsed);  
        if (FAILED(hr)) {  
            printf("IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer failed
                    with hr = 0x%x", hr);  
            goto Exit;  
        }  
  
        if (! cbUsed) {  
            break;  
        }  
  
        LPWSTR pwzNameSpace = (LPWSTR)(abData + pBlob->ofsNamespace);  
        LPWSTR pwzName      = (LPWSTR)(abData + pBlob->ofsName);  
        LPWSTR pwzValue     = (LPWSTR)(abData + pBlob->ofsValue);  
        printf("%ws: %ws = %ws\n", pwzNameSpace, pwzName, pwzValue);  
  
        hr = pEnum->Skip(1);  
        if (FAILED(hr)) {  
            printf("IEnumIDENTITY_ATTRIBUTE::Skip failed with hr =
                    0x%x", hr);  
            goto Exit;  
        }  
    }  
  
    iResult = 0;  
  
Exit:  
  
    Shutdown();  
  
    if (pUnk) {  
        pUnk->Release();  
    }  
  
    if (pRef) {  
        pRef->Release();  
    }  
  
    if (pEnum) {  
        pEnum->Release();  
    }  
  
    return iResult;  
}  
```  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="0f426-124">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f426-124">To run the sample</span></span>  
 <span data-ttu-id="0f426-125">C:\\> EnumAssemblyAttributes.exe C:-WINDOWS-Microsoft.NET-Framework-v2.0.50727-System.dll</span><span class="sxs-lookup"><span data-stu-id="0f426-125">C:\\> EnumAssemblyAttributes.exe C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\System.dll</span></span>  
  
### <a name="sample-output"></a><span data-ttu-id="0f426-126">Salida de ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f426-126">Sample output</span></span>  
 <span data-ttu-id="0f426-127">Cultura - neutral</span><span class="sxs-lookup"><span data-stu-id="0f426-127">Culture = neutral</span></span>  
  
 <span data-ttu-id="0f426-128">nombre : Sistema</span><span class="sxs-lookup"><span data-stu-id="0f426-128">name = System</span></span>  
  
 <span data-ttu-id="0f426-129">processorArchitecture - MSIL</span><span class="sxs-lookup"><span data-stu-id="0f426-129">processorArchitecture = MSIL</span></span>  
  
 <span data-ttu-id="0f426-130">PublicKeyToken á b77a5c561934e089</span><span class="sxs-lookup"><span data-stu-id="0f426-130">PublicKeyToken = b77a5c561934e089</span></span>  
  
 <span data-ttu-id="0f426-131">Versión 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="0f426-131">Version = 2.0.0.0</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f426-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f426-132">Requirements</span></span>  
 <span data-ttu-id="0f426-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f426-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f426-134">**Encabezado:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="0f426-134">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="0f426-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f426-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f426-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0f426-136">See also</span></span>

- [<span data-ttu-id="0f426-137">IReferenceIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f426-137">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
- [<span data-ttu-id="0f426-138">IEnumIDENTITY_ATTRIBUTE (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f426-138">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)
- [<span data-ttu-id="0f426-139">IDENTITY_ATTRIBUTE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="0f426-139">IDENTITY_ATTRIBUTE Structure</span></span>](identity-attribute-structure.md)
- [<span data-ttu-id="0f426-140">Estructuras de fusión</span><span class="sxs-lookup"><span data-stu-id="0f426-140">Fusion Structures</span></span>](fusion-structures.md)
