---
title: Crear una aplicación transaccional
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: 318771c83a5b7ebc0f3fb2bb8c59240269a2dea9
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205823"
---
# <a name="writing-a-transactional-application"></a>Crear una aplicación transaccional
Como un programador de la aplicación transaccional, puede tomar la ventaja de los dos modelos de programación proporcionados por el espacio de nombres <xref:System.Transactions> para crear una transacción. Puede utilizar el modelo de programación explícito mediante la <xref:System.Transactions.Transaction> clase, o el modelo de programación implícito en el que la infraestructura administra automáticamente las transacciones, mediante la <xref:System.Transactions.TransactionScope> clase. Se recomienda utilizar el modelo de transacción implícita para el desarrollo. Puede encontrar más información sobre cómo usar un ámbito de transacción en el tema [implementación de una transacción implícita mediante el ámbito](implementing-an-implicit-transaction-using-transaction-scope.md) de la transacción.  
  
 Ambos modelos permiten confirmar una transacción cuando el programa llega a un estado coherente. Si la confirmación tiene éxito, se confirma la transacción de forma duradera. Si se produce un error en la confirmación, la transacción se anula. Si el programa de aplicación no puede completar correctamente la transacción, intenta anular y deshacer los efectos de la transacción.  
  
## <a name="in-this-section"></a>En esta sección  
  
### <a name="creating-a-transaction"></a>Crear una transacción  
 El espacio de nombres <xref:System.Transactions> proporciona dos modelos para crear una transacción. Estos modelos se cubren en los temas siguientes.  
  
 [Implementación de una transacción implícita mediante el ámbito de transacción](implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 Describe cómo el espacio de nombres <xref:System.Transactions> permite crear transacciones implícitas mediante la clase <xref:System.Transactions.TransactionScope>.  
  
 [Implementación de una transacción explícita con CommittableTransaction](implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 Describe cómo el espacio de nombres <xref:System.Transactions> permite crear transacciones implícitas mediante la clase<xref:System.Transactions.CommittableTransaction>.  
  
### <a name="escalating-transaction-management"></a>Extendiendo la administración de transacción  
 Cuando una transacción necesita tener acceso a un recurso en otro dominio de aplicación, o si desea dar de alta en otro administrador de recursos duradero, la transacción se realiza de manera escalonada automáticamente para ser administrada por MSDTC. La extensión de la transacción se trata en el tema sobre escalado de la [Administración de transacciones](transaction-management-escalation.md) .  
  
### <a name="concurrency"></a>simultaneidad  
 El tema [administrar la simultaneidad con DependentTransaction](managing-concurrency-with-dependenttransaction.md) muestra cómo se puede lograr la simultaneidad entre tareas asincrónicas mediante la <xref:System.Transactions.DependentTransaction> clase.  
  
### <a name="com-interop"></a>Interoperabilidad COM+  
 El tema [interoperabilidad con Enterprise Services y transacciones de com+](interoperability-with-enterprise-services-and-com-transactions.md) muestra cómo puede hacer que las transacciones distribuidas interactúen con transacciones de com+.  
  
### <a name="diagnostics"></a>Diagnóstico  
 [Seguimientos de diagnóstico](diagnostic-traces.md) describe cómo puede usar los códigos de seguimiento generados por <xref:System.Transactions> la infraestructura de para solucionar errores en sus aplicaciones.  
  
### <a name="working-within-aspnet"></a>Funcionar dentro de ASP.NET  
 En el tema [uso de System. Transactions en ASP.net](using-system-transactions-in-aspnet.md) se describe <xref:System.Transactions> cómo se puede usar correctamente en una aplicación de ASP.net.
