---
title: Implementar el modo virtual en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode
- DataGridView control [Windows Forms], large data sets
ms.assetid: 98236267-f08e-4918-bcf9-77acf050a3ca
ms.openlocfilehash: f8612a808ac5c9facee55d820529945f481a2cea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736507"
---
# <a name="how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="01d9a-102">Cómo: Implementar el modo virtual en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="01d9a-102">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="01d9a-103">El ejemplo de código siguiente muestra cómo administrar grandes conjuntos de datos mediante un control <xref:System.Windows.Forms.DataGridView> con su propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> establecida en `true`.</span><span class="sxs-lookup"><span data-stu-id="01d9a-103">The following code example demonstrates how to manage large sets of data using a <xref:System.Windows.Forms.DataGridView> control with its <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property set to `true`.</span></span>  
  
 <span data-ttu-id="01d9a-104">Para una explicación más completa de este ejemplo de código, vea [Tutorial: Implementar el modo virtual en el control DataGridView de Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="01d9a-104">For a complete explanation of this code example, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01d9a-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="01d9a-105">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#000)]
 [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="01d9a-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="01d9a-106">Compiling the Code</span></span>  
 <span data-ttu-id="01d9a-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="01d9a-107">This example requires:</span></span>  
  
- <span data-ttu-id="01d9a-108">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="01d9a-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01d9a-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01d9a-109">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="01d9a-110">Tutorial: Implementar el modo virtual en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="01d9a-110">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-wf-datagridview-control.md)
- [<span data-ttu-id="01d9a-111">Ajuste del rendimiento del control DataGridView en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="01d9a-111">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="01d9a-112">Modo virtual del control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="01d9a-112">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)
