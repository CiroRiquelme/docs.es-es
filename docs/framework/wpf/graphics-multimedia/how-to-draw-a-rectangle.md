---
title: 'Cómo: Dibujar un rectángulo'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 95191e9d90bc2ac32902399125d9a51192e897bf
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452940"
---
# <a name="how-to-draw-a-rectangle"></a><span data-ttu-id="bc8fe-102">Cómo: Dibujar un rectángulo</span><span class="sxs-lookup"><span data-stu-id="bc8fe-102">How to: Draw a Rectangle</span></span>
<span data-ttu-id="bc8fe-103">En este ejemplo se muestra cómo dibujar un rectángulo mediante el elemento <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="bc8fe-103">This example shows how to draw a rectangle by using the <xref:System.Windows.Shapes.Rectangle> element.</span></span>  
  
 <span data-ttu-id="bc8fe-104">Para dibujar un rectángulo, cree un elemento <xref:System.Windows.Shapes.Rectangle> y especifique su <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc8fe-104">To draw a rectangle, create a <xref:System.Windows.Shapes.Rectangle> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="bc8fe-105">Para pintar el interior del rectángulo, establezca su <xref:System.Windows.Shapes.Shape.Fill%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc8fe-105">To paint the inside of the rectangle, set its <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="bc8fe-106">Para asignar un contorno al rectángulo, use sus propiedades <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc8fe-106">To give the rectangle an outline, use its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties.</span></span>  
  
 <span data-ttu-id="bc8fe-107">Para dar al rectángulo esquinas redondeadas, especifique las propiedades <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> opcionales.</span><span class="sxs-lookup"><span data-stu-id="bc8fe-107">To give the rectangle rounded corners, specify the optional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="bc8fe-108">Las propiedades <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> establecen los radios de los ejes x e y de la elipse que se usa para redondear los vértices del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="bc8fe-108">The <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties set the x-axis and y-axis radii of the ellipse that is used to round the corners of the rectangle.</span></span>  
  
 <span data-ttu-id="bc8fe-109">En el ejemplo siguiente, se dibujan dos elementos <xref:System.Windows.Shapes.Rectangle> en una <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="bc8fe-109">In the following example, two <xref:System.Windows.Shapes.Rectangle> elements are drawn in a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="bc8fe-110">El primer rectángulo tiene un <xref:System.Windows.Media.Brushes.Blue%2A> interior.</span><span class="sxs-lookup"><span data-stu-id="bc8fe-110">The first rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior.</span></span> <span data-ttu-id="bc8fe-111">El segundo rectángulo tiene un <xref:System.Windows.Media.Brushes.Blue%2A> interior, un esquema <xref:System.Windows.Media.Brushes.Black%2A> y esquinas redondeadas.</span><span class="sxs-lookup"><span data-stu-id="bc8fe-111">The second rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior, a <xref:System.Windows.Media.Brushes.Black%2A> outline, and rounded corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc8fe-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc8fe-112">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#Rectangle1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 <span data-ttu-id="bc8fe-113">Aunque en este ejemplo se usa un <xref:System.Windows.Controls.Canvas> para contener los rectángulos, puede utilizar elementos de rectángulo (y todos los demás elementos de forma) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido que no sea de texto.</span><span class="sxs-lookup"><span data-stu-id="bc8fe-113">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the rectangles, you can use rectangle elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span> <span data-ttu-id="bc8fe-114">De hecho, los rectángulos son especialmente útiles para proporcionar el fondo para partes de los paneles de <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="bc8fe-114">In fact, rectangles are particularly useful for providing backgrounds for portions of <xref:System.Windows.Controls.Grid> panels.</span></span> <span data-ttu-id="bc8fe-115">Para obtener un ejemplo, vea la [información general](../advanced/table-overview.md)de la tabla.</span><span class="sxs-lookup"><span data-stu-id="bc8fe-115">For an example, see the [Table Overview](../advanced/table-overview.md).</span></span>  
  
 <span data-ttu-id="bc8fe-116">Este ejemplo forma parte de un ejemplo más grande; para obtener el ejemplo completo, vea [ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="bc8fe-116">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc8fe-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc8fe-117">See also</span></span>

- <xref:System.Windows.Shapes.Rectangle>
- [<span data-ttu-id="bc8fe-118">Ejemplo de elementos de forma</span><span class="sxs-lookup"><span data-stu-id="bc8fe-118">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [<span data-ttu-id="bc8fe-119">Información general sobre formas y dibujo básico en WPF</span><span class="sxs-lookup"><span data-stu-id="bc8fe-119">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="bc8fe-120">Información general sobre las tablas</span><span class="sxs-lookup"><span data-stu-id="bc8fe-120">Table Overview</span></span>](../advanced/table-overview.md)
