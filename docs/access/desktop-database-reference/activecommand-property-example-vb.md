---
<<<<<<< Título HEAD: TOCTitle ejemplo de propiedad ActiveCommand (VB): ms:assetid ejemplo de propiedad ActiveCommand (VB): 831032cb-d557-aa98-5637-07bad65f924a ms:mtpsurl: https://msdn.microsoft.com/library/JJ249569(v=office.15) ms:contentKeyID: ms.date 48545999: 18/09/2015 mtps_ versión: Office.15
---

# <a name="activecommand-property-example-vb"></a>Ejemplo de la propiedad ActiveCommand (VB)
=== título: ejemplo de la propiedad ActiveCommand (VB) TOCTitle: ActiveCommand (propiedad) (VB) de ejemplo ms:assetid: 831032cb-d557-aa98-5637-07bad65f924a ms:mtpsurl: https://msdn.microsoft.com/library/JJ249569(v=office.15) ms:contentKeyID: ms.date 48545999: 17/10/2018 mtps_version: Office.15
---

# <a name="activecommand-property-example-vb"></a>Ejemplo de la propiedad ActiveCommand (VB)
>>>>>>> master


**Se aplica a**: Access 2013 | Office 2013

En este ejemplo se muestra la propiedad [ActiveCommand](activecommand-property-ado.md).

A una subrutina se le asigna un objeto [Recordset](recordset-object-ado.md) cuya propiedad **ActiveCommand** se utiliza para mostrar el texto y los parámetros del comando que ha creado el objeto **Recordset**.

```vb 
 
'BeginActiveCommandVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 'recordset and connection variables 
 Dim cmd As ADODB.Command 
 Dim rst As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strCnxn As String 
 'record variables 
 Dim strPrompt As String 
 Dim strName As String 
 
 Set Cnxn = New ADODB.Connection 
 Set cmd = New ADODB.Command 
 
 strPrompt = "Enter an author's name (e.g., Ringer): " 
 strName = Trim(InputBox(strPrompt, "ActiveCommandX Example")) 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 
 'create SQL command string 
 cmd.CommandText = "SELECT * FROM Authors WHERE au_lname = ?" 
 cmd.Parameters.Append cmd.CreateParameter("LastName", adChar, adParamInput, 20, strName) 
 
 Cnxn.Open strCnxn 
 cmd.ActiveConnection = Cnxn 
 
 'create the recordset by executing command string 
 Set rst = cmd.Execute(, , adCmdText) 
 'see the results 
 Call ActiveCommandXprint(rst) 
 
 ' clean up 
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
'EndActiveCommandVB 
```

A la subrutina **ActiveCommandXprint** se le asigna sólo un objeto **Recordset**, si bien tiene que imprimir el texto y los parámetros del comando que ha creado el objeto **Recordset**. Esto es posible porque la propiedad **ActiveCommand** del objeto **Recordset** genera el objeto [Command](command-object-ado.md) asociado.

La propiedad [CommandText](commandtext-property-ado.md) del objeto **Command** genera el comando parametrizado que ha creado el objeto **Recordset**. La colección [Parameters](parameters-collection-ado.md) del objeto **Command** genera el valor que se ha reemplazado con el marcador de posición de parámetro del comando ("**?**").

Por último, se imprime el mensaje de error o el nombre y el identificador del autor.

```vb 
 
'BeginActiveCommandPrintVB 
Public Sub ActiveCommandXprint(rstp As ADODB.Recordset) 
 
 Dim strName As String 
 
 strName = rstp.ActiveCommand.Parameters.Item("LastName").Value 
 
 Debug.Print "Command text = '"; rstp.ActiveCommand.CommandText; "'" 
 Debug.Print "Parameter = '"; strName; "'" 
 
 If rstp.BOF = True Then 
 Debug.Print "Name = '"; strName; "', not found." 
 Else 
 Debug.Print "Name = '"; rstp!au_fname; " "; rstp!au_lname; _ 
 "', author ID = '"; rstp!au_id; "'" 
 End If 
 
 rstp.Close 
 Set rstp = Nothing 
End Sub 
'EndActiveCommandPrintVB 
```

