---
title: Correspondencias de DataTable y DataColumn en un objeto DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 6380dd0512bd7834f50b87f90f445cb01b7a8b95
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151564"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="864a8-102">Correspondencias de DataTable y DataColumn en un objeto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="864a8-102">DataAdapter DataTable and DataColumn Mappings</span></span>
<span data-ttu-id="864a8-103">Un **DataAdapter** contiene una colección de cero o más <xref:System.Data.Common.DataTableMapping> objetos en su **TableMappings** propiedad.</span><span class="sxs-lookup"><span data-stu-id="864a8-103">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="864a8-104">Un **DataTableMapping** proporciona una asignación maestra entre los datos devueltos de una consulta en un origen de datos y un <xref:System.Data.DataTable>archivo .</span><span class="sxs-lookup"><span data-stu-id="864a8-104">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="864a8-105">El **DataTableMapping** nombre se puede pasar en lugar del nombre **DataTable** a la **Fill** método de la **DataAdapter**.</span><span class="sxs-lookup"><span data-stu-id="864a8-105">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="864a8-106">En el ejemplo siguiente se crea un **DataTableMapping** denominado **AuthorsMapping** para el **Authors** tabla.</span><span class="sxs-lookup"><span data-stu-id="864a8-106">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="864a8-107">Un **DataTableMapping** le permite usar nombres de columna en un **DataTable** que son diferentes de los de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="864a8-107">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="864a8-108">El **DataAdapter** usa la asignación para que coincida con las columnas cuando se actualiza la tabla.</span><span class="sxs-lookup"><span data-stu-id="864a8-108">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="864a8-109">Si no especifica un **TableName** o un **DataTableMapping** nombre al llamar a la **Fill** o **Update** método de la **DataAdapter**, el **DataAdapter** busca un **DataTableMapping** denominado "Table".</span><span class="sxs-lookup"><span data-stu-id="864a8-109">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="864a8-110">Si ese **DataTableMapping** no existe, el **TableName** de la **DataTable** es "Table".</span><span class="sxs-lookup"><span data-stu-id="864a8-110">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="864a8-111">Puede especificar un valor predeterminado **DataTableMapping** mediante la creación de un **DataTableMapping** con el nombre de "Table".</span><span class="sxs-lookup"><span data-stu-id="864a8-111">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="864a8-112">En el ejemplo de código siguiente <xref:System.Data.Common> se crea un **DataTableMapping** (desde el espacio de nombres) y lo convierte en la asignación predeterminada para el **DataAdapter** especificado nombrándolo "Table".</span><span class="sxs-lookup"><span data-stu-id="864a8-112">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="864a8-113">A continuación, el ejemplo asigna las columnas de la primera tabla del resultado de la consulta (la tabla **Customers** de <xref:System.Data.DataSet>la base de datos **Northwind)** a un conjunto de nombres más fáciles de usar en la tabla **Northwind Customers** del archivo .</span><span class="sxs-lookup"><span data-stu-id="864a8-113">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="864a8-114">En las columnas que no se asignan se usa el nombre de la columna en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="864a8-114">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 <span data-ttu-id="864a8-115">En situaciones más avanzadas, puede decidir que desea que el mismo **DataAdapter** admita la carga de tablas diferentes con asignaciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="864a8-115">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="864a8-116">Para ello, simplemente agregue objetos **DataTableMapping** adicionales.</span><span class="sxs-lookup"><span data-stu-id="864a8-116">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="864a8-117">Cuando el **Fill** método se pasa una instancia de un **DataSet** y un **DataTableMapping** nombre, si existe una asignación con ese nombre se utiliza; de lo contrario, se utiliza un **DataTable** con ese nombre.</span><span class="sxs-lookup"><span data-stu-id="864a8-117">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="864a8-118">En los ejemplos siguientes se crea un **DataTableMapping** con un nombre de **Customers** y un **dataTable** nombre de **BizTalkSchema**.</span><span class="sxs-lookup"><span data-stu-id="864a8-118">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="864a8-119">A continuación, el ejemplo asigna las filas devueltas por la instrucción SELECT a **BizTalkSchema** **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="864a8-119">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
> <span data-ttu-id="864a8-120">Si no se proporciona un nombre de columna de origen en una asignación de columnas o no se identifica un nombre de tabla de origen en una asignación de tablas, se generan nombres predeterminados de forma automática.</span><span class="sxs-lookup"><span data-stu-id="864a8-120">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="864a8-121">Si no se proporciona ninguna columna de origen para una asignación de columnas, la asignación de columnas recibe un nombre predeterminado incremental de **SourceColumn** *N,* empezando por **SourceColumn1**.</span><span class="sxs-lookup"><span data-stu-id="864a8-121">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="864a8-122">Si no se proporciona ningún nombre de tabla de origen para una asignación de tabla, la asignación de tabla recibe un nombre predeterminado incremental de **SourceTable** *N*, empezando por **SourceTable1**.</span><span class="sxs-lookup"><span data-stu-id="864a8-122">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="864a8-123">Se recomienda evitar la convención de nomenclatura de **SourceColumn** *N* para una asignación de columnas o **SourceTable** *N* para una asignación de tabla, ya que el nombre que proporcione puede entrar en conflicto con un nombre de asignación de columna predeterminado existente en **ColumnMappingCollection** o nombre de asignación de tabla en **DataTableMappingCollection**.</span><span class="sxs-lookup"><span data-stu-id="864a8-123">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="864a8-124">Si el nombre proporcionado ya existe, se iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="864a8-124">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="864a8-125">Controlar varios conjuntos de resultados</span><span class="sxs-lookup"><span data-stu-id="864a8-125">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="864a8-126">Si **SelectCommand** devuelve varias tablas, **Fill** genera automáticamente nombres de tabla con valores incrementales para las tablas del **conjunto**de datos , empezando por el nombre de tabla especificado y continuando con el formulario **TableName** *N*, empezando por **TableName1**.</span><span class="sxs-lookup"><span data-stu-id="864a8-126">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="864a8-127">Puede utilizar asignaciones de tablas para asignar el nombre de tabla generado automáticamente a un nombre que desee especificar para la tabla en el **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="864a8-127">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="864a8-128">Por ejemplo, para un **SelectCommand** que devuelve dos tablas, **Customers** y **Orders**, emita la siguiente llamada a **Fill**.</span><span class="sxs-lookup"><span data-stu-id="864a8-128">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 <span data-ttu-id="864a8-129">Se crean dos tablas en el **conjunto de**datos : **Clientes** y **clientes1**.</span><span class="sxs-lookup"><span data-stu-id="864a8-129">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="864a8-130">Puede utilizar asignaciones de tablas para asegurarse de que la segunda tabla se denomina **Pedidos** en lugar de **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="864a8-130">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="864a8-131">Para ello, asigne la tabla de origen de **Customers1** a la tabla **DataSet** **Orders**, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="864a8-131">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a><span data-ttu-id="864a8-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="864a8-132">See also</span></span>

- [<span data-ttu-id="864a8-133">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="864a8-133">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="864a8-134">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="864a8-134">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="864a8-135">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="864a8-135">ADO.NET Overview</span></span>](ado-net-overview.md)
