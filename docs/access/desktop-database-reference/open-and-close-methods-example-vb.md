---
title: Ejemplo de los métodos Open y Close (VB)
TOCTitle: Open and Close Methods Example (VB)
ms:assetid: 5c000d5f-2560-2530-fe36-163f6600f3cc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249319(v=office.15)
ms:contentKeyID: 48545078
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c31932ae09f2ea9cc3a6b0c61f5e9de422713568
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484873"
---
# <a name="open-and-close-methods-example-vb"></a>Ejemplo de los métodos Open y Close (VB)


**Se aplica a**: Access 2013 | Office 2013

En este ejemplo se usan los métodos **Open** y [Close](close-method-ado.md) en objetos [Recordset](recordset-object-ado.md) y [Connection](connection-object-ado.md) que se han abierto.

```vb 
 
'BeginOpenVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub OpenX() 
 On Error GoTo ErrorHandler 
 
 Dim Cnxn As ADODB.Connection 
 Dim rstEmployees As ADODB.Recordset 
 Dim strCnxn As String 
 Dim strSQLEmployees As String 
 Dim varDate As Variant 
 
 ' Open connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Set Cnxn = New ADODB.Connection 
 Cnxn.Open strCnxn 
 
 ' Open employee table 
 Set rstEmployees = New ADODB.Recordset 
 strSQLEmployees = "employee" 
 rstEmployees.Open strSQLEmployees, Cnxn, adOpenKeyset, adLockOptimistic, adCmdTable 
 
 ' Assign the first employee record's hire date 
 ' to a variable, then change the hire date 
 varDate = rstEmployees!hire_date 
 Debug.Print "Original data" 
 Debug.Print " Name - Hire Date" 
 Debug.Print " " & rstEmployees!fname & " " & _ 
 rstEmployees!lname & " - " & rstEmployees!hire_date 
 rstEmployees!hire_date = #1/1/1900# 
 rstEmployees.Update 
 Debug.Print "Changed data" 
 Debug.Print " Name - Hire Date" 
 Debug.Print " " & rstEmployees!fname & " " & _ 
 rstEmployees!lname & " - " & rstEmployees!hire_date 
 
 ' Requery Recordset and reset the hire date 
 rstEmployees.Requery 
 rstEmployees!hire_date = varDate 
 rstEmployees.Update 
 Debug.Print "Data after reset" 
 Debug.Print " Name - Hire Date" 
 Debug.Print " " & rstEmployees!fname & " " & _ 
 rstEmployees!lname & " - " & rstEmployees!hire_date 
 
 ' clean up 
 rstEmployees.Close 
 Cnxn.Close 
 Set rstEmployees = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstEmployees Is Nothing Then 
 If rstEmployees.State = adStateOpen Then rstEmployees.Close 
 End If 
 Set rstEmployees = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndOpenVB 
```

