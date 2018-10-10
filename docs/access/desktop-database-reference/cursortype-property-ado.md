---
title: CursorType (propiedad, ADO)
TOCTitle: CursorType Property (ADO)
ms:assetid: f42ded8f-9f92-ef03-a198-ffb892324611
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250239(v=office.15)
ms:contentKeyID: 48548682
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0628edda3c85af08ecd815e550aecbd864955814
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25483795"
---
# <a name="cursortype-property-ado"></a><span data-ttu-id="0b440-102">CursorType (propiedad, ADO)</span><span class="sxs-lookup"><span data-stu-id="0b440-102">CursorType Property (ADO)</span></span>


<span data-ttu-id="0b440-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="0b440-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="0b440-104">Indica el tipo de cursor que se usa en un objeto [Recordset](recordset-object-ado.md).</span><span class="sxs-lookup"><span data-stu-id="0b440-104">Indicates the type of cursor used in a [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="0b440-105">Configuración y valores devueltos</span><span class="sxs-lookup"><span data-stu-id="0b440-105">Settings and Return Values</span></span>

<span data-ttu-id="0b440-p101">Establece o devuelve un valor de tipo [CursorTypeEnum](cursortypeenum.md). El valor predeterminado es **adOpenForwardOnly**.</span><span class="sxs-lookup"><span data-stu-id="0b440-p101">Sets or returns a [CursorTypeEnum](cursortypeenum.md) value. The default value is **adOpenForwardOnly**.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b440-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0b440-108">Remarks</span></span>

<span data-ttu-id="0b440-109">Use la propiedad **CursorType** para especificar el tipo de cursor que se va a usar cuando se abra el objeto **Recordset**.</span><span class="sxs-lookup"><span data-stu-id="0b440-109">Use the **CursorType** property to specify the type of cursor that should be used when opening the **Recordset** object.</span></span>

<span data-ttu-id="0b440-p102">Sólo se admite el valor **adOpenStatic** si la propiedad [CursorLocation](cursorlocation-property-ado.md) tiene el valor **adUseClient**. Si se establece un valor no admitido, no se generará ningún error sino que se utilizará el valor de **CursorType** admitido más próximo.</span><span class="sxs-lookup"><span data-stu-id="0b440-p102">Only a setting of **adOpenStatic** is supported if the [CursorLocation](cursorlocation-property-ado.md) property is set to **adUseClient**. If an unsupported value is set, then no error will result; the closest supported **CursorType** will be used instead.</span></span>

<span data-ttu-id="0b440-p103">Si un proveedor no admite el tipo de cursor solicitado, puede que devuelva otro tipo de cursor. El valor de la propiedad **CursorType** cambia para que coincida con el tipo de cursor que se usa realmente cuando está abierto el objeto [Recordset](recordset-object-ado.md). Para comprobar la funcionalidad específica del cursor devuelto, use el método [Supports](supports-method-ado.md). Tras cerrarse el objeto **Recordset**, se restablece el valor original de la propiedad **CursorType**.</span><span class="sxs-lookup"><span data-stu-id="0b440-p103">If a provider does not support the requested cursor type, it may return another cursor type. The **CursorType** property will change to match the actual cursor type in use when the [Recordset](recordset-object-ado.md) object is open. To verify specific functionality of the returned cursor, use the [Supports](supports-method-ado.md) method. After you close the **Recordset**, the **CursorType** property reverts to its original setting.</span></span>

<span data-ttu-id="0b440-116">En el gráfico siguiente se muestra la funcionalidad (identificada mediante las constantes del método **Supports** ) del proveedor que se requiere para cada tipo de cursor.</span><span class="sxs-lookup"><span data-stu-id="0b440-116">The following chart shows the provider functionality (identified by **Supports** method constants) required for each cursor type.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0b440-117">Para un objeto Recordset con este valor de CursorType</span><span class="sxs-lookup"><span data-stu-id="0b440-117">For a Recordset of this CursorType</span></span></p></th>
<th><p><span data-ttu-id="0b440-118">El método Supports debe devolver True para todas estas constantes</span><span class="sxs-lookup"><span data-stu-id="0b440-118">The Supports method must return True for all of these constants</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b440-119"><strong>adOpenForwardOnly</strong></span><span class="sxs-lookup"><span data-stu-id="0b440-119"><strong>adOpenForwardOnly</strong></span></span></p></td>
<td><p><span data-ttu-id="0b440-120">none</span><span class="sxs-lookup"><span data-stu-id="0b440-120">none</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b440-121"><strong>adOpenKeyset</strong></span><span class="sxs-lookup"><span data-stu-id="0b440-121"><strong>adOpenKeyset</strong></span></span></p></td>
<td><p><span data-ttu-id="0b440-122"><strong>adBookmark</strong>, <strong>adHoldRecords</strong>, <strong>adMovePrevious</strong>, <strong>adResync</strong></span><span class="sxs-lookup"><span data-stu-id="0b440-122"><strong>adBookmark</strong>, <strong>adHoldRecords</strong>, <strong>adMovePrevious</strong>, <strong>adResync</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b440-123"><strong>adOpenDynamic</strong></span><span class="sxs-lookup"><span data-stu-id="0b440-123"><strong>adOpenDynamic</strong></span></span></p></td>
<td><p><span data-ttu-id="0b440-124"><strong>adMovePrevious</strong></span><span class="sxs-lookup"><span data-stu-id="0b440-124"><strong>adMovePrevious</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b440-125"><strong>adOpenStatic</strong></span><span class="sxs-lookup"><span data-stu-id="0b440-125"><strong>adOpenStatic</strong></span></span></p></td>
<td><p><span data-ttu-id="0b440-126"><strong>adBookmark</strong>, <strong>adHoldRecords</strong>, <strong>adMovePrevious</strong>, <strong>adResync</strong></span><span class="sxs-lookup"><span data-stu-id="0b440-126"><strong>adBookmark</strong>, <strong>adHoldRecords</strong>, <strong>adMovePrevious</strong>, <strong>adResync</strong></span></span></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P><span data-ttu-id="0b440-p104">Si bien el método <STRONG>Supports</STRONG>(<STRONG>adUpdateBatch</STRONG>) puede tener el valor True para los cursores dinámicos y de sólo avance, para las actualizaciones por lotes se debe usar un cursor estático o un cursor de conjunto de claves. Establezca el valor de la propiedad <A href="locktype-property-ado.md">LockType</A> en <STRONG>adLockBatchOptimistic</STRONG> y el valor de la propiedad <STRONG>CursorLocation</STRONG> en <STRONG>adUseClient</STRONG> para habilitar el Servicio de cursores para OLE DB, que se requiere para las actualizaciones por lotes.</span><span class="sxs-lookup"><span data-stu-id="0b440-p104">Although <STRONG>Supports</STRONG>(<STRONG>adUpdateBatch</STRONG>) may be true for dynamic and forward-only cursors, for batch updates you should use either a keyset or static cursor. Set the <A href="locktype-property-ado.md">LockType</A> property to <STRONG>adLockBatchOptimistic</STRONG> and the <STRONG>CursorLocation</STRONG> property to <STRONG>adUseClient</STRONG> to enable the Cursor Service for OLE DB, which is required for batch updates.</span></span></P>



<span data-ttu-id="0b440-129">La propiedad **CursorType** es de lectura y escritura cuando el objeto **Recordset** está cerrado, y es de sólo lectura cuando está abierto.</span><span class="sxs-lookup"><span data-stu-id="0b440-129">The **CursorType** property is read/write when the **Recordset** is closed and read-only when it is open.</span></span>

<span data-ttu-id="0b440-130">**Uso de servicio de datos remotos** Cuando se usa en un objeto Recordset de cliente, la propiedad **CursorType** puede establecerse sólo en **adOpenStatic**.</span><span class="sxs-lookup"><span data-stu-id="0b440-130">**Remote Data Service Usage**When used on a client-side Recordset object, the **CursorType** property can be set only to **adOpenStatic**.</span></span>
