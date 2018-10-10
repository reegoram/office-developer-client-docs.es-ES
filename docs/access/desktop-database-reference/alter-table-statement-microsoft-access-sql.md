---
title: Instrucción ALTER TABLE (Microsoft Access SQL)
TOCTitle: ALTER TABLE Statement (Microsoft Access SQL)
ms:assetid: 78e6c92c-e88c-e55f-6b89-435360c166a6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196148(v=office.15)
ms:contentKeyID: 48545763
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277560
dev_langs:
- sql
f1_categories:
- Office.Version=v15
ms.openlocfilehash: b8fc826d438973b4d079e9b90d3663ab755821cc
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486312"
---
# <a name="alter-table-statement-microsoft-access-sql"></a><span data-ttu-id="112e4-102">Instrucción ALTER TABLE (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="112e4-102">ALTER TABLE Statement (Microsoft Access SQL)</span></span>


<span data-ttu-id="112e4-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="112e4-103">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="112e4-104">Modifica el diseño de una tabla después de que se ha creado con la instrucción [CREATE TABLE](create-table-statement-microsoft-access-sql.md).</span><span class="sxs-lookup"><span data-stu-id="112e4-104">Modifies the design of a table after it has been created with the [CREATE TABLE](create-table-statement-microsoft-access-sql.md) statement.</span></span>


> [!NOTE]
> <span data-ttu-id="112e4-p101">[!NOTA] El motor de base de datos de Microsoft Access no admite el uso de ALTER TABLE, ni las instrucciones de lenguaje de definición de datos (DDL), con bases de datos que no sean de Microsoft Access. En su lugar, use los métodos Create de DAO.</span><span class="sxs-lookup"><span data-stu-id="112e4-p101">The Microsoft Access database engine does not support the use of ALTER TABLE, or any of the data definition language (DDL) statements, with non-Microsoft Access databases. Use the DAO Create methods instead.</span></span>



## <a name="syntax"></a><span data-ttu-id="112e4-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="112e4-107">Syntax</span></span>

<span data-ttu-id="112e4-108">ALTER TABLE *tabla* {agregar {el *tipo de campo*de columna\[(*tamaño*)\] \[NOT NULL\] \[CONSTRAINT *índice* \] | ALTER COLUMN *tipo de campo*\[(*tamaño*)\] | CONSTRAINT *índicedevarioscampos*} | DROP {COLUMN *campo* I CONSTRAINT *nombreDeÍndice*}}</span><span class="sxs-lookup"><span data-stu-id="112e4-108">ALTER TABLE *table* {ADD {COLUMN *field type*\[(*size*)\] \[NOT NULL\] \[CONSTRAINT *index*\] | ALTER COLUMN *field type*\[(*size*)\] | CONSTRAINT *multifieldindex*} | DROP {COLUMN *field* I CONSTRAINT *indexname*} }</span></span>

<span data-ttu-id="112e4-109">La instrucción ALTER TABLE consta de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="112e4-109">The ALTER TABLE statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="112e4-110">Parte</span><span class="sxs-lookup"><span data-stu-id="112e4-110">Part</span></span></p></th>
<th><p><span data-ttu-id="112e4-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="112e4-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="112e4-112"><em>tabla</em></span><span class="sxs-lookup"><span data-stu-id="112e4-112"><em>table</em></span></span></p></td>
<td><p><span data-ttu-id="112e4-113">Nombre de la tabla que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="112e4-113">The name of the table to be altered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="112e4-114"><em>campo</em></span><span class="sxs-lookup"><span data-stu-id="112e4-114"><em>field</em></span></span></p></td>
<td><p><span data-ttu-id="112e4-p102">Nombre del campo que se va a agregar o eliminar en la <em>tabla</em>. O bien, nombre del campo que se va a modificar en la <em>tabla</em>.</span><span class="sxs-lookup"><span data-stu-id="112e4-p102">The name of the field to be added to or deleted from <em>table</em>. Or, the name of the field to be altered in <em>table</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="112e4-117"><em>type</em></span><span class="sxs-lookup"><span data-stu-id="112e4-117"><em>type</em></span></span></p></td>
<td><p><span data-ttu-id="112e4-118">Tipo de datos del <em>campo</em>.</span><span class="sxs-lookup"><span data-stu-id="112e4-118">The data type of <em>field</em>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="112e4-119"><em>size</em></span><span class="sxs-lookup"><span data-stu-id="112e4-119"><em>size</em></span></span></p></td>
<td><p><span data-ttu-id="112e4-120">Tamaño del campo en caracteres (sólo los campos de tipo texto y binario).</span><span class="sxs-lookup"><span data-stu-id="112e4-120">The field size in characters (Text and Binary fields only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="112e4-121"><em>índice</em></span><span class="sxs-lookup"><span data-stu-id="112e4-121"><em>index</em></span></span></p></td>
<td><p><span data-ttu-id="112e4-p103">Índice del <em>campo</em>. Para obtener más información acerca de cómo construir este índice, vea la <a href="constraint-clause-microsoft-access-sql.md">Cláusula CONSTRAINT</a>.</span><span class="sxs-lookup"><span data-stu-id="112e4-p103">The index for <em>field</em>. For more information on how to construct this index see <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT Clause</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="112e4-124"><em>índiceDeVariosCampos</em></span><span class="sxs-lookup"><span data-stu-id="112e4-124"><em>multifieldindex</em></span></span></p></td>
<td><p><span data-ttu-id="112e4-p104">Definición de un índice de varios campos que se agregará a la <em>tabla</em>. Para obtener más información acerca de cómo construir este índice, vea la <a href="constraint-clause-microsoft-access-sql.md">Cláusula CONSTRAINT</a>.</span><span class="sxs-lookup"><span data-stu-id="112e4-p104">The definition of a multiple-field index to be added to <em>table</em>. For more information on how to construct this index see <a href="constraint-clause-microsoft-access-sql.md">CONSTRAINT Clause</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="112e4-127"><em>nombreDeÍndice</em></span><span class="sxs-lookup"><span data-stu-id="112e4-127"><em>indexname</em></span></span></p></td>
<td><p><span data-ttu-id="112e4-128">Nombre del índice de varios campos que se eliminará.</span><span class="sxs-lookup"><span data-stu-id="112e4-128">The name of the multiple-field index to be removed.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="112e4-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="112e4-129">Remarks</span></span>

<span data-ttu-id="112e4-p105">Mediante la instrucción ALTER TABLE se puede modificar una tabla existente de varias formas. Se puede:</span><span class="sxs-lookup"><span data-stu-id="112e4-p105">Using the ALTER TABLE statement you can alter an existing table in several ways. You can:</span></span>

  - <span data-ttu-id="112e4-p106">Usar ADD COLUMN para agregar un campo nuevo a la tabla. Debe especificar el nombre del campo, el tipo de datos y (para los campos de tipo texto y binario) un tamaño opcional. Por ejemplo, la siguiente instrucción agrega un campo de texto de 25 caracteres llamado Notes a la tabla Employees:</span><span class="sxs-lookup"><span data-stu-id="112e4-p106">Use ADD COLUMN to add a new field to the table. You specify the field name, data type, and (for Text and Binary fields) an optional size. For example, the following statement adds a 25-character Text field called Notes to the Employees table:</span></span>
    
    ```sql
    ALTER TABLE Employees ADD COLUMN Notes TEXT(25)
    ```
    
    <span data-ttu-id="112e4-p107">También puede definir un índice en ese campo. Para obtener más información sobre los índices de un solo campo, consulte [Cláusula CONSTRAINT](constraint-clause-microsoft-access-sql.md).</span><span class="sxs-lookup"><span data-stu-id="112e4-p107">You can also define an index on that field. For more information on single-field indexes see [CONSTRAINT Clause](constraint-clause-microsoft-access-sql.md).</span></span>
    
    <span data-ttu-id="112e4-137">Si especifica NOT NULL en un campo, será obligatorio que los nuevos registros tengan datos válidos en ese campo.</span><span class="sxs-lookup"><span data-stu-id="112e4-137">If you specify NOT NULL for a field then new records are required to have valid data in that field.</span></span>

  - <span data-ttu-id="112e4-p108">Usar ALTER COLUMN para cambiar el tipo de datos de un campo existente. Debe especificar el nombre del campo, el nuevo tipo de datos y un tamaño opcional para los campos de tipo texto y binario. Por ejemplo, la siguiente instrucción cambia el tipo de datos de un campo de la tabla Employees llamado ZipCode (definido originalmente como Integer) a un campo Texto de 10 caracteres:</span><span class="sxs-lookup"><span data-stu-id="112e4-p108">Use ALTER COLUMN to change the data type of an existing field. You specify the field name, the new data type, and an optional size for Text and Binary fields. For example, the following statement changes the data type of a field in the Employees table called ZipCode (originally defined as Integer) to a 10-character Text field:</span></span>
    
    ```sql
    ALTER TABLE Employees ALTER COLUMN ZipCode TEXT(10)
    ```

  - <span data-ttu-id="112e4-p109">Usar ADD CONSTRAINT para agregar un índice de varios campos. Para obtener más información acerca de los índices de varios campos, vea la [Cláusula CONSTRAINT](constraint-clause-microsoft-access-sql.md).</span><span class="sxs-lookup"><span data-stu-id="112e4-p109">Use ADD CONSTRAINT to add a multiple-field index. For more information on multiple-field indexes see [CONSTRAINT Clause](constraint-clause-microsoft-access-sql.md).</span></span>

  - <span data-ttu-id="112e4-p110">Usar DROP COLUMN para eliminar un campo. Sólo debe especificar el nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="112e4-p110">Use DROP COLUMN to delete a field. You specify only the name of the field.</span></span>

  - <span data-ttu-id="112e4-p111">Usar DROP CONSTRAINT para eliminar un índice de varios campos. Sólo debe especificar el nombre del índice a continuación de la palabra reservada CONSTRAINT.</span><span class="sxs-lookup"><span data-stu-id="112e4-p111">Use DROP CONSTRAINT to delete a multiple-field index. You specify only the index name following the CONSTRAINT reserved word.</span></span>


> [!NOTE]
> <UL>
> <LI>
> <P><span data-ttu-id="112e4-147">[!NOTA] No se puede agregar o eliminar más de un campo o índice a la vez.</span><span class="sxs-lookup"><span data-stu-id="112e4-147">You cannot add or delete more than one field or index at a time.</span></span></P>
> <LI>
> <P><span data-ttu-id="112e4-148">Puede usar la instrucción <A href="create-index-statement-microsoft-access-sql.md">CREATE INDEX</A> para agregar un índice de un solo campo o de varios campos a un tabla y puede usar ALTER TABLE o la instrucción <A href="drop-statement-microsoft-access-sql.md">DROP</A> para eliminar un índice creado con ALTER TABLE o CREATE INDEX.</span><span class="sxs-lookup"><span data-stu-id="112e4-148">You can use the <A href="create-index-statement-microsoft-access-sql.md">CREATE INDEX</A> statement to add a single- or multiple-field index to a table, and you can use ALTER TABLE or the <A href="drop-statement-microsoft-access-sql.md">DROP</A> statement to delete an index created with ALTER TABLE or CREATE INDEX.</span></span></P>
> <LI>
> <P><span data-ttu-id="112e4-p112">No puede usar NOT NULL en un campo único o en una cláusula CONSTRAINT con nombre que se aplique a un solo campo o a una cláusula CONSTRAINT con nombre de varios campos. Sin embargo, puede aplicar la restricción NOT NULL sólo una vez a un campo. Si intenta aplicar esta restricción más de una vez, se producirá un error en tiempo de ejecución. 
</span><span class="sxs-lookup"><span data-stu-id="112e4-p112">You can use NOT NULL on a single field or within a named CONSTRAINT clause that applies to either a single field or to a multiple-field named CONSTRAINT. However, you can apply the NOT NULL restriction only once to a field. Attempting to apply this restriction more than once restuls in a run-time error.</span></span></P></LI></UL>



## <a name="example"></a><span data-ttu-id="112e4-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="112e4-152">Example</span></span>

<span data-ttu-id="112e4-153">En este ejemplo, se agrega un campo Salary con el tipo de datos **Money** a la tabla Employees.</span><span class="sxs-lookup"><span data-stu-id="112e4-153">This example adds a Salary field with the data type **Money** to the Employees table.</span></span>

```vb
    Sub AlterTableX1() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Add the Salary field to the Employees table  
        ' and make it a Money data type. 
        dbs.Execute "ALTER TABLE Employees " _ 
            & "ADD COLUMN Salary MONEY;" 
     
        dbs.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="112e4-154">En este ejemplo, se cambia el tipo de datos del campo Salary de **Money** a **Char**.</span><span class="sxs-lookup"><span data-stu-id="112e4-154">This example changes the Salary field from the data type **Money** to the data type **Char**.</span></span>

```vb
    Sub AlterTableX2() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Add the Salary field to the Employees table  
        ' and make it a Money data type. 
        dbs.Execute "ALTER TABLE Employees " _ 
            & "ALTER COLUMN Salary CHAR(20);" 
     
        dbs.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="112e4-155">En este ejemplo, se quita el campo Salary de la tabla Employees.</span><span class="sxs-lookup"><span data-stu-id="112e4-155">This example removes the Salary field from the Employees table.</span></span>

```vb
    Sub AlterTableX3() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Delete the Salary field from the Employees table. 
        dbs.Execute "ALTER TABLE Employees " _ 
            & "DROP COLUMN Salary;" 
     
        dbs.Close 
     
    End Sub
```

<br/>

<span data-ttu-id="112e4-p113">En este ejemplo, se agrega una clave externa a la tabla Orders. La clave externa se basa en el campo EmployeeID y hace referencia al campo EmployeeID de la tabla Employees. En este ejemplo, no tiene que enumerar el campo EmployeeID después de la tabla Employees en la cláusula REFERENCES porque EmployeeID es la clave principal de la tabla Employees.</span><span class="sxs-lookup"><span data-stu-id="112e4-p113">This example adds a foreign key to the Orders table. The foreign key is based on the EmployeeID field and refers to the EmployeeID field of the Employees table. In this example, you do not have to list the EmployeeID field after the Employees table in the REFERENCES clause because EmployeeID is the primary key of the Employees table.</span></span>

```vb
    Sub AlterTableX4() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Add a foreign key to the Orders table. 
        dbs.Execute "ALTER TABLE Orders " _ 
            & "ADD CONSTRAINT OrdersRelationship " _ 
            & "FOREIGN KEY (EmployeeID) " _ 
            & "REFERENCES Employees (EmployeeID);" 
     
        dbs.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="112e4-159">En este ejemplo, se elimina la clave externa de la tabla Orders.</span><span class="sxs-lookup"><span data-stu-id="112e4-159">This example removes the foreign key from the Orders table.</span></span>

```vb
    Sub AlterTableX5() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Remove the OrdersRelationship foreign key from 
        ' the Orders table. 
        dbs.Execute "ALTER TABLE Orders " _ 
            & "DROP CONSTRAINT OrdersRelationship;" 
     
        dbs.Close 
     
    End Sub
```