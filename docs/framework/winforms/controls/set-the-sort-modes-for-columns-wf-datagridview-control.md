---
title: Establecer los modos de ordenación de las columnas en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 45ee1e7d82f826cddbd3492fed0f63e7a9c2cf1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742999"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="0ede7-102">Cómo: Establecer modos de ordenación de columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ede7-102">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="0ede7-103">En el control <xref:System.Windows.Forms.DataGridView>, las columnas del cuadro de texto utilizan la ordenación automática de forma predeterminada, mientras que otros tipos de columna no se ordenan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0ede7-103">In the <xref:System.Windows.Forms.DataGridView> control, text box columns use automatic sorting by default, while other column types are not sorted automatically.</span></span> <span data-ttu-id="0ede7-104">A veces, querrá invalidar estos valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="0ede7-104">Sometimes you will want to override these defaults.</span></span> <span data-ttu-id="0ede7-105">Por ejemplo, puede mostrar imágenes en lugar de los valores de celda de texto, números o enumeración.</span><span class="sxs-lookup"><span data-stu-id="0ede7-105">For example, you can display images in place of text, numbers, or enumeration cell values.</span></span> <span data-ttu-id="0ede7-106">Aunque no se pueden ordenar las imágenes, se pueden ordenar los valores subyacentes que representan.</span><span class="sxs-lookup"><span data-stu-id="0ede7-106">While the images cannot be sorted, the underlying values that they represent can be sorted.</span></span>  
  
 <span data-ttu-id="0ede7-107">En el control <xref:System.Windows.Forms.DataGridView>, el valor de la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> de una columna determina su comportamiento de ordenación.</span><span class="sxs-lookup"><span data-stu-id="0ede7-107">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property value of a column determines its sorting behavior.</span></span>  
  
 <span data-ttu-id="0ede7-108">En el procedimiento siguiente se muestra la `Priority` columna de [Cómo: personalizar el formato de datos en el control DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="0ede7-108">The following procedure shows the `Priority` column from [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="0ede7-109">Esta columna es una columna de imagen y no se ordena de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0ede7-109">This column is an image column and is not sortable by default.</span></span> <span data-ttu-id="0ede7-110">No obstante, contiene valores de celda reales que son cadenas, por lo que se puede ordenar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0ede7-110">It contains actual cell values that are strings, however, so it can be sorted automatically.</span></span>  
  
### <a name="to-set-the-sort-mode-for-a-column"></a><span data-ttu-id="0ede7-111">Para establecer el modo de ordenación de una columna</span><span class="sxs-lookup"><span data-stu-id="0ede7-111">To set the sort mode for a column</span></span>  
  
- <span data-ttu-id="0ede7-112">Establecer la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0ede7-112">Set the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0ede7-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="0ede7-113">Compiling the Code</span></span>  
 <span data-ttu-id="0ede7-114">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="0ede7-114">This example requires:</span></span>  
  
- <span data-ttu-id="0ede7-115">Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1` que contiene una columna llamada `Priority`.</span><span class="sxs-lookup"><span data-stu-id="0ede7-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Priority`.</span></span>  
  
- <span data-ttu-id="0ede7-116">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0ede7-116">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ede7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ede7-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0ede7-118">Ordenar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ede7-118">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="0ede7-119">Modos de ordenación de columnas del control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ede7-119">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="0ede7-120">Personalizar la ordenación en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ede7-120">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
