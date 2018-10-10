---
title: Status (propiedad, Recordset ADO)
TOCTitle: Status Property (ADO Recordset)
ms:assetid: bf3ccb36-c985-5fae-4f76-c48a0e20e6f7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249930(v=office.15)
ms:contentKeyID: 48547482
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1ce4e3fc2d879521bbe1bbdb34d203a640fbe06c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25483600"
---
# <a name="status-property-ado-recordset"></a><span data-ttu-id="04bb7-102">Status (propiedad, Recordset ADO)</span><span class="sxs-lookup"><span data-stu-id="04bb7-102">Status Property (ADO Recordset)</span></span>


<span data-ttu-id="04bb7-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="04bb7-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="04bb7-104">Indica el estado del registro actual con respecto a actualizaciones por lotes u otras operaciones masivas.</span><span class="sxs-lookup"><span data-stu-id="04bb7-104">Indicates the status of the current record with respect to batch updates or other bulk operations.</span></span>

## <a name="return-value"></a><span data-ttu-id="04bb7-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="04bb7-105">Return Value</span></span>

<span data-ttu-id="04bb7-106">Devuelve una suma de uno o más valores [RecordStatusEnum](recordstatusenum.md).</span><span class="sxs-lookup"><span data-stu-id="04bb7-106">Returns a sum of one or more [RecordStatusEnum](recordstatusenum.md) values.</span></span>

## <a name="remarks"></a><span data-ttu-id="04bb7-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04bb7-107">Remarks</span></span>

<span data-ttu-id="04bb7-p101">Use la propiedad **Status** para ver los cambios pendientes en los registros modificados durante la actualización por lotes. La propiedad **Status** también se puede usar para ver el estado de registros que producen error durante operaciones masivas, por ejemplo al llamar a los métodos [Resync](resync-method-ado.md), [UpdateBatch](updatebatch-method-ado.md) o [CancelBatch](cancelbatch-method-ado.md) de un objeto [Recordset](recordset-object-ado.md) o al establecer la propiedad [Filter](filter-property-ado.md) de un objeto **Recordset** en una matriz de marcadores. Con esta propiedad, es posible determinar cómo se produjo el error de un registro determinado y solucionarlo en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="04bb7-p101">Use the **Status** property to see what changes are pending for records modified during batch updating. You can also use the **Status** property to view the status of records that fail during bulk operations, such as when you call the [Resync](resync-method-ado.md), [UpdateBatch](updatebatch-method-ado.md), or [CancelBatch](cancelbatch-method-ado.md) methods on a [Recordset](recordset-object-ado.md) object, or set the [Filter](filter-property-ado.md) property on a **Recordset** object to an array of bookmarks. With this property, you can determine how a given record failed and resolve it accordingly.</span></span>
