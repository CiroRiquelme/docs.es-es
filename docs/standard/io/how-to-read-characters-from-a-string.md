---
title: Procedimiento Leer caracteres de una cadena
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET Framework], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
ms.openlocfilehash: ed267ad62e46f6216c94906df1bcefb0684ab51b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78155768"
---
# <a name="how-to-read-characters-from-a-string"></a>Procedimiento Leer caracteres de una cadena
En los ejemplos de código siguientes se muestra cómo leer caracteres desde una cadena de forma sincrónica o asincrónica.  
  
## <a name="example-read-characters-synchronously"></a>Ejemplo: Leer caracteres de forma sincrónica
 Este ejemplo lee trece caracteres de forma sincrónica de una cadena, los almacena en una matriz y los muestra. A continuación, el ejemplo lee el resto de los caracteres de la cadena, los almacena en la matriz a partir del sexto elemento y muestra el contenido de la matriz.  
  
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example-read-characters-asynchronously"></a>Ejemplo: Leer caracteres de forma asincrónica  
 El ejemplo siguiente es el código subyacente en una aplicación WPF. En la carga de la ventana, el ejemplo lee todos los caracteres de forma asincrónica desde un control <xref:System.Windows.Controls.TextBox> y los almacena en una matriz. Luego escribe de forma asincrónica cada carácter de letra o espacio en blanco en una línea independiente de un control <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.StringReader>  
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
- [E/S de archivos asincrónica](../../../docs/standard/io/asynchronous-file-i-o.md)  
- [Cómo: Crear una lista de directorios](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))  
- [Cómo: Leer y escribir en un archivo de datos recién creado](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Cómo: Abrir y anexar a un archivo de registro](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [Cómo: Leer texto de un archivo](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [Cómo: Escribir texto en un archivo](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [Cómo: Escribir caracteres en una cadena](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
