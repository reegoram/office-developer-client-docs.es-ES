---
<<<<<<< Título HEAD: colección Parameters, TOCTitle de ejemplo de propiedad comando (VB): colección Parameters, ejemplo de propiedad comando (VB) === título: colección de parámetros, ejemplo de la propiedad comando (VB) TOCTitle: parámetros Colección de ejemplo de la propiedad comando (VB)
>>>>>>> Master ms:assetid: 3bb3e6e1-0ee5-70bb-7f2c-beb461d3914a ms:mtpsurl: https://msdn.microsoft.com/library/JJ249151(v=office.15) ms:contentKeyID: ms.date 48544290: 18/09/2015 mtps_version: Office.15
---

<<<<<<< HEAD
# <a name="parameters-collection-command-property-example-vb"></a>Ejemplo de colección Parameters, propiedad Comando (VB)
=======
# <a name="parameters-collection-command-property-example-vb"></a>Colección de parámetros, ejemplo de la propiedad comando (VB)
>>>>>>> master


**Se aplica a**: Access 2013 | Office 2013

El código siguiente muestra cómo utilizar la propiedad [Comando](command-property-adox.md) con el objeto [Command](command-object-ado.md) para recuperar información de parámetros para el procedimiento.

```vb 
 
' BeginParametersVB 
Sub Main() 
 On Error GoTo ProcedureParametersError 
 
 Dim cnn As New ADODB.Connection 
 Dim cmd As ADODB.Command 
 Dim prm As ADODB.Parameter 
 Dim cat As New ADOX.Catalog 
 
 ' Open the Connection 
 cnn.Open _ 
 "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "Data Source='c:\Program Files\Microsoft Office\" & _ 
 "Office\Samples\Northwind.mdb';" 
 
 ' Open the catalog 
 Set cat.ActiveConnection = cnn 
 
 ' Get the command object 
 Set cmd = cat.Procedures("CustomerById").Command 
 
 ' Retrieve Parameter information 
 cmd.Parameters.Refresh 
 For Each prm In cmd.Parameters 
 Debug.Print prm.Name & ":" & prm.Type 
 Next 
 
 'Clean up 
 cnn.Close 
 Set cat = Nothing 
 Set cmd = Nothing 
 Set cnn = Nothing 
 Exit Sub 
 
ProcedureParametersError: 
 
 Set cat = Nothing 
 Set cmd = Nothing 
 
 If Not cnn Is Nothing Then 
 If cnn.State = adStateOpen Then cnn.Close 
 End If 
 Set cnn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
' EndParametersVB 
```

