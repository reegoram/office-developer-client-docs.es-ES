---
title: Field.DefaultValue Property (DAO)
TOCTitle: DefaultValue Property
ms:assetid: 8a1c558b-c8f6-757d-c595-4e50b9b6ae3f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197092(v=office.15)
ms:contentKeyID: 48546185
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5b5e479739177fa869bb2e96329c47c5f5889b64
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25483502"
---
# <a name="fielddefaultvalue-property-dao"></a>Field.DefaultValue Property (DAO)


**Se aplica a**: Access 2013 | Office 2013


Establece o devuelve el valor predeterminado de un objeto **[Field](field-object-dao.md)**. Para un objeto **Field** que todavía no se ha anexado a la colección **[Fields](fields-collection-dao.md)**, esta propiedad es de lectura y escritura (sólo áreas de trabajo de Microsoft Access).

## <a name="syntax"></a>Sintaxis

*expresión* . DefaultValue

*expresión* Variable que representa un objeto **Field** .

## <a name="remarks"></a>Observaciones

La configuración o el valor devuelto es un tipo de datos **String** que puede contener 255 caracteres como máximo. Puede ser texto o una expresión. Si el valor de la propiedad es una expresión, no puede contener funciones definidas por el usuario, funciones de agregado SQL del motor de base de datos de Microsoft Access ni referencias a consultas, formularios u otros objetos **Field**.


> [!NOTE]
> <P>[!NOTA] También puede establecer la propiedad <STRONG>DefaultValue</STRONG> de un objeto <STRONG>Field</STRONG> en un objeto <STRONG><A href="tabledef-object-dao.md">TableDef</A></STRONG> en un valor especial denominado "GenUniqueID( )". Con este valor se asigna un número aleatorio a este campo cuando se agrega o crea un registro nuevo, con lo que cada registro recibe un identificador único. La propiedad <STRONG><A href="field-type-property-dao.md">Type</A></STRONG> del campo debe ser de tipo <STRONG>Long</STRONG>.</P>



La disponibilidad de la propiedad **DefaultValue** depende del objeto que contiene la colección **Fields**, como se indica en la siguiente tabla.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Si la colección Fields pertenece a</p></th>
<th><p>Entonces DefaultValue</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Objeto Index</p></td>
<td><p>No está admitido</p></td>
</tr>
<tr class="even">
<td><p>Objeto QueryDef</p></td>
<td><p>Sólo lectura</p></td>
</tr>
<tr class="odd">
<td><p>Objeto Recordset</p></td>
<td><p>Sólo lectura</p></td>
</tr>
<tr class="even">
<td><p>Objeto Relation</p></td>
<td><p>No está admitido</p></td>
</tr>
<tr class="odd">
<td><p>Objeto TableDef</p></td>
<td><p>Lectura y escritura</p></td>
</tr>
</tbody>
</table>


Cuando se crea un registro nuevo, el valor de la propiedad **DefaultValue** se especifica automáticamente como el valor del campo. Puede cambiar el valor del campo estableciendo su propiedad **[Value](field-value-property-dao.md)**.

La propiedad **DefaultValue** no se aplica a los campos de tipo **AutoNumber** y **Long Binary**.

## <a name="example"></a>Ejemplo

En este ejemplo se utiliza la propiedad **DefaultValue** para advertir al usuario de un valor normal del campo mientras se le piden datos de entrada. Además, se demuestra cómo los registros nuevos se rellenarán utilizando **DefaultValue** en ausencia de cualquier otra entrada. Se requiere la función DefaultPrompt para que pueda ejecutarse este procedimiento.

```vb
    Sub DefaultValueX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim strOldDefault As String 
     Dim rstEmployees As Recordset 
     Dim strMessage As String 
     Dim strCode As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind.TableDefs!Employees 
     
     ' Store original DefaultValue information and set the 
     ' property to a new value. 
     strOldDefault = _ 
     tdfEmployees.Fields!PostalCode.DefaultValue 
     tdfEmployees.Fields!PostalCode.DefaultValue = "98052" 
     
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     
     With rstEmployees 
     ' Add a new record to the Recordset. 
     .AddNew 
     !FirstName = "Bruce" 
     !LastName = "Oberg" 
     
     ' Get user input. If user enters something, the field 
     ' will be filled with that data; otherwise, it will be 
     ' filled with the DefaultValue information. 
     strMessage = "Enter postal code for " & vbCr & _ 
     !FirstName & " " & !LastName & ":" 
     strCode = DefaultPrompt(strMessage, !PostalCode) 
     If strCode <> "" Then !PostalCode = strCode 
     .Update 
     
     ' Go to new record and print information. 
     .Bookmark = .LastModified 
     Debug.Print " FirstName = " & !FirstName 
     Debug.Print " LastName = " & !LastName 
     Debug.Print " PostalCode = " & !PostalCode 
     
     ' Delete new record because this is a demonstration. 
     .Delete 
     .Close 
     End With 
     
     ' Restore original DefaultValue property because this is a 
     ' demonstration. 
     tdfEmployees.Fields!PostalCode.DefaultValue = _ 
     strOldDefault 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Function DefaultPrompt(strPrompt As String, _ 
     fldTemp As Field) As String 
     
     Dim strFullPrompt As String 
     
     ' Ask user for new DefaultValue setting for the specified 
     ' Field object. 
     strFullPrompt = strPrompt & vbCr & _ 
     "[Default = " & fldTemp.DefaultValue & _ 
     ", Cancel - use default]" 
     DefaultPrompt = InputBox(strFullPrompt) 
     
    End Function
```
