---
title: 'Cómo: Buscar elementos con un atributo específico (XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 4bb38d2c-bc7c-4196-8909-aaf41fb86b28
ms.openlocfilehash: 36f725a7684dc009dbfb956a1584fd6ca5e487b0
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78267046"
---
# <a name="how-to-find-elements-with-a-specific-attribute-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="a6022-102">Cómo: Buscar elementos con un atributo específico (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6022-102">How to: Find Elements with a Specific Attribute (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="a6022-103">En ocasiones, deseará buscar todos los elementos que tengan un atributo en particular.</span><span class="sxs-lookup"><span data-stu-id="a6022-103">Sometimes you want to find all elements that have a specific attribute.</span></span> <span data-ttu-id="a6022-104">Pero no le preocupa cuáles es el contenido del atributo.</span><span class="sxs-lookup"><span data-stu-id="a6022-104">You are not concerned about the contents of the attribute.</span></span> <span data-ttu-id="a6022-105">En vez de ello, desea realizar la selección en función de si existe o no el atributo.</span><span class="sxs-lookup"><span data-stu-id="a6022-105">Instead, you want to select based on the existence of the attribute.</span></span>  
  
 <span data-ttu-id="a6022-106">La expresión XPath es:</span><span class="sxs-lookup"><span data-stu-id="a6022-106">The XPath expression is:</span></span>  
  
 `./*[@Select]`  
  
## <a name="example"></a><span data-ttu-id="a6022-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6022-107">Example</span></span>  
 <span data-ttu-id="a6022-108">El siguiente código selecciona únicamente los elementos que tengan el atributo `Select`.</span><span class="sxs-lookup"><span data-stu-id="a6022-108">The following code selects just the elements that have the `Select` attribute.</span></span>  
  
```vb  
Dim doc As XElement = _
    <Root>  
        <Child1>1</Child1>  
        <Child2 Select='true'>2</Child2>  
        <Child3>3</Child3>  
        <Child4 Select='true'>4</Child4>  
        <Child5>5</Child5>  
    </Root>  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    From el In doc.Elements() _  
    Where el.@Select <> Nothing _  
    Select el  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = DirectCast(doc.XPathEvaluate _  
    ("./*[@Select]"), IEnumerable).Cast(Of XElement)()  
  
If list1.Count() = list2.Count() And _  
    list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="a6022-109">En este ejemplo se produce la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="a6022-109">This example produces the following output:</span></span>  
  
```console
Results are identical  
<Child2 Select="true">2</Child2>  
<Child4 Select="true">4</Child4>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6022-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6022-110">See also</span></span>

- [<span data-ttu-id="a6022-111">LINQ to XMLLINQ to XML para usuarios de XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6022-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
