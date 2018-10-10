---
title: Ejemplo de propiedad IndexNulls (VB)
TOCTitle: IndexNulls Property Example (VB)
ms:assetid: 69b5661c-931e-3a1c-d60e-96a0f93b9494
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249414(v=office.15)
ms:contentKeyID: 48545417
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f35220f3c9426686a452e184330b8704fabb961a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486523"
---
# <a name="indexnulls-property-example-vb"></a><span data-ttu-id="261f9-102">Ejemplo de propiedad IndexNulls (VB)</span><span class="sxs-lookup"><span data-stu-id="261f9-102">IndexNulls Property Example (VB)</span></span>

<span data-ttu-id="261f9-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="261f9-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="261f9-104">En este ejemplo, se muestra la propiedad [IndexNulls](indexnulls-property-adox.md) de un [índice](index-object-adox.md).</span><span class="sxs-lookup"><span data-stu-id="261f9-104">This example demonstrates the [IndexNulls](indexnulls-property-adox.md) property of an [Index](index-object-adox.md).</span></span> <span data-ttu-id="261f9-105">El código crea un nuevo índice y establece el valor de **IndexNulls** en función de valores especificados por el usuario (de un cuadro de lista denominado List1).</span><span class="sxs-lookup"><span data-stu-id="261f9-105">The code creates a new index and sets the value of **IndexNulls** based on user input (from a list box named List1).</span></span> <span data-ttu-id="261f9-106">A continuación, se anexa el **índice** a la [tabla](table-object-adox.md) de **empleados** en el [catálogo](catalog-object-adox.md)de *Northwind* .</span><span class="sxs-lookup"><span data-stu-id="261f9-106">Then, the **Index** is appended to the **Employees** [Table](table-object-adox.md) in the *Northwind* [Catalog](catalog-object-adox.md).</span></span> <span data-ttu-id="261f9-107">El nuevo **índice** se aplica a un [conjunto de registros](recordset-object-ado.md) basándose en la tabla **Employees** y el **conjunto de registros** se abre.</span><span class="sxs-lookup"><span data-stu-id="261f9-107">The new **Index** is applied to a [Recordset](recordset-object-ado.md) based on the **Employees** table, and the **Recordset** is opened.</span></span> <span data-ttu-id="261f9-108">Se añade un nuevo registro a la tabla **Employees**, con valor **Nulo** en el campo indizado.</span><span class="sxs-lookup"><span data-stu-id="261f9-108">A new record is added to the **Employees** table, with a **Null** value in the indexed field.</span></span> <span data-ttu-id="261f9-109">Que el nuevo registro se muestre o no depende de la configuración de la propiedad **IndexNulls**.</span><span class="sxs-lookup"><span data-stu-id="261f9-109">Whether this new record is displayed depends on the setting of the **IndexNulls** property.</span></span>

```vb
    ' IndexNullsVB 
    Sub Main() 
     On Error GoTo IndexNullsXError 
     
     Dim cnn As New ADODB.Connection 
     Dim catNorthwind As New ADOX.Catalog 
     Dim idxNew As New ADOX.Index 
     Dim rstEmployees As New ADODB.Recordset 
     Dim varBookmark As Variant 
     
     ' Connect the catalog. 
     cnn.Open "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
     "Data Source='c:\Program Files\" & _ 
     "Microsoft Office\Office\Samples\Northwind.mdb';" 
     
     Set catNorthwind.ActiveConnection = cnn 
     
     ' Append Country column to new index 
     idxNew.Columns.Append "Country" 
     idxNew.Name = "NewIndex" 
     
     Dim Response 
     Response = MsgBox("Allow 'Null' index? Otherwise ignore 'Null' index.", vbYesNo) 
     '"Allow 'Null' index? Otherwise ignore 'Null' index." 
     ', vbYesNo + vbCritical + vbDefaultButton2,,,, 
     If Response = vbYes Then ' User chose Yes. 
     idxNew.IndexNulls = adIndexNullsAllow 
     Else ' User chose No. 
     idxNew.IndexNulls = adIndexNullsIgnore 
     End If 
     
     'Append new index to Employees table 
     catNorthwind.Tables("Employees").Indexes.Append idxNew 
     
     rstEmployees.Index = idxNew.Name 
     rstEmployees.Open "Employees", cnn, adOpenKeyset, _ 
     adLockOptimistic, adCmdTableDirect 
     
     With rstEmployees 
     ' Add a new record to the Employees table. 
     .AddNew 
     !FirstName = "Gary" 
     !LastName = "Haarsager" 
     .Update 
     
     ' Bookmark the newly added record 
     varBookmark = .Bookmark 
     
     ' Use the new index to set the order of the records. 
     .MoveFirst 
     
     Debug.Print "Index = " & .Index & _ 
     ", IndexNulls = " & idxNew.IndexNulls 
     Debug.Print " Country - Name" 
     
     ' Enumerate the Recordset. The value of the 
     ' IndexNulls property will determine if the newly 
     ' added record appears in the output. 
     Do While Not .EOF 
     Debug.Print " " & _ 
     IIf(IsNull(!Country), "[Null]", !Country) & _ 
     " - " & !FirstName & " " & !LastName 
     .MoveNext 
     Loop 
     
     ' Delete new record because this is a demonstration. 
     .Bookmark = varBookmark 
     .Delete 
     
     .Close 
     End With 
     
     'Clean up 
     Set rstEmployees = Nothing 
     catNorthwind.Tables("Employees").Indexes.Delete idxNew.Name 
     cnn.Close 
     Set cnn = Nothing 
     Set catNorthwind = Nothing 
     Set idxNew = Nothing 
     Exit Sub 
     
    IndexNullsXError: 
     
     If Not rstEmployees Is Nothing Then 
     If rstEmployees.State = adStateOpen Then rstEmployees.Close 
     End If 
     Set rstEmployees = Nothing 
     
     ' Delete new Index because this is a demonstration. 
     If Not catNorthwind Is Nothing Then 
     catNorthwind.Tables("Employees").Indexes.Delete idxNew.Name 
     End If 
     
     If Not cnn Is Nothing Then 
     If cnn.State = adStateOpen Then cnn.Close 
     End If 
     Set cnn = Nothing 
     
     Set catNorthwind = Nothing 
     Set idxNew = Nothing 
     
     If Err <> 0 Then 
     MsgBox Err.Source & "-->" & Err.Description, , "Error" 
     End If 
     
    End Sub 
    ' EndIndexNullsVB
```