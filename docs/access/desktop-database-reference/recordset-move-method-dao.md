---
title: Recordset.Move Method (DAO)
TOCTitle: Move Method
ms:assetid: 21ca5ab5-ff71-1ae8-21b3-8991d5f795cf
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191697(v=office.15)
ms:contentKeyID: 48543689
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052941
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 23de94392fb2d9f1b0106c39f21a8872783b6d7b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485744"
---
# <a name="recordsetmove-method-dao"></a>Recordset.Move Method (DAO)


**Se aplica a**: Access 2013 | Office 2013

Mueve la posición del registro activo de un objeto **[Recordset](recordset-object-dao.md)**.

## <a name="syntax"></a>Sintaxis

*expresión* . Move (***filas***, ***StartBookmark***)

*expresión* Variable que representa un objeto **Recordset** .

### <a name="parameters"></a>Parámetros

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Nombre</p></th>
<th><p>Necesario/Opcional</p></th>
<th><p>Tipo de datos</p></th>
<th><p>Descripción</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Filas</p></td>
<td><p>Obligatorio</p></td>
<td><p><strong>Long</strong></p></td>
<td><p>El número de filas en que se mueve la posición. Si rows es superior a 0, la posición se desplaza hacia delante (hacia el final del archivo). Si rows es inferior a 0, la posición se desplaza hacia atrás (hacia el principio del archivo).</p></td>
</tr>
<tr class="even">
<td><p>StartBookmark</p></td>
<td><p>Opcional</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>Valor que identifica un marcador. Si especifica startbookmark, el desplazamiento se inicia en relación con este marcador. De lo contrario, el desplazamiento comienza en el registro activo.</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>Observaciones

Si usa **Move** para colocar el puntero del registro actual delante del primer registro, el puntero del registro actual se mueve al principio del archivo. Si el objeto **Recordset** no contiene ningún registro y su propiedad **[BOF](recordset-bof-property-dao.md)** es **True**, el uso de este método para un movimiento hacia delante produce un error.

Si usa **Move** para colocar el puntero del registro actual detrás del primer registro, la posición del puntero del último registro actual se mueve al final del archivo. Si el objeto **Recordset** no contiene ningún registro y su propiedad **[EOF](recordset-eof-property-dao.md)** es **True**, el uso de este método para un movimiento hacia atrás produce un error.

Si la propiedad **BOF** o **EOF** es **True** e intenta utilizar el método **Move** sin un marcador válido, se produce un error en tiempo de ejecución.


> [!NOTE]
> <UL>
> <LI>
> <P>Cuando use <STRONG>Move</STRONG> en un objeto <STRONG>Recordset</STRONG> de tipo de solo avance, el argumento rows debe ser un entero positivo y no se permiten marcadores. Esto significa que el movimiento solo puede ser hacia delante.</P>
> <LI>
> <P>Para que el registro primero, último, siguiente o anterior de un objeto <STRONG>Recordset</STRONG> sea el registro activo, use el método <STRONG>MoveFirst</STRONG>, <STRONG>MoveLast</STRONG>, <STRONG>MoveNext</STRONG> o <STRONG>MovePrevious</STRONG>.</P>
> <LI>
> <P>El uso de <STRONG>Move</STRONG> con un número de filas igual a 0 es una manera fácil de recuperar los datos subyacentes para el registro activo. Esto es útil si desea asegurarse de que el registro activo tiene los datos más recientes de las tablas base. Asimismo, cancela cualquier llamada <STRONG><A href="recordset2-edit-method-dao.md">Edit</A></STRONG> o <STRONG><A href="recordset-addnew-method-dao.md">AddNew</A></STRONG> pendiente.</P></LI></UL>



## <a name="example"></a>Ejemplo

En este ejemplo se utiliza el método **Move** para ubicar el puntero de registros, basándose en los datos proporcionados por el usuario.

```vb
    Sub MoveX() 
     
       Dim dbsNorthwind As Database 
       Dim rstSuppliers As Recordset 
       Dim varBookmark As Variant 
       Dim strCommand As String 
       Dim lngMove As Long 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       Set rstSuppliers = _ 
          dbsNorthwind.OpenRecordset("SELECT CompanyName, " & _ 
          "City, Country FROM Suppliers ORDER BY CompanyName", _ 
          dbOpenDynaset) 
     
       With rstSuppliers 
          ' Populate recordset. 
          .MoveLast 
          .MoveFirst 
     
          Do While True 
             ' Display information about current record and ask  
             ' how many records to move. 
             strCommand = InputBox( _ 
                "Record " & (.AbsolutePosition + 1) & " of " & _ 
                .RecordCount & vbCr & "Company: " & _ 
                !CompanyName & vbCr & "Location: " & !City & _ 
                ", " & !Country & vbCr & vbCr & _ 
                "Enter number of records to Move " & _ 
                "(positive or negative).") 
     
             If strCommand = "" Then Exit Do 
     
             ' Store bookmark in case the Move doesn't work. 
             varBookmark = .Bookmark 
     
             ' Move method requires parameter of data type Long. 
             lngMove = CLng(strCommand) 
             .Move lngMove 
     
             ' Trap for BOF or EOF. 
             If .BOF Then 
                MsgBox "Too far backward! " & _ 
                   "Returning to current record." 
                .Bookmark = varBookmark 
             End If 
             If .EOF Then 
                MsgBox "Too far forward! " & _ 
                   "Returning to current record." 
                .Bookmark = varBookmark 
             End If 
          Loop 
          .Close 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub
```
