---
title: Información general sobre el uso de controles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, controls
- controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: fddbe951-4485-459d-a5fd-665ea346dbc1
ms.openlocfilehash: ca8b9fab3c53e256792faf0969b5066d5e35f6c7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744350"
---
# <a name="overview-of-using-controls-in-windows-forms"></a><span data-ttu-id="d553b-102">Información general sobre cómo utilizar controles en los formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d553b-102">Overview of Using Controls in Windows Forms</span></span>
<span data-ttu-id="d553b-103">En este tema se describen los elementos esenciales de una aplicación Windows Forms y se proporciona un ejemplo sencillo que usa controles y controla eventos en una aplicación Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d553b-103">This topic describes the essential elements of a Windows Forms application and provides a simple example that uses controls and handles events in a Windows Forms application.</span></span>  
  
## <a name="simple-windows-forms-applications"></a><span data-ttu-id="d553b-104">Aplicaciones Windows Forms simples</span><span class="sxs-lookup"><span data-stu-id="d553b-104">Simple Windows Forms Applications</span></span>  
 <span data-ttu-id="d553b-105">Como mínimo, una aplicación Windows Forms consta de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="d553b-105">At a minimum, a Windows Forms application consists of the following elements:</span></span>  
  
- <span data-ttu-id="d553b-106">Una o más clases que derivan de <xref:System.Windows.Forms.Form?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d553b-106">One or more classes that derive from <xref:System.Windows.Forms.Form?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="d553b-107">`Main` método que invoca el `static` (`shared` en Visual Basic) <xref:System.Windows.Forms.Application.Run%2A> método y le pasa una instancia de <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="d553b-107">A `Main` method that invokes the `static` (`shared` in Visual Basic) <xref:System.Windows.Forms.Application.Run%2A> method and passes a <xref:System.Windows.Forms.Form> instance to it.</span></span> <span data-ttu-id="d553b-108">El método <xref:System.Windows.Forms.Application.Run%2A> procesa los mensajes del sistema operativo a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d553b-108">The <xref:System.Windows.Forms.Application.Run%2A> method processes messages from the operating system to the application.</span></span>  
  
 <span data-ttu-id="d553b-109">En el ejemplo de código siguiente se muestran los elementos esenciales de una aplicación Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d553b-109">The following code example shows the essential elements of a Windows Forms application.</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
  
Public Class MyForm  
   Inherits Form  
  
   Public Sub New()  
      Me.Text = "Hello World"  
   End Sub 'New  
  
   <STAThread()> _  
   Public Shared Sub Main()  
      Dim aform As New MyForm()  
      ' The Application.Run method processes messages from the operating system   
      ' to your application. If you comment out the next line of code,   
      ' your application will compile and execute, but because it is not in the  
      ' message loop, it will exit after an instance of the form is created.  
      Application.Run(aform)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
  
public class MyForm : Form {  
  
   public MyForm() {  
      this.Text = "Hello World";  
   }  
   [STAThread]  
   public static void Main(string[] args) {  
     MyForm aform = new MyForm();  
// The Application.Run method processes messages from the operating system   
// to your application. If you comment out the next line of code,   
// your application will compile and execute, but because it is not in the // message loop, it will exit after an instance of the form is created.  
      Application.Run(aform);  
   }  
}  
```  
  
## <a name="using-controls-in-a-windows-forms-application"></a><span data-ttu-id="d553b-110">Usar controles en una aplicación Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d553b-110">Using Controls in a Windows Forms Application</span></span>  
 <span data-ttu-id="d553b-111">En el ejemplo de código siguiente se muestra una aplicación sencilla que muestra cómo Windows Forms aplicaciones utilizan los controles y controlan los eventos.</span><span class="sxs-lookup"><span data-stu-id="d553b-111">The following code example shows a simple application that illustrates how Windows Forms applications use controls and handle events.</span></span> <span data-ttu-id="d553b-112">El ejemplo consta de tres botones en un formulario; cada botón cambia el color de fondo al hacer clic en él.</span><span class="sxs-lookup"><span data-stu-id="d553b-112">The example consists of three buttons on a form; each button changes the background color when clicked.</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.ComponentModel  
Imports System.Windows.Forms  
Imports System.Resources  
Imports System.Drawing  
  
Public Class MyForm  
   Inherits Form  
   Private red As Button  
   Private blue As Button  
   Private green As Button  
  
   Public Sub New()  
      InitializeComponent()  
   End Sub  
  
   Protected Overloads Overrides Sub Dispose(disposing as Boolean)  
      MyBase.Dispose(disposing)  
   End Sub  
  
   ' InitializeComponent is a helper method for the constructor.   
   ' It is included for consistency with code that is   
   ' auto-generated by the Windows Forms designer in Visual Studio.   
   Private Sub InitializeComponent()  
  
      ' Creates three buttons, sets their properties, and attaches  
      ' an event handler to each button.  
      red = New Button()  
      red.Text = "Red"  
      red.Location = New Point(100, 50)  
      red.Size = New Size(50, 50)  
      AddHandler red.Click, AddressOf button_Click  
      Controls.Add(red)  
  
      blue = New Button()  
      blue.Text = "Blue"  
      blue.Location = New Point(100, 100)  
      blue.Size = New Size(50, 50)  
      AddHandler blue.Click, AddressOf button_Click  
      Controls.Add(blue)  
  
      green = New Button()  
      green.Text = "Green"  
      green.Location = New Point(100, 150)  
      green.Size = New Size(50, 50)  
      AddHandler green.Click, AddressOf button_Click  
      Controls.Add(green)  
   End Sub  
  
   ' Event handler.  
   Private Sub button_Click(sender As Object, e As EventArgs)  
      If sender Is red Then  
         Me.BackColor = Color.Red  
      Else  
         If sender Is blue Then  
            Me.BackColor = Color.Blue  
         Else  
            Me.BackColor = Color.Green  
         End If  
      End If   
   End Sub  
  
   ' The STAThreadAttribute informs the common language runtime that  
   ' Windows Forms uses the single-threaded apartment model.  
   <STAThread()> _  
   Public Shared Sub Main()  
      Application.Run(New MyForm())  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.ComponentModel;  
using System.Windows.Forms;  
using System.Resources;  
using System.Drawing;  
  
public class MyForm : Form {  
   private Button red;  
   private Button blue;  
   private Button green;  
  
   public MyForm() : base() {     
      InitializeComponent();     
   }  
  
   protected override void Dispose(bool disposing) {  
      base.Dispose(disposing);  
   }  
  
// InitializeComponent is a helper method for the constructor.   
// It is included for consistency with code that is   
// auto-generated by the Windows Forms designer in Visual Studio.   
   private void InitializeComponent() {  
  
// A delegate for the click event of a button. The argument to   
// the constructor contains a reference to the method that performs the   
// event handling logic.  
      EventHandler handler = new EventHandler(button_Click);  
  
// Creates three buttons, sets their properties, and attaches  
// an event handler to each button.  
  
      red = new Button();  
      red.Text = "Red";  
      red.Location = new Point(100, 50);  
      red.Size = new Size(50, 50);  
      red.Click +=handler;  
      Controls.Add(red);  
  
      blue = new Button();  
      blue.Text = "Blue";  
      blue.Location = new Point(100, 100);  
      blue.Size = new Size(50, 50);  
      blue.Click += handler;  
      Controls.Add(blue);  
  
      green = new Button();  
      green.Text = "Green";  
      green.Location = new Point(100, 150);  
      green.Size = new Size(50, 50);  
      green.Click += handler;  
      Controls.Add(green);        
      }  
  
   // Event handler.  
   private void button_Click(object sender, EventArgs e) {  
            if (sender == red) this.BackColor = Color.Red ;  
                  else if (sender == blue) this.BackColor = Color.Blue;  
                  else this.BackColor = Color.Green;  
        }  
   // The STAThreadAttribute informs the common language runtime that  
   // Windows Forms uses the single-threaded apartment model.  
  [STAThread]  
   public static void Main(string[] args) {  
   Application.Run(new MyForm());  
   }  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d553b-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d553b-113">See also</span></span>

- [<span data-ttu-id="d553b-114">Desarrollar controles personalizados de Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d553b-114">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="d553b-115">Fundamentos de desarrollo de controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d553b-115">Windows Forms Control Development Basics</span></span>](windows-forms-control-development-basics.md)
