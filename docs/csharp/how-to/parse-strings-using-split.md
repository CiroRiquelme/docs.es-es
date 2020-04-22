---
title: Procedimiento para analizar cadenas mediante String.Split (Guía de C#)
description: String.Split devuelve una matriz de cadenas dividida entre un conjunto de delimitadores. Es una manera sencilla de analizar cadenas.
ms.date: 01/03/2018
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
ms.custom: mvc
ms.openlocfilehash: cf8307517213b54041b272843232eb595660b2e9
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389505"
---
# <a name="how-to-parse-strings-using-stringsplit-in-c"></a>Procedimiento para analizar cadenas mediante String.Split en C\#

El método <xref:System.String.Split%2A?displayProperty=nameWithType> crea una matriz de subcadenas mediante la división de la cadena de entrada en función de uno o varios delimitadores. Suele ser la manera más fácil de separar una cadena en límites de palabras. También sirve para dividir las cadenas en otras cadenas o caracteres específicos.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Este código divide una frase común en una matriz de cadenas para cada palabra.

[!code-csharp-interactive[split strings on word boundaries](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#1)]

Todas las instancias de un carácter separador generan un valor en la matriz devuelta. Los caracteres separadores consecutivos generan la cadena vacía como un valor en la matriz devuelta. Puede ver cómo se crea una cadena vacía en el ejemplo siguiente, en el que se usa el carácter de espacio como separador.

[!code-csharp-interactive[split strings with repeated separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#2)]

Este comportamiento facilita formatos como los de los archivos de valores separados por comas (CSV) que representan datos tabulares. Las comas consecutivas representan una columna en blanco.

Puede pasar un parámetro <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> opcional para excluir cualquier cadena vacía en la matriz devuelta. Para un procesamiento más complicado de la colección devuelta, puede usar [LINQ](../programming-guide/concepts/linq/index.md) para manipular la secuencia de resultados.

<xref:System.String.Split%2A?displayProperty=nameWithType> puede usar varios caracteres separadores.
En este ejemplo se usan espacios, comas, puntos, dos puntos y tabulaciones; están incluidos todos en una matriz que contiene estos caracteres de separación y que se pasa a <xref:System.String.Split%2A>.
En el bucle al final del código se muestra cada una de las palabras de la matriz devuelta.  

[!code-csharp-interactive[split strings using multiple separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#3)]

Las instancias consecutivas de cualquier separador generan la cadena vacía en la matriz de salida:

[!code-csharp-interactive[split strings using multiple consecutive separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#4)]

<xref:System.String.Split%2A?displayProperty=nameWithType> puede tomar una matriz de cadenas (secuencias de caracteres que actúan como separadores para analizar la cadena de destino, en lugar de caracteres individuales).  
  
[!code-csharp-interactive[split strings using strings as separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#5)]

Eche un vistazo al código de nuestro [repositorio de GitHub](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings) y pruebe estos ejemplos. O bien, puede descargar los ejemplos [como un archivo ZIP](../../../samples/snippets/csharp/how-to/strings.zip).

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../programming-guide/index.md)
- [Cadenas](../programming-guide/strings/index.md)
- [Expresiones regulares de .NET](../../standard/base-types/regular-expressions.md)
