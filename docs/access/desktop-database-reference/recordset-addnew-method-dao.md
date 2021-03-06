---
title: Método Recordset.AddNew (DAO)
TOCTitle: AddNew Method
ms:assetid: 18cb35f6-8652-fb20-2460-3d13fae39d23
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845624(v=office.15)
ms:contentKeyID: 48543483
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052883
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 8aee4e63959beca98e96d04d14f817b2b6a30e7c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485431"
---
# <a name="recordsetaddnew-method-dao"></a>Método Recordset.AddNew (DAO)


**Se aplica a**: Access 2013 | Office 2013

Crea un nuevo registro de un objeto **[Recordset](recordset-object-dao.md)** actualizable.

## <a name="syntax"></a>Sintaxis

*expresión* . AddNew

*expresión* Variable que representa un objeto **Recordset** .

## <a name="remarks"></a>Comentarios

Use el método **AddNew** para crear y agregar un nuevo registro al objeto **Recordset** designado por el conjunto de registros. Este método configura los campos en sus valores predeterminados y, si no especifica ningún valor predeterminado, configura los campos en Null (valores predeterminados especificados para un objeto **Recordset** de tipo tabla).

Después de modificar el nuevo registro, use el método **[Update](recordset-update-method-dao.md)** para guardar los cambios y agregar el registro a **Recordset**. No se producen cambios en la base de datos hasta que use el método **Update**.


> [!NOTE]
> <P>[!NOTA] Si emite un <STRONG>AddNew</STRONG> y ejecuta luego realiza cualquier operación para desplazarse a otro registro, pero sin usar <STRONG>Update</STRONG>, los cambios se perderán sin ninguna advertencia. Además, si cierra <STRONG>Recordset</STRONG> o termina el procedimiento que declara el objeto <STRONG>Recordset</STRONG> o su objeto <STRONG><A href="database-object-dao.md">Database</A></STRONG>, el nuevo registro se descarta sin advertencia.</P>




> [!NOTE]
> <P>[!NOTA] Al usar <STRONG>AddNew</STRONG> en un área de trabajo de Microsoft Access y el motor de base de datos tiene que crear una nueva página para albergar el registro actual, el bloqueo de página es pesimista. Si el nuevo registro se ajusta a una página existente, el bloqueo de página es optimista.</P>



Si no se ha desplazado al último registro del objeto **Recordset**, se pueden incluir los registros agregados a las tablas base mediante otros procesos si están colocados más allá del registro actual. Sin embargo, si agrega un registro a su propio objeto **Recordset**, el registro será visible en **Recordset** y se incluirá en la tabla subyacente donde estará visible para cualquier nuevo objeto **Recordset**.

La posición del nuevo registro depende del tipo de **Recordset**:

  - En un objeto **Recordset** de tipo Dynaset, los registros se insertan al final de **Recordset**, independientemente de las reglas de clasificación u ordenación que se aplicaban al abrir **Recordset**.

  - En un objeto **Recordset** de tipo tabla cuya la propiedad **[Index](recordset-index-property-dao.md)** está configurada, los registros se devuelven a su posición correcta según el criterio de ordenación. Si no configura la propiedad **Index**, los nuevos registros se devuelven al final de **Recordset**.

El registro que estaba activo antes de usar **AddNew** sigue siendo el registro actual. Si quiere convertir el nuevo registro en el registro actual, puede configurar la propiedad **[Bookmark](recordset-bookmark-property-dao.md)** en el marcador identificado por el valor de propiedad **[LastModified](recordset-lastmodified-property-dao.md)**.


> [!NOTE]
> <P>[!NOTA] Para agregar, editar o eliminar un registro, debe haber un índice único en el registro del origen de datos subyacente. En caso contrario, se produce un error de "denegación de permiso" en la llamada al método <STRONG>AddNew</STRONG>, <STRONG>Delete</STRONG> o <STRONG>Edit</STRONG> en un área de trabajo de Microsoft Access.</P>



## <a name="example"></a>Ejemplo

En este ejemplo se utiliza el método **AddNew** para crear un registro nuevo con el nombre especificado. Se requiere la función AddName para que pueda ejecutarse este procedimiento.

```vb
    Sub AddNewX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     Dim strFirstName As String 
     Dim strLastName As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", dbOpenDynaset) 
     
     ' Get data from the user. 
     strFirstName = Trim(InputBox( _ 
     "Enter first name:")) 
     strLastName = Trim(InputBox( _ 
     "Enter last name:")) 
     
     ' Proceed only if the user actually entered something 
     ' for both the first and last names. 
     If strFirstName <> "" and strLastName <> "" Then 
     
     ' Call the function that adds the record. 
     AddName rstEmployees, strFirstName, strLastName 
     
     ' Show the newly added data. 
     With rstEmployees 
     Debug.Print "New record: " & !FirstName & _ 
     " " & !LastName 
     ' Delete new record because this is a demonstration. 
     .Delete 
     End With 
     
     Else 
     Debug.Print _ 
     "You must input a string for first and last name!" 
     End If 
     
     rstEmployees.Close 
     dbsNorthwind.Close 
     
    End Sub 
     
    Function AddName(rstTemp As Recordset, _ 
     strFirst As String, strLast As String) 
     
     ' Adds a new record to a Recordset using the data passed 
     ' by the calling procedure. The new record is then made 
     ' the current record. 
     With rstTemp 
     .AddNew 
     !FirstName = strFirst 
     !LastName = strLast 
     .Update 
     .Bookmark = .LastModified 
     End With 
     
    End Function
```
