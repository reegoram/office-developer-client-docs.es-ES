---
title: Compartir información del calendario por correo electrónico
TOCTitle: Share calendar information through email
ms:assetid: 3382010c-0a16-4dca-a99e-669e9178354e
ms:mtpsurl: https://msdn.microsoft.com/library/Bb609881(v=office.15)
ms:contentKeyID: 55119817
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 574b8ec24b330276ebd47952d5353c4d170ee8db
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406445"
---
# <a name="share-calendar-information-through-email"></a><span data-ttu-id="b1f3b-102">Compartir información del calendario por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="b1f3b-102">Share calendar information through email</span></span>

<span data-ttu-id="b1f3b-103">En este ejemplo se muestra cómo compartir información de un calendario por correo electrónico con el formato iCalendar.</span><span class="sxs-lookup"><span data-stu-id="b1f3b-103">This example shows how to share information from a calendar by e-mail in the iCalendar format.</span></span>

## <a name="example"></a><span data-ttu-id="b1f3b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1f3b-104">Example</span></span>

<span data-ttu-id="b1f3b-105">El formato iCalendar le permite enviar elementos a Outlook o a otros clientes que no son de Outlook a través de protocolos y formatos de correo estándar de Internet.</span><span class="sxs-lookup"><span data-stu-id="b1f3b-105">The iCalendar format allows you to send items to other Outlook or non-Outlook clients via standard Internet mail formats and protocols. The code sample uses the T:Microsoft.Office.Interop.Outlook.CalendarSharing object that supports exporting information from a calendar folder to the iCalendar format.</span></span> <span data-ttu-id="b1f3b-106">En el ejemplo de código utiliza el objeto [CalendarSharing](https://msdn.microsoft.com/library/bb624344\(v=office.15\)) que admite la exportación de información de una carpeta de calendario en el formato iCalendar.</span><span class="sxs-lookup"><span data-stu-id="b1f3b-106">The iCalendar format allows you to send items to other Outlook or non-Outlook clients via standard Internet mail formats and protocols. The code sample uses the [T:Microsoft.Office.Interop.Outlook.CalendarSharing](https://msdn.microsoft.com/library/bb624344\(v=office.15\)) object that supports exporting information from a calendar folder to the iCalendar format.</span></span>

<span data-ttu-id="b1f3b-107">El ejemplo de código llama primero a [GetCalendarExporter](https://msdn.microsoft.com/library/bb610021\(v=office.15\)) en la carpeta de calendario predeterminada para obtener un objeto **CalendarSharing**.</span><span class="sxs-lookup"><span data-stu-id="b1f3b-107">The code sample first calls [GetCalendarExporter](https://msdn.microsoft.com/library/bb610021\(v=office.15\)) on the default Calendar folder to obtain a **CalendarSharing** object.</span></span> <span data-ttu-id="b1f3b-108">Después establece las propiedades del objeto **CalendarSharing** para especificar criterios para la exportación, como el intervalo de fechas de información del calendario, si se deben incluir datos adjuntos y detalles de las citas que están marcados como "privada".</span><span class="sxs-lookup"><span data-stu-id="b1f3b-108">The code sample first calls M:Microsoft.Office.Interop.Outlook.MAPIFolder.GetCalendarExporter on the default Calendar folder to obtain a **CalendarSharing** object. Then it sets properties of the CalendarSharing object to specify criteria for the export, such as the date range of calendar information, whether to include attachments, and details of appointments that are marked "private."</span></span>

<span data-ttu-id="b1f3b-109">Para enviar la información del calendario por correo electrónico, el ejemplo de código llama al método [ForwardAsICal](https://msdn.microsoft.com/library/bb652866\(v=office.15\)) del objeto **CalendarSharing**.</span><span class="sxs-lookup"><span data-stu-id="b1f3b-109">To send the calendar information by e-mail, the code sample calls the [M:Microsoft.Office.Interop.Outlook._CalendarSharing.ForwardAsICal(Microsoft.Office.Interop.Outlook.OlCalendarMailFormat)](https://msdn.microsoft.com/library/bb652866\(v=office.15\)) method of the **CalendarSharing** object.</span></span>

<span data-ttu-id="b1f3b-110">Si usa Visual Studio para probar este ejemplo de código, primero debe agregar una referencia al componente de la biblioteca de objetos de Microsoft Outlook 15.0 y especificar la variable de Outlook al importar el espacio de nombres **Microsoft.Office.Interop.Outlook**.</span><span class="sxs-lookup"><span data-stu-id="b1f3b-110">
    If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the \*\*Microsoft.Office.Interop.Outlook\*\* namespace. The using statement must not occur directly before the functions in the code example but must be added before the public Class declaration. The following line of code shows how to do the import and assignment in C#.
</span></span> <span data-ttu-id="b1f3b-111">La instrucción **Imports** o **using** no debe producirse directamente antes de las funciones en el ejemplo de código, pero deben agregarse antes de la declaración de clase pública.</span><span class="sxs-lookup"><span data-stu-id="b1f3b-111">The **Imports** or **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="b1f3b-112">La siguiente línea de código muestra cómo llevar a cabo la importación y la asignación en Visual Basic y C\#.</span><span class="sxs-lookup"><span data-stu-id="b1f3b-112">The following lines of code show how to do the import and assignment in Visual Basic and C\#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```vb
Private Sub SendNextWeekToAddress(ByVal sendToAddresses As String)
    If String.IsNullOrEmpty(sendToAddresses) Then
        Throw New ArgumentException( _
            "Parameter must contain a value.", "sendToAddress")
    End If

    Dim calendar As Outlook.Folder = TryCast( _
        Application.Session.GetDefaultFolder( _
        Outlook.OlDefaultFolders.olFolderCalendar), Outlook.Folder)
    Dim exporter As Outlook.CalendarSharing = calendar.GetCalendarExporter()

    '' Set the properties for the export
    exporter.CalendarDetail = Outlook.OlCalendarDetail.olFullDetails
    exporter.IncludeAttachments = True
    exporter.IncludePrivateDetails = False
    exporter.RestrictToWorkingHours = False
    exporter.StartDate = DateTime.Today.Date
    exporter.EndDate = DateTime.Today.Date.AddDays(7)

    '' Create a new mail item
    Dim calendarMail As Outlook.MailItem = exporter.ForwardAsICal _
        (Outlook.OlCalendarMailFormat. _
        olCalendarMailFormatDailySchedule)
    calendarMail.To = sendToAddresses
    calendarMail.Send()
    calendarMail.Display()
End Sub
```

```csharp
private void SendNextWeekToAddress(string sendToAddresses)
{
    if (string.IsNullOrEmpty(sendToAddresses))
        throw new ArgumentException(
        "sendToAddress","Parameter must contain a value.");
    Outlook.Folder calendar = 
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderCalendar)
        as Outlook.Folder;
    Outlook.CalendarSharing exporter = calendar.GetCalendarExporter();

    // Set the properties for the export
    exporter.CalendarDetail = Outlook.OlCalendarDetail.olFullDetails;
    exporter.IncludeAttachments = true;
    exporter.IncludePrivateDetails = false;
    exporter.RestrictToWorkingHours = false;
    exporter.StartDate = DateTime.Today.Date;
    exporter.EndDate = DateTime.Today.Date.AddDays(7);

    // Create a new mail item
    Outlook.MailItem calendarMail = 
        exporter.ForwardAsICal(Outlook.OlCalendarMailFormat.
        olCalendarMailFormatDailySchedule);
    calendarMail.To = sendToAddresses;
    ((Outlook.MailItemClass)calendarMail).Send();
    ((Outlook.MailItemClass)calendarMail).Display(Type.Missing);
}
```

## <a name="see-also"></a><span data-ttu-id="b1f3b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1f3b-113">See also</span></span>

- [<span data-ttu-id="b1f3b-114">Calendario</span><span class="sxs-lookup"><span data-stu-id="b1f3b-114">Calendar</span></span>](calendar.md)
