---
<<<<<<< Título HEAD: DateCreated y DateModified propiedades ejemplo (VB) TOCTitle: DateCreated y DateModified propiedades ejemplo (VB) === título: ejemplo de las propiedades DateCreated y DateModified (VB) TOCTitle: DateCreated y Ejemplo de las propiedades DateModified (VB)
>>>>>>> Master ms:assetid: 5afdb5a9-394f-c38f-83a4-ae7017673c5e ms:mtpsurl: https://msdn.microsoft.com/library/JJ249316(v=office.15) ms:contentKeyID: ms.date 48545063: 18/09/2015 mtps_version: Office.15
---

<<<<<<< HEAD
# <a name="datecreated-and-datemodified-properties-example-vb"></a>Ejemplo de propiedades DateCreated y DateModified (VB)
=======
# <a name="datecreated-and-datemodified-properties-example-vb"></a>Ejemplo de las propiedades DateCreated y DateModified (VB)
>>>>>>> master


**Se aplica a**: Access 2013 | Office 2013

En este ejemplo, se muestran las propiedades [DateCreated](datecreated-property-adox.md) y [DateModified](datemodified-property-adox.md) agregando una nueva [columna](column-object-adox.md) a una [tabla](table-object-adox.md) existente y creando una nueva **tabla**. El procedimiento DateOutput es necesario para que se pueda ejecutar este ejemplo.

```vb 
 
' BeginDateCreatedVB 
Sub Main() 
 On Error GoTo DateCreatedXError 
 
 Dim cat As New ADOX.Catalog 
 Dim tblEmployees As ADOX.Table 
 Dim tblNewTable As ADOX.Table 
 
 ' Connect the catalog. 
 cat.ActiveConnection = "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "Data Source='c:\Program Files\" & _ 
 "Microsoft Office\Office\Samples\Northwind.mdb';" 
 
 With cat 
 Set tblEmployees = .Tables("Employees") 
 
 ' Print current information about the Employees table. 
 DateOutput "Current properties", tblEmployees 
 
 ' Create and append column to the Employees table. 
 tblEmployees.Columns.Append "NewColumn", adInteger 
 .Tables.Refresh 
 
 ' Print new information about the Employees table. 
 DateOutput "After creating a new column", tblEmployees 
 
 ' Delete new column because this is a demonstration. 
 tblEmployees.Columns.Delete "NewColumn" 
 
 ' Create and append new Table object to the Northwind database. 
 Set tblNewTable = New ADOX.Table 
 tblNewTable.Name = "NewTable" 
 tblNewTable.Columns.Append "NewColumn", adInteger 
 .Tables.Append tblNewTable 
 .Tables.Refresh 
 
 ' Print information about the new Table object. 
 DateOutput "After creating a new table", .Tables("NewTable") 
 
 ' Delete new Table object because this is a demonstration. 
 .Tables.Delete tblNewTable.Name 
 End With 
 
 'Clean up 
 Set cat.ActiveConnection = Nothing 
 Set cat = Nothing 
 Exit Sub 
 
DateCreatedXError: 
 Set cat = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
 
End Sub 
 
Sub DateOutput(strTemp As String, tblTemp As ADOX.Table) 
 ' Print DateCreated and DateModified information about 
 ' specified Table object. 
 Debug.Print strTemp 
 Debug.Print " Table: " & tblTemp.Name 
 Debug.Print " DateCreated = " & tblTemp.DateCreated 
 Debug.Print " DateModified = " & tblTemp.DateModified 
 Debug.Print 
End Sub 
' EndDateCreatedVB 
```

