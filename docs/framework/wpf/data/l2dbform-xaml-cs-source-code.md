---
title: Código fuente de L2DBForm.xaml.cs
ms.date: 10/22/2019
ms.topic: sample
ms.openlocfilehash: 882699a76eab3c291cd92c298287bc5d28fb08e1
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921159"
---
# <a name="l2dbformxamlcs-source-code"></a>Código fuente de L2DBForm.xaml.cs

Esta página contiene el contenido y la descripción del C# código fuente en el archivo *L2DBForm.Xaml.CS*. La clase parcial L2XDBForm contenida en este archivo se puede dividir en tres secciones lógicas: miembros de datos y los controladores de eventos Click de botones `OnRemove` y `OnAddBook`.

## <a name="data-members"></a>Miembros de datos

Se utilizan dos miembros de datos privados para asociar esta clase con los recursos de la ventana que se utilizan en *L2DBForm.xaml*.

- La variable del espacio de nombres `myBooks` se inicializa en `"http://www.mybooks.com"`.

- El miembro `bookList` se inicializa en el constructor en la cadena CDATA de *L2DBForm.xaml* con la siguiente línea:

    ```csharp
    bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
    ```

## <a name="onaddbook-event-handler"></a>Controlador de eventos OnAddBook

Este método contiene las siguientes tres instrucciones:

- La primera instrucción condicional se utiliza para la validación de entrada.

- La segunda instrucción crea un nuevo <xref:System.Xml.Linq.XElement> a partir de los valores de cadena que el usuario ha especificado en la sección de la interfaz de usuario (IU) **Agregar nuevo libro**.

- La última instrucción agrega este nuevo elemento de libro al proveedor de datos de *L2DBForm.xaml*. En consecuencia, el enlace de datos dinámicos actualizará la IU con este nuevo elemento; no se requiere ningún código adicional proporcionado por el usuario.

## <a name="onremove-event-handler"></a>Controlador de eventos OnRemove

El controlador `OnRemove` es más complicado que el controlador `OnAddBook` por dos motivos. En primer lugar, como el XML sin formato contiene espacios en blanco conservados, las nuevas líneas coincidentes deben quitarse con la entrada del libro. En segundo lugar, por comodidad, la selección, que se hizo en el elemento eliminado, se restablece a la selección previa de la lista.

Pero el trabajo principal de quitar el elemento de libro seleccionado se logra con solo dos instrucciones:

- En primer lugar, se recupera el elemento de libro asociado con el elemento seleccionado actualmente en el cuadro de lista:

    ```csharp
    XElement selBook = (XElement)lbBooks.SelectedItem;
    ```

- A continuación, se elimina este elemento del proveedor de datos:

    ```csharp
    selBook.Remove();
    ```

De nuevo, el enlace de datos dinámicos garantiza que la IU del programa se actualiza automáticamente.

## <a name="example"></a>Ejemplo

### <a name="code"></a>Código

```csharp
using System;
using System.Linq;
using System.Collections;
using System.Collections.Generic;
using System.Diagnostics;
using System.Text;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Input;
using System.Xml;
using System.Xml.Linq;

namespace LinqToXmlDataBinding {
    /// <summary>
    /// Interaction logic for L2XDBForm.xaml
    /// </summary>

    public partial class L2XDBForm : System.Windows.Window
    {
        XNamespace mybooks = "http://www.mybooks.com";
        XElement bookList;

        public L2XDBForm()
        {
            InitializeComponent();
            bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
        }

        void OnRemoveBook(object sender, EventArgs e)
        {
            int index = lbBooks.SelectedIndex;
            if (index < 0) return;

            XElement selBook = (XElement)lbBooks.SelectedItem;
            //Get next node before removing element.
            XNode nextNode = selBook.NextNode;
            selBook.Remove();

            //Remove any matching newline node.
            if (nextNode != null && nextNode.ToString().Trim().Equals(""))
            { nextNode.Remove(); }

            //Set selected item.
            if (lbBooks.Items.Count > 0)
            {  lbBooks.SelectedItem = lbBooks.Items[index > 0 ? index - 1 : 0]; }
        }

        void OnAddBook(object sender, EventArgs e)
        {
            if (String.IsNullOrEmpty(tbAddID.Text) ||
                String.IsNullOrEmpty(tbAddValue.Text))
            {
                MessageBox.Show("Please supply both a Book ID and a Value!", "Entry Error!");
                return;
            }
            XElement newBook = new XElement(
                                mybooks + "book",
                                new XAttribute("id", tbAddID.Text),
                                tbAddValue.Text);
            bookList.Add("  ", newBook, "\r\n");
        }
    }
}
```

### <a name="comments"></a>Comentarios

Para conocer el código fuente XAML asociado para esos controladores, vea [Código fuente de L2DBForm.xaml](l2dbform-xaml-source-code.md).

## <a name="see-also"></a>Vea también

- [Tutorial: Ejemplo de LinqToXmlDataBinding](linq-to-xml-data-binding-sample.md)
- [Código fuente de L2DBForm.xaml](l2dbform-xaml-source-code.md)
