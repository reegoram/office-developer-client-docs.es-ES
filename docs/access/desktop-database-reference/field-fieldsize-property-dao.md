---
title: Field.FieldSize Property (DAO)
TOCTitle: FieldSize Property
ms:assetid: c81bd5cb-6b7c-5390-2d6b-049143f2f3b6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823165(v=office.15)
ms:contentKeyID: 48547645
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4de733dd88be212779d3ab9d9b562d4741492a87
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486166"
---
# <a name="fieldfieldsize-property-dao"></a><span data-ttu-id="ae6c8-102">Field.FieldSize Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="ae6c8-102">Field.FieldSize Property (DAO)</span></span>


<span data-ttu-id="ae6c8-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="ae6c8-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="ae6c8-104">Devuelve el número de bytes usados en la base de datos (en lugar de en la memoria) de un objeto Memo o Long Binary **[Field](field-object-dao.md)** en la colección **[Fields](fields-collection-dao.md)** de un objeto **[Recordset](recordset-object-dao.md)**.</span><span class="sxs-lookup"><span data-stu-id="ae6c8-104">Returns the number of bytes used in the database (rather than in memory) of a Memo or Long Binary **[Field](field-object-dao.md)** object in the **[Fields](fields-collection-dao.md)** collection of a **[Recordset](recordset-object-dao.md)** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="ae6c8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae6c8-105">Syntax</span></span>

<span data-ttu-id="ae6c8-106">*expresión* . TamañoDelCampo</span><span class="sxs-lookup"><span data-stu-id="ae6c8-106">*expression* .FieldSize</span></span>

<span data-ttu-id="ae6c8-107">*expresión* Variable que representa un objeto **Field** .</span><span class="sxs-lookup"><span data-stu-id="ae6c8-107">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="ae6c8-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ae6c8-108">Remarks</span></span>

<span data-ttu-id="ae6c8-109">Puede utilizar **FieldSize** con los métodos **[AppendChunk](field-appendchunk-method-dao.md)** y **[GetChunk](field-getchunk-method-dao.md)** para manipular campos grandes.</span><span class="sxs-lookup"><span data-stu-id="ae6c8-109">You can use **FieldSize** with the **[AppendChunk](field-appendchunk-method-dao.md)** and **[GetChunk](field-getchunk-method-dao.md)** methods to manipulate large fields.</span></span>

<span data-ttu-id="ae6c8-110">Como el tamaño de un campo Long Binary o Memo puede ser mayor de 64K, debería asignar el valor que devuelve **FieldSize** a una variable lo suficientemente grande como para almacenar una variable **Long**.</span><span class="sxs-lookup"><span data-stu-id="ae6c8-110">Because the size of a Long Binary or Memo field can exceed 64K, you should assign the value returned by **FieldSize** to a variable large enough to store a **Long** variable.</span></span>

<span data-ttu-id="ae6c8-111">Para determinar el tamaño de un objeto **Field** distinto de los tipos Memo y Long Binary, utilice la propiedad **[Size](field-size-property-dao.md)**.</span><span class="sxs-lookup"><span data-stu-id="ae6c8-111">To determine the size of a **Field** object other than Memo and Long Binary types, use the **[Size](field-size-property-dao.md)** property.</span></span>

  - <span data-ttu-id="ae6c8-112">Si el servidor de base de datos o el controlador ODBC no admiten cursores de servidor.</span><span class="sxs-lookup"><span data-stu-id="ae6c8-112">If the database server or ODBC driver does not support server-side cursors.</span></span>

  - <span data-ttu-id="ae6c8-113">Si está utilizando la biblioteca de cursores ODBC (es decir, la propiedad **DefaultCursorDriver** está establecida en **dbUseODBC** o en **dbUseDefault** cuando el servidor no admite cursores de servidor).</span><span class="sxs-lookup"><span data-stu-id="ae6c8-113">If you are using the ODBC cursor library (that is, the **DefaultCursorDriver** property is set to **dbUseODBC**, or to **dbUseDefault** when the server does not support server-side cursors).</span></span>

  - <span data-ttu-id="ae6c8-114">Si está utilizando una consulta sin cursor (es decir, la propiedad **DefaultCursorDriver** está establecida en **dbUseNoCursor**).</span><span class="sxs-lookup"><span data-stu-id="ae6c8-114">If you are using a cursorless query (that is, the **DefaultCursorDriver** property is set to **dbUseNoCursor**).</span></span>

<span data-ttu-id="ae6c8-p101">La propiedad **FieldSize** y las funciones VBA **Len()** o **LenB()** pueden devolver valores distintos como longitud de una misma cadena. Las cadenas se almacenan en una base de datos de Microsoft Access con formato de juego de caracteres de varios bytes (MBCS), pero expuesta a través de VBA con formato Unicode. Como resultado, la función **Len()** siempre devolverá el número de caracteres, **LenB** siempre devolverá el número de caracteres X 2 (Unicode utiliza dos bytes por cada carácter), pero **FieldSize** devolverá algún valor intermedio si la cadena contiene cualquiera de los caracteres MBCS. Por ejemplo, en una cadena que consta de tres caracteres normales y dos caracteres MBCS, **Len()** devolverá 5, **LenB()** devolverá 10 y **FieldSize** devolverá 7, la suma de 1 por cada carácter normal y 2 por cada carácter MBCS.</span><span class="sxs-lookup"><span data-stu-id="ae6c8-p101">The **FieldSize** property and the VBA **Len()** or **LenB()** functions may return different values as the length of the same string. Strings are stored in a Microsoft Access database in multi-byte character set (MBCS) form, but exposed through VBA in Unicode format. As a result, the **Len()** function will always return the number of characters, **LenB** will always return the number of characters X 2 (Unicode uses two bytes for each character), but **FieldSize** will return some value in between if the string has any MBCS characters. For example, given a string consisting of three normal characters and two MBCS characters, **Len()** will return 5, **LenB()** will return 10, and **FieldSize** will return 7, the sum of 1 for each normal character and 2 for each MBCS character.</span></span>

## <a name="example"></a><span data-ttu-id="ae6c8-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae6c8-119">Example</span></span>

<span data-ttu-id="ae6c8-120">En este ejemplo se utiliza la propiedad **FieldSize** para enumerar el número de bytes utilizados en los objetos Memo y Long Binary Field en dos tablas distintas.</span><span class="sxs-lookup"><span data-stu-id="ae6c8-120">This example uses the **FieldSize** property to list the number of bytes used by the Memo and Long Binary Field objects in two different tables.</span></span>

```vb
    Sub FieldSizeX() 
     
     Dim dbsNorthwind As Database 
     Dim rstCategories As Recordset 
     Dim rstEmployees As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstCategories = _ 
     dbsNorthwind.OpenRecordset("Categories", _ 
     dbOpenDynaset) 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     
     Debug.Print _ 
     "Field sizes from records in Categories table" 
     
     With rstCategories 
     Debug.Print " CategoryName - " & _ 
     "Description (bytes) - Picture (bytes)" 
     
     ' Enumerate the Categories Recordset and print the size 
     ' in bytes of the picture field for each record. 
     Do While Not .EOF 
     Debug.Print " " & !CategoryName & " - " & _ 
     !Description.FieldSize & " - " & _ 
     !Picture.FieldSize 
     .MoveNext 
     Loop 
     
     .Close 
     End With 
     
     Debug.Print "Field sizes from records in Employees table" 
     
     With rstEmployees 
     Debug.Print " LastName - Notes (bytes) - " & _ 
     "Photo (bytes)" 
     
     ' Enumerate the Employees Recordset and print the size 
     ' in bytes of the picture field for each record. 
     Do While Not .EOF 
     Debug.Print " " & !LastName & " - " & _ 
     !Notes.FieldSize & " - " & !Photo.FieldSize 
     .MoveNext 
     Loop 
     
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="ae6c8-p102">En este ejemplo se utilizan los métodos **AppendChunk** y **GetChunk** para rellenar un campo de objeto OLE con datos de otro registro, 32 K cada vez. En una aplicación real, se podría utilizar un procedimiento como éste para copiar un registro de empleado (incluida la foto del mismo) de una tabla a otra. En este ejemplo, el registro simplemente se vuelve a copiar en la misma tabla. Tenga en cuenta que todas las operaciones con fragmentos de campo se producen dentro de una sola secuencia AddNew-Update.</span><span class="sxs-lookup"><span data-stu-id="ae6c8-p102">This example uses the **AppendChunk** and **GetChunk** methods to fill an OLE object field with data from another record, 32K at a time. In a real application, one might use a procedure like this to copy an employee record (including the employee's photo) from one table to another. In this example, the record is simply being copied back to same table. Note that all the chunk manipulation takes place within a single AddNew-Update sequence.</span></span>

```vb
    Sub AppendChunkX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     Dim rstEmployees2 As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     ' Open two recordsets from the Employees table. 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     Set rstEmployees2 = rstEmployees.Clone 
     
     ' Add a new record to the first Recordset and copy the 
     ' data from a record in the second Recordset. 
     With rstEmployees 
     .AddNew 
     !FirstName = rstEmployees2!FirstName 
     !LastName = rstEmployees2!LastName 
     CopyLargeField rstEmployees2!Photo, !Photo 
     .Update 
     
     ' Delete new record because this is a demonstration. 
     .Bookmark = .LastModified 
     .Delete 
     .Close 
     End With 
     
     rstEmployees2.Close 
     dbsNorthwind.Close 
     
    End Sub 
     
    Function CopyLargeField(fldSource As Field, _ 
     fldDestination As Field) 
     
     ' Set size of chunk in bytes. 
     Const conChunkSize = 32768 
     
     Dim lngOffset As Long 
     Dim lngTotalSize As Long 
     Dim strChunk As String 
     
     ' Copy the photo from one Recordset to the other in 32K 
     ' chunks until the entire field is copied. 
     lngTotalSize = fldSource.FieldSize 
     Do While lngOffset < lngTotalSize 
     strChunk = fldSource.GetChunk(lngOffset, conChunkSize) 
     fldDestination.AppendChunk strChunk 
     lngOffset = lngOffset + conChunkSize 
     Loop 
     
    End Function
```