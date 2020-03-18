---
title: 'Cómo: convertir una WebRequest a propiedades específicas del protocolo de acceso'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
ms.openlocfilehash: d38a40aa1e6e3db769aedfc440077721cdfaf06d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180755"
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a><span data-ttu-id="c41c1-102">Cómo: convertir una WebRequest a propiedades específicas del protocolo de acceso</span><span class="sxs-lookup"><span data-stu-id="c41c1-102">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>
<span data-ttu-id="c41c1-103">En este ejemplo se muestra cómo convertir una WebRequest de manera que pueda tener acceso a las propiedades específicas del protocolo.</span><span class="sxs-lookup"><span data-stu-id="c41c1-103">This example shows how to typecast a WebRequest so that you can access protocol specific properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c41c1-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c41c1-104">Example</span></span>  
  
```csharp  
HttpWebRequest httpreq =
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a><span data-ttu-id="c41c1-105">Vea también</span><span class="sxs-lookup"><span data-stu-id="c41c1-105">See also</span></span>

- [<span data-ttu-id="c41c1-106">Programar protocolos acoplables</span><span class="sxs-lookup"><span data-stu-id="c41c1-106">Programming Pluggable Protocols</span></span>](programming-pluggable-protocols.md)
