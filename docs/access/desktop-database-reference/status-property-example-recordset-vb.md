---
<<<<<<< Título HEAD: ejemplo de propiedad Status (Recordset) (VB) TOCTitle: ejemplo de propiedad Status (Recordset) (VB) === título: ejemplo de la propiedad Status (Recordset) (VB) TOCTitle: ejemplo de la propiedad Status (Recordset) (VB)
>>>>>>> Master ms:assetid: 97ddd465-88ed-81dd-3714-1841f1c87611 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249677(v=office.15) ms:contentKeyID: ms.date 48546476: 18/09/2015 mtps_version: Office.15
---

<<<<<<< HEAD
# <a name="status-property-example-recordset-vb"></a>Ejemplo de la propiedad Status (Recordset) (VB)
=======
# <a name="status-property-example-recordset-vb"></a>Ejemplo de la propiedad Status (Recordset) (VB)
>>>>>>> master


**Se aplica a**: Access 2013 | Office 2013

En este ejemplo se utiliza la propiedad [Status](status-property-ado-recordset.md) para mostrar qué registros se han modificado en una operación por lotes antes de que se haya producido una actualización por lotes.

```vb 
 
'BeginStatusRecordsetVB 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
 ' connection and recordset variables 
 Dim rstTitles As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strCnxn As String 
 Dim strSQLTitles As String 
 
 ' open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' open recordset for batch update 
 Set rstTitles = New ADODB.Recordset 
 strSQLTitles = "Titles" 
 rstTitles.Open strSQLTitles, Cnxn, adOpenKeyset, adLockBatchOptimistic, adCmdTable 
 
 ' change the type of psychology titles 
 Do Until rstTitles.EOF 
 If Trim(rstTitles!Type) = "psychology" Then rstTitles!Type = "self_help" 
 rstTitles.MoveNext 
 Loop 
 
 ' display Title ID and status 
 rstTitles.MoveFirst 
 Do Until rstTitles.EOF 
 If rstTitles.Status = adRecModified Then 
 Debug.Print rstTitles!title_id & " - Modified" 
 Else 
 Debug.Print rstTitles!title_id 
 End If 
 rstTitles.MoveNext 
 Loop 
 
 ' clean up 
 rstTitles.Close 
 Cnxn.Close 
 Set rstTitles = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstTitles Is Nothing Then 
 If rstTitles.State = adStateOpen Then 
 ' Cancel the update because this is a demonstration 
 rstTitles.CancelBatch 
 rstTitles.Close 
 End If 
 End If 
 Set rstTitles = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndStatusRecordsetVB 
```

