---
title: MoveRecordOptionsEnum
TOCTitle: MoveRecordOptionsEnum
ms:assetid: 2785bca0-777c-a802-51d7-6f5cf0fb4210
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249039(v=office.15)
ms:contentKeyID: 48543842
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 41ec6eaf39545bf8a71f443a8e3b90052a74f1de
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486262"
---
# <a name="moverecordoptionsenum"></a><span data-ttu-id="d89b9-102">MoveRecordOptionsEnum</span><span class="sxs-lookup"><span data-stu-id="d89b9-102">MoveRecordOptionsEnum</span></span>


<span data-ttu-id="d89b9-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="d89b9-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="d89b9-104">Especifica el comportamiento del método [MoveRecord](record-object-ado.md) del objeto [Record](moverecord-method-ado.md).</span><span class="sxs-lookup"><span data-stu-id="d89b9-104">Specifies the behavior of the [Record](record-object-ado.md) object [MoveRecord](moverecord-method-ado.md) method.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d89b9-105">Constante</span><span class="sxs-lookup"><span data-stu-id="d89b9-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="d89b9-106">Valor</span><span class="sxs-lookup"><span data-stu-id="d89b9-106">Value</span></span></p></th>
<th><p><span data-ttu-id="d89b9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d89b9-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d89b9-108"><strong>adMoveUnspecified</strong></span><span class="sxs-lookup"><span data-stu-id="d89b9-108"><strong>adMoveUnspecified</strong></span></span></p></td>
<td><p><span data-ttu-id="d89b9-109">-1</span><span class="sxs-lookup"><span data-stu-id="d89b9-109">-1</span></span></p></td>
<td><p><span data-ttu-id="d89b9-p101">Valor predeterminado. Realiza la operación mover predeterminada: la operación falla si el archivo o el directorio de destino ya existen; por otro lado, la operación actualiza los vínculos de hipertexto.</span><span class="sxs-lookup"><span data-stu-id="d89b9-p101">Default. Performs the default move operation: The operation fails if the destination file or directory already exists, and the operation updates hypertext links.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89b9-112"><strong>adMoveOverWrite</strong></span><span class="sxs-lookup"><span data-stu-id="d89b9-112"><strong>adMoveOverWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="d89b9-113">1</span><span class="sxs-lookup"><span data-stu-id="d89b9-113">1</span></span></p></td>
<td><p><span data-ttu-id="d89b9-114">Sobrescribe el archivo o el directorio de destino, incluso si ya existen.</span><span class="sxs-lookup"><span data-stu-id="d89b9-114">Overwrites the destination file or directory, even if it already exists.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d89b9-115"><strong>adMoveDontUpdateLinks</strong></span><span class="sxs-lookup"><span data-stu-id="d89b9-115"><strong>adMoveDontUpdateLinks</strong></span></span></p></td>
<td><p><span data-ttu-id="d89b9-116">2</span><span class="sxs-lookup"><span data-stu-id="d89b9-116">2</span></span></p></td>
<td><p><span data-ttu-id="d89b9-p102">Modifica el comportamiento predeterminado del método <strong>MoveRecord</strong>, no actualizando los vínculos de hipertexto del <strong>Record</strong> de origen. El comportamiento predeterminado depende de las capacidades del proveedor. La operación mover actualiza los vínculos si el proveedor es capaz. Si el proveedor no puede reparar vínculos, o si no se especifica este valor, entonces la operación de movimiento funcionará incluso aunque los vínculos no se hayan reparado.</span><span class="sxs-lookup"><span data-stu-id="d89b9-p102">Modifies the default behavior of <strong>MoveRecord</strong> method by not updating the hypertext links of the source <strong>Record</strong>. The default behavior depends on the capabilities of the provider. Move operation updates links if the provider is capable. If the provider cannot fix links or if this value is not specified, then the move succeeds even when links have not been fixed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89b9-121"><strong>adMoveAllowEmulation</strong></span><span class="sxs-lookup"><span data-stu-id="d89b9-121"><strong>adMoveAllowEmulation</strong></span></span></p></td>
<td><p><span data-ttu-id="d89b9-122">4</span><span class="sxs-lookup"><span data-stu-id="d89b9-122">4</span></span></p></td>
<td><p><span data-ttu-id="d89b9-p103">Solicita que el proveedor intente simular la operación de movimiento (mediante operaciones de descarga, carga y eliminación). Si el intento de mover el <strong>Record</strong> falla debido a que la dirección URL de destino está en un servidor diferente o atendida por un proveedor diferente del de origen, esto puede ocasionar un aumento de latencia o pérdida de datos debido a diferencias de capacidades de los proveedores al mover recursos entre ellos.</span><span class="sxs-lookup"><span data-stu-id="d89b9-p103">Requests that the provider attempt to simulate the move (using download, upload, and delete operations). If the attempt to move the <strong>Record</strong> fails because the destination URL is on a different server or serviced by a different provider than the source, this may cause increased latency or data loss, due to different provider capabilities when moving resources between providers.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d89b9-125">**Equivalente ADO/WFC**</span><span class="sxs-lookup"><span data-stu-id="d89b9-125">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="d89b9-126">Estas constantes no tienen equivalentes ADO/WFC.</span><span class="sxs-lookup"><span data-stu-id="d89b9-126">These constants do not have ADO/WFC equivalents.</span></span>
