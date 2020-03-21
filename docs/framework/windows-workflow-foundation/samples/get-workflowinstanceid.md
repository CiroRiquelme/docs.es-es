---
title: Get WorkflowInstanceId
ms.date: 03/30/2017
ms.assetid: bd7eea3b-1c28-4b84-9a67-003bc553aa81
ms.openlocfilehash: 8cb83fcf15b814b0ca6f7f95f1a9b8eec70185cb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142737"
---
# <a name="get-workflowinstanceid"></a><span data-ttu-id="f64f3-102">Get WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="f64f3-102">Get WorkflowInstanceId</span></span>
<span data-ttu-id="f64f3-103">En este ejemplo se muestra cómo utilizar la actividad personalizada `GetWorkflowInstanceId` para devolver el identificador de la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f64f3-103">This sample demonstrates how to use the custom activity, `GetWorkflowInstanceId` to return the workflow instance ID.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="f64f3-104">Muestra</span><span class="sxs-lookup"><span data-stu-id="f64f3-104">Demonstrates</span></span>  
 <span data-ttu-id="f64f3-105">Desarrollo de actividades personalizadas, cómo tener acceso a la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f64f3-105">Custom activity development, how to access the workflow instance.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="f64f3-106">Discusión</span><span class="sxs-lookup"><span data-stu-id="f64f3-106">Discussion</span></span>  
 <span data-ttu-id="f64f3-107">La obtención del Id. de instancia de un flujo de trabajo en ejecución requiere código de escritura.</span><span class="sxs-lookup"><span data-stu-id="f64f3-107">Getting the instance ID of a running workflow requires writing code.</span></span> <span data-ttu-id="f64f3-108">Si desea escribir un flujo de trabajo totalmente declarativo, necesita una actividad que pueda devolver el identificador de la instancia de flujo de trabajo para que se pueda hacer referencia a la actividad en el flujo de trabajo a fin de proporcionar un flujo de trabajo totalmente declarativo que cree la experiencia.</span><span class="sxs-lookup"><span data-stu-id="f64f3-108">If you want to write a fully-declarative workflow, then you need an activity that can return the workflow instance ID so that the activity can be referenced in the workflow to provide a fully-declarative workflow authoring experience.</span></span> <span data-ttu-id="f64f3-109">Muchos escenarios requieren tener acceso al Id. de instancia: algunos ejemplos son para registrar o auditar propósitos o para realizar una correlación en la aplicación proporcionando el Id. de instancia a un cliente para su asociación futura (por ejemplo, utilizando esta actividad dentro de una actividad SendReply).</span><span class="sxs-lookup"><span data-stu-id="f64f3-109">Many scenarios require access to the instance ID: a few examples are for logging or auditing purposes or for doing application-level correlation by providing the instance ID back to a client for future association (for example, by using this activity inside a SendReply activity).</span></span>  
  
 <span data-ttu-id="f64f3-110">`GetWorkflowInstanceId` se implementa como un objeto <xref:System.Activities.CodeActivity%601> porque debe devolver un valor de tipo <xref:System.Guid> y debe tener acceso a <xref:System.Activities.CodeActivityContext> para obtener el Id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f64f3-110">`GetWorkflowInstanceId` is implemented as a <xref:System.Activities.CodeActivity%601> because it must return a value of type <xref:System.Guid>, and it must have access to the <xref:System.Activities.CodeActivityContext> for getting the workflow’s instance ID.</span></span> <span data-ttu-id="f64f3-111">Su implementación es bastante básica.</span><span class="sxs-lookup"><span data-stu-id="f64f3-111">Its implementation is fairly basic.</span></span>  
  
```csharp  
public sealed class GetWorkflowInstanceId : CodeActivity<Guid>  
{  
    protected override Guid Execute(CodeActivityContext context)  
    {  
        return context.WorkflowInstanceId;  
    }  
}
```  
  
> [!IMPORTANT]
> <span data-ttu-id="f64f3-112">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="f64f3-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f64f3-113">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f64f3-113">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="f64f3-114">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f64f3-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f64f3-115">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="f64f3-115">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\GetWorkflowInstanceId`
