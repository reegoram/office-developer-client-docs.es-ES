---
title: ExecuteOptionEnum (referencia de escritorio de la base de datos de Access)
TOCTitle: ExecuteOptionEnum
ms:assetid: bd6d44a3-e471-7aa0-3e65-6775334de2ff
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249915(v=office.15)
ms:contentKeyID: 48547438
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: aeb1083c693e0848e30a0b9217ae709994daddb5
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484869"
---
# <a name="executeoptionenum"></a><span data-ttu-id="37b54-102">ExecuteOptionEnum</span><span class="sxs-lookup"><span data-stu-id="37b54-102">ExecuteOptionEnum</span></span>


<span data-ttu-id="37b54-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="37b54-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="37b54-104">Especifica la forma en que un proveedor debe ejecutar un comando.</span><span class="sxs-lookup"><span data-stu-id="37b54-104">Specifies how a provider should execute a command.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="37b54-105">Constante</span><span class="sxs-lookup"><span data-stu-id="37b54-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="37b54-106">Valor</span><span class="sxs-lookup"><span data-stu-id="37b54-106">Value</span></span></p></th>
<th><p><span data-ttu-id="37b54-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="37b54-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37b54-108"><strong>adAsyncExecute</strong></span><span class="sxs-lookup"><span data-stu-id="37b54-108"><strong>adAsyncExecute</strong></span></span></p></td>
<td><p><span data-ttu-id="37b54-109">0 x 10</span><span class="sxs-lookup"><span data-stu-id="37b54-109">0x10</span></span></p></td>
<td><p><span data-ttu-id="37b54-110">Indica que el comando se debe ejecutar asincrónicamente.
</span><span class="sxs-lookup"><span data-stu-id="37b54-110">Indicates that the command should execute asynchronously.</span></span> <span data-ttu-id="37b54-111">Este valor no se puede combinar con el valor <strong>adCmdTableDirect</strong> de <a href="commandtypeenum.md">CommandTypeEnum</a>.</span><span class="sxs-lookup"><span data-stu-id="37b54-111">This value cannot be combined with the <a href="commandtypeenum.md">CommandTypeEnum</a> value <strong>adCmdTableDirect</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37b54-112"><strong>adAsyncFetch</strong></span><span class="sxs-lookup"><span data-stu-id="37b54-112"><strong>adAsyncFetch</strong></span></span></p></td>
<td><p><span data-ttu-id="37b54-113">0 x 20</span><span class="sxs-lookup"><span data-stu-id="37b54-113">0x20</span></span></p></td>
<td><p><span data-ttu-id="37b54-114">Indica que las filas restantes después de la cantidad inicial especificada en la propiedad <a href="cachesize-property-ado.md">CacheSize</a> se deben recuperar asincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="37b54-114">Indicates that the remaining rows after the initial quantity specified in the <a href="cachesize-property-ado.md">CacheSize</a> property should be retrieved asynchronously.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37b54-115"><strong>adAsyncFetchNonBlocking</strong></span><span class="sxs-lookup"><span data-stu-id="37b54-115"><strong>adAsyncFetchNonBlocking</strong></span></span></p></td>
<td><p><span data-ttu-id="37b54-116">0 x 40</span><span class="sxs-lookup"><span data-stu-id="37b54-116">0x40</span></span></p></td>
<td><p><span data-ttu-id="37b54-117">Indica que el subproceso principal se bloquea nunca al recuperar.</span><span class="sxs-lookup"><span data-stu-id="37b54-117">Indicates that the main thread never blocks while retrieving.</span></span> <span data-ttu-id="37b54-118">Si la fila solicitada no se ha recuperado, la fila actual se mueve automáticamente hasta el final del archivo.</span><span class="sxs-lookup"><span data-stu-id="37b54-118">If the requested row has not been retrieved, the current row automatically moves to the end of the file.</span></span> <span data-ttu-id="37b54-119">Si abre un <a href="recordset-object-ado.md">Recordset</a> de un <a href="stream-object-ado.md">Stream</a> que contiene un objeto <strong>Recordset</strong> almacenado persistentemente, <strong>adAsyncFetchNonBlocking</strong> no tendrá un efecto (la operación será sincrónica y bloqueante).</span><span class="sxs-lookup"><span data-stu-id="37b54-119">If you open a <a href="recordset-object-ado.md">Recordset</a> from a <a href="stream-object-ado.md">Stream</a> containing a persistently stored <strong>Recordset</strong>, <strong>adAsyncFetchNonBlocking</strong> will not have an effect; the operation will be synchronous and blocking.</span></span> <span data-ttu-id="37b54-120"><strong>adAsynchFetchNonBlocking</strong> no tiene efecto cuando la opción <a href="commandtypeenum.md">adCmdTableDirect</a> se usa para abrir el objeto <strong>Recordset</strong>.</span><span class="sxs-lookup"><span data-stu-id="37b54-120"><strong>adAsynchFetchNonBlocking</strong> has no effect when the <a href="commandtypeenum.md">adCmdTableDirect</a> option is used to open the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37b54-121"><strong>adExecuteNoRecords</strong></span><span class="sxs-lookup"><span data-stu-id="37b54-121"><strong>adExecuteNoRecords</strong></span></span></p></td>
<td><p><span data-ttu-id="37b54-122">0 x 80</span><span class="sxs-lookup"><span data-stu-id="37b54-122">0x80</span></span></p></td>
<td><p><span data-ttu-id="37b54-123">Indica que el texto de comando es un comando o un procedimiento almacenado que no devuelve filas (por ejemplo, un comando que sólo inserta datos).</span><span class="sxs-lookup"><span data-stu-id="37b54-123">Indicates that the command text is a command or stored procedure that does not return rows (for example, a command that only inserts data).</span></span> <span data-ttu-id="37b54-124">Si se recuperan todas las filas, se descartan y no se devuelve.</span><span class="sxs-lookup"><span data-stu-id="37b54-124">If any rows are retrieved, they are discarded and not returned.</span></span> <span data-ttu-id="37b54-125"><strong>adExecuteNoRecords</strong> sólo se puede pasar como un parámetro opcional al método <strong>Execute</strong> de <strong>Connection</strong> o <strong>comando</strong> .</span><span class="sxs-lookup"><span data-stu-id="37b54-125"><strong>adExecuteNoRecords</strong> can only be passed as an optional parameter to the <strong>Command</strong> or <strong>Connection</strong> <strong>Execute</strong> method.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37b54-126"><strong>adExecuteStream</strong></span><span class="sxs-lookup"><span data-stu-id="37b54-126"><strong>adExecuteStream</strong></span></span></p></td>
<td><p><span data-ttu-id="37b54-127">0 x 400</span><span class="sxs-lookup"><span data-stu-id="37b54-127">0x400</span></span></p></td>
<td><p><span data-ttu-id="37b54-128">Indica que los resultados de la ejecución de un comando se deben devolver como una secuencia.
</span><span class="sxs-lookup"><span data-stu-id="37b54-128">Indicates that the results of a command execution should be returned as a stream.</span></span> <span data-ttu-id="37b54-129"><strong>adExecuteStream</strong> sólo se puede pasar como un parámetro opcional al método <strong>Execute</strong> de <strong>comando</strong> .</span><span class="sxs-lookup"><span data-stu-id="37b54-129"><strong>adExecuteStream</strong> can only be passed as an optional parameter to the <strong>Command</strong> <strong>Execute</strong> method.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37b54-130"><strong>adExecuteRecord</strong></span><span class="sxs-lookup"><span data-stu-id="37b54-130"><strong>adExecuteRecord</strong></span></span></p></td>
<td><p><br />
</p></td>
<td><p><span data-ttu-id="37b54-131">Indica que el objeto <strong>CommandText</strong> es un comando o un procedimiento almacenado que devuelve una sola fila y que se debería devolver como un objeto <strong>Record</strong>.</span><span class="sxs-lookup"><span data-stu-id="37b54-131">Indicates that the <strong>CommandText</strong> is a command or stored procedure that returns a single row which should be returned as a <strong>Record</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37b54-132"><strong>realiza la consulta</strong></span><span class="sxs-lookup"><span data-stu-id="37b54-132"><strong>adOptionUnspecified</strong></span></span></p></td>
<td><p><span data-ttu-id="37b54-133">-1</span><span class="sxs-lookup"><span data-stu-id="37b54-133">-1</span></span></p></td>
<td><p><span data-ttu-id="37b54-134">Indica que no se especifica el comando.</span><span class="sxs-lookup"><span data-stu-id="37b54-134">Indicates that the command is unspecified.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="37b54-135">**Equivalente ADO/WFC**</span><span class="sxs-lookup"><span data-stu-id="37b54-135">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="37b54-136">Paquete: **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="37b54-136">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="37b54-137">Constante</span><span class="sxs-lookup"><span data-stu-id="37b54-137">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37b54-138">AdoEnums.ExecuteOption.ASYNCEXECUTE</span><span class="sxs-lookup"><span data-stu-id="37b54-138">AdoEnums.ExecuteOption.ASYNCEXECUTE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37b54-139">AdoEnums.ExecuteOption.ASYNCFETCH</span><span class="sxs-lookup"><span data-stu-id="37b54-139">AdoEnums.ExecuteOption.ASYNCFETCH</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37b54-140">AdoEnums.ExecuteOption.ASYNCFETCHNONBLOCKING</span><span class="sxs-lookup"><span data-stu-id="37b54-140">AdoEnums.ExecuteOption.ASYNCFETCHNONBLOCKING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37b54-141">AdoEnums.ExecuteOption.NORECORDS</span><span class="sxs-lookup"><span data-stu-id="37b54-141">AdoEnums.ExecuteOption.NORECORDS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37b54-142">AdoEnums.ExecuteOption.UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="37b54-142">AdoEnums.ExecuteOption.UNSPECIFIED</span></span></p></td>
</tr>
</tbody>
</table>
