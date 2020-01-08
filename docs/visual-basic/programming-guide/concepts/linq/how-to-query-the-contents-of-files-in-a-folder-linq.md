---
title: 'Cómo: Consultar el contenido de los archivos de una carpeta (LINQ)'
ms.date: 07/20/2015
ms.assetid: edacbcd3-f3e4-4429-a8be-28a58dc0dd70
ms.openlocfilehash: 3ad5fd6c893d590d46be67e6320ac5b915829f4b
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346046"
---
# <a name="how-to-query-the-contents-of-files-in-a-folder-linq-visual-basic"></a><span data-ttu-id="67b73-102">Cómo consultar el contenido de los archivos de una carpeta (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67b73-102">How to query the contents of files in a folder (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="67b73-103">En este ejemplo se muestra cómo consultar todos los archivos en un árbol de directorios especificado, abrir cada archivo e inspeccionar su contenido.</span><span class="sxs-lookup"><span data-stu-id="67b73-103">This example shows how to query over all the files in a specified directory tree, open each file, and inspect its contents.</span></span> <span data-ttu-id="67b73-104">Este tipo de técnica puede usarse para crear índices o índices inversos del contenido de un árbol de directorios.</span><span class="sxs-lookup"><span data-stu-id="67b73-104">This type of technique could be used to create indexes or reverse indexes of the contents of a directory tree.</span></span> <span data-ttu-id="67b73-105">En este ejemplo, se realiza una búsqueda de cadena simple.</span><span class="sxs-lookup"><span data-stu-id="67b73-105">A simple string search is performed in this example.</span></span> <span data-ttu-id="67b73-106">Pero los tipos más complejos de coincidencia de patrones se pueden realizar con una expresión regular.</span><span class="sxs-lookup"><span data-stu-id="67b73-106">However, more complex types of pattern matching can be performed with a regular expression.</span></span> <span data-ttu-id="67b73-107">Para obtener más información, vea [Cómo: combinar consultas LINQ con expresiones regulares (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="67b73-107">For more information, see [How to: Combine LINQ Queries with Regular Expressions (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="67b73-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67b73-108">Example</span></span>  
  
```vb
Imports System.IO

Module Module1  
    'QueryContents  
    Public Sub Main()  
  
        ' Modify this path as necessary.  
        Dim startFolder = "C:\Program Files (x86)\Microsoft Visual Studio 14.0"  

        ' Take a snapshot of the folder contents.
        Dim dir As New DirectoryInfo(startFolder)
        Dim fileList = dir.GetFiles("*.*", SearchOption.AllDirectories)

        Dim searchTerm = "Welcome"

        ' Search the contents of each file.
        ' A regular expression created with the RegEx class
        ' could be used instead of the Contains method.
        Dim queryMatchingFiles = From file In fileList _
                                 Where file.Extension = ".html" _
                                 Let fileText = GetFileText(file.FullName) _
                                 Where fileText.Contains(searchTerm) _
                                 Select file.FullName

        Console.WriteLine("The term " & searchTerm & " was found in:")

        ' Execute the query.
        For Each filename In queryMatchingFiles
            Console.WriteLine(filename)
        Next

        ' Keep the console window open in debug mode.
        Console.WriteLine("Press any key to exit")
        Console.ReadKey()

    End Sub

    ' Read the contents of the file. This is done in a separate
    ' function in order to handle potential file system errors.
    Function GetFileText(name As String) As String

        ' If the file has been deleted, the right thing
        ' to do in this case is return an empty string.
        Dim fileContents = String.Empty

        ' If the file has been deleted since we took
        ' the snapshot, ignore it and return the empty string.
        If File.Exists(name) Then
            fileContents = File.ReadAllText(name)
        End If

        Return fileContents

    End Function
End Module
```

## <a name="compile-the-code"></a><span data-ttu-id="67b73-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="67b73-109">Compile the code</span></span>

<span data-ttu-id="67b73-110">Cree un proyecto de aplicación de consola de Visual Basic, copie y pegue el ejemplo de código y ajuste el valor del objeto startup en las propiedades del proyecto.</span><span class="sxs-lookup"><span data-stu-id="67b73-110">Create a Visual Basic console application project, copy and paste the code sample, and adjust the Startup object value in the project properties.</span></span>

## <a name="see-also"></a><span data-ttu-id="67b73-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="67b73-111">See also</span></span>

- [<span data-ttu-id="67b73-112">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67b73-112">LINQ to Objects (Visual Basic)</span></span>](linq-to-objects.md)
- [<span data-ttu-id="67b73-113">LINQ y directorios de archivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67b73-113">LINQ and File Directories (Visual Basic)</span></span>](linq-and-file-directories.md)
