---
<<<<<<< Título HEAD: ejemplo de propiedad StayInSync (VB) TOCTitle: ejemplo de propiedad StayInSync (VB) === título: ejemplo de la propiedad StayInSync (VB) TOCTitle: ejemplo de la propiedad StayInSync (VB)
>>>>>>> Master ms:assetid: 1b35f19a-0104-efd5-5222-55f92e08473b ms:mtpsurl: https://msdn.microsoft.com/library/JJ248952(v=office.15) ms:contentKeyID: ms.date 48543535: 18/09/2015 mtps_version: Office.15
---

<<<<<<< HEAD
# <a name="stayinsync-property-example-vb"></a>Ejemplo de la propiedad StayInSync (VB)
=======
# <a name="stayinsync-property-example-vb"></a>Ejemplo de la propiedad StayInSync (VB)
>>>>>>> master


**Se aplica a**: Access 2013 | Office 2013

En este ejemplo se muestra cómo facilita la propiedad [StayInSync](stayinsync-property-ado.md) el acceso a las filas de un objeto [Recordset](recordset-object-ado.md) jerárquico.

El bucle externo muestra el nombre y apellido de cada autor, el país y la identificación. El objeto **Recordset** anexado de cada fila se recupera desde la colección [Fields](fields-collection-ado.md) y es asignado automáticamente a **rstTitleAuthor** por la propiedad **StayInSync** siempre que el objeto **Recordset** primario se mueve a una nueva fila. El bucle interno muestra cuatro campos de cada fila en el conjunto de registros anexado.

```vb 
 
'BeginStayInSyncVB 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 'To integrate this code create a DSN called Pubs 
 'with a user_id = sa and no password 
 
 Dim Cnxn As ADODB.Connection 
 Dim rst As ADODB.Recordset 
 Dim rstTitleAuthor As New ADODB.Recordset 
 Dim strCnxn As String 
 
 ' open connection with Data Shape attributes 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider=MSDataShape;Data Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' create recordset 
 Set rst = New ADODB.Recordset 
 rst.StayInSync = True 
 rst.Open "SHAPE {select * from Authors} " & _ 
 "APPEND ( { select * from titleauthor} AS chapTitleAuthor " & _ 
 "RELATE au_id TO au_id) ", Cnxn, , , adCmdText 
 
 Set rstTitleAuthor = rst("chapTitleAuthor").Value 
 Do Until rst.EOF 
 Debug.Print rst!au_fname & " " & rst!au_lname & " " & _ 
 rst!State & " " & rst!au_id 
 
 Do Until rstTitleAuthor.EOF 
 Debug.Print rstTitleAuthor(0) & " " & rstTitleAuthor(1) & " " & _ 
 rstTitleAuthor(2) & " " & rstTitleAuthor(3) 
 rstTitleAuthor.MoveNext 
 Loop 
 
 rst.MoveNext 
 Loop 
 
 ' clean up 
 rst.Close 
 Cnxn.Close 
 Set rst = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rst Is Nothing Then 
 If rst.State = adStateOpen Then rst.Close 
 End If 
 Set rst = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndStayInSyncVB 
```

