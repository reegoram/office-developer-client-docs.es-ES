---
title: Ejemplo de la propiedad ActiveCommand (VB)
TOCTitle: ActiveCommand Property Example (VB)
ms:assetid: 831032cb-d557-aa98-5637-07bad65f924a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249569(v=office.15)
ms:contentKeyID: 48545999
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f0636141505599464c95af0b9a7df704f9e21dec
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485944"
---
# <a name="activecommand-property-example-vb"></a><span data-ttu-id="d099d-102">Ejemplo de la propiedad ActiveCommand (VB)</span><span class="sxs-lookup"><span data-stu-id="d099d-102">ActiveCommand Property Example (VB)</span></span>


<span data-ttu-id="d099d-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="d099d-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="d099d-104">En este ejemplo se muestra la propiedad [ActiveCommand](activecommand-property-ado.md).</span><span class="sxs-lookup"><span data-stu-id="d099d-104">This example demonstrates the [ActiveCommand](activecommand-property-ado.md) property.</span></span>

<span data-ttu-id="d099d-105">A una subrutina se le asigna un objeto [Recordset](recordset-object-ado.md) cuya propiedad **ActiveCommand** se utiliza para mostrar el texto y los parámetros del comando que ha creado el objeto **Recordset**.</span><span class="sxs-lookup"><span data-stu-id="d099d-105">A subroutine is given a [Recordset](recordset-object-ado.md) object whose **ActiveCommand** property is used to display the command text and parameter that created the **Recordset**.</span></span>

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

<span data-ttu-id="d099d-p101">A la subrutina **ActiveCommandXprint** se le asigna sólo un objeto **Recordset**, si bien tiene que imprimir el texto y los parámetros del comando que ha creado el objeto **Recordset**. Esto es posible porque la propiedad **ActiveCommand** del objeto **Recordset** genera el objeto [Command](command-object-ado.md) asociado.</span><span class="sxs-lookup"><span data-stu-id="d099d-p101">The **ActiveCommandXprint** routine is given only a **Recordset** object, yet it must print the command text and parameter that created the **Recordset**. This can be done because the **Recordset** object's **ActiveCommand** property yields the associated [Command](command-object-ado.md) object.</span></span>

<span data-ttu-id="d099d-p102">La propiedad [CommandText](commandtext-property-ado.md) del objeto **Command** genera el comando parametrizado que ha creado el objeto **Recordset**. La colección [Parameters](parameters-collection-ado.md) del objeto **Command** genera el valor que se ha reemplazado con el marcador de posición de parámetro del comando ("**?**").</span><span class="sxs-lookup"><span data-stu-id="d099d-p102">The **Command** object's [CommandText](commandtext-property-ado.md) property yields the parameterized command that created the **Recordset**. The **Command** object's [Parameters](parameters-collection-ado.md) collection yields the value that was substituted for the command's parameter placeholder ("**?**").</span></span>

<span data-ttu-id="d099d-110">Por último, se imprime el mensaje de error o el nombre y el identificador del autor.</span><span class="sxs-lookup"><span data-stu-id="d099d-110">Finally, an error message or the author's name and ID are printed.</span></span>

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
