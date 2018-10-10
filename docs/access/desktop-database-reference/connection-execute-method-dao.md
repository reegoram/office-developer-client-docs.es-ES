---
title: Connection.Execute Method (DAO)
TOCTitle: Execute Method
ms:assetid: d6140d4e-fa14-6455-525e-49d8aab3dff7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835040(v=office.15)
ms:contentKeyID: 48547978
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3171ec1d35f08a5bc9d6a02a9a50ca80e11413de
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485721"
---
# <a name="connectionexecute-method-dao"></a><span data-ttu-id="8c57a-102">Connection.Execute Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="8c57a-102">Connection.Execute Method (DAO)</span></span>


<span data-ttu-id="8c57a-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="8c57a-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="8c57a-104">Ejecuta una consulta de acción o una instrucción SQL en el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="8c57a-104">Runs an action query or executes an SQL statement on the specified object.</span></span>

## <a name="syntax"></a><span data-ttu-id="8c57a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c57a-105">Syntax</span></span>

<span data-ttu-id="8c57a-106">*expresión* . Ejecutar (***consulta***, ***Opciones***)</span><span class="sxs-lookup"><span data-stu-id="8c57a-106">*expression* .Execute(***Query***, ***Options***)</span></span>

<span data-ttu-id="8c57a-107">*expresión* Variable que representa un objeto **Connection** .</span><span class="sxs-lookup"><span data-stu-id="8c57a-107">*expression* A variable that represents a **Connection** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="8c57a-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8c57a-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8c57a-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="8c57a-109">Name</span></span></p></th>
<th><p><span data-ttu-id="8c57a-110">Necesario/Opcional</span><span class="sxs-lookup"><span data-stu-id="8c57a-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="8c57a-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8c57a-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="8c57a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c57a-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c57a-113">Query</span><span class="sxs-lookup"><span data-stu-id="8c57a-113">Query</span></span></p></td>
<td><p><span data-ttu-id="8c57a-114">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8c57a-114">Required</span></span></p></td>
<td><p><span data-ttu-id="8c57a-115"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="8c57a-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="8c57a-116"><strong>String</strong> que es una instrucción SQL o el valor de la propiedad <strong>Name</strong> de un objeto <strong>QueryDef</strong>.</span><span class="sxs-lookup"><span data-stu-id="8c57a-116">A <strong>String</strong> that is an SQL statement or the <strong>Name</strong> property value of a <strong>QueryDef</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c57a-117">Options</span><span class="sxs-lookup"><span data-stu-id="8c57a-117">Options</span></span></p></td>
<td><p><span data-ttu-id="8c57a-118">Opcional</span><span class="sxs-lookup"><span data-stu-id="8c57a-118">Optional</span></span></p></td>
<td><p><span data-ttu-id="8c57a-119"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="8c57a-119"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="8c57a-120">Constante o combinación de constantes que determinan las características de integridad de los datos, tal como se especifica en la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="8c57a-120">A constant or combination of constants that determines the data integrity characteristics of the query, as specified in Settings.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="8c57a-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8c57a-121">Remarks</span></span>

<span data-ttu-id="8c57a-122">Puede usar las siguientes constantes **[RecordsetOptionEnum](recordsetoptionenum-enumeration-dao.md)** para ver las opciones.</span><span class="sxs-lookup"><span data-stu-id="8c57a-122">You can use the following **[RecordsetOptionEnum](recordsetoptionenum-enumeration-dao.md)** constants for options.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8c57a-123">Constante</span><span class="sxs-lookup"><span data-stu-id="8c57a-123">Constant</span></span></p></th>
<th><p><span data-ttu-id="8c57a-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c57a-124">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c57a-125"><strong>dbDenyWrite</strong></span><span class="sxs-lookup"><span data-stu-id="8c57a-125"><strong>dbDenyWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="8c57a-126">Deniega el permiso de escritura a otros usuarios (sólo áreas de trabajo de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="8c57a-126">Denies write permission to other users (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c57a-127"><strong>dbInconsistent</strong></span><span class="sxs-lookup"><span data-stu-id="8c57a-127"><strong>dbInconsistent</strong></span></span></p></td>
<td><p><span data-ttu-id="8c57a-128">(Valor predeterminado) Ejecuta actualizaciones no coherentes (sólo áreas de trabajo de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="8c57a-128">(Default) Executes inconsistent updates (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c57a-129"><strong>dbConsistent</strong></span><span class="sxs-lookup"><span data-stu-id="8c57a-129"><strong>dbConsistent</strong></span></span></p></td>
<td><p><span data-ttu-id="8c57a-130">Ejecuta actualizaciones coherentes (sólo áreas de trabajo de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="8c57a-130">Executes consistent updates (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c57a-131"><strong>dbSQLPassThrough</strong></span><span class="sxs-lookup"><span data-stu-id="8c57a-131"><strong>dbSQLPassThrough</strong></span></span></p></td>
<td><p><span data-ttu-id="8c57a-p101">Ejecuta una consulta de paso a través de SQL. Establecer esta opción pasa la instrucción SQL a una base de datos ODBC para procesamiento (sólo áreas de trabajo de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="8c57a-p101">Executes an SQL pass-through query. Setting this option passes the SQL statement to an ODBC database for processing (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c57a-134"><strong>dbFailOnError</strong></span><span class="sxs-lookup"><span data-stu-id="8c57a-134"><strong>dbFailOnError</strong></span></span></p></td>
<td><p><span data-ttu-id="8c57a-135">Deshace las actualizaciones si se produce un error (sólo áreas de trabajo de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="8c57a-135">Rolls back updates if an error occurs (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c57a-136"><strong>dbSeeChanges</strong></span><span class="sxs-lookup"><span data-stu-id="8c57a-136"><strong>dbSeeChanges</strong></span></span></p></td>
<td><p><span data-ttu-id="8c57a-137">Genera un error en tiempo de ejecución si otro usuario cambia los datos que está usted editando (sólo áreas de trabajo de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="8c57a-137">Generates a run-time error if another user is changing data you are editing (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c57a-138"><strong>dbRunAsync</strong></span><span class="sxs-lookup"><span data-stu-id="8c57a-138"><strong>dbRunAsync</strong></span></span></p></td>
<td><p><span data-ttu-id="8c57a-139">Ejecuta la consulta de forma asincrónica (sólo conexiones ODBCDirect y objetos QueryDef).</span><span class="sxs-lookup"><span data-stu-id="8c57a-139">Executes the query asynchronously (ODBCDirect Connection and QueryDef objects only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c57a-140"><strong>dbExecDirect</strong></span><span class="sxs-lookup"><span data-stu-id="8c57a-140"><strong>dbExecDirect</strong></span></span></p></td>
<td><p><span data-ttu-id="8c57a-141">Ejecuta la instrucción sin llamar primero a la función API de ODBC SQLPrepare (sólo conexiones ODBCDirect y objetos QueryDef).</span><span class="sxs-lookup"><span data-stu-id="8c57a-141">Executes the statement without first calling SQLPrepare ODBC API function (ODBCDirect Connection and QueryDef objects only).</span></span></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P><span data-ttu-id="8c57a-p102">[!NOTA] No se admiten áreas de trabajo de ODBCDirect en Microsoft Access 2013. Use ADO si quiere acceder a orígenes de datos externos sin usar el motor de base de datos de Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="8c57a-p102">ODBCDirect workspaces are not supported in Microsoft Access 2013. Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></P>




> [!NOTE]
> <P><span data-ttu-id="8c57a-p103">[!NOTA] Las constantes <STRONG>dbConsistent</STRONG> y <STRONG>dbInconsistent</STRONG> son mutuamente excluyentes. Puede usar una o la otra, pero no ambas, en una instancia específica de <STRONG>OpenRecordset</STRONG>. Si se usan <STRONG>dbConsistent</STRONG> y <STRONG>dbInconsistent</STRONG>, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="8c57a-p103">The constants <STRONG>dbConsistent</STRONG> and <STRONG>dbInconsistent</STRONG> are mutually exclusive. You can use one or the other, but not both in a given instance of <STRONG>OpenRecordset</STRONG>. Using both <STRONG>dbConsistent</STRONG> and <STRONG>dbInconsistent</STRONG> causes an error.</span></span></P>



<span data-ttu-id="8c57a-p104">El método **Execute** solo es válido para consultas de acción. Si utiliza **Execute** con otro tipo de consulta, se produce un error. Como una consulta de acción no devuelve registros, **Execute** no devuelve un objeto **Recordset**. (La ejecución de una consulta de paso SQL en un área de trabajo de ODBCDirect no devuelve un error si no se devuelve un objeto **Recordset**.)</span><span class="sxs-lookup"><span data-stu-id="8c57a-p104">The **Execute** method is valid only for action queries. If you use **Execute** with another type of query, an error occurs. Because an action query doesn't return any records, **Execute** doesn't return a **Recordset**. (Executing an SQL pass-through query in an ODBCDirect workspace will not return an error if a **Recordset** isn't returned.)</span></span>

<span data-ttu-id="8c57a-p105">Utilice la propiedad **RecordsAffected** del objeto **Connection**, **Database** o **QueryDef** para determinar el número de registros afectados por el método **Execute** más reciente. Por ejemplo, **RecordsAffected** contiene el número de registros eliminados, actualizados o insertados al ejecutar una consulta de acción. Cuando se utiliza el método **Execute** para ejecutar una consulta, la propiedad **RecordsAffected** del objeto **QueryDef** se establece en el número de registros afectados.</span><span class="sxs-lookup"><span data-stu-id="8c57a-p105">Use the **RecordsAffected** property of the **Connection**, **Database**, or **QueryDef** object to determine the number of records affected by the most recent **Execute** method. For example, **RecordsAffected** contains the number of records deleted, updated, or inserted when executing an action query. When you use the **Execute** method to run a query, the **RecordsAffected** property of the **QueryDef** object is set to the number of records affected.</span></span>

<span data-ttu-id="8c57a-p106">En un área de trabajo de Microsoft Access, si especifica una instrucción SQL sintácticamente correcta y dispone de los permisos correspondientes, el método **Execute** no producirá un error, aunque no pueda modificarse ni eliminarse una fila. Por tanto, utilice siempre la opción **dbFailOnError** cuando use el método **Execute** para ejecutar una actualización o eliminar una consulta. Esta opción genera un error en tiempo de ejecución y deshace todos los cambios que se han realizado correctamente si alguno de los registros afectados está bloqueado y no se puede actualizar o eliminar.</span><span class="sxs-lookup"><span data-stu-id="8c57a-p106">In a Microsoft Access workspace, if you provide a syntactically correct SQL statement and have the appropriate permissions, the **Execute** method won't fail — even if not a single row can be modified or deleted. Therefore, always use the **dbFailOnError** option when using the **Execute** method to run an update or delete query. This option generates a run-time error and rolls back all successful changes if any of the records affected are locked and can't be updated or deleted.</span></span>

<span data-ttu-id="8c57a-p107">En versiones anteriores del motor de base de datos de Microsoft Jet, las instrucciones SQL se insertaban automáticamente en transacciones implícitas. Si parte de una instrucción ejecutada con **dbFailOnError** producía un error, se revertía toda la instrucción. Para mejorar el rendimiento, desde la versión 3.5 estas instrucciones implícitas ya no existen. Si actualiza código DAO antiguo, no olvide que debe usar transacciones explícitas con las instrucciones **Execute**.</span><span class="sxs-lookup"><span data-stu-id="8c57a-p107">In earlier versions of the Microsoft Jet database engine, SQL statements were automatically embedded in implicit transactions. If part of a statement executed with **dbFailOnError** failed, the entire statement would be rolled back. To improve performance, these implicit transactions were removed starting with version 3.5. If you are updating older DAO code, be sure to consider using explicit transactions around **Execute** statements.</span></span>

<span data-ttu-id="8c57a-p108">Para mejorar el rendimiento en un área de trabajo de Microsoft Access, especialmente en un entorno multiusuario, anide el método **Execute** dentro de una transacción. Utilice el método **BeginTrans** en el objeto **Workspace** actual y, a continuación, utilice el método **Execute** y complete la transacción empleando el método **CommitTrans** en el objeto **Workspace**. De esta forma, se reducirán los cambios en disco y se liberarán todos los bloqueos aplicados mientras se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="8c57a-p108">For best performance in a Microsoft Access workspace, especially in a multiuser environment, nest the **Execute** method inside a transaction. Use the **BeginTrans** method on the current **Workspace** object, then use the **Execute** method, and complete the transaction by using the **CommitTrans** method on the **Workspace**. This saves changes on disk and frees any locks placed while the query is running.</span></span>
