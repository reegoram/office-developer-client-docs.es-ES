---
title: Recordset2.MoveNext Method (DAO)
TOCTitle: MoveNext Method
ms:assetid: 0eeb917e-f76a-03ec-9e1e-aa8d501db031
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845265(v=office.15)
ms:contentKeyID: 48543254
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fd6eddf9f9b41223603887bb038bf2c9bd227031
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485419"
---
# <a name="recordset2movenext-method-dao"></a><span data-ttu-id="2878d-102">Recordset2.MoveNext Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="2878d-102">Recordset2.MoveNext Method (DAO)</span></span>


<span data-ttu-id="2878d-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="2878d-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="2878d-104">Se desplaza al siguiente registro de un objeto **Recordset** especificado y convierte ese registro en el registro activo.</span><span class="sxs-lookup"><span data-stu-id="2878d-104">Moves to the next record in a specified **Recordset** object and make that record the current record.</span></span>

## <a name="syntax"></a><span data-ttu-id="2878d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2878d-105">Syntax</span></span>

<span data-ttu-id="2878d-106">*expresión* . MoveNext</span><span class="sxs-lookup"><span data-stu-id="2878d-106">*expression* .MoveNext</span></span>

<span data-ttu-id="2878d-107">*expresión* Variable que representa un objeto **Recordset2** .</span><span class="sxs-lookup"><span data-stu-id="2878d-107">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="2878d-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2878d-108">Remarks</span></span>

<span data-ttu-id="2878d-109">Utilice los métodos **Move** para desplazarse de un registro a otro sin aplicar una condición.</span><span class="sxs-lookup"><span data-stu-id="2878d-109">Use the **Move** methods to move from record to record without applying a condition.</span></span>

<span data-ttu-id="2878d-p101">Si edita el registro activo, asegúrese de que utiliza el método **Update** para guardar los cambios antes de moverse a otro registro. Si se desplaza a otro registro sin ejecutar una actualización, los cambios se pierden sin advertencia.</span><span class="sxs-lookup"><span data-stu-id="2878d-p101">If you edit the current record, be sure you use the **Update** method to save the changes before you move to another record. If you move to another record without updating, your changes are lost without warning.</span></span>

<span data-ttu-id="2878d-p102">Cuando abre un objeto **Recordset**, el primer registro es el activo y la propiedad **BOF** es **False**. Si **Recordset** no contiene registros, la propiedad **BOF** es **True** y no hay ningún registro activo.</span><span class="sxs-lookup"><span data-stu-id="2878d-p102">When you open a **Recordset**, the first record is current and the **BOF** property is **False**. If the **Recordset** contains no records, the **BOF** property is **True**, and there is no current record.</span></span>

<span data-ttu-id="2878d-p103">Si utiliza **MoveNext** cuando el último registro está activo, la propiedad **EOF** es **True** y no hay registro activo. Si utiliza **MoveNext** de nuevo, se produce un error y **EOF** sigue siendo **True**.</span><span class="sxs-lookup"><span data-stu-id="2878d-p103">If you use **MoveNext** when the last record is current, the **EOF** property is **True**, and there is no current record. If you use **MoveNext** again, an error occurs, and **EOF** remains **True**.</span></span>

<span data-ttu-id="2878d-116">Si el objeto recordset hace referencia a un **objeto Recordset** de tipo tabla (sólo áreas de trabajo de Microsoft Access), el desplazamiento sigue el índice actual.</span><span class="sxs-lookup"><span data-stu-id="2878d-116">If recordset refers to a table-type **Recordset** (Microsoft Access workspaces only), movement follows the current index.</span></span> <span data-ttu-id="2878d-117">Puede definir el índice actual mediante la propiedad **Index**.</span><span class="sxs-lookup"><span data-stu-id="2878d-117">You can set the current index by using the **Index** property.</span></span> <span data-ttu-id="2878d-118">Si no define el índice actual, el orden de los registros devueltos queda sin definir.</span><span class="sxs-lookup"><span data-stu-id="2878d-118">If you don't set the current index, the order of returned records is undefined.</span></span>

<span data-ttu-id="2878d-119">No puede usar los métodos **MoveFirst**, **MoveLast**ni **MovePrevious** en un objeto **Recordset** de tipo forward – only.</span><span class="sxs-lookup"><span data-stu-id="2878d-119">You can't use the **MoveFirst**, **MoveLast**, and **MovePrevious** methods on a forward–only–type **Recordset** object.</span></span>

<span data-ttu-id="2878d-120">Para mover hacia delante o hacia atrás la posición del registro actual en un objeto **Recordset** un número determinado de registros, use el método **Move**.</span><span class="sxs-lookup"><span data-stu-id="2878d-120">To move the position of the current record in a **Recordset** object a specific number of records forward or backward, use the **Move** method.</span></span>
