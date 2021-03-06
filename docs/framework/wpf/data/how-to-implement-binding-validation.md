---
title: 'Cómo: Implementar la validación de enlaces'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 245b05d9cfa7ca66dec310bd9a5291def0101d19
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459106"
---
# <a name="how-to-implement-binding-validation"></a>Cómo: Implementar la validación de enlaces

En este ejemplo se muestra cómo usar un <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> y un desencadenador de estilo para proporcionar comentarios visuales para informar al usuario cuando se escribe un valor no válido, en función de una regla de validación personalizada.

## <a name="example"></a>Ejemplo

El contenido de texto del <xref:System.Windows.Controls.TextBox> en el ejemplo siguiente se enlaza a la propiedad `Age` (de tipo int) de un objeto de origen de enlace denominado `ods`. El enlace se configura para usar una regla de validación denominada `AgeRangeRule`, por lo que si el usuario especifica caracteres no numéricos o un valor inferior a 21 o superior a 130, aparece un signo de exclamación junto al cuadro de texto y aparece información sobre herramientas con el mensaje de error cuando el usuario coloca el mouse sobre el cuadro de texto.

[!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]

En el ejemplo siguiente se muestra la implementación de `AgeRangeRule`, que hereda de <xref:System.Windows.Controls.ValidationRule> e invalida el método <xref:System.Windows.Controls.ValidationRule.Validate%2A>. Se llama al método `Int32.Parse` en el valor para asegurarse de que no contiene ningún carácter no válido. El método <xref:System.Windows.Controls.ValidationRule.Validate%2A> devuelve un <xref:System.Windows.Controls.ValidationResult> que indica si el valor es válido en función de si se detecta una excepción durante el análisis y si el valor de edad está fuera de los límites inferior y superior.

[!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]
[!code-vb[BindValidation#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindValidation/VisualBasic/AgeRangeRule.vb#3)]

En el ejemplo siguiente se muestra el `validationTemplate` de <xref:System.Windows.Controls.ControlTemplate> personalizado que crea un signo de exclamación rojo para notificar al usuario de un error de validación. Las plantillas de control se usan para redefinir la apariencia de un control.

[!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]

Como se muestra en el ejemplo siguiente, el <xref:System.Windows.Controls.ToolTip> que muestra el mensaje de error se crea con el estilo denominado `textBoxInError`. Si el valor de <xref:System.Windows.Controls.Validation.HasError%2A> es `true`, el desencadenador establece la información sobre herramientas del <xref:System.Windows.Controls.TextBox> actual en el primer error de validación. La <xref:System.Windows.Data.Binding.RelativeSource%2A> se establece en <xref:System.Windows.Data.RelativeSourceMode.Self>, haciendo referencia al elemento actual.

[!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]

Para obtener el ejemplo completo, vea [ejemplo de validación de enlace](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).
  
Tenga en cuenta que si no proporciona un <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> personalizado, aparece la plantilla de error predeterminada para proporcionar información visual al usuario cuando se produce un error de validación. Vea "Validación de datos" en [Información sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md) para obtener más información. Además, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una regla de validación incorporada que selecciona las excepciones que se producen durante la actualización de la propiedad del origen de enlace. Para obtener más información, vea <xref:System.Windows.Controls.ExceptionValidationRule>.

## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
