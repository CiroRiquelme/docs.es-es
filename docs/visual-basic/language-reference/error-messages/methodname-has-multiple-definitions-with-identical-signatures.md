---
title: "'<methodname>' tiene varias definiciones con firmas idénticas"
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: b884220053bbcec633c964a41892bc8df42f41c7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64602440"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a>'\<methodname >' tiene varias definiciones con firmas idénticas
Un `Function` o `Sub` declaración de procedimiento utiliza el procedimiento idéntico nombre y lista de argumentos que una declaración anterior. Una posible causa es un intento de sobrecargar el procedimiento original. Los procedimientos sobrecargados deben tener distintas listas de argumentos.  
  
 **Identificador de error:** BC30269  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Cambiar el nombre del procedimiento o la lista de argumentos, o quite la declaración duplicada.  
  
## <a name="see-also"></a>Vea también

- [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Consideraciones sobre la sobrecarga de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
