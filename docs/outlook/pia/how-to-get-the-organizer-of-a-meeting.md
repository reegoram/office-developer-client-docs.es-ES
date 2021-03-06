---
title: Obtener el organizador de una reunión
TOCTitle: Get the organizer of a meeting
ms:assetid: 6a33db84-573b-4d1b-a91a-903f30630ec9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184615(v=office.15)
ms:contentKeyID: 55119872
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 87d8486b29039f87cb0cbedd2693ce1b4d38b1dc
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406774"
---
# <a name="get-the-organizer-of-a-meeting"></a>Obtener el organizador de una reunión

Este ejemplo muestra cómo devolver el organizador de una reunión mediante programación.

## <a name="example"></a>Ejemplo

> [!NOTE] 
> El siguiente ejemplo de código es un fragmento de [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493) (Programación de aplicaciones para Microsoft Office Outlook 2007).

En el siguiente ejemplo de código, GetMeetingOrganizer toma un parámetro de tipo [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) que representa una reunión y usa el objeto [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) y el método [GetProperty ( String)](https://msdn.microsoft.com/library/bb645726\(v=office.15\)) para obtener el [EntryID](https://msdn.microsoft.com/library/bb645980\(v=office.15\)) para el objeto **AppointmentItem**. Una vez obtenga el **EntryID**, el ejemplo usa el método [GetAddressEntryFromID(String)](https://msdn.microsoft.com/library/ff185034\(v=office.15\)) para devolver el objeto [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) que representa el organizador de la reunión.

Si usa Visual Studio para probar este ejemplo de código, primero debe agregar una referencia al componente de la biblioteca de objetos de Microsoft Outlook 15.0 y especificar la variable de Outlook al importar el espacio de nombres **Microsoft.Office.Interop.Outlook**. La instrucción **using** no debe producirse directamente antes de las funciones en el ejemplo de código, pero debe agregarse antes de la declaración de clase pública. La siguiente línea de código muestra cómo llevar a cabo la importación y la asignación en C\#.

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private Outlook.AddressEntry GetMeetingOrganizer(Outlook.AppointmentItem appt)
{
    if (appt == null)
    {
        throw new ArgumentNullException();
    }
    string PR_SENT_REPRESENTING_ENTRYID =
        @"https://schemas.microsoft.com/mapi/proptag/0x00410102";
    string organizerEntryID =
        appt.PropertyAccessor.BinaryToString(
            appt.PropertyAccessor.GetProperty(
            PR_SENT_REPRESENTING_ENTRYID));
    Outlook.AddressEntry organizer =
        Application.Session.
        GetAddressEntryFromID(organizerEntryID);
    if (organizer != null)
    {
        return organizer; 
    }
    else
    {
        return null;
    }
}
```

## <a name="see-also"></a>Vea también

- [Meeting requests](meeting-requests.md) (Convocatorias de reunión)

