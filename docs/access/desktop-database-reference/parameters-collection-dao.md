---
title: Parameters Collection (DAO)
TOCTitle: Parameters Collection
ms:assetid: 52fc1ce4-7b3e-152d-7b6a-9c32a6470147
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193967(v=office.15)
ms:contentKeyID: 48544862
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7f302f83db902498421649ea98b440c01a235d41
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484351"
---
# <a name="parameters-collection-dao"></a><span data-ttu-id="c8508-102">Parameters Collection (DAO)</span><span class="sxs-lookup"><span data-stu-id="c8508-102">Parameters Collection (DAO)</span></span>

<span data-ttu-id="c8508-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="c8508-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c8508-104">Una colección **Parameters** contiene los objetos **Parameter** de un objeto **QueryDef**.</span><span class="sxs-lookup"><span data-stu-id="c8508-104">A **Parameters** collection contains all the **Parameter** objects of a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="c8508-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c8508-105">Remarks</span></span>

<span data-ttu-id="c8508-p101">La colección **Parameters** proporciona información sobre los parámetros existentes. No puede agregar ni eliminar objetos en la colección **Parameters**.</span><span class="sxs-lookup"><span data-stu-id="c8508-p101">The **Parameters** collection provides information only about existing parameters. You can't append objects to or delete objects from the **Parameters** collection.</span></span>

## <a name="example"></a><span data-ttu-id="c8508-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8508-108">Example</span></span>

<span data-ttu-id="c8508-p102">En este ejemplo se utilizan objetos **Parameter** y la colección **Parameters** para crear un objeto **QueryDef** temporal y recuperar datos a partir de los cambios efectuados en los **Parameters** del objeto **QueryDef**. Se requiere el procedimiento ParametersChange para que pueda ejecutarse este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c8508-p102">This example demonstrates **Parameter** objects and the **Parameters** collection by creating a temporary **QueryDef** and retrieving data based on changes made to the **QueryDef** object's **Parameters**. The ParametersChange procedure is required for this procedure to run.</span></span>

```vb
    Sub ParameterX() 
     
       Dim dbsNorthwind As Database 
       Dim qdfReport As QueryDef 
       Dim prmBegin As Parameter 
       Dim prmEnd As Parameter 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
       ' Create temporary QueryDef object with two  
       ' parameters. 
       Set qdfReport = dbsNorthwind.CreateQueryDef("", _ 
          "PARAMETERS dteBegin DateTime, dteEnd DateTime; " & _ 
          "SELECT EmployeeID, COUNT(OrderID) AS NumOrders " & _ 
          "FROM Orders WHERE ShippedDate BETWEEN " & _ 
          "[dteBegin] AND [dteEnd] GROUP BY EmployeeID " & _ 
          "ORDER BY EmployeeID") 
       Set prmBegin = qdfReport.Parameters!dteBegin 
       Set prmEnd = qdfReport.Parameters!dteEnd 
     
       ' Print report using specified parameter values. 
       ParametersChange qdfReport, prmBegin, #1/1/95#, _ 
          prmEnd, #6/30/95# 
       ParametersChange qdfReport, prmBegin, #7/1/95#, _ 
          prmEnd, #12/31/95# 
     
       dbsNorthwind.Close 
     
    End Sub 
     
    Sub ParametersChange(qdfTemp As QueryDef, _ 
       prmFirst As Parameter, dteFirst As Date, _ 
       prmLast As Parameter, dteLast As Date) 
       ' Report function for ParameterX. 
     
       Dim rstTemp As Recordset 
       Dim fldLoop As Field 
     
       ' Set parameter values and open recordset from  
       ' temporary QueryDef object. 
       prmFirst = dteFirst 
       prmLast = dteLast 
       Set rstTemp = _  
          qdfTemp.OpenRecordset(dbOpenForwardOnly) 
       Debug.Print "Period " & dteFirst & " to " & dteLast 
     
       ' Enumerate recordset. 
       Do While Not rstTemp.EOF 
     
          ' Enumerate Fields collection of recordset. 
          For Each fldLoop In rstTemp.Fields 
             Debug.Print " - " & fldLoop.Name & " = " & fldLoop; 
          Next fldLoop 
     
          Debug.Print 
          rstTemp.MoveNext 
       Loop 
     
       rstTemp.Close 
     
    End Sub 
```

<br/>

En el siguiente ejemplo se muestra cómo crear una consulta de parámetro. Se crea una consulta denominada **myQuery** con dos parámetros, denominados Param1 y parámetro2. <span data-ttu-id="c8508-113">Para ello, la propiedad SQL de la consulta está configurada en una instrucción Lenguaje de consulta estructurado (SQL) que define los parámetros.</span><span class="sxs-lookup"><span data-stu-id="c8508-113">To do this, the SQL property of the query is set to a Structured Query Language (SQL) statement that defines the parameters.</span></span>

<span data-ttu-id="c8508-114">**Código de ejemplo proporcionado por** la [referencia del programador de Microsoft Access 2010](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span><span class="sxs-lookup"><span data-stu-id="c8508-114">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    Sub CreateQueryWithParameters()
    
        Dim dbs As DAO.Database
        Dim qdf As DAO.QueryDef
        Dim strSQL As String
    
        Set dbs = CurrentDb
        Set qdf = dbs.CreateQueryDef("myQuery")
        Application.RefreshDatabaseWindow
    
        strSQL = "PARAMETERS Param1 TEXT, Param2 INT; "
        strSQL = strSQL & "SELECT * FROM [Table1] "
        strSQL = strSQL & "WHERE [Field1] = [Param1] AND [Field2] = [Param2];"
        qdf.SQL = strSQL
    
        qdf.Close
        Set qdf = Nothing
        Set dbs = Nothing
    
    End Sub
```

<br/>

<span data-ttu-id="c8508-p104">En el ejemplo siguiente vemos cómo ejecutar una consulta de parámetros. La colección Parameters se usa para establecer el parámetro Organization de la consulta myActionQuery antes de que esta se ejecute.</span><span class="sxs-lookup"><span data-stu-id="c8508-p104">The following example shows how to execute a parameter query. The Parameters collection is used to set the Organization parameter of the myActionQuery query before the query is executed.</span></span>

```vb
    Public Sub ExecParameterQuery()
    
        Dim dbs As DAO.Database
        Dim qdf As DAO.QueryDef
    
        Set dbs = CurrentDb
        Set qdf = dbs.QueryDefs("myActionQuery")
    
        'Set the value of the QueryDef's parameter
        qdf.Parameters("Organization").Value = "Microsoft"
    
        'Execute the query
        qdf.Execute dbFailOnError
    
        'Clean up
        qdf.Close
        Set qdf = Nothing
        Set dbs = Nothing
    
    End Sub
```

<br/>

<span data-ttu-id="c8508-117">En el ejemplo siguiente vemos cómo abrir un Recordset basado en una consulta de parámetros.</span><span class="sxs-lookup"><span data-stu-id="c8508-117">The following example shows how to open a Recordset that is based on a parameter query.</span></span>

```vb
    Dim dbs As DAO.Database
    Dim qdf As DAO.QueryDef
    Dim rst As DAO.Recordset
    
    Set dbs = CurrentDb
    
    'Get the parameter query
    Set qfd = dbs.QueryDefs("qryMyParameterQuery")
    
    'Supply the parameter value
    qdf.Parameters("EnterStartDate") = Date
    qdf.Parameters("EnterEndDate") = Date + 7
    
    'Open a Recordset based on the parameter query
    Set rst = qdf.OpenRecordset()
```