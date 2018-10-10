---
title: Database.RecordsAffected Property (DAO)
TOCTitle: RecordsAffected Property
ms:assetid: 1c591231-21dd-f0b1-4ba6-87784c5890d3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845732(v=office.15)
ms:contentKeyID: 48543567
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8f0fb54773b6ab28a871b4a550e91dda5516c97c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486223"
---
# <a name="databaserecordsaffected-property-dao"></a><span data-ttu-id="52fe8-102">Database.RecordsAffected Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="52fe8-102">Database.RecordsAffected Property (DAO)</span></span>


<span data-ttu-id="52fe8-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="52fe8-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="52fe8-104">Devuelve el número de registros afectados por el último método **[Execute](connection-execute-method-dao.md)** invocado.</span><span class="sxs-lookup"><span data-stu-id="52fe8-104">Returns the number of records affected by the most recently invoked **[Execute](connection-execute-method-dao.md)** method.</span></span>

## <a name="syntax"></a><span data-ttu-id="52fe8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52fe8-105">Syntax</span></span>

<span data-ttu-id="52fe8-106">*expresión* . RecordsAffected</span><span class="sxs-lookup"><span data-stu-id="52fe8-106">*expression* .RecordsAffected</span></span>

<span data-ttu-id="52fe8-107">*expresión* Variable que representa un objeto de **base de datos** .</span><span class="sxs-lookup"><span data-stu-id="52fe8-107">*expression* A variable that represents a **Database** object.</span></span>

## <a name="example"></a><span data-ttu-id="52fe8-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="52fe8-108">Example</span></span>

<span data-ttu-id="52fe8-p101">En este ejemplo, se usa la propiedad **RecordsAffected** con consultas de acciones ejecutadas desde un objeto **Database** y desde un objeto **QueryDef**. La función RecordsAffectedOutput es necesaria para que se ejecute este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="52fe8-p101">This example uses the **RecordsAffected** property with action queries executed from a **Database** object and from a **QueryDef** object. The RecordsAffectedOutput function is required for this procedure to run.</span></span>

```vb
    Sub RecordsAffectedX() 
     
     Dim dbsNorthwind As Database 
     Dim qdfTemp As QueryDef 
     Dim strSQLChange As String 
     Dim strSQLRestore As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     With dbsNorthwind 
     ' Print report of contents of the Employees 
     ' table. 
     Debug.Print _ 
     "Number of records in Employees table: " & _ 
     .TableDefs!Employees.RecordCount 
     RecordsAffectedOutput dbsNorthwind 
     
     ' Define and execute an action query. 
     strSQLChange = "UPDATE Employees " & _ 
     "SET Country = 'United States' " & _ 
     "WHERE Country = 'USA'" 
     .Execute strSQLChange 
     
     ' Print report of contents of the Employees 
     ' table. 
     Debug.Print _ 
     "RecordsAffected after executing query " & _ 
     "from Database: " & .RecordsAffected 
     RecordsAffectedOutput dbsNorthwind 
     
     ' Define and run another action query. 
     strSQLRestore = "UPDATE Employees " & _ 
     "SET Country = 'USA' " & _ 
     "WHERE Country = 'United States'" 
     Set qdfTemp = .CreateQueryDef("", strSQLRestore) 
     qdfTemp.Execute 
     
     ' Print report of contents of the Employees 
     ' table. 
     Debug.Print _ 
     "RecordsAffected after executing query " & _ 
     "from QueryDef: " & qdfTemp.RecordsAffected 
     RecordsAffectedOutput dbsNorthwind 
     
     .Close 
     
     End With 
     
    End Sub 
     
    Function RecordsAffectedOutput(dbsNorthwind As Database) 
     
     Dim rstEmployees As Recordset 
     
     ' Open a Recordset object from the Employees table. 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees") 
     
     With rstEmployees 
     ' Enumerate Recordset. 
     .MoveFirst 
     Do While Not .EOF 
     Debug.Print " " & !LastName & ", " & !Country 
     .MoveNext 
     Loop 
     .Close 
     End With 
     
    End Function
```