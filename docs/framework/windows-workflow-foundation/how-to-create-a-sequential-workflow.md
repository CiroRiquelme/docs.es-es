---
title: Procedimiento para crear un flujo de trabajo secuencial
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: 61e3f01b1259536ff15d71526e91aef42069722e
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989703"
---
# <a name="how-to-create-a-sequential-workflow"></a>Procedimiento para crear un flujo de trabajo secuencial

Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas. En este tema se describe cómo crear un flujo de trabajo que usa tanto actividades integradas <xref:System.Activities.Statements.Sequence> , como la actividad, y las actividades personalizadas [de los procedimientos anteriores: Cree un tema](how-to-create-an-activity.md) de la actividad. El flujo de trabajo modela un juego de adivinanzas de números.

> [!NOTE]
> Cada uno de los temas del tutorial de introducción depende de los temas anteriores. Para completar este tema, primero debe completar [el procedimiento: Cree una actividad](how-to-create-an-activity.md).

> [!NOTE]
> Para descargar una versión completa del tutorial, consulte [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45): tutorial introductorio)](https://go.microsoft.com/fwlink/?LinkID=248976).

## <a name="to-create-the-workflow"></a>Para crear el flujo de trabajo

1. Haga clic con el botón secundario en **NumberGuessWorkflowActivities** en **Explorador de soluciones** y seleccione **Agregar**, **nuevo elemento**.

2. En el nodo **instalado**, **elementos comunes** , seleccione **flujo de trabajo**. Seleccione **actividad** en la lista **flujo de trabajo** .

3. Escriba `SequentialNumberGuessWorkflow` en el cuadro **nombre** y haga clic en **Agregar**.

4. Arrastre una actividad **Sequence** de la sección **flujo de control** del **cuadro de herramientas** y colóquela en la etiqueta **colocar actividad aquí** en la superficie de diseño de flujo de trabajo.

## <a name="to-create-the-workflow-variables-and-arguments"></a>Para crear las variables y argumentos de flujo de trabajo

1. Haga doble clic en **SequentialNumberGuessWorkflow. Xaml** en **Explorador de soluciones** para mostrar el flujo de trabajo en el diseñador, si aún no se muestra.

2. Haga clic en **argumentos** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **argumentos** .

3. Haga clic en **crear argumento**.

4. Escriba `MaxNumber` en el cuadro **nombre** , seleccione **en en** la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione Entrar para guardar el argumento.

5. Haga clic en **crear argumento**.

6. Escriba `Turns` en el cuadro **nombre** que se encuentra debajo del argumento `MaxNumber` recién agregado, seleccione **salida** en la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione Entrar.

7. Haga clic en **argumentos** en el lado inferior izquierdo del diseñador de actividad para cerrar el panel **argumentos** .

8. Haga clic en **variables** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **variables** .

9. Haga clic en **crear variable**.

    > [!TIP]
    > Si no se muestra ningún cuadro **crear variable** , haga clic en la actividad **secuencia** en la superficie del diseñador de flujo de trabajo para seleccionarla.

10. Escriba `Guess` en el cuadro **nombre** , seleccione **Int32** en la lista desplegable **tipo de variable** y presione Entrar para guardar la variable.

11. Haga clic en **crear variable**.

12. Escriba `Target` en el cuadro **nombre** , seleccione **Int32** en la lista desplegable **tipo de variable** y presione Entrar para guardar la variable.

13. Haga clic en **variables** en el lado inferior izquierdo del diseñador de actividad para cerrar el panel **variables** .

## <a name="to-add-the-workflow-activities"></a>Para agregar actividades de flujo de trabajo

1. Arrastre una actividad **assign** de la sección **primitivas** del **cuadro de herramientas** y colóquela en la actividad **Sequence** . Escriba `Target` en el cuadro **para** y la siguiente expresión en el cuadro **Escriba C# una expresión** o **Escriba una expresión de VB** .

    ```vb
    New System.Random().Next(1, MaxNumber + 1)
    ```

    ```csharp
    new System.Random().Next(1, MaxNumber + 1)
    ```

    > [!TIP]
    > Si no se muestra la ventana **cuadro de herramientas** , seleccione **cuadro de herramientas** en el menú **Ver** .

2. Arrastre una actividad **While** de la sección **flujo de control** del **cuadro de herramientas** y colóquela en el flujo de trabajo para que esté debajo de la actividad **assign** .

3. Escriba la siguiente expresión en el **cuadro de valor** de la propiedad **condición** de la actividad.

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

     Una actividad <xref:System.Activities.Statements.DoWhile> ejecuta sus actividades secundarias y después evalúa su <xref:System.Activities.Statements.DoWhile.Condition%2A>. Si <xref:System.Activities.Statements.DoWhile.Condition%2A> se evalúa como `True`, las actividades de <xref:System.Activities.Statements.DoWhile> se ejecutan de nuevo. En este ejemplo, se evalúa el intento del usuario y <xref:System.Activities.Statements.DoWhile> continúa hasta que se acierta el número.

4. Arrastre una actividad **prompt** de la sección **NumberGuessWorkflowActivities** del **cuadro de herramientas** y colóquela en la actividad **While** del paso anterior.

5. En la **ventana Propiedades**, escriba `"EnterGuess"` entre comillas en el cuadro de valor de la propiedad **BookmarkName** para la actividad **prompt** . Escriba `Guess` en el cuadro de valor de la propiedad **resultado** y escriba la siguiente expresión en el cuadro de la propiedad **texto** .

    ```vb
    "Please enter a number between 1 and " & MaxNumber
    ```

    ```csharp
    "Please enter a number between 1 and " + MaxNumber
    ```

    > [!TIP]
    > Si no se muestra la **ventana Propiedades** , seleccione **ventana Propiedades** en el menú **Ver** .

6. Arrastre una actividad **assign** desde la sección **primitivas** del **cuadro de herramientas** y colóquela en la actividad **While** para que siga la actividad **prompt** .

    > [!NOTE]
    > Al quitar la actividad **assign** , observe cómo el diseñador de flujo de trabajo agrega automáticamente una actividad **Sequence** para que contenga la actividad **prompt** y la actividad **assign** recién agregada.

7. Escriba `Turns` en el cuadro **para** y `Turns + 1` en el cuadro **Escriba C# una expresión** o **Escriba una expresión de VB** .

8. Arrastre una actividad **If** de la sección **flujo de control** del **cuadro de herramientas** y colóquela en la actividad **Sequence** para que siga la actividad **assign** recién agregada.

9. Escriba la siguiente expresión en el cuadro de valor de la propiedad **condición** de la actividad **If** .

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

10. Arrastre otra actividad **If** de la sección **flujo de control** del **cuadro de herramientas** y colóquela en la sección **then** de la primera actividad **If** .

11. Escriba la siguiente expresión en el cuadro de valor de la propiedad **condición** de la actividad **If** recién agregada.

    ```text
    Guess < Target
    ```

12. Arrastre dos actividades **WriteLine** de la sección **primitivas** del **cuadro de herramientas** y colóquelas de modo que una esté en la sección **then** de la actividad **If** recién agregada, y otra esté en la sección **else** .

13. Haga clic en la actividad **WriteLine** en la sección **then** para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **Text** .

    ```text
    "Your guess is too low."
    ```

14. Haga clic en la actividad **WriteLine** en la sección **otro** para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **texto** .

    ```text
    "Your guess is too high."
    ```

     En el ejemplo siguiente se muestra el flujo de trabajo completado:

     ![Captura de pantalla que muestra el flujo de trabajo secuencial completado.](./media/how-to-create-a-sequential-workflow/complete-sequential-workflow.jpg)

## <a name="to-build-the-workflow"></a>Para compilar el flujo de trabajo

1. Presione CTRL+MAYÚS+B para compilar la solución.

     Para obtener instrucciones sobre cómo ejecutar el flujo de trabajo, consulte el tema siguiente [, How to: Ejecutar un flujo](how-to-run-a-workflow.md)de trabajo. Si ya ha completado el [procedimiento: Ejecutar un paso](how-to-run-a-workflow.md) de flujo de trabajo con un estilo diferente de flujo de trabajo y desea ejecutarlo mediante el flujo de trabajo secuencial desde este paso, vaya a la sección [para compilar y ejecutar la aplicación](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) de [cómo: Ejecutar un flujo](how-to-run-a-workflow.md)de trabajo.

## <a name="see-also"></a>Vea también

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [Programación de Windows Workflow Foundation](programming.md)
- [Diseño de flujos de trabajo](designing-workflows.md)
- [Tutorial de introducción](getting-started-tutorial.md)
- [Cómo: Crear una actividad](how-to-create-an-activity.md)
- [Procedimientos: Ejecutar un flujo de trabajo](how-to-run-a-workflow.md)
