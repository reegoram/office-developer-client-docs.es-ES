---
title: Recordset.LockEdits Property (DAO)
TOCTitle: LockEdits Property
ms:assetid: baa11b24-a330-eaa4-bd03-b8b9739d209e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822514(v=office.15)
ms:contentKeyID: 48547379
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052877
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 74708911adcf51d0499e6b37567eafc0858e21d7
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485794"
---
# <a name="recordsetlockedits-property-dao"></a>Recordset.LockEdits Property (DAO)


**Se aplica a**: Access 2013 | Office 2013

Establece o devuelve un valor que indica el tipo de bloqueo que está activo mientras se modifica.

## <a name="syntax"></a>Sintaxis

*expresión* . LockEdits

*expresión* Variable que representa un objeto **Recordset** .

## <a name="remarks"></a>Observaciones

La configuración o el valor devuelto indica el tipo de bloqueo, como se especifica en la siguiente tabla.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Valor</p></th>
<th><p>Descripción</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>True</p></td>
<td><p>Predeterminado. Está activado un bloqueo pesimista. La página que contiene el registro que está editando se bloquea tan pronto como llama al método Edit.</p></td>
</tr>
<tr class="even">
<td><p>False</p></td>
<td><p>Bloqueo optimista es en efecto para su edición. La página que contiene el registro no se bloquee hasta que se ejecuta el método Update.</p></td>
</tr>
</tbody>
</table>


Puede usar la propiedad **LockEdits** con objetos **[Recordset](recordset-object-dao.md)** actualizables.

Si la página está bloqueada, ningún otro usuario puede editar registros en esa página. Si establece **LockEdits** en **True** y otro usuario ya ha bloqueado la página, se producirá un error cuando usted intente utilizar el método **Edit**. Otros usuarios pueden leer datos de páginas bloqueadas.

Si establece la propiedad **LockEdits** en **False** y después utiliza el método **Update** mientras otro usuario ha bloqueado la página, se producirá un error. Para ver los cambios realizados por otro usuario en su registro, utilice el método **[Move](recordset-move-method-dao.md)** con 0 como argumento; sin embargo, al hacer esto perderá sus cambios.

Cuando trabaje con un motor de base de datos Microsoft Access conectado a orígenes de datos ODBC, la propiedad **LockEdits** estará siempre establecida en **False** o en bloqueo optimista. El motor de base de datos Microsoft Access no tiene control sobre los mecanismos de bloqueo utilizados en servidores de bases de datos externos.


> [!NOTE]
> <P>Puede definir previamente el valor de <STRONG>LockEdits</STRONG> la primera vez que abre el <STRONG>conjunto de registros</STRONG> estableciendo el argumento lockedits del método <STRONG><A href="connection-openrecordset-method-dao.md">OpenRecordset</A></STRONG> . Establecer el argumento lockedits en <STRONG>dbPessimistic</STRONG> se establecerá la propiedad <STRONG>LockEdits</STRONG> en <STRONG>True</STRONG>, y configuración lockedits en cualquier otro valor establecerá la propiedad <STRONG>LockEdits</STRONG> en <STRONG>False</STRONG>.</P>



## <a name="example"></a>Ejemplo

En este ejemplo se muestra un bloqueo pesimista al establecer la propiedad **LockEdits** en **True**, después se muestra un bloqueo optimista al establecer la propiedad **LockEdits** en False. También se muestra el tipo de tratamiento de errores necesario en un entorno de base de datos multiusuario para poder modificar un campo. Se requieren las funciones PessimisticLock y OptimisticLock para que pueda ejecutarse este procedimiento.

```vb
    Sub LockEditsX() 
     
     Dim dbsNorthwind As Database 
     Dim rstCustomers As Recordset 
     Dim strOldName As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstCustomers = _ 
     dbsNorthwind.OpenRecordset("Customers", _ 
     dbOpenDynaset) 
     
     With rstCustomers 
     ' Store original data. 
     strOldName = !CompanyName 
     
     If MsgBox("Pessimistic locking demonstration...", _ 
     vbOKCancel) = vbOK Then 
     
     ' Attempt to modify data with pessimistic locking 
     ' in effect. 
     If PessimisticLock(rstCustomers, !CompanyName, _ 
     "Acme Foods") Then 
     MsgBox "Record successfully edited." 
     
     ' Restore original data... 
     .Edit 
     !CompanyName = strOldName 
     .Update 
     End If 
     
     End If 
     
     If MsgBox("Optimistic locking demonstration...", _ 
     vbOKCancel) = vbOK Then 
     
     ' Attempt to modify data with optimistic locking 
     ' in effect. 
     If OptimisticLock(rstCustomers, !CompanyName, _ 
     "Acme Foods") Then 
     MsgBox "Record successfully edited." 
     
     ' Restore original data... 
     .Edit 
     !CompanyName = strOldName 
     .Update 
     End If 
     
     End If 
     
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Function PessimisticLock(rstTemp As Recordset, _ 
     fldTemp As Field, strNew As String) As Boolean 
     
     dim ErrLoop as Error 
     
     PessimisticLock = True 
     
     With rstTemp 
     .LockEdits = True 
     
     ' When you set LockEdits to True, you trap for errors 
     ' when you call the Edit method. 
     On Error GoTo Err_Lock 
     .Edit 
     On Error GoTo 0 
     
     ' If the Edit is still in progress, then no errors 
     ' were triggered; you may modify the data. 
     If .EditMode = dbEditInProgress Then 
     fldTemp = strNew 
     .Update 
     .Bookmark = .LastModified 
     Else 
     ' Retrieve current record to see changes made by 
     ' other user. 
     .Move 0 
     End If 
     
     End With 
     
     Exit Function 
     
    Err_Lock: 
     
     If DBEngine.Errors.Count > 0 Then 
     ' Enumerate the Errors collection. 
     For Each errLoop In DBEngine.Errors 
     MsgBox "Error number: " & errLoop.Number & _ 
     vbCr & errLoop.Description 
     Next errLoop 
     PessimisticLock = False 
     End If 
     
     Resume Next 
     
    End Function 
     
    Function OptimisticLock(rstTemp As Recordset, _ 
     fldTemp As Field, strNew As String) As Boolean 
     
     dim ErrLoop as Error 
     
     OptimisticLock = True 
     
     With rstTemp 
     .LockEdits = False 
     .Edit 
     fldTemp = strNew 
     
     ' When you set LockEdits to False, you trap for errors 
     ' when you call the Update method. 
     On Error GoTo Err_Lock 
     .Update 
     On Error GoTo 0 
     
     ' If there is no Edit in progress, then no errors were 
     ' triggered; you may modify the data. 
     If .EditMode = dbEditNone Then 
     ' Move current record pointer to the most recently 
     ' modified record. 
     .Bookmark = .LastModified 
     Else 
     .CancelUpdate 
     ' Retrieve current record to see changes made by 
     ' other user. 
     .Move 0 
     End If 
     
     End With 
     
     Exit Function 
     
    Err_Lock: 
     
     If DBEngine.Errors.Count > 0 Then 
     ' Enumerate the Errors collection. 
     For Each errLoop In DBEngine.Errors 
     MsgBox "Error number: " & errLoop.Number & _ 
     vbCr & errLoop.Description 
     Next errLoop 
     OptimisticLock = False 
     End If 
     
     Resume Next 
     
    End Function
```
