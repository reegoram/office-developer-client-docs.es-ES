---
title: Proveedor de Microsoft OLE DB para Servicios de Index Server de Microsoft
TOCTitle: Microsoft OLE DB Provider for Microsoft Indexing Service
ms:assetid: 01c2e75c-950a-dd8a-2b20-bbd916315ec5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248786(v=office.15)
ms:contentKeyID: 48542942
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 10af40231fc10e222f818896b3d65f44ac3d6d71
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484584"
---
# <a name="microsoft-ole-db-provider-for-microsoft-indexing-service"></a><span data-ttu-id="99954-102">Proveedor de Microsoft OLE DB para Servicios de Index Server de Microsoft</span><span class="sxs-lookup"><span data-stu-id="99954-102">Microsoft OLE DB Provider for Microsoft Indexing Service</span></span>


<span data-ttu-id="99954-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="99954-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="99954-p101">El Proveedor de Microsoft OLE DB para Servicios de Index Server de Microsoft proporciona acceso de sólo lectura mediante programación al sistema de datos y a los datos Web indizados por los Servicios de Index Server. Las aplicaciones ADO pueden emitir consultas SQL para recuperar contenido e información sobre las propiedades de los archivos.</span><span class="sxs-lookup"><span data-stu-id="99954-p101">The Microsoft OLE DB Provider for Microsoft Indexing Service provides programmatic read-only access to file system and Web data indexed by Microsoft Indexing Service. ADO applications can issue SQL queries to retrieve content and file property information.</span></span>

<span data-ttu-id="99954-106">El proveedor es de subprocesamiento libre y está habilitado para Unicode.</span><span class="sxs-lookup"><span data-stu-id="99954-106">The provider is free-threaded and unicode enabled.</span></span>

## <a name="connection-string-parameters"></a><span data-ttu-id="99954-107">Parámetros de la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="99954-107">Connection String Parameters</span></span>

<span data-ttu-id="99954-108">Para conectar con este proveedor, establezca el argumento **Provider=** de la propiedad [ConnectionString](connectionstring-property-ado.md) en:</span><span class="sxs-lookup"><span data-stu-id="99954-108">To connect to this provider, set the **Provider=** argument to the [ConnectionString](connectionstring-property-ado.md) property to:</span></span>

```vb 
 
MSIDXS 
```

<span data-ttu-id="99954-109">La lectura de la propiedad [Provider](provider-property-ado.md) devolverá también esta cadena.</span><span class="sxs-lookup"><span data-stu-id="99954-109">Reading the [Provider](provider-property-ado.md) property will return this string as well.</span></span>

## <a name="typical-connection-string"></a><span data-ttu-id="99954-110">Cadena de conexión típica</span><span class="sxs-lookup"><span data-stu-id="99954-110">Typical Connection String</span></span>

<span data-ttu-id="99954-111">Una típica cadena de conexión de este proveedor es:</span><span class="sxs-lookup"><span data-stu-id="99954-111">A typical connection string for this provider is:</span></span>

```vb 
 
"Provider=MSIDXS;Data Source=myCatalog;Locale Identifier=nnnn;" 
```

<span data-ttu-id="99954-112">La cadena consta de estas palabras clave:</span><span class="sxs-lookup"><span data-stu-id="99954-112">The string consists of these keywords:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="99954-113">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="99954-113">Keyword</span></span></p></th>
<th><p><span data-ttu-id="99954-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="99954-114">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99954-115"><strong>Provider</strong></span><span class="sxs-lookup"><span data-stu-id="99954-115"><strong>Provider</strong></span></span></p></td>
<td><p><span data-ttu-id="99954-p102">Especifica el Proveedor OLE DB para los Servicios de Index Server. Normalmente ésta es la única palabra clave especificada en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="99954-p102">Specifies the OLE DB Provider for Microsoft Indexing Service. Typically this is the only keyword specified in the connection string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-118"><strong>Data Source</strong></span><span class="sxs-lookup"><span data-stu-id="99954-118"><strong>Data Source</strong></span></span></p></td>
<td><p><span data-ttu-id="99954-p103">Especifica el nombre de catálogo de los Servicios de Index Server. Si no se especifica esta palabra clave, se utiliza el catálogo predeterminado del sistema.</span><span class="sxs-lookup"><span data-stu-id="99954-p103">Specifies the Indexing Service catalog name. If this keyword is not specified, the default system catalog is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-121"><strong>Locale Identifier</strong></span><span class="sxs-lookup"><span data-stu-id="99954-121"><strong>Locale Identifier</strong></span></span></p></td>
<td><p><span data-ttu-id="99954-p104">Especifica un número exclusivo de 32 bits (por ejemplo, 1033) que indica preferencias relacionadas con el idioma del usuario. Estas preferencias indican el formato de las fechas y las horas, el modo en que los elementos se ordenan alfabéticamente, en que se comparan las cadenas, etc. Si no se especifica esta palabra clave, se utiliza el identificador de configuración regional predeterminado del sistema.</span><span class="sxs-lookup"><span data-stu-id="99954-p104">Specifies a unique 32-bit number (for example, 1033) that specifies preferences related to the user's language. These preferences indicate how dates and times are formatted, items are sorted alphabetically, strings are compared, and so on. If this keyword is not specified, the default system locale identifier is used.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="command-text"></a><span data-ttu-id="99954-125">Texto del comando</span><span class="sxs-lookup"><span data-stu-id="99954-125">Command Text</span></span>

<span data-ttu-id="99954-p105">La sintaxis de las consultas SQL de los Servicios de Index Server se compone de extensiones de la instrucción **SELECT** de SQL-92 y sus cláusulas **FROM** y **WHERE**. Los resultados de la consulta se devuelven a través de conjuntos de filas de OLE DB, que pueden ser usados por ADO y manipulados como objetos [Recordset](recordset-object-ado.md).</span><span class="sxs-lookup"><span data-stu-id="99954-p105">The Indexing Service SQL query syntax consists of extensions to the SQL-92 **SELECT** statement and its **FROM** and **WHERE** clauses. The results of the query are returned via OLE DB rowsets, which can be consumed by ADO and manipulated as [Recordset](recordset-object-ado.md) objects.</span></span>

<span data-ttu-id="99954-p106">Puede buscar palabras o frases exactas o utilizar comodines para buscar patrones o raíces de palabras. La búsqueda lógica se puede basar en decisiones booleanas, términos sopesados o proximidad a otras palabras. También se puede buscar por "texto libre", que busca coincidencias basadas en el significado en lugar de en palabras exactas.</span><span class="sxs-lookup"><span data-stu-id="99954-p106">You can search for exact words or phrases, or use wildcards to search for patterns or stems of words. The search logic can be based on Boolean decisions, weighted terms, or proximity to other words. You can also search by "free text," which finds matches based on meaning, rather than exact words.</span></span>

<span data-ttu-id="99954-131">El proveedor no acepta llamadas a procedimientos almacenados o nombres de tabla simples (por ejemplo, la propiedad [CommandType](commandtype-property-ado.md) siempre será **adCmdText**).</span><span class="sxs-lookup"><span data-stu-id="99954-131">The provider does not accept stored procedure calls or simple table names (for example, the [CommandType](commandtype-property-ado.md) property will always be **adCmdText**).</span></span>

## <a name="recordset-behavior"></a><span data-ttu-id="99954-132">Comportamiento de Recordset</span><span class="sxs-lookup"><span data-stu-id="99954-132">Recordset Behavior</span></span>

<span data-ttu-id="99954-133">En las tablas siguientes se enumeran las características disponibles en un objeto **Recordset** abierto con este proveedor.</span><span class="sxs-lookup"><span data-stu-id="99954-133">The following tables list the features available with a **Recordset** object opened with this provider.</span></span> <span data-ttu-id="99954-134">El tipo de cursor estático (**adOpenStatic**) está disponible.</span><span class="sxs-lookup"><span data-stu-id="99954-134">Only the Static cursor type (**adOpenStatic**) is available.</span></span>

<span data-ttu-id="99954-135">Para obtener información más detallada acerca del comportamiento del objeto **Recordset** para la configuración del proveedor, ejecute el método [Supports](supports-method-ado.md) y enumere la colección [Properties](properties-collection-ado.md) del objeto **Recordset** para determinar si las propiedades dinámicas específicas del proveedor están presentes.</span><span class="sxs-lookup"><span data-stu-id="99954-135">For more detailed information about **Recordset** behavior for your provider configuration, run the [Supports](supports-method-ado.md) method and enumerate the [Properties](properties-collection-ado.md) collection of the **Recordset** to determine whether provider-specific dynamic properties are present.</span></span>

<span data-ttu-id="99954-136">Disponibilidad de las propiedades estándar del objeto **Recordset** de ADO:</span><span class="sxs-lookup"><span data-stu-id="99954-136">Availability of standard ADO **Recordset** properties:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="99954-137">Propiedad</span><span class="sxs-lookup"><span data-stu-id="99954-137">Property</span></span></p></th>
<th><p><span data-ttu-id="99954-138">Disponibilidad</span><span class="sxs-lookup"><span data-stu-id="99954-138">Availability</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99954-139"><a href="absolutepage-property-ado.md">AbsolutePage</a></span><span class="sxs-lookup"><span data-stu-id="99954-139"><a href="absolutepage-property-ado.md">AbsolutePage</a></span></span></p></td>
<td><p><span data-ttu-id="99954-140">lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="99954-140">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-141"><a href="absoluteposition-property-ado.md">AbsolutePosition</a></span><span class="sxs-lookup"><span data-stu-id="99954-141"><a href="absoluteposition-property-ado.md">AbsolutePosition</a></span></span></p></td>
<td><p><span data-ttu-id="99954-142">lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="99954-142">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-143"><a href="activeconnection-property-ado.md">ActiveConnection</a></span><span class="sxs-lookup"><span data-stu-id="99954-143"><a href="activeconnection-property-ado.md">ActiveConnection</a></span></span></p></td>
<td><p><span data-ttu-id="99954-144">solo lectura</span><span class="sxs-lookup"><span data-stu-id="99954-144">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-145"><a href="bof-eof-properties-ado.md">BOF</a></span><span class="sxs-lookup"><span data-stu-id="99954-145"><a href="bof-eof-properties-ado.md">BOF</a></span></span></p></td>
<td><p><span data-ttu-id="99954-146">solo lectura</span><span class="sxs-lookup"><span data-stu-id="99954-146">read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-147"><a href="bookmark-property-ado.md">Marcador</a>\*</span><span class="sxs-lookup"><span data-stu-id="99954-147"><a href="bookmark-property-ado.md">Bookmark</a>\*</span></span></p></td>
<td><p><span data-ttu-id="99954-148">lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="99954-148">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-149"><a href="cachesize-property-ado.md">CacheSize</a></span><span class="sxs-lookup"><span data-stu-id="99954-149"><a href="cachesize-property-ado.md">CacheSize</a></span></span></p></td>
<td><p><span data-ttu-id="99954-150">lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="99954-150">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-151"><a href="cursorlocation-property-ado.md">CursorLocation</a></span><span class="sxs-lookup"><span data-stu-id="99954-151"><a href="cursorlocation-property-ado.md">CursorLocation</a></span></span></p></td>
<td><p><span data-ttu-id="99954-152">siempre <strong>adUseServer</strong></span><span class="sxs-lookup"><span data-stu-id="99954-152">always <strong>adUseServer</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-153"><a href="cursortype-property-ado.md">CursorType</a></span><span class="sxs-lookup"><span data-stu-id="99954-153"><a href="cursortype-property-ado.md">CursorType</a></span></span></p></td>
<td><p><span data-ttu-id="99954-154">siempre <strong>adOpenStatic</strong></span><span class="sxs-lookup"><span data-stu-id="99954-154">always <strong>adOpenStatic</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-155"><a href="editmode-property-ado.md">EditMode</a></span><span class="sxs-lookup"><span data-stu-id="99954-155"><a href="editmode-property-ado.md">EditMode</a></span></span></p></td>
<td><p><span data-ttu-id="99954-156">siempre <strong>adEditNone</strong></span><span class="sxs-lookup"><span data-stu-id="99954-156">always <strong>adEditNone</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-157"><a href="bof-eof-properties-ado.md">EOF</a></span><span class="sxs-lookup"><span data-stu-id="99954-157"><a href="bof-eof-properties-ado.md">EOF</a></span></span></p></td>
<td><p><span data-ttu-id="99954-158">solo lectura</span><span class="sxs-lookup"><span data-stu-id="99954-158">read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-159"><a href="filter-property-ado.md">Filter</a></span><span class="sxs-lookup"><span data-stu-id="99954-159"><a href="filter-property-ado.md">Filter</a></span></span></p></td>
<td><p><span data-ttu-id="99954-160">lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="99954-160">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-161"><a href="locktype-property-ado.md">LockType</a></span><span class="sxs-lookup"><span data-stu-id="99954-161"><a href="locktype-property-ado.md">LockType</a></span></span></p></td>
<td><p><span data-ttu-id="99954-162">lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="99954-162">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-163"><a href="marshaloptions-property-ado.md">MarshalOptions</a></span><span class="sxs-lookup"><span data-stu-id="99954-163"><a href="marshaloptions-property-ado.md">MarshalOptions</a></span></span></p></td>
<td><p><span data-ttu-id="99954-164">No disponible</span><span class="sxs-lookup"><span data-stu-id="99954-164">not available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-165"><a href="maxrecords-property-ado.md">MaxRecords</a></span><span class="sxs-lookup"><span data-stu-id="99954-165"><a href="maxrecords-property-ado.md">MaxRecords</a></span></span></p></td>
<td><p><span data-ttu-id="99954-166">lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="99954-166">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-167"><a href="pagecount-property-ado.md">PageCount</a></span><span class="sxs-lookup"><span data-stu-id="99954-167"><a href="pagecount-property-ado.md">PageCount</a></span></span></p></td>
<td><p><span data-ttu-id="99954-168">solo lectura</span><span class="sxs-lookup"><span data-stu-id="99954-168">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-169"><a href="pagesize-property-ado.md">PageSize</a></span><span class="sxs-lookup"><span data-stu-id="99954-169"><a href="pagesize-property-ado.md">PageSize</a></span></span></p></td>
<td><p><span data-ttu-id="99954-170">lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="99954-170">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-171"><a href="recordcount-property-ado.md">RecordCount</a></span><span class="sxs-lookup"><span data-stu-id="99954-171"><a href="recordcount-property-ado.md">RecordCount</a></span></span></p></td>
<td><p><span data-ttu-id="99954-172">solo lectura</span><span class="sxs-lookup"><span data-stu-id="99954-172">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-173"><a href="source-property-ado-recordset.md">Source</a></span><span class="sxs-lookup"><span data-stu-id="99954-173"><a href="source-property-ado-recordset.md">Source</a></span></span></p></td>
<td><p><span data-ttu-id="99954-174">lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="99954-174">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-175"><a href="state-property-ado.md">State</a></span><span class="sxs-lookup"><span data-stu-id="99954-175"><a href="state-property-ado.md">State</a></span></span></p></td>
<td><p><span data-ttu-id="99954-176">solo lectura</span><span class="sxs-lookup"><span data-stu-id="99954-176">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-177"><a href="status-property-ado-recordset.md">Status</a></span><span class="sxs-lookup"><span data-stu-id="99954-177"><a href="status-property-ado-recordset.md">Status</a></span></span></p></td>
<td><p><span data-ttu-id="99954-178">solo lectura</span><span class="sxs-lookup"><span data-stu-id="99954-178">read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="99954-179">\*Marcadores deben estar habilitados en el proveedor en orden para esta característica de que existan en el **conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="99954-179">\*Bookmarks must be enabled on the provider in order for this feature to exist on the **Recordset**.</span></span>

<span data-ttu-id="99954-180">Disponibilidad de métodos estándar **Recordset** ADO:</span><span class="sxs-lookup"><span data-stu-id="99954-180">Availability of standard ADO **Recordset** methods:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="99954-181">Método</span><span class="sxs-lookup"><span data-stu-id="99954-181">Method</span></span></p></th>
<th><p><span data-ttu-id="99954-182">¿Disponible?</span><span class="sxs-lookup"><span data-stu-id="99954-182">Available?</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99954-183"><a href="addnew-method-ado.md">AddNew</a></span><span class="sxs-lookup"><span data-stu-id="99954-183"><a href="addnew-method-ado.md">AddNew</a></span></span></p></td>
<td><p><span data-ttu-id="99954-184">No</span><span class="sxs-lookup"><span data-stu-id="99954-184">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-185"><a href="cancel-method-ado.md">Cancel</a></span><span class="sxs-lookup"><span data-stu-id="99954-185"><a href="cancel-method-ado.md">Cancel</a></span></span></p></td>
<td><p><span data-ttu-id="99954-186">Sí</span><span class="sxs-lookup"><span data-stu-id="99954-186">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-187"><a href="cancelbatch-method-ado.md">CancelBatch</a></span><span class="sxs-lookup"><span data-stu-id="99954-187"><a href="cancelbatch-method-ado.md">CancelBatch</a></span></span></p></td>
<td><p><span data-ttu-id="99954-188">No</span><span class="sxs-lookup"><span data-stu-id="99954-188">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-189"><a href="cancelupdate-method-ado.md">CancelUpdate</a></span><span class="sxs-lookup"><span data-stu-id="99954-189"><a href="cancelupdate-method-ado.md">CancelUpdate</a></span></span></p></td>
<td><p><span data-ttu-id="99954-190">No</span><span class="sxs-lookup"><span data-stu-id="99954-190">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-191"><a href="clone-method-ado.md">Clone</a></span><span class="sxs-lookup"><span data-stu-id="99954-191"><a href="clone-method-ado.md">Clone</a></span></span></p></td>
<td><p><span data-ttu-id="99954-192">Sí</span><span class="sxs-lookup"><span data-stu-id="99954-192">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-193"><a href="close-method-ado.md">Close</a></span><span class="sxs-lookup"><span data-stu-id="99954-193"><a href="close-method-ado.md">Close</a></span></span></p></td>
<td><p><span data-ttu-id="99954-194">Sí</span><span class="sxs-lookup"><span data-stu-id="99954-194">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-195"><a href="delete-method-ado-recordset.md">Delete</a></span><span class="sxs-lookup"><span data-stu-id="99954-195"><a href="delete-method-ado-recordset.md">Delete</a></span></span></p></td>
<td><p><span data-ttu-id="99954-196">No</span><span class="sxs-lookup"><span data-stu-id="99954-196">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-197"><a href="getrows-method-ado.md">GetRows</a></span><span class="sxs-lookup"><span data-stu-id="99954-197"><a href="getrows-method-ado.md">GetRows</a></span></span></p></td>
<td><p><span data-ttu-id="99954-198">Sí</span><span class="sxs-lookup"><span data-stu-id="99954-198">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-199"><a href="move-method-ado.md">Mover</a></span><span class="sxs-lookup"><span data-stu-id="99954-199"><a href="move-method-ado.md">Move</a></span></span></p></td>
<td><p><span data-ttu-id="99954-200">Sí</span><span class="sxs-lookup"><span data-stu-id="99954-200">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-201"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">Métodos MoveFirst</a></span><span class="sxs-lookup"><span data-stu-id="99954-201"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a></span></span></p></td>
<td><p><span data-ttu-id="99954-202">Sí</span><span class="sxs-lookup"><span data-stu-id="99954-202">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-203"><a href="nextrecordset-method-ado.md">NextRecordset</a></span><span class="sxs-lookup"><span data-stu-id="99954-203"><a href="nextrecordset-method-ado.md">NextRecordset</a></span></span></p></td>
<td><p><span data-ttu-id="99954-204">Sí</span><span class="sxs-lookup"><span data-stu-id="99954-204">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-205"><a href="open-method-ado-recordset.md">Open</a></span><span class="sxs-lookup"><span data-stu-id="99954-205"><a href="open-method-ado-recordset.md">Open</a></span></span></p></td>
<td><p><span data-ttu-id="99954-206">Sí</span><span class="sxs-lookup"><span data-stu-id="99954-206">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-207"><a href="requery-method-ado.md">Requery</a></span><span class="sxs-lookup"><span data-stu-id="99954-207"><a href="requery-method-ado.md">Requery</a></span></span></p></td>
<td><p><span data-ttu-id="99954-208">Sí</span><span class="sxs-lookup"><span data-stu-id="99954-208">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-209"><a href="resync-method-ado.md">Resync</a></span><span class="sxs-lookup"><span data-stu-id="99954-209"><a href="resync-method-ado.md">Resync</a></span></span></p></td>
<td><p><span data-ttu-id="99954-210">Sí</span><span class="sxs-lookup"><span data-stu-id="99954-210">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-211"><a href="supports-method-ado.md">Admite</a></span><span class="sxs-lookup"><span data-stu-id="99954-211"><a href="supports-method-ado.md">Supports</a></span></span></p></td>
<td><p><span data-ttu-id="99954-212">Sí</span><span class="sxs-lookup"><span data-stu-id="99954-212">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99954-213"><a href="update-method-ado.md">Actualizar</a></span><span class="sxs-lookup"><span data-stu-id="99954-213"><a href="update-method-ado.md">Update</a></span></span></p></td>
<td><p><span data-ttu-id="99954-214">No</span><span class="sxs-lookup"><span data-stu-id="99954-214">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99954-215"><a href="updatebatch-method-ado.md">UpdateBatch</a></span><span class="sxs-lookup"><span data-stu-id="99954-215"><a href="updatebatch-method-ado.md">UpdateBatch</a></span></span></p></td>
<td><p><span data-ttu-id="99954-216">No</span><span class="sxs-lookup"><span data-stu-id="99954-216">No</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="99954-217">Vea también</span><span class="sxs-lookup"><span data-stu-id="99954-217">See also</span></span>

<span data-ttu-id="99954-218">Para detalles de implementación específicos e información funcional acerca del proveedor de Microsoft OLE DB para Microsoft Indexing Service, consulte referencia de Microsoft OLE DB del programador.</span><span class="sxs-lookup"><span data-stu-id="99954-218">For specific implementation details and functional information about the Microsoft OLE DB Provider for Microsoft Indexing Service, consult the Microsoft OLE DB Programmer's Reference.</span></span>
