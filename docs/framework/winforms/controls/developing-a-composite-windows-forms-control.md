---
title: Desarrollar un control compuesto
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: d80564c71dad57ce9145fbedd45a1396df1ddfec
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746029"
---
# <a name="develop-a-composite-windows-forms-control"></a><span data-ttu-id="ee5d9-102">Desarrollar un control de Windows Forms compuesto</span><span class="sxs-lookup"><span data-stu-id="ee5d9-102">Develop a composite Windows Forms control</span></span>

<span data-ttu-id="ee5d9-103">Puede desarrollar un control de Windows Forms compuesto mediante la combinación de otros controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ee5d9-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="ee5d9-104">Los controles compuestos que derivan de <xref:System.Web.UI.UserControl> se denominan controles de usuario.</span><span class="sxs-lookup"><span data-stu-id="ee5d9-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="ee5d9-105">La clase base, <xref:System.Windows.Forms.UserControl>, proporciona el enrutamiento de teclado de los controles secundarios, lo que asegura que puedan recibir el foco.</span><span class="sxs-lookup"><span data-stu-id="ee5d9-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="ee5d9-106">Para obtener un ejemplo de un control de usuario, vea el ejemplo <xref:System.Windows.Forms.UserControl> en [Cómo: aplicar atributos en controles de Windows Forms](how-to-apply-attributes-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ee5d9-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>

<span data-ttu-id="ee5d9-107">El diseñador de Windows Forms de Visual Studio proporciona una compatibilidad enriquecida en tiempo de diseño para la creación de controles de usuario.</span><span class="sxs-lookup"><span data-stu-id="ee5d9-107">The Windows Forms designer in Visual Studio provides rich design-time support for authoring user controls.</span></span>

- [<span data-ttu-id="ee5d9-108">Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos de cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="ee5d9-108">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)

- [<span data-ttu-id="ee5d9-109">Tutorial: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="ee5d9-109">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)

- [<span data-ttu-id="ee5d9-110">Tutorial: Heredar de un control de Windows Forms con Visual C#</span><span class="sxs-lookup"><span data-stu-id="ee5d9-110">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)

- [<span data-ttu-id="ee5d9-111">Cómo: Proporcionar un mapa de bits del cuadro de herramientas para un control</span><span class="sxs-lookup"><span data-stu-id="ee5d9-111">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)

- [<span data-ttu-id="ee5d9-112">Cómo: Heredar de controles de Windows Forms existentes</span><span class="sxs-lookup"><span data-stu-id="ee5d9-112">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)

- [<span data-ttu-id="ee5d9-113">Tutorial: Depurar controles personalizados de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="ee5d9-113">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)

- [<span data-ttu-id="ee5d9-114">Cómo: Heredar de una clase de control</span><span class="sxs-lookup"><span data-stu-id="ee5d9-114">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)

- [<span data-ttu-id="ee5d9-115">Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ee5d9-115">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)

- [<span data-ttu-id="ee5d9-116">Cómo: Alinear un control con los bordes de los formularios en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="ee5d9-116">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)

- [<span data-ttu-id="ee5d9-117">cómo: Heredar de la clase UserControl</span><span class="sxs-lookup"><span data-stu-id="ee5d9-117">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)

- [<span data-ttu-id="ee5d9-118">Cómo: Crear controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee5d9-118">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)

- [<span data-ttu-id="ee5d9-119">Cómo: Crear controles compuestos</span><span class="sxs-lookup"><span data-stu-id="ee5d9-119">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)

- [<span data-ttu-id="ee5d9-120">Tutorial: Crear un control compuesto con Visual C#</span><span class="sxs-lookup"><span data-stu-id="ee5d9-120">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)

- [<span data-ttu-id="ee5d9-121">Tutorial: Crear un control de Windows Forms que aproveche las características en tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ee5d9-121">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

- <span data-ttu-id="ee5d9-122">[Cómo: Crear un control de Windows Forms que aproveche las características de tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ee5d9-122">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>

## <a name="see-also"></a><span data-ttu-id="ee5d9-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ee5d9-123">See also</span></span>

- [<span data-ttu-id="ee5d9-124">Aplicar atributos en controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee5d9-124">How to: Apply Attributes in Windows Forms Controls</span></span>](how-to-apply-attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="ee5d9-125">Desarrollar controles personalizados de Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ee5d9-125">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="ee5d9-126">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="ee5d9-126">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
