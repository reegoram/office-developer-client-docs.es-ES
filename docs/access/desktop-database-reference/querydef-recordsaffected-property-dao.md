---
title: QueryDef.RecordsAffected Property (DAO)
TOCTitle: RecordsAffected Property
ms:assetid: 29a864b5-305c-d33f-b2ca-fc9a08baaa5c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192040(v=office.15)
ms:contentKeyID: 48543886
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053082
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 9377f61ec334f41b7f8ccba61b87a9d5953b4429
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485641"
---
# <a name="querydefrecordsaffected-property-dao"></a><span data-ttu-id="af978-102">QueryDef.RecordsAffected Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="af978-102">QueryDef.RecordsAffected Property (DAO)</span></span>


<span data-ttu-id="af978-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="af978-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="af978-104">Devuelve el número de registros afectados por el último método **[Execute](querydef-execute-method-dao.md)** invocado.</span><span class="sxs-lookup"><span data-stu-id="af978-104">Returns the number of records affected by the most recently invoked **[Execute](querydef-execute-method-dao.md)** method.</span></span>

## <a name="syntax"></a><span data-ttu-id="af978-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af978-105">Syntax</span></span>

<span data-ttu-id="af978-106">*expresión* . RecordsAffected</span><span class="sxs-lookup"><span data-stu-id="af978-106">*expression* .RecordsAffected</span></span>

<span data-ttu-id="af978-107">*expresión* Variable que representa un objeto **QueryDef** .</span><span class="sxs-lookup"><span data-stu-id="af978-107">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="af978-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="af978-108">Remarks</span></span>

<span data-ttu-id="af978-109">Cuando utilice el método **Execute** para ejecutar una consulta de acción desde un objeto **QueryDef**, la propiedad **RecordsAffected** contendrá el número de registros eliminados, actualizados o insertados.</span><span class="sxs-lookup"><span data-stu-id="af978-109">When you use the **Execute** method to run an action query from a **QueryDef** object, the **RecordsAffected** property will contain the number of records deleted, updated, or inserted.</span></span>

## <a name="example"></a><span data-ttu-id="af978-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="af978-110">Example</span></span>

<span data-ttu-id="af978-p101">En este ejemplo se usa la propiedad **RecordsAffected** con consultas de acción ejecutadas desde un objeto **[Database](database-object-dao.md)** y desde un objeto **QueryDef**. Se requiere la función RecordsAffectedOutput para que pueda ejecutarse este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="af978-p101">This example uses the **RecordsAffected** property with action queries executed from a **[Database](database-object-dao.md)** object and from a **QueryDef** object. The RecordsAffectedOutput function is required for this procedure to run.</span></span>

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