---
title: CancelUpdate (método, ADO)
TOCTitle: CancelUpdate Method (ADO)
ms:assetid: 2bd4d168-ba52-7786-5046-44febeda88e1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249065(v=office.15)
ms:contentKeyID: 48543938
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6aaf4a7e9c94864c5cdd43ad764a305c248718b4
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486393"
---
# <a name="cancelupdate-method-ado"></a><span data-ttu-id="7d856-102">CancelUpdate (método, ADO)</span><span class="sxs-lookup"><span data-stu-id="7d856-102">CancelUpdate Method (ADO)</span></span>


<span data-ttu-id="7d856-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="7d856-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="7d856-104">Cancela los cambios realizados en la fila activa o fila nueva de un objeto [Recordset](recordset-object-ado.md), o bien, la colección [Fields](fields-collection-ado.md) de un objeto [Record](record-object-ado.md), antes de llamar al método [Update](update-method-ado.md).</span><span class="sxs-lookup"><span data-stu-id="7d856-104">Cancels any changes made to the current or new row of a [Recordset](recordset-object-ado.md) object, or the [Fields](fields-collection-ado.md) collection of a [Record](record-object-ado.md) object, before calling the [Update](update-method-ado.md) method.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d856-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d856-105">Syntax</span></span>

<span data-ttu-id="7d856-106">*conjunto de registros*. CancelUpdate</span><span class="sxs-lookup"><span data-stu-id="7d856-106">*recordset*.CancelUpdate</span></span>

<span data-ttu-id="7d856-107">*registro*. *Los campos*. CancelUpdate</span><span class="sxs-lookup"><span data-stu-id="7d856-107">*record*.*Fields*.CancelUpdate</span></span>

## <a name="remarks"></a><span data-ttu-id="7d856-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7d856-108">Remarks</span></span>

<span data-ttu-id="7d856-109">**Recordset**</span><span class="sxs-lookup"><span data-stu-id="7d856-109">**Recordset**</span></span>

<span data-ttu-id="7d856-p101">Utilice el método **CancelUpdate** para cancelar los cambios realizados en la fila actual o descartar una fila recién agregada. No puede cancelar los cambios realizados en la fila actual o una fila nueva después de llamar al método **Update**, a menos que los cambios formen parte de una transacción que puede deshacer con el método [RollbackTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md), o bien, formen parte de una actualización por lotes. En este último caso, puede cancelar el método **Update** con el método **CancelUpdate** o [CancelBatch](cancelbatch-method-ado.md).</span><span class="sxs-lookup"><span data-stu-id="7d856-p101">Use the **CancelUpdate** method to cancel any changes made to the current row or to discard a newly added row. You cannot cancel changes to the current row or a new row after you call the **Update** method, unless the changes are either part of a transaction that you can roll back with the [RollbackTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) method, or part of a batch update. In the case of a batch update, you can cancel the **Update** with the **CancelUpdate** or [CancelBatch](cancelbatch-method-ado.md) method.</span></span>

<span data-ttu-id="7d856-113">Si está agregando una fila nueva al llamar al método **CancelUpdate**, la actual fila pasa a ser la fila que era actual antes de la llamada a [AddNew](addnew-method-ado.md).</span><span class="sxs-lookup"><span data-stu-id="7d856-113">If you are adding a new row when you call the **CancelUpdate** method, the current row becomes the row that was current before the [AddNew](addnew-method-ado.md) call.</span></span>

<span data-ttu-id="7d856-p102">Si está en modo de edición y desea salir del registro actual (por ejemplo, con [Move](move-method-ado.md), [NextRecordset](nextrecordset-method-ado.md) o [Close](close-method-ado.md)), puede usar **CancelUpdate** para cancelar los cambios pendientes. Quizás tenga que hacer esto si la actualización no se puede enviar correctamente al origen de datos (por ejemplo, un intento de eliminación que genera un error debido a infracciones de la integridad referencial dejará el objeto **Recordset** en modo de edición después de una llamada a [Delete](delete-method-ado-recordset.md)).</span><span class="sxs-lookup"><span data-stu-id="7d856-p102">If you are in edit mode and want to move off the current record (for example, with [Move](move-method-ado.md), [NextRecordset](nextrecordset-method-ado.md), or [Close](close-method-ado.md)), you can use **CancelUpdate** to cancel any pending changes. You may need to do this if the update cannot successfully be posted to the data source (for example, an attempted delete that fails due to referential integrity violations will leave the **Recordset** in edit mode after a call to [Delete](delete-method-ado-recordset.md)).</span></span>

<span data-ttu-id="7d856-116">**Record**</span><span class="sxs-lookup"><span data-stu-id="7d856-116">**Record**</span></span>

<span data-ttu-id="7d856-p103">El método **CancelUpdate** cancela todas las inserciones o eliminaciones pendientes de los objetos [Field](field-object-ado.md), además de cancelar las actualizaciones pendientes de los campos existentes y restaurar sus valores originales. La propiedad [Status](status-property-ado-recordset.md) de todos los campos de la colección **Fields** se establece en **adFieldOK**.</span><span class="sxs-lookup"><span data-stu-id="7d856-p103">The **CancelUpdate** method cancels any pending insertions or deletions of [Field](field-object-ado.md) objects, and cancels pending updates of existing fields and restores them to their original values. The [Status](status-property-ado-recordset.md) property of all fields in the **Fields** collection is set to **adFieldOK**.</span></span>
