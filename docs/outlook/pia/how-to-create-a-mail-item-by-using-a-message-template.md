---
title: Crear un elemento de correo con una plantilla de mensaje
TOCTitle: Create a mail item by using a message template
ms:assetid: 7d1ffc3b-d1a7-46d1-adb9-ac41e67f626a
ms:mtpsurl: https://msdn.microsoft.com/library/Bb623026(v=office.15)
ms:contentKeyID: 55119862
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 074a3eb7b83e4556b41549d18b81c97b96db1e6c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407103"
---
# <a name="create-a-mail-item-by-using-a-message-template"></a><span data-ttu-id="ffb8e-102">Crear un elemento de correo con una plantilla de mensaje</span><span class="sxs-lookup"><span data-stu-id="ffb8e-102">Create a mail item by using a message template</span></span>

<span data-ttu-id="ffb8e-103">Este ejemplo crea un elemento de correo mediante el método [CreateItemFromTemplate](https://msdn.microsoft.com/library/bb611329\(v=office.15\)).</span><span class="sxs-lookup"><span data-stu-id="ffb8e-103">This example creates a mail item by using the [M:Microsoft.Office.Interop.Outlook._Application.CreateItemFromTemplate(System.String,System.Object)](https://msdn.microsoft.com/library/bb611329\(v=office.15\)) method.</span></span>

## <a name="example"></a><span data-ttu-id="ffb8e-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ffb8e-104">Example</span></span>

<span data-ttu-id="ffb8e-105">Este ejemplo de código abre el archivo de plantilla Ivy.oft, asigna un tema y después guarda el mensaje en la carpeta Borradores.</span><span class="sxs-lookup"><span data-stu-id="ffb8e-105">This code sample opens the Ivy.oft template file, assigns a subject, and then saves the message to the Drafts folder.</span></span>

<span data-ttu-id="ffb8e-p101">El método **CreateItemFromTemplate** resulta útil si tiene un archivo de plantilla de formulario (.oft) de Outlook almacenado en el disco que desea usar como plantilla de mensaje. El archivo de plantilla puede contener texto con formato previo, diseños de fondo o imágenes que desee incluir en el mensaje. Sin embargo, si el archivo de plantilla contiene un código detrás del formulario, el código no se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="ffb8e-p101">The **CreateItemFromTemplate** method is useful if you have an Outlook form template file (.oft) stored on disk that you want to use as a message template. The template file can contain preformatted text, stationery, or images that you want to include in the message. However, if the template file contains code behind the form, the form code will not run.</span></span>

<span data-ttu-id="ffb8e-109">Si usa Visual Studio para probar este ejemplo de código, primero debe agregar una referencia al componente de la biblioteca de objetos de Microsoft Outlook 15.0 y especificar la variable de Outlook al importar el espacio de nombres **Microsoft.Office.Interop.Outlook**.</span><span class="sxs-lookup"><span data-stu-id="ffb8e-109">
    If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the \*\*Microsoft.Office.Interop.Outlook\*\* namespace. The using statement must not occur directly before the functions in the code example but must be added before the public Class declaration. The following line of code shows how to do the import and assignment in C#.
</span></span> <span data-ttu-id="ffb8e-110">La instrucción **Imports** o **using** no debe producirse directamente antes de las funciones en el ejemplo de código, pero deben agregarse antes de la declaración de clase pública.</span><span class="sxs-lookup"><span data-stu-id="ffb8e-110">The **Imports** or **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="ffb8e-111">La siguiente línea de código muestra cómo llevar a cabo la importación y la asignación en Visual Basic y C\#.</span><span class="sxs-lookup"><span data-stu-id="ffb8e-111">The following lines of code show how to do the import and assignment in Visual Basic and C\#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub CreateItemFromTemplate()
    Dim folder As Outlook.Folder = _
        CType(Application.Session.GetDefaultFolder( _
        Outlook.OlDefaultFolders.olFolderDrafts), Outlook.Folder)
    Dim mail As Outlook.MailItem = _
        CType(Application.CreateItemFromTemplate( _
        "c:\ivy.oft", folder), Outlook.MailItem)
    mail.Subject = "Congratulations"
    mail.Save()
End Sub
```


```csharp
private void CreateItemFromTemplate()
{
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderDrafts) as Outlook.Folder;
    Outlook.MailItem mail =
        Application.CreateItemFromTemplate(
        @"c:\ivy.oft", folder) as Outlook.MailItem;
    mail.Subject = "Congratulations";
    mail.Save();
}
```

## <a name="see-also"></a><span data-ttu-id="ffb8e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ffb8e-112">See also</span></span>

- [<span data-ttu-id="ffb8e-113">Correo</span><span class="sxs-lookup"><span data-stu-id="ffb8e-113">Mail</span></span>](mail.md)
