---
title: Responder a un elemento de solicitud de tarea
TOCTitle: Respond to a task request item
ms:assetid: 573c98ef-4d15-4fd1-bccd-25a22c9a63f0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184608(v=office.15)
ms:contentKeyID: 55119896
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: ca85ee701b26f5ae896f9f4d012f93fea42930ec
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406732"
---
# <a name="respond-to-a-task-request-item"></a><span data-ttu-id="a9406-102">Responder a un elemento de solicitud de tarea</span><span class="sxs-lookup"><span data-stu-id="a9406-102">Gets and responds to a task request item.</span></span>

<span data-ttu-id="a9406-103">En este ejemplo se muestra cómo obtener y responder a un elemento de solicitud de tarea.</span><span class="sxs-lookup"><span data-stu-id="a9406-103">This example shows how to get and respond to a task request item.</span></span>

## <a name="example"></a><span data-ttu-id="a9406-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9406-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="a9406-105">El siguiente ejemplo de código es un fragmento de [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493) (Programación de aplicaciones para Microsoft Office Outlook 2007).</span><span class="sxs-lookup"><span data-stu-id="a9406-105">The following code example is an excerpt from Programming Applications for Microsoft Office Outlook 2007, from  Microsoft Press http://www.microsoft.com/learning/books/default.mspx  (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="a9406-106">En el siguiente ejemplo de código, AcceptTaskRequest usa el método [GetAssociatedTask(Boolean)](https://msdn.microsoft.com/library/bb645779\(v=office.15\)) del objeto [TaskRequestItem](https://msdn.microsoft.com/library/bb610737\(v=office.15\)) para obtener el objeto [TaskItem](https://msdn.microsoft.com/library/bb624227\(v=office.15\)).</span><span class="sxs-lookup"><span data-stu-id="a9406-106">In the following code example, AcceptTaskRequest uses the [GetAssociatedTask(Boolean)](https://msdn.microsoft.com/library/bb645779\(v=office.15\)) method of the [TaskRequestItem](https://msdn.microsoft.com/library/bb610737\(v=office.15\)) object to get the [TaskItem](https://msdn.microsoft.com/library/bb624227\(v=office.15\)) object.</span></span> <span data-ttu-id="a9406-107">Después el ejemplo llama al método [Respond(OlTaskResponse, Object, Object)](https://msdn.microsoft.com/library/bb644188\(v=office.15\)) con el parámetro establecido en [olTaskAccept](https://msdn.microsoft.com/library/bb624484\(v=office.15\)) para aceptar la solicitud de tarea.</span><span class="sxs-lookup"><span data-stu-id="a9406-107">The example then calls the [Respond(OlTaskResponse, Object, Object)](https://msdn.microsoft.com/library/bb644188\(v=office.15\)) method with the parameter set to [olTaskAccept](https://msdn.microsoft.com/library/bb624484\(v=office.15\)) to accept the task request.</span></span>

<span data-ttu-id="a9406-108">Si usa Visual Studio para probar este ejemplo de código, primero debe agregar una referencia al componente de la biblioteca de objetos de Microsoft Outlook 15.0 y especificar la variable de Outlook al importar el espacio de nombres **Microsoft.Office.Interop.Outlook**.</span><span class="sxs-lookup"><span data-stu-id="a9406-108">
    If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the \*\*Microsoft.Office.Interop.Outlook\*\* namespace. The using statement must not occur directly before the functions in the code example but must be added before the public Class declaration. The following line of code shows how to do the import and assignment in C#.
</span></span> <span data-ttu-id="a9406-109">La instrucción **using** no debe producirse directamente antes de las funciones en el ejemplo de código, pero debe agregarse antes de la declaración de clase pública.</span><span class="sxs-lookup"><span data-stu-id="a9406-109">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="a9406-110">La siguiente línea de código muestra cómo llevar a cabo la importación y la asignación en C\#.</span><span class="sxs-lookup"><span data-stu-id="a9406-110">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void AcceptTaskRequest()
{
    string filter = "[MessageClass] = 'IPM.TaskRequest'";
    Outlook.Items items =
        Application.Session.GetDefaultFolder
        (Outlook.OlDefaultFolders.olFolderInbox).
        Items.Restrict(filter);
    if (items.Count > 0)
    {
        Outlook.TaskRequestItem taskRequest =
            (Outlook.TaskRequestItem)items[1];
        Outlook.TaskItem task =
            taskRequest.GetAssociatedTask(false);
        Outlook.TaskItem taskResponse = task.Respond(
            Outlook.OlTaskResponse.olTaskAccept, true, false);
        taskResponse.Send();
    }
}
```

## <a name="see-also"></a><span data-ttu-id="a9406-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9406-111">See also</span></span>

- <span data-ttu-id="a9406-112">[Tasks](tasks.md) (Tareas)</span><span class="sxs-lookup"><span data-stu-id="a9406-112">[Tasks](tasks.md)</span></span>
