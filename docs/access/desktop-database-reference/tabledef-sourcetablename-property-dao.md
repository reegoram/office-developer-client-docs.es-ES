---
title: TableDef.SourceTableName Property (DAO)
TOCTitle: SourceTableName Property
ms:assetid: 3c02f5f6-70ae-39ec-0984-8d6b81992418
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192675(v=office.15)
ms:contentKeyID: 48544300
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052901
f1_categories:
- Office.Version=v15
ms.openlocfilehash: f8a1ee45227518cee9b279e31f25d253f59bf1f1
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485479"
---
# <a name="tabledefsourcetablename-property-dao"></a><span data-ttu-id="8ca32-102">TableDef.SourceTableName Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="8ca32-102">TableDef.SourceTableName Property (DAO)</span></span>


<span data-ttu-id="8ca32-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="8ca32-103">**Applies to**: Access 2013 | Office 2013</span></span> 

<span data-ttu-id="8ca32-104">Establece o devuelve un valor que especifica el nombre de una tabla vinculada o el nombre de una tabla base (únicamente áreas de trabajo de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="8ca32-104">Sets or returns a value that specifies the name of a linked table or the name of a base table (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="8ca32-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ca32-105">Syntax</span></span>

<span data-ttu-id="8ca32-106">*expresión* . SourceTableName</span><span class="sxs-lookup"><span data-stu-id="8ca32-106">*expression* .SourceTableName</span></span>

<span data-ttu-id="8ca32-107">*expresión* Variable que representa un objeto **TableDef** .</span><span class="sxs-lookup"><span data-stu-id="8ca32-107">*expression* A variable that represents a **TableDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="8ca32-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8ca32-108">Remarks</span></span>

<span data-ttu-id="8ca32-p101">El valor de esta propiedad es de sólo lectura para una tabla base y de lectura y escritura para una tabla vinculada o un objeto no anexado a una colección. Para una tabla base, el valor es una cadena de longitud cero ("").</span><span class="sxs-lookup"><span data-stu-id="8ca32-p101">This property setting is read-only for a base table and read/write for a linked table or an object not appended to a collection. For a base table, the setting is a zero-length string ("").</span></span>

## <a name="example"></a><span data-ttu-id="8ca32-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ca32-111">Example</span></span>

<span data-ttu-id="8ca32-p102">En este ejemplo se usan las propiedades **Connect** y **SourceTableName** para vincular diversas tablas externas a una base de datos de Microsoft Access. Para que este procedimiento se ejecute se necesita el procedimiento ConnectOutput.</span><span class="sxs-lookup"><span data-stu-id="8ca32-p102">This example uses the **Connect** and **SourceTableName** properties to link various external tables to a Microsoft Access database. The ConnectOutput procedure is required for this procedure to run.</span></span>

```vb 
Sub ConnectX() 
 
 Dim dbsTemp As Database 
 Dim strMenu As String 
 Dim strInput As String 
 
 ' Open a Microsoft Access database to which you will link 
 ' a table. 
 Set dbsTemp = OpenDatabase("DB1.mdb") 
 
 ' Build menu text. 
 strMenu = "Enter number for data source:" & vbCr 
 strMenu = strMenu & _ 
 " 1. Microsoft Access database" & vbCr 
 strMenu = strMenu & _ 
 " 2. Microsoft FoxPro 3.0 table" & vbCr 
 strMenu = strMenu & _ 
 " 3. dBASE table" & vbCr 
 strMenu = strMenu & _ 
 " 4. Paradox table" & vbCr 
 strMenu = strMenu & _ 
 " M. (see choices 5-9)" 
 
 ' Get user's choice. 
 strInput = InputBox(strMenu) 
 
 If UCase(strInput) = "M" Then 
 
 ' Build menu text. 
 strMenu = "Enter number for data source:" & vbCr 
 strMenu = strMenu & _ 
 " 5. Microsoft Excel spreadsheet" & vbCr 
 strMenu = strMenu & _ 
 " 6. Lotus spreadsheet" & vbCr 
 strMenu = strMenu & _ 
 " 7. Comma-delimited text (CSV)" & vbCr 
 strMenu = strMenu & _ 
 " 8. HTML table" & vbCr 
 strMenu = strMenu & _ 
 " 9. Microsoft Exchange folder" 
 
 ' Get user's choice. 
 strInput = InputBox(strMenu) 
 
 End If 
 
 ' Call the ConnectOutput procedure. The third argument 
 ' will be used as the Connect string, and the fourth 
 ' argument will be used as the SourceTableName. 
 Select Case Val(strInput) 
 Case 1 
 ConnectOutput dbsTemp, _ 
 "AccessTable", _ 
 ";DATABASE=C:\My Documents\Northwind.mdb", _ 
 "Employees" 
 Case 2 
 ConnectOutput dbsTemp, _ 
 "FoxProTable", _ 
 "FoxPro 3.0;DATABASE=C:\FoxPro30\Samples", _ 
 "Q1Sales" 
 Case 3 
 ConnectOutput dbsTemp, _ 
 "dBASETable", _ 
 "dBase IV;DATABASE=C:\dBASE\Samples", _ 
 "Accounts" 
 Case 4 
 ConnectOutput dbsTemp, _ 
 "ParadoxTable", _ 
 "Paradox 3.X;DATABASE=C:\Paradox\Samples", _ 
 "Accounts" 
 Case 5 
 ConnectOutput dbsTemp, _ 
 "ExcelTable", _ 
 "Excel 5.0;" & _ 
 "DATABASE=C:\Excel\Samples\Q1Sales.xls", _ 
 "January Sales" 
 Case 6 
 ConnectOutput dbsTemp, _ 
 "LotusTable", _ 
 "Lotus WK3;" & _ 
 "DATABASE=C:\Lotus\Samples\Sales.xls", _ 
 "THIRDQTR" 
 Case 7 
 ConnectOutput dbsTemp, _ 
 "CSVTable", _ 
 "Text;DATABASE=C:\Samples", _ 
 "Sample.txt" 
 Case 8 
 ConnectOutput dbsTemp, _ 
 "HTMLTable", _ 
 "HTML Import;DATABASE=https://" & _ 
 "www.server1.com/samples/page1.html", _ 
 "Q1SalesData" 
 Case 9 
 ConnectOutput dbsTemp, _ 
 "ExchangeTable", _ 
 "Exchange 4.0;MAPILEVEL=" & _ 
 "Mailbox - Michelle Wortman (Exchange)" & _ 
 "|People\Important;", _ 
 "Jerry Wheeler" 
 End Select 
 
 dbsTemp.Close 
 
End Sub 
 
Sub ConnectOutput(dbsTemp As Database, _ 
 strTable As String, strConnect As String, _ 
 strSourceTable As String) 
 
 Dim tdfLinked As TableDef 
 Dim rstLinked As Recordset 
 Dim intTemp As Integer 
 
 ' Create a new TableDef, set its Connect and 
 ' SourceTableName properties based on the passed 
 ' arguments, and append it to the TableDefs collection. 
 Set tdfLinked = dbsTemp.CreateTableDef(strTable) 
 
 tdfLinked.Connect = strConnect 
 tdfLinked.SourceTableName = strSourceTable 
 dbsTemp.TableDefs.Append tdfLinked 
 
 Set rstLinked = dbsTemp.OpenRecordset(strTable) 
 
 Debug.Print "Data from linked table:" 
 
 ' Display the first three records of the linked table. 
 intTemp = 1 
 With rstLinked 
 Do While Not .EOF And intTemp <= 3 
 Debug.Print , .Fields(0), .Fields(1) 
 intTemp = intTemp + 1 
 .MoveNext 
 Loop 
 If Not .EOF Then Debug.Print , "[additional records]" 
 .Close 
 End With 
 
 ' Delete the linked table because this is a demonstration. 
 dbsTemp.TableDefs.Delete strTable 
 
End Sub 
 
```
