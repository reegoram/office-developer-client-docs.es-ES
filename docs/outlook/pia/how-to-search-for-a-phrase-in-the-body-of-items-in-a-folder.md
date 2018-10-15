---
title: Buscar una frase en el cuerpo de los elementos de una carpeta
TOCTitle: Search for a phrase in the body of items in a folder
ms:assetid: 2c9f3b5f-ed91-4a07-b247-8f89f00cbc68
ms:mtpsurl: https://msdn.microsoft.com/library/Bb644806(v=office.15)
ms:contentKeyID: 55119924
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 2792e5bd96547975d878f89a7e186c24c4983d8f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406935"
---
# <a name="search-for-a-phrase-in-the-body-of-items-in-a-folder"></a><span data-ttu-id="19c85-102">Buscar una frase en el cuerpo de los elementos de una carpeta</span><span class="sxs-lookup"><span data-stu-id="19c85-102">Search for a phrase in the body of items in a folder</span></span>

<span data-ttu-id="19c85-103">En este ejemplo se busca la cadena "office" en la sección Cuerpo de todos los elementos de la Bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="19c85-103">Searches for the string "office" in the Body of items in the Inbox.</span></span>

## <a name="example"></a><span data-ttu-id="19c85-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="19c85-104">Example</span></span>

<span data-ttu-id="19c85-105">En este ejemplo de código se usa una sintaxis de DASL (DAV Searching and Locating) para especificar una consulta.</span><span class="sxs-lookup"><span data-stu-id="19c85-105">This code sample uses a DAV Searching and Locating (DASL) syntax to specify a query.</span></span> <span data-ttu-id="19c85-106">Para crear el filtro, el código de ejemplo comprueba primero si la Búsqueda instantánea está habilitada en el almacén predeterminado, para determinar si se usa la palabra clave **ci\_phrasematch** para una coincidencia de la frase exacta "office" en el cuerpo del elemento, o la palabra clave **like** para cualquier coincidencia de "office" como una cadena exacta o una subcadena en el cuerpo del elemento.</span><span class="sxs-lookup"><span data-stu-id="19c85-106">To construct the filter, the code sample first checks if Instant Search is enabled in the default store to determine whether to use the **ci\_phrasematch** keyword for an exact phrase match of "office" in the item body, or the **like** keyword to match any occurrence of "office" as an exact string or a substring in the item body.</span></span> <span data-ttu-id="19c85-107">El ejemplo luego aplica el filtro del método [GetTable](https://msdn.microsoft.com/library/bb612592\(v=office.15\)) en la Bandeja de entrada y obtiene los resultados de un objeto [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)).</span><span class="sxs-lookup"><span data-stu-id="19c85-107">The sample then applies the filter to the [GetTable](https://msdn.microsoft.com/library/bb612592\(v=office.15\)) method on the Inbox and obtains the results in a [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) object.</span></span> <span data-ttu-id="19c85-108">En el ejemplo de código se muestra el asunto de cada uno de los elementos devueltos en **Table**.</span><span class="sxs-lookup"><span data-stu-id="19c85-108">The code sample then displays the subject of each of the returned items in the **Table**.</span></span>

<span data-ttu-id="19c85-109">En el código de ejemplo se especifica la propiedad **Body** usando la representación del espacio de nombres urn:schemas:httpmail:textdescription.</span><span class="sxs-lookup"><span data-stu-id="19c85-109">The code sample specifies the **Body** property by using the namespace representation urn:schemas:httpmail:textdescription.</span></span>

<span data-ttu-id="19c85-110">La sintaxis para utilizar la palabra clave **ci\_phrasematch** es:</span><span class="sxs-lookup"><span data-stu-id="19c85-110">The syntax for using the **ci\_phrasematch** keyword is:</span></span>

`<PropertySchemaName> ci_phrasematch <ComparisonString>`

<span data-ttu-id="19c85-111">La sintaxis para utilizar la palabra clave **like** para la coincidencia de prefijo es:</span><span class="sxs-lookup"><span data-stu-id="19c85-111">The syntax for using the **like** keyword for prefix matching is:</span></span>

`<PropertySchemaName> like <Token>%`

<span data-ttu-id="19c85-112">La sintaxis para utilizar la palabra clave **like** para la coincidencia de subcadena es:</span><span class="sxs-lookup"><span data-stu-id="19c85-112">The syntax for using the **like** keyword for any substring matching is:</span></span>

`<PropertySchemaName> like %<Token>%`

<span data-ttu-id="19c85-113">Si usa Visual Studio para probar este ejemplo de código, primero debe agregar una referencia al componente de la biblioteca de objetos de Microsoft Outlook 15.0 y especificar la variable de Outlook al importar el espacio de nombres **Microsoft.Office.Interop.Outlook**.</span><span class="sxs-lookup"><span data-stu-id="19c85-113">
    If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the \*\*Microsoft.Office.Interop.Outlook\*\* namespace. The using statement must not occur directly before the functions in the code example but must be added before the public Class declaration. The following line of code shows how to do the import and assignment in C#.
</span></span> <span data-ttu-id="19c85-114">Las instrucciones **Imports** o **using** no deben producirse directamente antes de las funciones en el ejemplo de código, pero deben agregarse antes de la declaración de Clase pública.</span><span class="sxs-lookup"><span data-stu-id="19c85-114">The **Imports** or **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="19c85-115">Las líneas de código siguientes muestran cómo llevar a cabo la importación y la asignación en Visual Basic y C\#.</span><span class="sxs-lookup"><span data-stu-id="19c85-115">The following lines of code show how to do the import and assignment in Visual Basic and C\#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub DemoSearchBody()
    Dim filter As String
    If (Application.Session.DefaultStore.IsInstantSearchEnabled) Then
        filter = "@SQL=" & Chr(34) _
            & "urn:schemas:httpmail:textdescription" & Chr(34) _
            & " ci_phrasematch 'office'"
    Else
        filter = "@SQL=" & Chr(34) _
            & "urn:schemas:httpmail:textdescription" & Chr(34) _
            & " like '%office%'"
    End If
    Dim table As Outlook.Table = _
        Application.Session.GetDefaultFolder( _
        Outlook.OlDefaultFolders.olFolderInbox).GetTable( _
        filter, Outlook.OlTableContents.olUserItems)
    While Not (table.EndOfTable)
        Dim row As Outlook.Row = table.GetNextRow()
        Debug.WriteLine(row("Subject"))
    End While
End Sub
```


```csharp
private void DemoSearchBody()
{
    string filter;
    if (Application.Session.DefaultStore.IsInstantSearchEnabled)
    {
        filter = "@SQL=" + "\""
            + "urn:schemas:httpmail:textdescription" + "\""
            + " ci_phrasematch 'office'";
    }
    else
    {
        filter = "@SQL=" + "\""
            + "urn:schemas:httpmail:textdescription" + "\""
            + " like '%office%'";
    }
    Outlook.Table table = Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox).GetTable(
        filter, Outlook.OlTableContents.olUserItems);
    while (!table.EndOfTable)
    {
        Outlook.Row row = table.GetNextRow();
        Debug.WriteLine(row["Subject"]);
    }
}
```

## <a name="see-also"></a><span data-ttu-id="19c85-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="19c85-116">See also</span></span>

- [<span data-ttu-id="19c85-117">Buscar y filtrar</span><span class="sxs-lookup"><span data-stu-id="19c85-117">Search and Filter</span></span>](search-and-filter.md)
