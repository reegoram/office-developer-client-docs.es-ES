---
title: Fields Collection (DAO)
TOCTitle: Fields Collection
ms:assetid: 4be3ba07-20c1-d958-c1b8-7dd8b4731f60
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193530(v=office.15)
ms:contentKeyID: 48544702
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9eb7d0b53e4e4058a178d7c3ad0f367f40bbe595
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486245"
---
# <a name="fields-collection-dao"></a><span data-ttu-id="ff477-102">Fields Collection (DAO)</span><span class="sxs-lookup"><span data-stu-id="ff477-102">Fields Collection (DAO)</span></span>


<span data-ttu-id="ff477-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="ff477-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="ff477-104">Una colección **Fields** contiene todos los objetos **Field** almacenados de un objeto **Index**, **QueryDef**, **Recordset**, **Relation** o **TableDef**.</span><span class="sxs-lookup"><span data-stu-id="ff477-104">A **Fields** collection contains all stored **Field** objects of an **Index**, **QueryDef**, **Recordset**, **Relation**, or **TableDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff477-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ff477-105">Remarks</span></span>

<span data-ttu-id="ff477-p101">Las colecciones **Fields** de los objetos **Index**, **QueryDef**, **Relation** y **TableDef** contienen las especificaciones para los campos que estos objetos representan. La colección **Fields** de un objeto **Recordset** representa los objetos **Field** de una fila de datos o de un registro. Use los objetos **Field** de un objeto **Recordset** para leer y establecer valores para los campos en el registro actual del objeto **Recordset**.</span><span class="sxs-lookup"><span data-stu-id="ff477-p101">The **Fields** collections of the **Index**, **QueryDef**, **Relation**, and **TableDef** objects contain the specifications for the fields those objects represent. The **Fields** collection of a **Recordset** object represents the **Field** objects in a row of data, or in a record. You use the **Field** objects in a **Recordset** object to read and to set values for the fields in the current record of the **Recordset** object.</span></span>

<span data-ttu-id="ff477-109">Para hacer referencia a un objeto **Field** de una colección mediante su número ordinal o mediante el valor de la propiedad **Name**, utilice una de las formas sintácticas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff477-109">To refer to a **Field** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

<span data-ttu-id="ff477-110">**Fields**(0)</span><span class="sxs-lookup"><span data-stu-id="ff477-110">**Fields**(0)</span></span>

<span data-ttu-id="ff477-111">**Campos** ("nombre")</span><span class="sxs-lookup"><span data-stu-id="ff477-111">**Fields**("name")</span></span>

<span data-ttu-id="ff477-112">**Campos**\!\[nombre\]</span><span class="sxs-lookup"><span data-stu-id="ff477-112">**Fields**\!\[name\]</span></span>

<span data-ttu-id="ff477-p102">Con las mismas formas sintácticas, puede hacer referencia igualmente a la propiedad **Value** de un objeto **Field** que crea y anexa a la colección **Fields**. El contexto de la referencia del campo determinará si hace referencia al objeto **Field** o a la propiedad **Value** del objeto **Field**.</span><span class="sxs-lookup"><span data-stu-id="ff477-p102">With the same syntax forms, you can also refer to the **Value** property of a **Field** object that you create and append to a **Fields** collection. The context of the field reference will determine whether you are referring to the **Field** object or the **Value** property of the **Field** object.</span></span>

## <a name="example"></a><span data-ttu-id="ff477-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ff477-115">Example</span></span>

<span data-ttu-id="ff477-p103">En este ejemplo se muestra qué propiedades son válidas para un objeto **Field** según dónde resida el objeto **Field** (por ejemplo, la colección **Fields** de un objeto **TableDef**, la colección **Fields** de un objeto **QueryDef**, etc.). Se requiere el procedimiento FieldOutput para que pueda ejecutarse este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ff477-p103">This example shows what properties are valid for a **Field** object depending on where the **Field** resides (for example, the **Fields** collection of a **TableDef**, the **Fields** collection of a **QueryDef**, and so forth). The FieldOutput procedure is required for this procedure to run.</span></span>

```vb
    Sub FieldX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     Dim fldTableDef As Field 
     Dim fldQueryDef As Field 
     Dim fldRecordset As Field 
     Dim fldRelation As Field 
     Dim fldIndex As Field 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees") 
     
     ' Assign a Field object from different Fields 
     ' collections to object variables. 
     Set fldTableDef = _ 
     dbsNorthwind.TableDefs(0).Fields(0) 
     Set fldQueryDef =dbsNorthwind.QueryDefs(0).Fields(0) 
     Set fldRecordset = rstEmployees.Fields(0) 
     Set fldRelation =dbsNorthwind.Relations(0).Fields(0) 
     Set fldIndex = _ 
     dbsNorthwind.TableDefs(0).Indexes(0).Fields(0) 
     
     ' Print report. 
     FieldOutput "TableDef", fldTableDef 
     FieldOutput "QueryDef", fldQueryDef 
     FieldOutput "Recordset", fldRecordset 
     FieldOutput "Relation", fldRelation 
     FieldOutput "Index", fldIndex 
     
     rstEmployees.Close 
     dbsNorthwind.Close 
     
    End Sub 
     
    Sub FieldOutput(strTemp As String, fldTemp As Field) 
     ' Report function for FieldX. 
     
     Dim prpLoop As Property 
     
     Debug.Print "Valid Field properties in " & strTemp 
     
     ' Enumerate Properties collection of passed Field 
     ' object. 
     For Each prpLoop In fldTemp.Properties 
     ' Some properties are invalid in certain 
     ' contexts (the Value property in the Fields 
     ' collection of a TableDef for example). Any 
     ' attempt to use an invalid property will 
     ' trigger an error. 
     On Error Resume Next 
     Debug.Print " " & prpLoop.Name & " = " & _ 
     prpLoop.Value 
     On Error GoTo 0 
     Next prpLoop 
     
    End Sub 
```

<br/>

<span data-ttu-id="ff477-p104">En este ejemplo se utiliza el método **CreateField** para crear tres **Fields** para un nuevo objeto **TableDef**. A continuación, se muestran las propiedades de estos objetos **Field** que se establecen automáticamente mediante el método **CreateField**. (No aparecen las propiedades cuyos valores están vacíos en el momento de crear **Field**.)</span><span class="sxs-lookup"><span data-stu-id="ff477-p104">This example uses the **CreateField** method to create three **Fields** for a new **TableDef**. It then displays the properties of those **Field** objects that are automatically set by the **CreateField** method. (Properties whose values are empty at the time of **Field** creation are not shown.)</span></span>

```vb
    Sub CreateFieldX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfNew As TableDef 
     Dim fldLoop As Field 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     Set tdfNew = dbsNorthwind.CreateTableDef("NewTableDef") 
     
     ' Create and append new Field objects for the new 
     ' TableDef object. 
     With tdfNew 
     ' The CreateField method will set a default Size 
     ' for a new Field object if one is not specified. 
     .Fields.Append .CreateField("TextField", dbText) 
     .Fields.Append .CreateField("IntegerField", dbInteger) 
     .Fields.Append .CreateField("DateField", dbDate) 
     End With 
     
     dbsNorthwind.TableDefs.Append tdfNew 
     
     Debug.Print "Properties of new Fields in " & tdfNew.Name 
     
     ' Enumerate Fields collection to show the properties of 
     ' the new Field objects. 
     For Each fldLoop In tdfNew.Fields 
     Debug.Print " " & fldLoop.Name 
     
     For Each prpLoop In fldLoop.Properties 
     ' Properties that are invalid in the context of 
     ' TableDefs will trigger an error if an attempt 
     ' is made to read their values. 
     On Error Resume Next 
     Debug.Print " " & prpLoop.Name & " - " & _ 
     IIf(prpLoop = "", "[empty]", prpLoop) 
     On Error GoTo 0 
     Next prpLoop 
     
     Next fldLoop 
     
     ' Delete new TableDef because this is a demonstration. 
     dbsNorthwind.TableDefs.Delete tdfNew.Name 
     dbsNorthwind.Close 
     
    End Sub
```