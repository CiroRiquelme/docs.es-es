---
title: Ejemplo MsgBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- marshaling, MsgBox sample
- data marshaling, MsgBox sample
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
ms.openlocfilehash: b970a5a193f82ca141c030491febce5ef352eb70
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181345"
---
# <a name="msgbox-sample"></a><span data-ttu-id="ee26e-102">Ejemplo MsgBox</span><span class="sxs-lookup"><span data-stu-id="ee26e-102">MsgBox Sample</span></span>
<span data-ttu-id="ee26e-103">En este ejemplo se muestra cómo pasar tipos de cadena por valor como parámetros In y cuándo utilizar los campos <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> y <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>.</span><span class="sxs-lookup"><span data-stu-id="ee26e-103">This sample demonstrates how to pass string types by value as In parameters and when to use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>, and <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> fields.</span></span>  
  
 <span data-ttu-id="ee26e-104">En el ejemplo MsgBox se utiliza la siguiente función no administrada, que se muestra con su declaración de función original:</span><span class="sxs-lookup"><span data-stu-id="ee26e-104">The MsgBox sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
- <span data-ttu-id="ee26e-105">**MessageBox** exportada desde User32.dll.</span><span class="sxs-lookup"><span data-stu-id="ee26e-105">**MessageBox** exported from User32.dll.</span></span>  
  
    ```cpp
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,
       UINT uType);  
    ```  
  
 <span data-ttu-id="ee26e-106">En este ejemplo, la clase `NativeMethods` contiene un prototipo administrado para cada función no administrada a la que se llama desde la clase `MsgBoxSample`.</span><span class="sxs-lookup"><span data-stu-id="ee26e-106">In this sample, the `NativeMethods` class contains a managed prototype for each unmanaged function called by the `MsgBoxSample` class.</span></span> <span data-ttu-id="ee26e-107">Los métodos de prototipo administrados `MsgBox`, `MsgBox2` y `MsgBox3` tienen declaraciones diferentes para la misma función no administrada.</span><span class="sxs-lookup"><span data-stu-id="ee26e-107">The managed prototype methods `MsgBox`, `MsgBox2`, and `MsgBox3` have different declarations for the same unmanaged function.</span></span>  
  
 <span data-ttu-id="ee26e-108">La declaración para `MsgBox2` produce una salida incorrecta en el cuadro de mensaje porque el tipo de caracteres, especificado como ANSI, no corresponde con el punto de entrada `MessageBoxW`, que es el nombre de la función Unicode.</span><span class="sxs-lookup"><span data-stu-id="ee26e-108">The declaration for `MsgBox2` produces incorrect output in the message box because the character type, specified as ANSI, is mismatched with the entry point `MessageBoxW`, which is the name of the Unicode function.</span></span> <span data-ttu-id="ee26e-109">La declaración de `MsgBox3` genera una falta de coincidencia entre los campos **EntryPoint**, **CharSet** y **ExactSpelling**.</span><span class="sxs-lookup"><span data-stu-id="ee26e-109">The declaration for `MsgBox3` creates a mismatch between the **EntryPoint**, **CharSet**, and **ExactSpelling** fields.</span></span> <span data-ttu-id="ee26e-110">Al llamar a `MsgBox3`, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="ee26e-110">When called, `MsgBox3` throws an exception.</span></span> <span data-ttu-id="ee26e-111">Para obtener información detallada sobre los nombres de cadena y la serialización de nombres, vea [Especificar un juego de caracteres](specifying-a-character-set.md).</span><span class="sxs-lookup"><span data-stu-id="ee26e-111">For detailed information on string naming and name marshaling, see [Specifying a Character Set](specifying-a-character-set.md).</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="ee26e-112">Declaración de prototipos</span><span class="sxs-lookup"><span data-stu-id="ee26e-112">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)]
 [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)]
 [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## <a name="calling-functions"></a><span data-ttu-id="ee26e-113">Llamadas a funciones</span><span class="sxs-lookup"><span data-stu-id="ee26e-113">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)]
 [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)]
 [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="ee26e-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ee26e-114">See also</span></span>

- [<span data-ttu-id="ee26e-115">Serialización de cadenas</span><span class="sxs-lookup"><span data-stu-id="ee26e-115">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="ee26e-116">Cálculo de referencias predeterminado para cadenas</span><span class="sxs-lookup"><span data-stu-id="ee26e-116">Default Marshaling for Strings</span></span>](default-marshaling-for-strings.md)
- [<span data-ttu-id="ee26e-117">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="ee26e-117">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="ee26e-118">Especificar un juego de caracteres</span><span class="sxs-lookup"><span data-stu-id="ee26e-118">Specifying a Character Set</span></span>](specifying-a-character-set.md)
