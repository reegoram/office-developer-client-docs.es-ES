---
title: Marcar los elementos de correo de un administrador para su seguimiento
TOCTitle: Flag mail items from a manager for follow-up
ms:assetid: 5f7f3678-0f63-451e-ba08-cd973525aa1b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424470(v=office.15)
ms:contentKeyID: 55119898
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 73c4a7ec8118b95edac06ae8ab5bc59902612ebc
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406368"
---
# <a name="flag-mail-items-from-a-manager-for-follow-up"></a><span data-ttu-id="8e216-102">Marcar los elementos de correo de un administrador para su seguimiento</span><span class="sxs-lookup"><span data-stu-id="8e216-102">Flag mail items from a manager for follow-up</span></span>

<span data-ttu-id="8e216-103">En este ejemplo se muestra cómo marcar los elementos de correo electrónico que se recibieron desde el administrador del usuario para su seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8e216-103">This example shows how to flag e-mail items that were received from the user’s manager for follow-up.</span></span>

## <a name="example"></a><span data-ttu-id="8e216-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8e216-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="8e216-105">El siguiente ejemplo de código es un fragmento de [Aplicaciones de programación para Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span><span class="sxs-lookup"><span data-stu-id="8e216-105">The following code example is an excerpt from Programming Applications for Microsoft Office Outlook 2007, from  Microsoft Press http://www.microsoft.com/learning/books/default.mspx  (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="8e216-106">Microsoft Outlook dispone de un sistema de marcación de tareas que permite marcar ciertos elementos de Outlook como los elementos de correo o los elementos de contacto para hacerles un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8e216-106">Microsoft Outlook provides a new task flagging system in which certain Outlook items such as mail items or contact items can be flagged for follow-up.</span></span> <span data-ttu-id="8e216-107">Al marcar un elemento de Outlook para su seguimiento, se muestra información sobre ese elemento de Outlook, junto con otra información basada en tareas, en la **Barra Tareas pendientes** y el módulo de navegación Calendario en la interfaz de usuario de Outlook.</span><span class="sxs-lookup"><span data-stu-id="8e216-107">Flagging an Outlook item for follow-up displays information about that Outlook item, along with other task-based information, on the **To-Do Bar** and Calendar navigation module in the Outlook user interface.The following Outlook item objects have been extended to support the task flagging system:</span></span> <span data-ttu-id="8e216-108">La **Barra Tareas pendientes** se muestra como un panel vertical en una configuración habitual de la ventana del explorador de Outlook.</span><span class="sxs-lookup"><span data-stu-id="8e216-108">The **To-Do Bar** is displayed as a vertical pane in a typical configuration of the Outlook explorer window.</span></span> <span data-ttu-id="8e216-109">Contiene un control del navegador de fechas, próximas citas y elementos que se han marcado para su seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8e216-109">It contains a date navigator control, upcoming appointments, and items that have been flagged for follow-up.</span></span> <span data-ttu-id="8e216-110">La **Barra Tareas pendientes** no es extensible y puede establecer opciones de configuración de la **Barra Tareas pendientes** solo a través de la interfaz de usuario de Outlook.</span><span class="sxs-lookup"><span data-stu-id="8e216-110">The **To-Do Bar** itself is not extensible, and you can set configuration options for the **To-Do Bar** only through the Outlook user interface.</span></span> <span data-ttu-id="8e216-111">Marcar elementos permite organizar y priorizar las tareas y los elementos pendientes.</span><span class="sxs-lookup"><span data-stu-id="8e216-111">Flagging items allows to you organize and prioritize tasks and to-do items.</span></span>

<span data-ttu-id="8e216-112">En el siguiente ejemplo de código se marca un grupo de elementos para un intervalo especificado de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8e216-112">The following code example marks a group of items for a specified follow-up interval.</span></span> <span data-ttu-id="8e216-113">El ejemplo obtiene todos los elementos de la Bandeja de entrada del usuario actual que provengan del administrador del usuario actual mediante una consulta de búsqueda DASL (DAV Searching and Locating) para filtrar los mensajes de tipo "IPM.NOTE"con el nombre del administrador como remitente.</span><span class="sxs-lookup"><span data-stu-id="8e216-113">The example gets all items in the current user’s Inbox that are from the current user’s manager by using a DAV Searching and Locating (DASL) query to filter for messages of type “IPM.NOTE” with the manager’s name as the sender.</span></span> <span data-ttu-id="8e216-114">Luego, marca todos los elementos de acuerdo con el valor [OlImportance](https://msdn.microsoft.com/library/bb609592\(v=office.15\)) de la propiedad [Importance](https://msdn.microsoft.com/library/bb611974\(v=office.15\)).</span><span class="sxs-lookup"><span data-stu-id="8e216-114">It then flags all items according to the [OlImportance](https://msdn.microsoft.com/library/bb609592\(v=office.15\)) value of the [Importance](https://msdn.microsoft.com/library/bb611974\(v=office.15\)) property.</span></span> <span data-ttu-id="8e216-115">Todos los elementos de alta importancia están marcados para el seguimiento hoy y todos los elementos de normal importancia están marcados para el seguimiento esta semana mediante el método [MarkAsTask(OlMarkInterval)](https://msdn.microsoft.com/library/bb609068\(v=office.15\)).</span><span class="sxs-lookup"><span data-stu-id="8e216-115">All high-importance items are flagged for follow-up today and all normal-importance items are flagged for follow-up this week by using the [MarkAsTask(OlMarkInterval)](https://msdn.microsoft.com/library/bb609068\(v=office.15\)) method.</span></span>


> [!NOTE]
> <span data-ttu-id="8e216-116">La propiedad **Importance** y el método **MarkAsTask** son miembros del objeto **Item**</span><span class="sxs-lookup"><span data-stu-id="8e216-116">The **Importance** property and the **MarkAsTask** method are **Item** object members</span></span>


<span data-ttu-id="8e216-117">Si usa Visual Studio para probar este ejemplo de código, primero debe agregar una referencia al componente de la biblioteca de objetos de Microsoft Outlook 15.0 y especificar la variable de Outlook al importar el espacio de nombres **Microsoft.Office.Interop.Outlook**.</span><span class="sxs-lookup"><span data-stu-id="8e216-117">
    If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the \*\*Microsoft.Office.Interop.Outlook\*\* namespace. The using statement must not occur directly before the functions in the code example but must be added before the public Class declaration. The following line of code shows how to do the import and assignment in C#.
</span></span> <span data-ttu-id="8e216-118">La instrucción **using** no debe producirse directamente antes de las funciones en el ejemplo de código, pero debe agregarse antes de la declaración de Clase pública.</span><span class="sxs-lookup"><span data-stu-id="8e216-118">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="8e216-119">La siguiente línea de código muestra cómo llevar a cabo la importación y la asignación en C\#.</span><span class="sxs-lookup"><span data-stu-id="8e216-119">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DemoTaskFlagging()
{
    const string PR_SENT_REPRESENTING_NAME =
        "https://schemas.microsoft.com/mapi/proptag/0x0042001E";
    const string PR_MESSAGE_CLASS =
        "https://schemas.microsoft.com/mapi/proptag/0x001A001E";
    Outlook.AddressEntry currentUser =
        Application.Session.CurrentUser.AddressEntry;
    if (currentUser.Type == "EX")
    {
        Outlook.ExchangeUser manager;
        try
        {
            manager = currentUser.
                GetExchangeUser().GetExchangeUserManager();
        }
        catch
        {
            Debug.WriteLine("Could not obtain user's manager.");
            return;
        }
        if (manager != null)
        {
            string displayName = manager.Name;
            string filter = "@SQL=" + "\""
                + PR_SENT_REPRESENTING_NAME + "\""
                + " = '" + displayName + "'" + " AND " + "\""
                + PR_MESSAGE_CLASS + "\"" + " = 'IPM.NOTE'";
            Outlook.Items items =
                Application.Session.GetDefaultFolder(
                Outlook.OlDefaultFolders.olFolderInbox).
                Items.Restrict(filter);
            foreach (Outlook.MailItem mail in items)
            {
                if (mail.Importance ==
                    Outlook.OlImportance.olImportanceHigh)
                {
                    mail.MarkAsTask(Outlook.OlMarkInterval.olMarkToday);
                    mail.Save();
                }
                if (mail.Importance ==
                    Outlook.OlImportance.olImportanceNormal)
                {
                    mail.MarkAsTask(Outlook.OlMarkInterval.olMarkThisWeek);
                    mail.Save();
                }
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="8e216-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e216-120">See also</span></span>

- [<span data-ttu-id="8e216-121">Tareas</span><span class="sxs-lookup"><span data-stu-id="8e216-121">Tasks</span></span>](tasks.md)
