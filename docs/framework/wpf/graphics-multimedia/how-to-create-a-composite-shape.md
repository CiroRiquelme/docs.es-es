---
title: 'Cómo: Crear una forma compuesta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: c56053f2b07d6055deac5097a68fd7b80ad704ba
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452102"
---
# <a name="how-to-create-a-composite-shape"></a><span data-ttu-id="d6bec-102">Cómo: Crear una forma compuesta</span><span class="sxs-lookup"><span data-stu-id="d6bec-102">How to: Create a Composite Shape</span></span>
<span data-ttu-id="d6bec-103">En este ejemplo se muestra cómo crear formas compuestas mediante <xref:System.Windows.Media.Geometry> objetos y cómo mostrarlas mediante un elemento <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="d6bec-103">This example shows how to create composite shapes using <xref:System.Windows.Media.Geometry> objects and display them using a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="d6bec-104">En el ejemplo siguiente, se usa un <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>y un <xref:System.Windows.Media.RectangleGeometry> con un <xref:System.Windows.Media.GeometryGroup> para crear una forma compuesta.</span><span class="sxs-lookup"><span data-stu-id="d6bec-104">In the following example, a <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, and a <xref:System.Windows.Media.RectangleGeometry> are used with a <xref:System.Windows.Media.GeometryGroup> to create a composite shape.</span></span> <span data-ttu-id="d6bec-105">A continuación, las geometrías se dibujan utilizando un elemento <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="d6bec-105">The geometries are then drawn using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6bec-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d6bec-106">Example</span></span>  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 <span data-ttu-id="d6bec-107">La siguiente ilustración muestra la forma creada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="d6bec-107">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="d6bec-108">![Geometría compuesta creada con GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span><span class="sxs-lookup"><span data-stu-id="d6bec-108">![A composite geometry created using a GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span></span>  
<span data-ttu-id="d6bec-109">Geometría compuesta</span><span class="sxs-lookup"><span data-stu-id="d6bec-109">Composite Geometry</span></span>  
  
 <span data-ttu-id="d6bec-110">Las formas más complejas, como polígonos y formas con segmentos curvos, se pueden crear con un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="d6bec-110">More complex shapes, such as polygons and shapes with curved segments, may be created using a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="d6bec-111">Para ver un ejemplo en el que se muestra cómo crear una forma mediante un <xref:System.Windows.Media.PathGeometry>, vea [crear una forma mediante una PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="d6bec-111">For an example showing how to create a shape using a <xref:System.Windows.Media.PathGeometry>, see [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  <span data-ttu-id="d6bec-112">Aunque en este ejemplo se representa una forma en la pantalla mediante un elemento <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Media.Geometry> objetos también se pueden usar para describir el contenido de un <xref:System.Windows.Media.GeometryDrawing> o de un <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="d6bec-112">Although this example renders a shape to the screen using a <xref:System.Windows.Shapes.Path> element, <xref:System.Windows.Media.Geometry> objects may also be used to describe the contents of a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="d6bec-113">También se pueden usar para el recorte y la prueba de posicionamiento.</span><span class="sxs-lookup"><span data-stu-id="d6bec-113">They may also be used for clipping and hit-testing.</span></span>  
  
 <span data-ttu-id="d6bec-114">Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Ejemplo de geometrías](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="d6bec-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>
