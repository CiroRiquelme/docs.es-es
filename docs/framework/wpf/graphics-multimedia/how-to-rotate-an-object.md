---
title: 'Cómo: Girar un objeto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: e17d3b7b9986b477df198480129edaf4c139c6bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112068"
---
# <a name="how-to-rotate-an-object"></a><span data-ttu-id="8114f-102">Cómo: Girar un objeto</span><span class="sxs-lookup"><span data-stu-id="8114f-102">How to: Rotate an Object</span></span>
<span data-ttu-id="8114f-103">Este ejemplo muestra cómo girar un objeto.</span><span class="sxs-lookup"><span data-stu-id="8114f-103">This example shows how to rotate an object.</span></span> <span data-ttu-id="8114f-104">El ejemplo primero <xref:System.Windows.Media.RotateTransform> crea a <xref:System.Windows.Media.RotateTransform.Angle%2A> y, a continuación, especifica su en grados.</span><span class="sxs-lookup"><span data-stu-id="8114f-104">The example first creates a <xref:System.Windows.Media.RotateTransform> and then specifies its <xref:System.Windows.Media.RotateTransform.Angle%2A> in degrees.</span></span>  
  
 <span data-ttu-id="8114f-105">En el ejemplo <xref:System.Windows.Shapes.Polyline> siguiente se gira un objeto 45 grados alrededor de su esquina superior izquierda.</span><span class="sxs-lookup"><span data-stu-id="8114f-105">The following example rotates a <xref:System.Windows.Shapes.Polyline> object 45 degrees about its upper-left corner.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8114f-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8114f-106">Example</span></span>  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <span data-ttu-id="8114f-107">Las <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> propiedades y <xref:System.Windows.Media.RotateTransform> las propiedades del especificar el punto sobre el que se gira el objeto.</span><span class="sxs-lookup"><span data-stu-id="8114f-107">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> specify the point about which the object is rotated.</span></span> <span data-ttu-id="8114f-108">Este punto central se expresa en el espacio de coordenadas del elemento que se transforma.</span><span class="sxs-lookup"><span data-stu-id="8114f-108">This center point is expressed in the coordinate space of the element that is transformed.</span></span> <span data-ttu-id="8114f-109">De forma predeterminada, la rotación se aplica a (0,0), que es la esquina superior izquierda del objeto que transformar.</span><span class="sxs-lookup"><span data-stu-id="8114f-109">By default, the rotation is applied to (0,0), which is the upper-left corner of the object to transform.</span></span>  
  
 <span data-ttu-id="8114f-110">En el ejemplo <xref:System.Windows.Shapes.Polyline> siguiente se gira un objeto en el sentido de las agujas del reloj 45 grados sobre el punto (25,50).</span><span class="sxs-lookup"><span data-stu-id="8114f-110">The next example rotates a <xref:System.Windows.Shapes.Polyline> object clockwise 45 degrees about the point (25,50).</span></span>  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 <span data-ttu-id="8114f-111">En la ilustración siguiente se <xref:System.Windows.Media.Transform> muestran los resultados de aplicar a los dos objetos.</span><span class="sxs-lookup"><span data-stu-id="8114f-111">The following illustration shows the results of applying a <xref:System.Windows.Media.Transform> to the two objects.</span></span>  
  
 <span data-ttu-id="8114f-112">![Rotaciones de 45 grados con diferentes centros](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="8114f-112">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
<span data-ttu-id="8114f-113">Dos objetos que se giran 45 grados desde distintos centros de giro</span><span class="sxs-lookup"><span data-stu-id="8114f-113">Two objects that rotate 45 degrees from different rotational centers</span></span>  
  
 <span data-ttu-id="8114f-114">El <xref:System.Windows.Shapes.Polyline> ejemplo anterior es <xref:System.Windows.UIElement>un archivo .</span><span class="sxs-lookup"><span data-stu-id="8114f-114">The <xref:System.Windows.Shapes.Polyline> in the previous examples is a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="8114f-115">Al aplicar <xref:System.Windows.Media.Transform> a <xref:System.Windows.UIElement.RenderTransform%2A> la propiedad <xref:System.Windows.UIElement>de un <xref:System.Windows.UIElement.RenderTransformOrigin%2A> , puede utilizar la <xref:System.Windows.Media.Transform> propiedad para especificar un origen para cada uno de los que aplique al elemento.</span><span class="sxs-lookup"><span data-stu-id="8114f-115">When you apply a <xref:System.Windows.Media.Transform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a <xref:System.Windows.UIElement>, you can use the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to specify an origin for every <xref:System.Windows.Media.Transform> that you apply to the element.</span></span> <span data-ttu-id="8114f-116">Dado <xref:System.Windows.UIElement.RenderTransformOrigin%2A> que la propiedad utiliza coordenadas relativas, puede aplicar una transformación al centro del elemento incluso si no conoce su tamaño.</span><span class="sxs-lookup"><span data-stu-id="8114f-116">Because the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property uses relative coordinates, you can apply a transformation to the center of the element even if you do not know its size.</span></span> <span data-ttu-id="8114f-117">Para obtener más información y un ejemplo, vea [Especificar el origen de una transformación mediante valores relativos](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span><span class="sxs-lookup"><span data-stu-id="8114f-117">For more information and for an example, see [Specify the Origin of a Transform by Using Relative Values](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span></span>  
  
 <span data-ttu-id="8114f-118">Para ver el ejemplo completo, consulte Ejemplo de [transformaciones 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="8114f-118">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8114f-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8114f-119">See also</span></span>

- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="8114f-120">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="8114f-120">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="8114f-121">Temas de información</span><span class="sxs-lookup"><span data-stu-id="8114f-121">How-to Topics</span></span>](transformations-how-to-topics.md)
