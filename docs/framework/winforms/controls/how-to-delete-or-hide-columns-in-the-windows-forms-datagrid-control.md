---
title: Eliminar u ocultar columnas en el control DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
ms.openlocfilehash: c730be934e9b978bdaf09bc7e668b4318077fba5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743299"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="18675-102">Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="18675-102">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="18675-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="18675-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="18675-104">Para obtener más información, consulte [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="18675-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="18675-105">Puede eliminar u ocultar columnas mediante programación en el control Windows Forms <xref:System.Windows.Forms.DataGrid> mediante las propiedades y los métodos de los objetos <xref:System.Windows.Forms.GridColumnStylesCollection> y <xref:System.Windows.Forms.DataGridColumnStyle> (que son miembros de la clase <xref:System.Windows.Forms.DataGridTableStyle>).</span><span class="sxs-lookup"><span data-stu-id="18675-105">You can programmatically delete or hide columns in the Windows Forms <xref:System.Windows.Forms.DataGrid> control by using the properties and methods of the <xref:System.Windows.Forms.GridColumnStylesCollection> and <xref:System.Windows.Forms.DataGridColumnStyle> objects (which are members of the <xref:System.Windows.Forms.DataGridTableStyle> class).</span></span>  
  
 <span data-ttu-id="18675-106">Las columnas eliminadas u ocultas todavía existen en el origen de datos al que está enlazada la cuadrícula y se puede seguir accediendo a ella mediante programación.</span><span class="sxs-lookup"><span data-stu-id="18675-106">The deleted or hidden columns still exist in the data source the grid is bound to, and can still be accessed programmatically.</span></span> <span data-ttu-id="18675-107">Ya no están visibles en el control DataGrid.</span><span class="sxs-lookup"><span data-stu-id="18675-107">They are just no longer visible in the datagrid.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18675-108">Si la aplicación no tiene acceso a determinadas columnas de datos y no desea que se muestren en el control DataGrid, es probable que no sea necesario incluirlas en el origen de datos en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="18675-108">If your application does not access certain columns of data, and you do not want them displayed in the datagrid, then it is probably not necessary to include them in the data source in the first place.</span></span>  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a><span data-ttu-id="18675-109">Para eliminar una columna de DataGrid mediante programación</span><span class="sxs-lookup"><span data-stu-id="18675-109">To delete a column from the DataGrid programmatically</span></span>  
  
1. <span data-ttu-id="18675-110">En el área declaraciones del formulario, declare una nueva instancia de la clase <xref:System.Windows.Forms.DataGridTableStyle>.</span><span class="sxs-lookup"><span data-stu-id="18675-110">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2. <span data-ttu-id="18675-111">Establezca la propiedad <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> en la tabla del origen de datos a la que desea aplicar el estilo.</span><span class="sxs-lookup"><span data-stu-id="18675-111">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> property to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="18675-112">En el ejemplo siguiente se usa la propiedad <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType>, que supone que ya está establecida.</span><span class="sxs-lookup"><span data-stu-id="18675-112">The following example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3. <span data-ttu-id="18675-113">Agregue el nuevo objeto <xref:System.Windows.Forms.DataGridTableStyle> a la colección de estilos de tabla de DataGrid.</span><span class="sxs-lookup"><span data-stu-id="18675-113">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4. <span data-ttu-id="18675-114">Llame al método <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> de la colección <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> del <xref:System.Windows.Forms.DataGrid>, especificando el índice de columna de la columna que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="18675-114">Call the <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DataGrid>'s <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> collection, specifying the column index of the column to delete.</span></span>  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a><span data-ttu-id="18675-115">Para ocultar una columna en el control DataGrid mediante programación</span><span class="sxs-lookup"><span data-stu-id="18675-115">To hide a column in the DataGrid programmatically</span></span>  
  
1. <span data-ttu-id="18675-116">En el área declaraciones del formulario, declare una nueva instancia de la clase <xref:System.Windows.Forms.DataGridTableStyle>.</span><span class="sxs-lookup"><span data-stu-id="18675-116">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2. <span data-ttu-id="18675-117">Establezca la propiedad <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> del <xref:System.Windows.Forms.DataGridTableStyle> en la tabla del origen de datos a la que desea aplicar el estilo.</span><span class="sxs-lookup"><span data-stu-id="18675-117">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property of the <xref:System.Windows.Forms.DataGridTableStyle> to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="18675-118">En el ejemplo de código siguiente se usa la propiedad <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType>, que supone que ya está establecida.</span><span class="sxs-lookup"><span data-stu-id="18675-118">The following code example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3. <span data-ttu-id="18675-119">Agregue el nuevo objeto <xref:System.Windows.Forms.DataGridTableStyle> a la colección de estilos de tabla de DataGrid.</span><span class="sxs-lookup"><span data-stu-id="18675-119">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4. <span data-ttu-id="18675-120">Oculte la columna estableciendo su `Width` propiedad en 0, especificando el índice de columna de la columna que se va a ocultar.</span><span class="sxs-lookup"><span data-stu-id="18675-120">Hide the column by setting its `Width` property to 0, specifying the column index of the column to hide.</span></span>  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="18675-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="18675-121">See also</span></span>

- [<span data-ttu-id="18675-122">Cómo: Cambiar los datos mostrados en tiempo de ejecución en el control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="18675-122">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [<span data-ttu-id="18675-123">Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="18675-123">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
