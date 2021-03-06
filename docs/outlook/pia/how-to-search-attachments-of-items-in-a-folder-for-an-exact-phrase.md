---
title: Buscar una frase exacta en los archivos adjuntos de los elementos de una carpeta
TOCTitle: Search attachments of items in a folder for an exact phrase
ms:assetid: 3202c0c7-ee3d-4396-b3a9-d24990b44829
ms:mtpsurl: https://msdn.microsoft.com/library/Bb609825(v=office.15)
ms:contentKeyID: 55119889
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 915ddd65e8227f6cc720c4494ed1767deed121b1
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406158"
---
# <a name="search-attachments-of-items-in-a-folder-for-an-exact-phrase"></a>Buscar una frase exacta en los archivos adjuntos de los elementos de una carpeta

Este ejemplo busca la cadena de búsqueda exacta "office" en los datos adjuntos de los elementos de la Bandeja de entrada.

## <a name="example"></a>Ejemplo

En este ejemplo de código se usa una sintaxis de DAV Searching and Locating (DASL) para especificar una consulta. Para crear el filtro, el código de ejemplo comprueba primero si la Búsqueda instantánea está habilitada en el almacén predeterminado para determinar si se utiliza la palabra clave **ci\_phrasematch** para obtener una coincidencia de una frase exacta "office" en los datos adjuntos. El ejemplo luego aplica el filtro del método [GetTable](https://msdn.microsoft.com/library/bb612592\(v=office.15\)) en la Bandeja de entrada y obtiene los resultados de un objeto [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)). En el ejemplo de código se muestra el asunto de cada uno de los elementos devueltos en **Table**.

Especifica el código de ejemplo de la propiedad **Attachments** de un elemento mediante la representación del espacio de nombres, https://schemas.microsoft.com/mapi/proptag/0x0EA5001E. La sintaxis para utilizar la palabra clave **ci\_phrasematch** es:

`<PropertySchemaName> ci_phrasematch <ComparisonString>`

Si usa Visual Studio para probar este ejemplo de código, primero debe agregar una referencia al componente de la biblioteca de objetos de Microsoft Outlook 15.0 y especificar la variable de Outlook al importar el espacio de nombres **Microsoft.Office.Interop.Outlook**. La instrucción **Imports** o **using** no deben producirse directamente antes de las funciones en el ejemplo de código, pero deben agregarse antes de la declaración de clase pública. La siguiente línea de código muestra cómo llevar a cabo la importación y la asignación en Visual Basic y C\#.

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub DemoSearchAttachments()
    Dim filter As String
    Const PR_SEARCH_ATTACHMENTS As String = _
        "https://schemas.microsoft.com/mapi/proptag/0x0EA5001E"
    If (Application.Session.DefaultStore.IsInstantSearchEnabled) Then
        filter = "@SQL=" & Chr(34) _
            & PR_SEARCH_ATTACHMENTS & Chr(34) _
            & " ci_phrasematch 'office'"
        Dim table As Outlook.Table = _
            Application.Session.GetDefaultFolder( _
            Outlook.OlDefaultFolders.olFolderInbox).GetTable( _
            filter, Outlook.OlTableContents.olUserItems)
        While Not (table.EndOfTable)
            Dim row As Outlook.Row = table.GetNextRow()
            Debug.WriteLine(row("Subject"))
        End While
    End If
End Sub
```


```csharp
private void DemoSearchAttachments()
{
    string filter;
    const string PR_SEARCH_ATTACHMENTS =
        "https://schemas.microsoft.com/mapi/proptag/0x0EA5001E";
    if (Application.Session.DefaultStore.IsInstantSearchEnabled)
    {
        filter = "@SQL=" + "\""
            + PR_SEARCH_ATTACHMENTS + "\""
            + " ci_phrasematch 'office'";
        Outlook.Table table = Application.Session.GetDefaultFolder(
            Outlook.OlDefaultFolders.olFolderInbox).GetTable(
            filter, Outlook.OlTableContents.olUserItems);
        while (!table.EndOfTable)
        {
            Outlook.Row row = table.GetNextRow();
            Debug.WriteLine(row["Subject"]);
        }
    }
}
```

## <a name="see-also"></a>Vea también

- [Search and filter](search-and-filter.md) (Buscar y filtrar)

