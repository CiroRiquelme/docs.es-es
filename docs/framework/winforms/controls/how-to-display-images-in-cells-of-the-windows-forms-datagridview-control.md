---
title: Mostrar imágenes en celdas del control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: e0e125c816877875b80e0f20887d9beee443577a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740275"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="e99f4-102">Cómo: Mostrar imágenes en celdas del control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e99f4-102">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e99f4-103">Una imagen o un gráfico es uno de los valores que se pueden mostrar en una fila de datos.</span><span class="sxs-lookup"><span data-stu-id="e99f4-103">A picture or graphic is one of the values that you can display in a row of data.</span></span> <span data-ttu-id="e99f4-104">Con frecuencia, estos gráficos adoptan la forma de la fotografía de un empleado o el logotipo de la empresa.</span><span class="sxs-lookup"><span data-stu-id="e99f4-104">Frequently, these graphics take the form of an employee's photograph or a company logo.</span></span>  
  
 <span data-ttu-id="e99f4-105">La incorporación de imágenes es sencilla cuando se muestran datos en el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="e99f4-105">Incorporating pictures is simple when you display data within the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="e99f4-106">El control <xref:System.Windows.Forms.DataGridView> controla de forma nativa cualquier formato de imagen admitido por la clase <xref:System.Drawing.Image>, así como el formato de imagen OLE utilizado por algunas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="e99f4-106">The <xref:System.Windows.Forms.DataGridView> control natively handles any image format supported by the <xref:System.Drawing.Image> class, as well as the OLE picture format used by some databases.</span></span>  
  
 <span data-ttu-id="e99f4-107">Si el origen de datos del control <xref:System.Windows.Forms.DataGridView> tiene una columna de imágenes, el control <xref:System.Windows.Forms.DataGridView> mostrará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e99f4-107">If the <xref:System.Windows.Forms.DataGridView> control's data source has a column of images, they will be displayed automatically by the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="e99f4-108">En el ejemplo de código siguiente se muestra cómo extraer un icono de un recurso incrustado y convertirlo en un mapa de bits para su presentación en cada celda de una columna de imagen.</span><span class="sxs-lookup"><span data-stu-id="e99f4-108">The following code example demonstrates how to extract an icon from an embedded resource and convert it to a bitmap for display in every cell of an image column.</span></span> <span data-ttu-id="e99f4-109">Para ver otro ejemplo en el que se reemplazan los valores de celda textual por las imágenes correspondientes, vea [Cómo: personalizar el formato de datos en el control DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="e99f4-109">For another example that replaces textual cell values with corresponding images, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e99f4-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e99f4-110">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e99f4-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e99f4-111">Compiling the Code</span></span>  
 <span data-ttu-id="e99f4-112">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e99f4-112">This example requires:</span></span>  
  
- <span data-ttu-id="e99f4-113">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="e99f4-113">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="e99f4-114">Un recurso de icono incrustado denominado `tree.ico`.</span><span class="sxs-lookup"><span data-stu-id="e99f4-114">An embedded icon resource named `tree.ico`.</span></span>  
  
- <span data-ttu-id="e99f4-115">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> y <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e99f4-115">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e99f4-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e99f4-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="e99f4-117">Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e99f4-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="e99f4-118">Personalizar el formato de los datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e99f4-118">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
