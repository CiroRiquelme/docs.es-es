---
title: 'Cómo: Animar un objeto mediante fotogramas clave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 0bc33b189fd856dbe8106c1db35bc18e27ea131e
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344703"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="48343-102">Cómo: Animar un objeto mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="48343-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="48343-103">En este ejemplo se muestra cómo animar un <xref:System.Windows.Controls.Page.Background%2A> objeto, <xref:System.Windows.Controls.Page> que en este ejemplo es la propiedad de un control, mediante marcos clave.</span><span class="sxs-lookup"><span data-stu-id="48343-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48343-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="48343-104">Example</span></span>  
 <span data-ttu-id="48343-105">En el ejemplo <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> siguiente se utiliza <xref:System.Windows.Controls.Page.Background%2A> la clase <xref:System.Windows.Controls.Page> para animar los cambios de color para la propiedad de un control.</span><span class="sxs-lookup"><span data-stu-id="48343-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="48343-106">La animación de ejemplo cambia a un pincel de fondo diferente a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="48343-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="48343-107">Esta animación <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> utiliza la clase para crear tres fotogramas clave diferentes.</span><span class="sxs-lookup"><span data-stu-id="48343-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="48343-108">La animación utiliza fotogramas clave de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="48343-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="48343-109">Al final del primer segundo, anima una <xref:System.Windows.Media.LinearGradientBrush> instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="48343-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="48343-110">Esta sección del ejemplo aplica un degradado lineal al color de fondo para que el color pase de amarillo a naranja a rojo.</span><span class="sxs-lookup"><span data-stu-id="48343-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="48343-111">Al final del segundo siguiente, anima una <xref:System.Windows.Media.RadialGradientBrush> instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="48343-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="48343-112">Esta sección del ejemplo aplica un degradado radial al color de fondo para que el color pase de blanco a azul a negro.</span><span class="sxs-lookup"><span data-stu-id="48343-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="48343-113">Al final del tercer segundo, anima una <xref:System.Windows.Media.DrawingBrush> instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="48343-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="48343-114">Esta sección del ejemplo aplica un patrón de tablero de ajedrez al fondo.</span><span class="sxs-lookup"><span data-stu-id="48343-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="48343-115">La animación comienza de nuevo y se repite indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="48343-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48343-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>es el único tipo de fotograma clave <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> que puede usar con la clase.</span><span class="sxs-lookup"><span data-stu-id="48343-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="48343-117">Los fotogramas clave como <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> crear cambios repentinos en los valores, es decir, los cambios de color en este ejemplo se producen repentinamente.</span><span class="sxs-lookup"><span data-stu-id="48343-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="48343-118">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="48343-118">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48343-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="48343-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="48343-120">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="48343-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="48343-121">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="48343-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
