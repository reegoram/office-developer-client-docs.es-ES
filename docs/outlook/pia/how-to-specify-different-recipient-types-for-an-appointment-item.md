---
title: Especificar diferentes tipos de destinatarios de un elemento de reunión
TOCTitle: Specify different recipient types for an appointment item
ms:assetid: 83aedc8f-adc0-453d-8e71-1bb9aacc7993
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184622(v=office.15)
ms:contentKeyID: 55119807
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: c1f9e1d8e7b4c884853dda9b5c37cd7357d48b6c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405689"
---
# <a name="specify-different-recipient-types-for-an-appointment-item"></a>Especificar diferentes tipos de destinatarios de un elemento de reunión

En este ejemplo se muestra cómo usar la enumeración [OlMeetingRecipientType](https://msdn.microsoft.com/library/bb623431\(v=office.15\)) para especificar diferentes tipos de destinatarios para un elemento de cita.

## <a name="example"></a>Ejemplo

> [!NOTE] 
> El siguiente ejemplo de código es un fragmento de [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493) (Programación de aplicaciones para Microsoft Office Outlook 2007).

Para agregar destinatarios a un objeto [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) que representa una convocatoria de reunión, use la enumeración OlMeetingRecipientType para especificar si el destinatario del mensaje es un asistente obligatorio u opcional, o un recurso (como una sala o equipos). 

En el siguiente ejemplo de código, SetRecipientTypeForAppt crea un objeto **AppointmentItem**, establece las propiedades del objeto y agrega asistentes obligatorios y opcionales. También agrega una sala de conferencias para la reunión. Tenga en cuenta que la propiedad [MeetingStatus](https://msdn.microsoft.com/library/bb611417\(v=office.15\)) se establece en [olMeeting](https://msdn.microsoft.com/library/bb644590\(v=office.15\)), lo que indica que la cita es una convocatoria de reunión.

Si usa Visual Studio para probar este ejemplo de código, primero debe agregar una referencia al componente de la biblioteca de objetos de Microsoft Outlook 15.0 y especificar la variable de Outlook al importar el espacio de nombres **Microsoft.Office.Interop.Outlook**. La instrucción **using** no debe producirse directamente antes de las funciones en el ejemplo de código, pero debe agregarse antes de la declaración de clase pública. La siguiente línea de código muestra cómo llevar a cabo la importación y la asignación en C\#.

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void SetRecipientTypeForAppt()
{
    Outlook.AppointmentItem appt =
        Application.CreateItem(
        Outlook.OlItemType.olAppointmentItem)
        as Outlook.AppointmentItem;
    appt.Subject = "Customer Review";
    appt.MeetingStatus = Outlook.OlMeetingStatus.olMeeting;
    appt.Location = "36/2021";
    appt.Start = DateTime.Parse("10/20/2006 10:00 AM");
    appt.End = DateTime.Parse("10/20/2006 11:00 AM");
    Outlook.Recipient recipRequired =
        appt.Recipients.Add("Ryan Gregg");
    recipRequired.Type =
        (int)Outlook.OlMeetingRecipientType.olRequired;
    Outlook.Recipient recipOptional =
        appt.Recipients.Add("Peter Allenspach");
    recipOptional.Type =
        (int)Outlook.OlMeetingRecipientType.olOptional;
    Outlook.Recipient recipConf =
        appt.Recipients.Add("Conf Room 36/2021 (14) AV");
    recipConf.Type =
        (int)Outlook.OlMeetingRecipientType.olResource;
    appt.Recipients.ResolveAll();
    appt.Display(false);
}
```

## <a name="see-also"></a>Vea también

- [Appointments](appointments.md) (Citas)

