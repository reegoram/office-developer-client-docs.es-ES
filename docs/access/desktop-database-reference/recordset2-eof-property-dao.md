---
title: Recordset2.EOF Property (DAO)
TOCTitle: EOF Property
ms:assetid: 9d4e1ee2-e866-3ebf-e08b-b31b0cb47ed9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198245(v=office.15)
ms:contentKeyID: 48546622
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052886
f1_categories:
- Office.Version=v15
ms.openlocfilehash: abb99f58b151c9bafe554486f8b6f1308322560f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485252"
---
# <a name="recordset2eof-property-dao"></a><span data-ttu-id="f70f4-102">Recordset2.EOF Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="f70f4-102">Recordset2.EOF Property (DAO)</span></span>


<span data-ttu-id="f70f4-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="f70f4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="f70f4-p101">Devuelve un valor que indica si la posición actual del registro se encuentra después del último registro en un objeto **Recordset**. **Boolean** de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="f70f4-p101">Returns a value that indicates whether the current record position is after the last record in a **Recordset** object. Read-only **Boolean**.</span></span>

## <a name="syntax"></a><span data-ttu-id="f70f4-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f70f4-106">Syntax</span></span>

<span data-ttu-id="f70f4-107">*expresión* . EOF</span><span class="sxs-lookup"><span data-stu-id="f70f4-107">*expression* .EOF</span></span>

<span data-ttu-id="f70f4-108">*expresión* Variable que representa un objeto **Recordset2** .</span><span class="sxs-lookup"><span data-stu-id="f70f4-108">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="f70f4-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f70f4-109">Remarks</span></span>

<span data-ttu-id="f70f4-110">Puede usar las propiedades **BOF** y **EOF** para determinar si un objeto **Recordset** contiene registros o si se desplazó más allá de los límites de un objeto **Recordset** cuando se mueve de un registro a otro.</span><span class="sxs-lookup"><span data-stu-id="f70f4-110">You can use the **BOF** and **EOF** properties to determine whether a **Recordset** object contains records or whether you've gone beyond the limits of a **Recordset** object when you move from record to record.</span></span>

<span data-ttu-id="f70f4-111">La ubicación del puntero de registro actual determina los valores **BOF** y **EOF** devueltos.</span><span class="sxs-lookup"><span data-stu-id="f70f4-111">The location of the current record pointer determines the **BOF** and **EOF** return values.</span></span>

<span data-ttu-id="f70f4-112">Si la propiedad **BOF** o **EOF** es **True**, no hay ningún registro actual.</span><span class="sxs-lookup"><span data-stu-id="f70f4-112">If either the **BOF** or **EOF** property is **True**, there is no current record.</span></span>

<span data-ttu-id="f70f4-p102">Si abre un objeto **Recordset** sin registros, las propiedades **BOF** y **EOF** se configuran en **True**, y el valor de la propiedad **RecordCount** del objeto **Recordset** será 0. Si abre un objeto **Recordset** con al menos un registro, el primer registro será el registro actual, y las propiedades **BOF** y **EOF** serán **False**; estas serán **False** hasta que se desplace más allá del principio o del final del objeto **Recordset** mediante el método **MovePrevious** o **MoveNext**, respectivamente. Cuando se desplace más allá del principio o del final del **Recordset**, no habrá registro actual o no existirá ningún registro.</span><span class="sxs-lookup"><span data-stu-id="f70f4-p102">If you open a **Recordset** object containing no records, the **BOF** and **EOF** properties are set to **True**, and the **Recordset** object's **RecordCount** property setting is 0. When you open a **Recordset** object that contains at least one record, the first record is the current record and the **BOF** and **EOF** properties are **False**; they remain **False** until you move beyond the beginning or end of the **Recordset** object by using the **MovePrevious** or **MoveNext** method, respectively. When you move beyond the beginning or end of the **Recordset**, there is no current record or no record exists.</span></span>

<span data-ttu-id="f70f4-116">Si elimina el último registro que queda en el objeto **Recordset**, puede que el valor de las propiedades **BOF** y **EOF** siga siendo **False** hasta que intente ajustar la posición del registro actual.</span><span class="sxs-lookup"><span data-stu-id="f70f4-116">If you delete the last remaining record in the **Recordset** object, the **BOF** and **EOF** properties may remain **False** until you attempt to reposition the current record.</span></span>

<span data-ttu-id="f70f4-p103">Si usa el método **MoveLast** en un objeto **Recordset** que contiene registros, el último registro será el registro actual; si usa el método **MoveNext**, el registro actual no será válido y la propiedad **EOF** se configurará en **True**. A la inversa, si usa el método **MoveFirst** en un objeto **Recordset** que contiene registros, el primer registró será el registro actual; si usa el método **MovePrevious**, no habrá registro actual y la propiedad **BOF** se configurará en **True**.</span><span class="sxs-lookup"><span data-stu-id="f70f4-p103">If you use the **MoveLast** method on a **Recordset** object containing records, the last record becomes the current record; if you then use the **MoveNext** method, the current record becomes invalid and the **EOF** property is set to **True**. Conversely, if you use the **MoveFirst** method on a **Recordset** object containing records, the first record becomes the current record; if you then use the **MovePrevious** method, there is no current record and the **BOF** property is set to **True**.</span></span>

<span data-ttu-id="f70f4-119">Generalmente al trabajar con todos los registros en un objeto **Recordset**, el código repetirá los registros con el método **MoveNext** hasta que la propiedad **EOF** se configure en **True**.</span><span class="sxs-lookup"><span data-stu-id="f70f4-119">Typically, when you work with all the records in a **Recordset** object, your code will loop through the records by using the **MoveNext** method until the **EOF** property is set to **True**.</span></span>

<span data-ttu-id="f70f4-120">Si usa el método **MoveNext** mientras la propiedad **EOF** se configura en **True**, o usa el método **MovePrevious** mientras la propiedad **BOF** se configura en **True**, se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="f70f4-120">If you use the **MoveNext** method while the **EOF** property is set to **True** or the **MovePrevious** method while the **BOF** property is set to **True**, an error occurs.</span></span>

<span data-ttu-id="f70f4-121">En esta tabla se muestran los métodos Move permitidos con diferentes combinaciones de las propiedades **BOF** y **EOF**.</span><span class="sxs-lookup"><span data-stu-id="f70f4-121">This table shows which Move methods are allowed with different combinations of the **BOF** and **EOF** properties.</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><p></p></th>
<th><p><span data-ttu-id="f70f4-122">Métodos MoveFirst,</span><span class="sxs-lookup"><span data-stu-id="f70f4-122">MoveFirst,</span></span><br />
<span data-ttu-id="f70f4-123">MoveLast</span><span class="sxs-lookup"><span data-stu-id="f70f4-123">MoveLast</span></span></p></th>
<th><p><span data-ttu-id="f70f4-124">MovePrevious,</span><span class="sxs-lookup"><span data-stu-id="f70f4-124">MovePrevious,</span></span><br />
<span data-ttu-id="f70f4-125">Mover &lt; 0</span><span class="sxs-lookup"><span data-stu-id="f70f4-125">Move &lt; 0</span></span></p></th>
<th><p><br />
<span data-ttu-id="f70f4-126">Move 0</span><span class="sxs-lookup"><span data-stu-id="f70f4-126">Move 0</span></span></p></th>
<th><p><span data-ttu-id="f70f4-127">MoveNext,</span><span class="sxs-lookup"><span data-stu-id="f70f4-127">MoveNext,</span></span><br />
<span data-ttu-id="f70f4-128">Mover &gt; 0</span><span class="sxs-lookup"><span data-stu-id="f70f4-128">Move &gt; 0</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f70f4-129"><strong>BOF = True,</strong></span><span class="sxs-lookup"><span data-stu-id="f70f4-129"><strong>BOF=True,</strong></span></span><br /><span data-ttu-id="f70f4-130">
<strong>EOF = False</strong></span><span class="sxs-lookup"><span data-stu-id="f70f4-130">
<strong>EOF=False</strong></span></span></p></td>
<td><p><span data-ttu-id="f70f4-131">Permitido</span><span class="sxs-lookup"><span data-stu-id="f70f4-131">Allowed</span></span></p></td>
<td><p><span data-ttu-id="f70f4-132">Error</span><span class="sxs-lookup"><span data-stu-id="f70f4-132">Error</span></span></p></td>
<td><p><span data-ttu-id="f70f4-133">Error</span><span class="sxs-lookup"><span data-stu-id="f70f4-133">Error</span></span></p></td>
<td><p><span data-ttu-id="f70f4-134">Permitido</span><span class="sxs-lookup"><span data-stu-id="f70f4-134">Allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f70f4-135"><strong>BOF = False,</strong></span><span class="sxs-lookup"><span data-stu-id="f70f4-135"><strong>BOF=False,</strong></span></span><br /><span data-ttu-id="f70f4-136">
<strong>EOF = True</strong></span><span class="sxs-lookup"><span data-stu-id="f70f4-136">
<strong>EOF=True</strong></span></span></p></td>
<td><p><span data-ttu-id="f70f4-137">Permitido</span><span class="sxs-lookup"><span data-stu-id="f70f4-137">Allowed</span></span></p></td>
<td><p><span data-ttu-id="f70f4-138">Permitido</span><span class="sxs-lookup"><span data-stu-id="f70f4-138">Allowed</span></span></p></td>
<td><p><span data-ttu-id="f70f4-139">Error</span><span class="sxs-lookup"><span data-stu-id="f70f4-139">Error</span></span></p></td>
<td><p><span data-ttu-id="f70f4-140">Error</span><span class="sxs-lookup"><span data-stu-id="f70f4-140">Error</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f70f4-141">Ambas propiedades son <strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="f70f4-141">Both <strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="f70f4-142">Error</span><span class="sxs-lookup"><span data-stu-id="f70f4-142">Error</span></span></p></td>
<td><p><span data-ttu-id="f70f4-143">Error</span><span class="sxs-lookup"><span data-stu-id="f70f4-143">Error</span></span></p></td>
<td><p><span data-ttu-id="f70f4-144">Error</span><span class="sxs-lookup"><span data-stu-id="f70f4-144">Error</span></span></p></td>
<td><p><span data-ttu-id="f70f4-145">Error</span><span class="sxs-lookup"><span data-stu-id="f70f4-145">Error</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f70f4-146">Ambas propiedades son <strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="f70f4-146">Both <strong>False</strong></span></span></p></td>
<td><p><span data-ttu-id="f70f4-147">Permitido</span><span class="sxs-lookup"><span data-stu-id="f70f4-147">Allowed</span></span></p></td>
<td><p><span data-ttu-id="f70f4-148">Permitido</span><span class="sxs-lookup"><span data-stu-id="f70f4-148">Allowed</span></span></p></td>
<td><p><span data-ttu-id="f70f4-149">Permitido</span><span class="sxs-lookup"><span data-stu-id="f70f4-149">Allowed</span></span></p></td>
<td><p><span data-ttu-id="f70f4-150">Permitido</span><span class="sxs-lookup"><span data-stu-id="f70f4-150">Allowed</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f70f4-p104">Permitir un método Move no significa que ese método se ubique correctamente en un registro. Simplemente indica que se permite un intento para realizar el método Move especificado y que no se producirá un error. El estado de las propiedades **BOF** y **EOF** puede cambiar como resultado del intento de Move.</span><span class="sxs-lookup"><span data-stu-id="f70f4-p104">Allowing a Move method doesn't mean that the method will successfully locate a record. It merely indicates that an attempt to perform the specified Move method is allowed and won't generate an error. The state of the **BOF** and **EOF** properties may change as a result of the attempted Move.</span></span>

<span data-ttu-id="f70f4-p105">Un método **OpenRecordset** invoca internamente a un método **MoveFirst**. Por tanto, usar un método **OpenRecordset** en un conjunto de registros vacío, configura las propiedades **BOF** y **EOF** en **True**. (En la siguiente tabla puede ver el comportamiento de un método **MoveFirst** cuando se produce un error).</span><span class="sxs-lookup"><span data-stu-id="f70f4-p105">An **OpenRecordset** method internally invokes a **MoveFirst** method. Therefore, using an **OpenRecordset** method on an empty set of records sets the **BOF** and **EOF** properties to **True**. (See the following table for the behavior of a failed **MoveFirst** method.)</span></span>

<span data-ttu-id="f70f4-157">Todos los métodos Move que se ubican correctamente en un registro, configurarán **BOF** y **EOF** en **False**.</span><span class="sxs-lookup"><span data-stu-id="f70f4-157">All Move methods that successfully locate a record will set both **BOF** and **EOF** to **False**.</span></span>

<span data-ttu-id="f70f4-158">En un área de trabajo de Microsoft Access, si agrega un registro a un **Recordset** vacío, **BOF** será **False**, pero **EOF** seguirá en **True**, lo que indica que la posición actual se encuentra al final del **Recordset**.</span><span class="sxs-lookup"><span data-stu-id="f70f4-158">In a Microsoft Access workspace, if you add a record to an empty **Recordset**, **BOF** will become **False**, but **EOF** will remain **True**, indicating that the current position is at the end of **Recordset**.</span></span>

<span data-ttu-id="f70f4-159">Cualquier método **Delete**, incluso si quita el único registro de un **Recordset**, no cambiará la configuración de la propiedad **BOF** o **EOF**.</span><span class="sxs-lookup"><span data-stu-id="f70f4-159">Any **Delete** method, even if it removes the only remaining record from a **Recordset**, won't change the setting of the **BOF** or **EOF** property.</span></span>

<span data-ttu-id="f70f4-160">En la siguiente tabla se muestra cómo los métodos Move que no han ubicado un registro afectan a la configuración de las propiedades **BOF** y **EOF**.</span><span class="sxs-lookup"><span data-stu-id="f70f4-160">The following table shows how Move methods that don't locate a record affect the **BOF** and **EOF** property settings.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p></p></th>
<th><p><span data-ttu-id="f70f4-161">BOF</span><span class="sxs-lookup"><span data-stu-id="f70f4-161">BOF</span></span></p></th>
<th><p><span data-ttu-id="f70f4-162">EOF</span><span class="sxs-lookup"><span data-stu-id="f70f4-162">EOF</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f70f4-163"><strong>Métodos MoveFirst</strong>, <strong>MoveLast</strong></span><span class="sxs-lookup"><span data-stu-id="f70f4-163"><strong>MoveFirst</strong>, <strong>MoveLast</strong></span></span></p></td>
<td><p><span data-ttu-id="f70f4-164"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="f70f4-164"><strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="f70f4-165"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="f70f4-165"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f70f4-166"><strong>Move</strong> 0</span><span class="sxs-lookup"><span data-stu-id="f70f4-166"><strong>Move</strong> 0</span></span></p></td>
<td><p><span data-ttu-id="f70f4-167">No cambia</span><span class="sxs-lookup"><span data-stu-id="f70f4-167">No change</span></span></p></td>
<td><p><span data-ttu-id="f70f4-168">No cambia</span><span class="sxs-lookup"><span data-stu-id="f70f4-168">No change</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f70f4-169"><strong>MovePrevious</strong>, <strong>mueva</strong> &lt; 0</span><span class="sxs-lookup"><span data-stu-id="f70f4-169"><strong>MovePrevious</strong>, <strong>Move</strong> &lt; 0</span></span></p></td>
<td><p><span data-ttu-id="f70f4-170"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="f70f4-170"><strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="f70f4-171">No cambia</span><span class="sxs-lookup"><span data-stu-id="f70f4-171">No change</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f70f4-172"><strong>MoveNext</strong>, <strong>mueva</strong> &gt; 0</span><span class="sxs-lookup"><span data-stu-id="f70f4-172"><strong>MoveNext</strong>, <strong>Move</strong> &gt; 0</span></span></p></td>
<td><p><span data-ttu-id="f70f4-173">No cambia</span><span class="sxs-lookup"><span data-stu-id="f70f4-173">No change</span></span></p></td>
<td><p><span data-ttu-id="f70f4-174"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="f70f4-174"><strong>True</strong></span></span></p></td>
</tr>
</tbody>
</table>
