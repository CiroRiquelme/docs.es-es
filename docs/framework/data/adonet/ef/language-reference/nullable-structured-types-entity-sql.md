---
title: Tipos estructurados que aceptan valores NULL [Entity SQL]
ms.date: 03/30/2017
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
ms.openlocfilehash: b155c672d8c0bef8b01fb26fb49908f094add25a
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319486"
---
# <a name="nullable-structured-types-entity-sql"></a>Tipos estructurados que aceptan valores NULL [Entity SQL]
Una instancia `null` de un tipo estructurado es una instancia que no existe. Es diferente de una instancia existente en la que todas las propiedades tienen valores `null`.  
  
 En este tema se describen los tipos estructurados que admiten valores NULL, incluidos los que admiten valores NULL cuyos patrones de código producen instancias de `null` de tipos que admiten valores NULL estructurados.  
  
## <a name="kinds-of-nullable-structured-types"></a>Modalidad de tipos estructurados que admiten valores NULL  
 Hay tres modalidades de tipos de estructura que admiten valores NULL:  
  
- Tipos de fila.  
  
- Tipos complejos.  
  
- Tipos de entidad.  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a>Patrones de código que generan instancias NULL de tipos estructurados  
 Las escenarios siguientes producen instancias `null`:  
  
- Dar forma a `null` como un tipo estructurado:  
  
    ```sql  
    TREAT (NULL AS StructuredType)  
    ```  
  
- Convertir un tipo base en un tipo derivado:  
  
    ```sql  
    TREAT (BaseType AS DerivedType)  
    ```  
  
- Unión externa en una condición falsa:  
  
    ```sql  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     O bien  
  
    ```sql  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     O bien  
  
    ```sql  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
- Desreferenciar `null`:  
  
    ```sql  
    DEREF(NullRef)  
    ```  
  
- Obtener ANYELEMENT de una colección vacía:  
  
    ```sql  
    ANYELEMENT(EmptyCollection)  
    ```  
  
- Comprobar instancias `null` de tipos estructurados:  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine("[NULL]");  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## <a name="see-also"></a>Vea también

- [Información general sobre Entity SQL](entity-sql-overview.md)
