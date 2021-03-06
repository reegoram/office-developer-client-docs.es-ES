---
title: Crear una cita que comience en la zona horaria del Pacífico y finalice en la zona horaria oriental
TOCTitle: Create an appointment that starts in the Pacific Time Zone and ends in the Eastern Time Zone
ms:assetid: ba19532b-df31-4384-8816-e64e6eecbe53
ms:mtpsurl: https://msdn.microsoft.com/library/Bb623388(v=office.15)
ms:contentKeyID: 55119808
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 9cb21bddb425adb54082dbe21b32653e1fe3ca75
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406081"
---
# <a name="create-an-appointment-that-starts-in-the-pacific-time-zone-and-ends-in-the-eastern-time-zone"></a>Crear una cita que comience en la zona horaria del Pacífico y finalice en la zona horaria oriental

En ocasiones, una cita puede abarcar un período de tiempo durante el cual es posible que el usuario haya viajado a una zona horaria diferente que cuando comenzó la cita. En este ejemplo se crea una cita que comienza en la zona Hora del Pacífico (UCT-8:00) y finaliza en la zona Hora oriental (UCT-5:30).

## <a name="example"></a>Ejemplo

Este ejemplo de código usa el objeto [TimeZones](https://msdn.microsoft.com/library/bb611081\(v=office.15\)), que representa las zonas horarias reconocidas en Microsoft Windows. También usa el objeto [TimeZone](https://msdn.microsoft.com/library/bb646259\(v=office.15\)) para establecer u obtener la propiedad [StartTimeZone](https://msdn.microsoft.com/library/bb623657\(v=office.15\)) y la propiedad [EndTimeZone](https://msdn.microsoft.com/library/bb612198\(v=office.15\)) en el objeto [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)).

Outlook muestra todas las fechas en hora local, que se expresa en la zona horaria actual del usuario, controlada por la configuración del usuario en el Panel de control de Windows. Outlook también obtiene o establece otras propiedades, como [Start](https://msdn.microsoft.com/library/bb647263\(v=office.15\)) y [End](https://msdn.microsoft.com/library/bb623715\(v=office.15\)), en la hora local. Sin embargo, Outlook almacena los valores de fecha y hora en la hora del Pacífico (UTC) en lugar de la hora local. Si examina el valor interno de Appointment.Start mediante el objeto [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)), verá que el valor interno de fecha y hora es igual que el valor local de fecha y hora convertido al valor equivalente de fecha y hora UTC.

Outlook usa la información de zona horaria para asignar la cita a la hora UTC correcta cuando guarda una cita, y a la hora local correcta cuando muestra el elemento en el calendario. La modificación de la propiedad StartTimeZone afecta al valor de Appointment.Start, que siempre se expresa en la zona horaria local, representada por la propiedad [CurrentTimeZone](https://msdn.microsoft.com/library/bb612024\(v=office.15\)) del objeto devuelto por [TimeZones](https://msdn.microsoft.com/library/bb645170\(v=office.15\)). De forma similar, la modificación de la propiedad EndTimeZone afecta al valor de Appointment.End, que siempre se expresa en la zona horaria local, representada por la propiedad CurrentTimeZone del objeto devuelto por Application.TimeZones.

Puede recuperar un objeto TimeZone específico del objeto TimeZones usando la clave independiente de TimeZone del registro de Windows. Las claves independientes de TimeZone se muestran en la siguiente clave: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\TimeZones`.

Si usa Visual Studio para probar este ejemplo de código, primero debe agregar una referencia al componente de la biblioteca de objetos de Microsoft Outlook 15.0 y especificar la variable de Outlook al importar el espacio de nombres **Microsoft.Office.Interop.Outlook**. La instrucción **Imports** o **using** no debe producirse directamente antes de las funciones en el ejemplo de código, pero deben agregarse antes de la declaración de clase pública. La siguiente línea de código muestra cómo llevar a cabo la importación y la asignación en Visual Basic y C\#.


```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```



```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```



```vb
Private Sub TimeZoneExample()
    Dim appt As Outlook.AppointmentItem = _
        CType(Application.CreateItem( _
        Outlook.OlItemType.olAppointmentItem), Outlook.AppointmentItem)
    Dim tzs As Outlook.TimeZones = Application.TimeZones
    ' Obtain timezone using indexer and locale-independent key
    Dim tzEastern As Outlook.TimeZone = tzs("Eastern Standard Time")
    Dim tzPacific As Outlook.TimeZone = tzs("Pacific Standard Time")
    appt.Subject = "SEA - JFK Flight"
    appt.Start = DateTime.Parse("8/9/2006 8:00 AM")
    appt.StartTimeZone = tzPacific
    appt.End = DateTime.Parse("8/9/2006 5:30 PM")
    appt.EndTimeZone = tzEastern
    appt.Display(False)
End Sub
```



```csharp
private void TimeZoneExample()
{
    Outlook.AppointmentItem appt = Application.CreateItem(
        Outlook.OlItemType.olAppointmentItem)
        as Outlook.AppointmentItem;
    Outlook.TimeZones tzs = Application.TimeZones;
    // Obtain timezone using indexer and locale-independent key
    Outlook.TimeZone tzEastern = tzs["Eastern Standard Time"];
    Outlook.TimeZone tzPacific = tzs["Pacific Standard Time"];
    appt.Subject = "SEA - JFK Flight";
    appt.Start = DateTime.Parse("8/9/2006 8:00 AM");
    appt.StartTimeZone = tzPacific;
    appt.End = DateTime.Parse("8/9/2006 5:30 PM");
    appt.EndTimeZone = tzEastern; 
    appt.Display(false);
}
```

## <a name="see-also"></a>Vea también

- [Citas](appointments.md)

