---
title: Procedimiento para recuperar una colección de atributos (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
ms.openlocfilehash: 02871b38c3b1a1ed64fa6ca808e193811cd7f721
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347645"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a><span data-ttu-id="ee3bb-102">Procedimiento para recuperar una colección de atributos (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="ee3bb-102">How to retrieve a collection of attributes (LINQ to XML) (C#)</span></span>
<span data-ttu-id="ee3bb-103">En este tema se presenta el método <xref:System.Xml.Linq.XElement.Attributes%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee3bb-103">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="ee3bb-104">Este método recupera los atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="ee3bb-104">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee3bb-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ee3bb-105">Example</span></span>  
 <span data-ttu-id="ee3bb-106">En el ejemplo siguiente se muestra cómo procesar una iteración en la colección de atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="ee3bb-106">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
```csharp  
XElement val = new XElement("Value",  
    new XAttribute("ID", "1243"),  
    new XAttribute("Type", "int"),  
    new XAttribute("ConvertableTo", "double"),  
    "100");  
IEnumerable<XAttribute> listOfAttributes =  
    from att in val.Attributes()  
    select att;  
foreach (XAttribute a in listOfAttributes)  
    Console.WriteLine(a);  
```  
  
 <span data-ttu-id="ee3bb-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="ee3bb-107">This code produces the following output:</span></span>  
  
```output  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee3bb-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee3bb-108">See also</span></span>

- <span data-ttu-id="ee3bb-109">[LINQ to XML Axes (C#)](./linq-to-xml-axes-overview.md) (Ejes de LINQ to XML [C#])</span><span class="sxs-lookup"><span data-stu-id="ee3bb-109">[LINQ to XML Axes (C#)](./linq-to-xml-axes-overview.md)</span></span>
