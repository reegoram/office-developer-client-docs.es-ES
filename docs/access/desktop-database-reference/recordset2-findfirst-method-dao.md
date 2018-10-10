---
title: Recordset2.FindFirst Method (DAO)
TOCTitle: FindFirst Method
ms:assetid: 2a18e81a-a9e5-cc1a-50b2-40c1f1b7fa06
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192064(v=office.15)
ms:contentKeyID: 48543902
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 97c72b017c3ebe0216f10d7395abe37c4d8f7392
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486471"
---
# <a name="recordset2findfirst-method-dao"></a><span data-ttu-id="383fe-102">Recordset2.FindFirst Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="383fe-102">Recordset2.FindFirst Method (DAO)</span></span>


<span data-ttu-id="383fe-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="383fe-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="383fe-104">Busca el primer registro de un objeto **Recordset** de tipo Dynaset o instantánea que satisfaga los criterios especificados y convierte el registro en el registro actual (solo en áreas de trabajo de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="383fe-104">Locates the first record in a dynaset- or snapshot-type **Recordset** object that satisfies the specified criteria and makes that record the current record (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="383fe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="383fe-105">Syntax</span></span>

<span data-ttu-id="383fe-106">*expresión* . FindFirst (***criterios***)</span><span class="sxs-lookup"><span data-stu-id="383fe-106">*expression* .FindFirst(***Criteria***)</span></span>

<span data-ttu-id="383fe-107">*expresión* Variable que representa un objeto **Recordset2** .</span><span class="sxs-lookup"><span data-stu-id="383fe-107">*expression* A variable that represents a **Recordset2** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="383fe-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="383fe-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="383fe-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="383fe-109">Name</span></span></p></th>
<th><p><span data-ttu-id="383fe-110">Necesario/Opcional</span><span class="sxs-lookup"><span data-stu-id="383fe-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="383fe-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="383fe-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="383fe-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="383fe-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="383fe-113">Criterios</span><span class="sxs-lookup"><span data-stu-id="383fe-113">Criteria</span></span></p></td>
<td><p><span data-ttu-id="383fe-114">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="383fe-114">Required</span></span></p></td>
<td><p><span data-ttu-id="383fe-115"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="383fe-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="383fe-p101">Cadena que se utiliza para localizar el registro. Es como una cláusula WHERE en una instrucción SQL pero sin la palabra WHERE.</span><span class="sxs-lookup"><span data-stu-id="383fe-p101">A String used to locate the record. It is like the WHERE clause in an SQL statement, but without the word WHERE.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="383fe-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="383fe-118">Remarks</span></span>

<span data-ttu-id="383fe-p102">Si quiere incluir en la búsqueda todos los registros, y no solo los que cumplan una condición determinada, use los métodos **Move** para moverse de un registro a otro. Para buscar un registro en un **Recordset** de tipo tabla, use el método **Seek**.</span><span class="sxs-lookup"><span data-stu-id="383fe-p102">If you want to include all the records in your search — not just those that meet a specific condition — use the **Move** methods to move from record to record. To locate a record in a table-type **Recordset**, use the **Seek** method.</span></span>

<span data-ttu-id="383fe-p103">Si no se encuentra ningún registro que coincida con los criterios, el puntero del registro actual será desconocido y la propiedad **NoMatch** se configurará como **True**. Si el conjunto de registros contiene varios registros que cumplen los criterios, **FindFirst** buscará el primero, **FindNext** buscará el segundo y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="383fe-p103">If a record matching the criteria isn't located, the current record pointer is unknown, and the **NoMatch** property is set to **True**. If recordset contains more than one record that satisfies the criteria, **FindFirst** locates the first occurrence, **FindNext** locates the next occurrence, and so on.</span></span>

<span data-ttu-id="383fe-123">Cada método **Find** empieza a buscar a partir de la ubicación y en la dirección que se especifican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="383fe-123">Each of the **Find** methods begins its search from the location and in the direction specified in the following table.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="383fe-124">Método Find</span><span class="sxs-lookup"><span data-stu-id="383fe-124">Find method</span></span></p></th>
<th><p><span data-ttu-id="383fe-125">Empieza la búsqueda en</span><span class="sxs-lookup"><span data-stu-id="383fe-125">Begins searching at</span></span></p></th>
<th><p><span data-ttu-id="383fe-126">Dirección de búsqueda</span><span class="sxs-lookup"><span data-stu-id="383fe-126">Search direction</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="383fe-127"><strong>FindFirst</strong></span><span class="sxs-lookup"><span data-stu-id="383fe-127"><strong>FindFirst</strong></span></span></p></td>
<td><p><span data-ttu-id="383fe-128">Principio del conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="383fe-128">Beginning of recordset</span></span></p></td>
<td><p><span data-ttu-id="383fe-129">Final del conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="383fe-129">End of recordset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="383fe-130"><strong>FindLast</strong></span><span class="sxs-lookup"><span data-stu-id="383fe-130"><strong>FindLast</strong></span></span></p></td>
<td><p><span data-ttu-id="383fe-131">Final del conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="383fe-131">End of recordset</span></span></p></td>
<td><p><span data-ttu-id="383fe-132">Principio del conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="383fe-132">Beginning of recordset</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="383fe-133"><strong>FindNext</strong></span><span class="sxs-lookup"><span data-stu-id="383fe-133"><strong>FindNext</strong></span></span></p></td>
<td><p><span data-ttu-id="383fe-134">Registro actual</span><span class="sxs-lookup"><span data-stu-id="383fe-134">Current record</span></span></p></td>
<td><p><span data-ttu-id="383fe-135">Final del conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="383fe-135">End of recordset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="383fe-136"><strong>FindPrevious</strong></span><span class="sxs-lookup"><span data-stu-id="383fe-136"><strong>FindPrevious</strong></span></span></p></td>
<td><p><span data-ttu-id="383fe-137">Registro actual</span><span class="sxs-lookup"><span data-stu-id="383fe-137">Current record</span></span></p></td>
<td><p><span data-ttu-id="383fe-138">Principio del conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="383fe-138">Beginning of recordset</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="383fe-p104">No obstante, el uso de uno de los métodos **Find** no es igual a utilizar el método **Move**, que activa simplemente el registro primero, último, siguiente o anterior sin especificar una condición. Puede proseguir una operación Find con una operación Move.</span><span class="sxs-lookup"><span data-stu-id="383fe-p104">Using one of the **Find** methods isn't the same as using a **Move** method, however, which simply makes the first, last, next, or previous record current without specifying a condition. You can follow a Find operation with a Move operation.</span></span>

<span data-ttu-id="383fe-p105">Compruebe siempre el valor de la propiedad **NoMatch** para determinar si la operación Find se ha realizado correctamente. Si la búsqueda es correcta, **NoMatch** es **False**. Si se produce un error, **NoMatch** es **True** y el registro activo no está definido. En este caso, debe colocar de nuevo el puntero de registros activo en un registro válido.</span><span class="sxs-lookup"><span data-stu-id="383fe-p105">Always check the value of the **NoMatch** property to determine whether the Find operation has succeeded. If the search succeeds, **NoMatch** is **False**. If it fails, **NoMatch** is **True** and the current record isn't defined. In this case, you must position the current record pointer back to a valid record.</span></span>

<span data-ttu-id="383fe-p106">Usar los métodos **Find** con conjuntos de registros a los que se accede por ODBC con conexión a un motor de base de datos de Microsoft Access puede resultar ineficiente. Tal vez observe que resulta más rápido reformular los criterios para buscar un determinado registro, especialmente al trabajar con conjuntos de registros de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="383fe-p106">Using the **Find** methods with Microsoft Access database engine-connected ODBC-accessed recordsets can be inefficient. You may find that rephrasing your criteria to locate a specific record is faster, especially when working with large recordsets.</span></span>

<span data-ttu-id="383fe-p107">Al trabajar con grandes objetos **Recordset** de tipo conjunto de registros dinámicos y bases de datos ODBC conectadas a un motor de base de datos de Microsoft Access, puede que compruebe que usar los métodos **Find** o las propiedades **Sort** o **Filter** resulta lento. Para mejorar el rendimiento, use consultas SQL con cláusulas ORDER BY o WHERE personalizadas, consultas de parámetros u objetos **QueryDef** que recuperen registros indexados concretos.</span><span class="sxs-lookup"><span data-stu-id="383fe-p107">When working with Microsoft Access database engine-connected ODBC databases and large dynaset-type **Recordset** objects, you might discover that using the **Find** methods or using the **Sort** or **Filter** property is slow. To improve performance, use SQL queries with customized ORDER BY or WHERE clauses, parameter queries, or **QueryDef** objects that retrieve specific indexed records.</span></span>

<span data-ttu-id="383fe-p108">Debe utilizar el formato de fecha de EE.UU. (mes-día-año) cuando busca campos que contienen fechas, incluso si no utiliza la versión americana del motor de base de datos de Microsoft Access; de lo contrario, es posible que no se encuentre la fecha. Utilice la función **Format** de Visual Basic para convertir la fecha. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="383fe-p108">You should use the U.S. date format (month-day-year) when you search for fields containing dates, even if you're not using the U.S. version of the Microsoft Access database engine; otherwise, the data may not be found. Use the Visual Basic **Format** function to convert the date. For example:</span></span>

```vb
rstEmployees.FindFirst "HireDate > #" _ 
        & Format(mydate, 'm-d-yy' ) & "#" 
```

<span data-ttu-id="383fe-152">Si criteria está compuesto de una cadena que se concatena con un valor no entero y los parámetros del sistema especifican un carácter decimal que no sean-US como una coma (por ejemplo, strSQL = "PRICE \> " & lngPrice y lngPrice = 125,50), se produce un error al intentar Llame al método.</span><span class="sxs-lookup"><span data-stu-id="383fe-152">If criteria is composed of a string concatenated with a non-integer value, and the system parameters specify a non-U.S. decimal character such as a comma (for example, strSQL = "PRICE \> " & lngPrice, and lngPrice = 125,50), an error occurs when you try to call the method.</span></span> <span data-ttu-id="383fe-153">Esto se produce porque durante la concatenación, el número se convertirá en una cadena utilizando el carácter decimal predeterminado de su sistema y Microsoft Access SQL sólo acepta caracteres decimales con el formato estándar de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="383fe-153">This is because during concatenation, the number will be converted to a string using your system's default decimal character, and Microsoft Access SQL only accepts U.S. decimal characters.</span></span>


> [!NOTE]
> <UL>
> <LI>
> <P><span data-ttu-id="383fe-154">Para obtener el mejor rendimiento, los <EM>criterios</EM> deben tener el formulario "<EM>campo</EM> = <EM>valor</EM>" donde <EM>campo</EM> es un campo indizado en la tabla base subyacente o "<EM>campo</EM> LIKE <EM>prefijo</EM>" donde <EM>campo</EM> es un campo indizado en la tabla base subyacente y <EM>prefijo</EM> es una cadena de búsqueda de prefijo (por ejemplo, "ART \*").</span><span class="sxs-lookup"><span data-stu-id="383fe-154">For best performance, the <EM>criteria</EM> should be in either the form "<EM>field</EM> = <EM>value</EM>" where <EM>field</EM> is an indexed field in the underlying base table, or "<EM>field</EM> LIKE <EM>prefix</EM>" where <EM>field</EM> is an indexed field in the underlying base table and <EM>prefix</EM> is a prefix search string (for example, "ART\*" ).</span></span></P>
> <LI>
> <P><span data-ttu-id="383fe-p110">En general, para tipos de búsquedas equivalentes, el método <STRONG>Seek</STRONG> proporciona un mejor rendimiento que los métodos <STRONG>Find</STRONG>. Esto supone que los objetos <STRONG>Recordset</STRONG> de tipo tabla por sí mismos pueden satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="383fe-p110">In general, for equivalent types of searches, the <STRONG>Seek</STRONG> method provides better performance than the <STRONG>Find</STRONG> methods. This assumes that table-type <STRONG>Recordset</STRONG> objects alone can satisfy your needs.</span></span></P></LI></UL>

