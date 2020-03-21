---
title: Compatibilidad de UI Automation con controles estándar
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 36028d589e98177f6a0e83092edd656860b1a8d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179850"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="5ec52-102">Compatibilidad de UI Automation con controles estándar</span><span class="sxs-lookup"><span data-stu-id="5ec52-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="5ec52-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="5ec52-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5ec52-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="5ec52-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="5ec52-105">Este tema contiene [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] información sobre la compatibilidad [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]con controles estándar en aplicaciones desarrolladas para los marcos de trabajo , Win32 y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5ec52-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="5ec52-106">Controles de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="5ec52-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="5ec52-107">Todos los elementos de control [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] que ofrecen información o compatibilidad para la interacción del usuario tienen compatibilidad nativa completa con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ec52-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="5ec52-108">Otros elementos, como paneles, no son visibles para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ec52-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a><span data-ttu-id="5ec52-109">Controles de Win32</span><span class="sxs-lookup"><span data-stu-id="5ec52-109">Win32 Controls</span></span>  
 <span data-ttu-id="5ec52-110">La mayoría de los [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] controles Win32 se exponen a través de proveedores del lado cliente en UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="5ec52-110">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="5ec52-111">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="5ec52-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="5ec52-112">La compatibilidad completa solo se proporciona para los controles de la versión 6 de *ComCtrl32.dll*.</span><span class="sxs-lookup"><span data-stu-id="5ec52-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="5ec52-113">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="5ec52-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="5ec52-114">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="5ec52-114">Class name</span></span>|<span data-ttu-id="5ec52-115">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="5ec52-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="5ec52-116">Botón</span><span class="sxs-lookup"><span data-stu-id="5ec52-116">Button</span></span>|<span data-ttu-id="5ec52-117">Botón</span><span class="sxs-lookup"><span data-stu-id="5ec52-117">Button</span></span>|  
|<span data-ttu-id="5ec52-118">Botón</span><span class="sxs-lookup"><span data-stu-id="5ec52-118">Button</span></span>|<span data-ttu-id="5ec52-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5ec52-119">RadioButton</span></span>|  
|<span data-ttu-id="5ec52-120">Botón</span><span class="sxs-lookup"><span data-stu-id="5ec52-120">Button</span></span>|<span data-ttu-id="5ec52-121">Grupo</span><span class="sxs-lookup"><span data-stu-id="5ec52-121">Group</span></span>|  
|<span data-ttu-id="5ec52-122">Botón</span><span class="sxs-lookup"><span data-stu-id="5ec52-122">Button</span></span>|<span data-ttu-id="5ec52-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-123">CheckBox</span></span>|  
|<span data-ttu-id="5ec52-124">Botón</span><span class="sxs-lookup"><span data-stu-id="5ec52-124">Button</span></span>|<span data-ttu-id="5ec52-125">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="5ec52-125">Hyperlink</span></span>|  
|<span data-ttu-id="5ec52-126">Botón</span><span class="sxs-lookup"><span data-stu-id="5ec52-126">Button</span></span>|<span data-ttu-id="5ec52-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="5ec52-127">SplitButton</span></span>|  
|<span data-ttu-id="5ec52-128">Botón</span><span class="sxs-lookup"><span data-stu-id="5ec52-128">Button</span></span>|<span data-ttu-id="5ec52-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-129">CheckBox</span></span>|  
|<span data-ttu-id="5ec52-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="5ec52-130">ComboBoxEx32</span></span>|<span data-ttu-id="5ec52-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-131">ComboBox</span></span>|  
|<span data-ttu-id="5ec52-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-132">ComboBox</span></span>|<span data-ttu-id="5ec52-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-133">ComboBox</span></span>|  
|<span data-ttu-id="5ec52-134">Editar</span><span class="sxs-lookup"><span data-stu-id="5ec52-134">Edit</span></span>|<span data-ttu-id="5ec52-135">Documento</span><span class="sxs-lookup"><span data-stu-id="5ec52-135">Document</span></span>|  
|<span data-ttu-id="5ec52-136">Editar</span><span class="sxs-lookup"><span data-stu-id="5ec52-136">Edit</span></span>|<span data-ttu-id="5ec52-137">Editar</span><span class="sxs-lookup"><span data-stu-id="5ec52-137">Edit</span></span>|  
|<span data-ttu-id="5ec52-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="5ec52-138">SysLink</span></span>|<span data-ttu-id="5ec52-139">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="5ec52-139">Hyperlink</span></span>|  
|<span data-ttu-id="5ec52-140">estática</span><span class="sxs-lookup"><span data-stu-id="5ec52-140">Static</span></span>|<span data-ttu-id="5ec52-141">Texto</span><span class="sxs-lookup"><span data-stu-id="5ec52-141">Text</span></span>|  
|<span data-ttu-id="5ec52-142">estática</span><span class="sxs-lookup"><span data-stu-id="5ec52-142">Static</span></span>|<span data-ttu-id="5ec52-143">Imagen</span><span class="sxs-lookup"><span data-stu-id="5ec52-143">Image</span></span>|  
|<span data-ttu-id="5ec52-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="5ec52-144">SysIPAddress32</span></span>|<span data-ttu-id="5ec52-145">Personalizado</span><span class="sxs-lookup"><span data-stu-id="5ec52-145">Custom</span></span>|  
|<span data-ttu-id="5ec52-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="5ec52-146">SysHeader32</span></span>|<span data-ttu-id="5ec52-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="5ec52-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="5ec52-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="5ec52-148">SysListView32</span></span>|<span data-ttu-id="5ec52-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="5ec52-149">DataGrid</span></span>|  
|<span data-ttu-id="5ec52-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="5ec52-150">SysListView32</span></span>|<span data-ttu-id="5ec52-151">List</span><span class="sxs-lookup"><span data-stu-id="5ec52-151">List</span></span>|  
|<span data-ttu-id="5ec52-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-152">ListBox</span></span>|<span data-ttu-id="5ec52-153">List</span><span class="sxs-lookup"><span data-stu-id="5ec52-153">List</span></span>|  
|<span data-ttu-id="5ec52-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-154">ListBox</span></span>|<span data-ttu-id="5ec52-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="5ec52-155">ListItem</span></span>|  
|<span data-ttu-id="5ec52-156">#32768</span><span class="sxs-lookup"><span data-stu-id="5ec52-156">#32768</span></span>|<span data-ttu-id="5ec52-157">Menú</span><span class="sxs-lookup"><span data-stu-id="5ec52-157">Menu</span></span>|  
|<span data-ttu-id="5ec52-158">#32768</span><span class="sxs-lookup"><span data-stu-id="5ec52-158">#32768</span></span>|<span data-ttu-id="5ec52-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="5ec52-159">MenuItem</span></span>|  
|<span data-ttu-id="5ec52-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="5ec52-160">msctls_progress32</span></span>|<span data-ttu-id="5ec52-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="5ec52-161">ProgressBar</span></span>|  
|<span data-ttu-id="5ec52-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="5ec52-162">RichEdit</span></span>|<span data-ttu-id="5ec52-163">Documentar.</span><span class="sxs-lookup"><span data-stu-id="5ec52-163">Document.</span></span> <span data-ttu-id="5ec52-164">Vea la nota.</span><span class="sxs-lookup"><span data-stu-id="5ec52-164">See note.</span></span>|  
|<span data-ttu-id="5ec52-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="5ec52-165">RichEdit20A</span></span>|<span data-ttu-id="5ec52-166">Documento</span><span class="sxs-lookup"><span data-stu-id="5ec52-166">Document</span></span>|  
|<span data-ttu-id="5ec52-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="5ec52-167">RichEdit20W</span></span>|<span data-ttu-id="5ec52-168">Documento</span><span class="sxs-lookup"><span data-stu-id="5ec52-168">Document</span></span>|  
|<span data-ttu-id="5ec52-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="5ec52-169">RichEdit50W</span></span>|<span data-ttu-id="5ec52-170">Documento</span><span class="sxs-lookup"><span data-stu-id="5ec52-170">Document</span></span>|  
|<span data-ttu-id="5ec52-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="5ec52-171">ScrollBar</span></span>|<span data-ttu-id="5ec52-172">Control deslizante</span><span class="sxs-lookup"><span data-stu-id="5ec52-172">Slider</span></span>|  
|<span data-ttu-id="5ec52-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="5ec52-173">msctls_trackbar32</span></span>|<span data-ttu-id="5ec52-174">Control deslizante</span><span class="sxs-lookup"><span data-stu-id="5ec52-174">Slider</span></span>|  
|<span data-ttu-id="5ec52-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="5ec52-175">msctls_updown32</span></span>|<span data-ttu-id="5ec52-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="5ec52-176">Spinner</span></span>|  
|<span data-ttu-id="5ec52-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="5ec52-177">msctls_statusbar32</span></span>|<span data-ttu-id="5ec52-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="5ec52-178">StatusBar</span></span>|  
|<span data-ttu-id="5ec52-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="5ec52-179">SysTabControl32</span></span>|<span data-ttu-id="5ec52-180">Pestaña</span><span class="sxs-lookup"><span data-stu-id="5ec52-180">Tab</span></span>|  
|<span data-ttu-id="5ec52-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="5ec52-181">SysTabControl32</span></span>|<span data-ttu-id="5ec52-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="5ec52-182">TabItem</span></span>|  
|<span data-ttu-id="5ec52-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5ec52-183">ToolbarWindow32</span></span>|<span data-ttu-id="5ec52-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="5ec52-184">ToolBar</span></span>|  
|<span data-ttu-id="5ec52-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5ec52-185">ToolbarWindow32</span></span>|<span data-ttu-id="5ec52-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="5ec52-186">MenuItem</span></span>|  
|<span data-ttu-id="5ec52-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5ec52-187">ToolbarWindow32</span></span>|<span data-ttu-id="5ec52-188">Botón</span><span class="sxs-lookup"><span data-stu-id="5ec52-188">Button</span></span>|  
|<span data-ttu-id="5ec52-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5ec52-189">ToolbarWindow32</span></span>|<span data-ttu-id="5ec52-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-190">CheckBox</span></span>|  
|<span data-ttu-id="5ec52-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5ec52-191">ToolbarWindow32</span></span>|<span data-ttu-id="5ec52-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5ec52-192">RadioButton</span></span>|  
|<span data-ttu-id="5ec52-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5ec52-193">ToolbarWindow32</span></span>|<span data-ttu-id="5ec52-194">Separador</span><span class="sxs-lookup"><span data-stu-id="5ec52-194">Separator</span></span>|  
|<span data-ttu-id="5ec52-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="5ec52-195">tooltips_class32</span></span>|<span data-ttu-id="5ec52-196">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="5ec52-196">ToolTip</span></span>|  
|<span data-ttu-id="5ec52-197">#32774</span><span class="sxs-lookup"><span data-stu-id="5ec52-197">#32774</span></span>|<span data-ttu-id="5ec52-198">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="5ec52-198">ToolTip</span></span>|  
|<span data-ttu-id="5ec52-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="5ec52-199">ReBarWindow32</span></span>|<span data-ttu-id="5ec52-200">Barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="5ec52-200">Toolbar</span></span>|  
|<span data-ttu-id="5ec52-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="5ec52-201">SysTreeView32</span></span>|<span data-ttu-id="5ec52-202">Árbol</span><span class="sxs-lookup"><span data-stu-id="5ec52-202">Tree</span></span>|  
|<span data-ttu-id="5ec52-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="5ec52-203">SysTreeView32</span></span>|<span data-ttu-id="5ec52-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="5ec52-204">TreeItem</span></span>|  
  
 <span data-ttu-id="5ec52-205">**Nota** El control RichEdit solo se admite para las versiones incluidas con Windows Vista (en RichEd20.dll versión 3.1 y posteriores, y MsftEdit.dll versión 4.1 y posteriores).</span><span class="sxs-lookup"><span data-stu-id="5ec52-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="5ec52-206">No se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="5ec52-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="5ec52-207">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="5ec52-207">Class name</span></span>|<span data-ttu-id="5ec52-208">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="5ec52-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="5ec52-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="5ec52-209">SysAnimate32</span></span>|<span data-ttu-id="5ec52-210">Imagen</span><span class="sxs-lookup"><span data-stu-id="5ec52-210">Image</span></span>|  
|<span data-ttu-id="5ec52-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="5ec52-211">SysPager</span></span>|<span data-ttu-id="5ec52-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="5ec52-212">Spinner</span></span>|  
|<span data-ttu-id="5ec52-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="5ec52-213">SysDateTimePick32</span></span>|<span data-ttu-id="5ec52-214">Personalizado</span><span class="sxs-lookup"><span data-stu-id="5ec52-214">Custom</span></span>|  
|<span data-ttu-id="5ec52-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="5ec52-215">SysMonthCal32</span></span>|<span data-ttu-id="5ec52-216">Calendario</span><span class="sxs-lookup"><span data-stu-id="5ec52-216">Calendar</span></span>|  
|<span data-ttu-id="5ec52-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="5ec52-217">MS_WINNOTE</span></span>|<span data-ttu-id="5ec52-218">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="5ec52-218">Tooltip</span></span>|  
|<span data-ttu-id="5ec52-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="5ec52-219">VBBubble</span></span>|<span data-ttu-id="5ec52-220">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="5ec52-220">Tooltip</span></span>|  
|<span data-ttu-id="5ec52-221">ScrollBar (cuando se usa como control independiente)</span><span class="sxs-lookup"><span data-stu-id="5ec52-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="5ec52-222">Control deslizante</span><span class="sxs-lookup"><span data-stu-id="5ec52-222">Slider</span></span>|  
|<span data-ttu-id="5ec52-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="5ec52-223">SuperGrid</span></span>|<span data-ttu-id="5ec52-224">Personalizado</span><span class="sxs-lookup"><span data-stu-id="5ec52-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a><span data-ttu-id="5ec52-225">Controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5ec52-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="5ec52-226">Los controles de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] formularios Windows Forms se exponen a través de proveedores del lado cliente en UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="5ec52-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="5ec52-227">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="5ec52-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="5ec52-228">Normalmente, los controles de formularios Windows Forms que son [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]contenedores administrados para controles comunes de Win32 son compatibles con .</span><span class="sxs-lookup"><span data-stu-id="5ec52-228">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="5ec52-229">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="5ec52-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="5ec52-230">Class Name (Nombre de clase)</span><span class="sxs-lookup"><span data-stu-id="5ec52-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="5ec52-231">Botón</span><span class="sxs-lookup"><span data-stu-id="5ec52-231">Button</span></span>|  
|<span data-ttu-id="5ec52-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-232">CheckBox</span></span>|  
|<span data-ttu-id="5ec52-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-233">CheckedListBox</span></span>|  
|<span data-ttu-id="5ec52-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="5ec52-234">ColorDialog</span></span>|  
|<span data-ttu-id="5ec52-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-235">ComboBox</span></span>|  
|<span data-ttu-id="5ec52-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="5ec52-236">FolderBrowser</span></span>|  
|<span data-ttu-id="5ec52-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="5ec52-237">FontDialog</span></span>|  
|<span data-ttu-id="5ec52-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-238">GroupBox</span></span>|  
|<span data-ttu-id="5ec52-239">HScrollBar</span><span class="sxs-lookup"><span data-stu-id="5ec52-239">HscrollBar</span></span>|  
|<span data-ttu-id="5ec52-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="5ec52-240">ImageList</span></span>|  
|<span data-ttu-id="5ec52-241">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="5ec52-241">Label</span></span>|  
|<span data-ttu-id="5ec52-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-242">ListBox</span></span>|  
|<span data-ttu-id="5ec52-243">ListView</span><span class="sxs-lookup"><span data-stu-id="5ec52-243">ListView</span></span>|  
|<span data-ttu-id="5ec52-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="5ec52-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="5ec52-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="5ec52-245">MonthCalendar</span></span>|  
|<span data-ttu-id="5ec52-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="5ec52-246">NotifyIcon</span></span>|  
|<span data-ttu-id="5ec52-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="5ec52-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="5ec52-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="5ec52-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="5ec52-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="5ec52-249">PrintDialog</span></span>|  
|<span data-ttu-id="5ec52-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="5ec52-250">ProgressBar</span></span>|  
|<span data-ttu-id="5ec52-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5ec52-251">RadioButton</span></span>|  
|<span data-ttu-id="5ec52-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-252">RichTextBox</span></span>|  
|<span data-ttu-id="5ec52-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="5ec52-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="5ec52-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="5ec52-254">ScrollableControl</span></span>|  
|<span data-ttu-id="5ec52-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="5ec52-255">SoundPlayer</span></span>|  
|<span data-ttu-id="5ec52-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="5ec52-256">StatusBar</span></span>|  
|<span data-ttu-id="5ec52-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="5ec52-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="5ec52-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-258">TextBox</span></span>|  
|<span data-ttu-id="5ec52-259">Timer</span><span class="sxs-lookup"><span data-stu-id="5ec52-259">Timer</span></span>|  
|<span data-ttu-id="5ec52-260">Barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="5ec52-260">Toolbar</span></span>|  
|<span data-ttu-id="5ec52-261">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="5ec52-261">ToolTip</span></span>|  
|<span data-ttu-id="5ec52-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="5ec52-262">TrackBar</span></span>|  
|<span data-ttu-id="5ec52-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="5ec52-263">TreeView</span></span>|  
|<span data-ttu-id="5ec52-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="5ec52-264">VscrollBar</span></span>|  
|<span data-ttu-id="5ec52-265">ExploradorWeb</span><span class="sxs-lookup"><span data-stu-id="5ec52-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="5ec52-266">Los siguientes controles [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] se exponen solo a través de su compatibilidad con Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="5ec52-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="5ec52-267">Es posible que algunas funciones no estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="5ec52-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="5ec52-268">Nombre del control</span><span class="sxs-lookup"><span data-stu-id="5ec52-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="5ec52-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="5ec52-269">BindingSource</span></span>|  
|<span data-ttu-id="5ec52-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="5ec52-270">DataGrid</span></span>|  
|<span data-ttu-id="5ec52-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="5ec52-271">DataGridView</span></span>|  
|<span data-ttu-id="5ec52-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="5ec52-272">DataNavigator</span></span>|  
|<span data-ttu-id="5ec52-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="5ec52-273">DomainUpDown</span></span>|  
|<span data-ttu-id="5ec52-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="5ec52-274">ErrorProvider</span></span>|  
|<span data-ttu-id="5ec52-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5ec52-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="5ec52-276">Form</span><span class="sxs-lookup"><span data-stu-id="5ec52-276">Form</span></span>|  
|<span data-ttu-id="5ec52-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="5ec52-277">LinkLabel</span></span>|  
|<span data-ttu-id="5ec52-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="5ec52-278">HelpProvider</span></span>|  
|<span data-ttu-id="5ec52-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="5ec52-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="5ec52-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="5ec52-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="5ec52-281">NumericUpDown</span></span>|  
|<span data-ttu-id="5ec52-282">Panel</span><span class="sxs-lookup"><span data-stu-id="5ec52-282">Panel</span></span>|  
|<span data-ttu-id="5ec52-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="5ec52-283">PictureBox</span></span>|  
|<span data-ttu-id="5ec52-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="5ec52-284">PrintDocument</span></span>|  
|<span data-ttu-id="5ec52-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="5ec52-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="5ec52-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="5ec52-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="5ec52-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="5ec52-287">PropertyGrid</span></span>|  
|<span data-ttu-id="5ec52-288">Control de usuario</span><span class="sxs-lookup"><span data-stu-id="5ec52-288">UserControl</span></span>|  
|<span data-ttu-id="5ec52-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="5ec52-289">ToolStrip</span></span>|  
|<span data-ttu-id="5ec52-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5ec52-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="5ec52-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="5ec52-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="5ec52-292">Divisor</span><span class="sxs-lookup"><span data-stu-id="5ec52-292">Splitter</span></span>|  
|<span data-ttu-id="5ec52-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="5ec52-293">RaftingContainer</span></span>|  
|<span data-ttu-id="5ec52-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="5ec52-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ec52-295">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5ec52-295">See also</span></span>

- [<span data-ttu-id="5ec52-296">Tipos de control de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="5ec52-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
