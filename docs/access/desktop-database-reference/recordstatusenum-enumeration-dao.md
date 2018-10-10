---
title: RecordStatusEnum Enumeration (DAO)
TOCTitle: RecordStatusEnum Enumeration
ms:assetid: bf4492f2-8d8f-f10f-7a3c-d6296d2ce96b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822784(v=office.15)
ms:contentKeyID: 48547483
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 78f86e8c80a6bbc09499e9512e2daee87fc67998
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484363"
---
# <a name="recordstatusenum-enumeration-dao"></a><span data-ttu-id="bcc05-102">RecordStatusEnum Enumeration (DAO)</span><span class="sxs-lookup"><span data-stu-id="bcc05-102">RecordStatusEnum Enumeration (DAO)</span></span>


<span data-ttu-id="bcc05-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="bcc05-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="bcc05-104">Se utiliza con la propiedad **RecordStatus** para indicar el estado de actualización del registro actual si forma parte de una actualización por lotes.</span><span class="sxs-lookup"><span data-stu-id="bcc05-104">Used with the **RecordStatus** property to indicate the update status of the current record if it is part of a batch update.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bcc05-105">Nombre</span><span class="sxs-lookup"><span data-stu-id="bcc05-105">Name</span></span></p></th>
<th><p><span data-ttu-id="bcc05-106">Valor</span><span class="sxs-lookup"><span data-stu-id="bcc05-106">Value</span></span></p></th>
<th><p><span data-ttu-id="bcc05-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bcc05-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bcc05-108">dbRecordDBDeleted</span><span class="sxs-lookup"><span data-stu-id="bcc05-108">dbRecordDBDeleted</span></span></p></td>
<td><p><span data-ttu-id="bcc05-109">4</span><span class="sxs-lookup"><span data-stu-id="bcc05-109">4</span></span></p></td>
<td><p><span data-ttu-id="bcc05-110">El registro se ha eliminado localmente y en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bcc05-110">The record has been deleted locally and in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcc05-111">dbRecordDeleted</span><span class="sxs-lookup"><span data-stu-id="bcc05-111">dbRecordDeleted</span></span></p></td>
<td><p><span data-ttu-id="bcc05-112">3</span><span class="sxs-lookup"><span data-stu-id="bcc05-112">3</span></span></p></td>
<td><p><span data-ttu-id="bcc05-113">El registro se ha eliminado, pero permanece todavía en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bcc05-113">The record has been deleted, but not yet deleted in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcc05-114">dbRecordModified</span><span class="sxs-lookup"><span data-stu-id="bcc05-114">dbRecordModified</span></span></p></td>
<td><p><span data-ttu-id="bcc05-115">1</span><span class="sxs-lookup"><span data-stu-id="bcc05-115">1</span></span></p></td>
<td><p><span data-ttu-id="bcc05-116">El registro se ha modificado y no se ha actualizado en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bcc05-116">The record has been modified and not updated in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcc05-117">dbRecordNew</span><span class="sxs-lookup"><span data-stu-id="bcc05-117">dbRecordNew</span></span></p></td>
<td><p><span data-ttu-id="bcc05-118">2</span><span class="sxs-lookup"><span data-stu-id="bcc05-118">2</span></span></p></td>
<td><p><span data-ttu-id="bcc05-119">El registro se ha insertado con el método <strong>AddNew</strong>, pero no se ha insertado todavía en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bcc05-119">The record has been inserted with the <strong>AddNew</strong> method, but not yet inserted into the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcc05-120">dbRecordUnmodified</span><span class="sxs-lookup"><span data-stu-id="bcc05-120">dbRecordUnmodified</span></span></p></td>
<td><p><span data-ttu-id="bcc05-121">0</span><span class="sxs-lookup"><span data-stu-id="bcc05-121">0</span></span></p></td>
<td><p><span data-ttu-id="bcc05-122">(Valor predeterminado) El registro no se ha modificado o se ha actualizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bcc05-122">(Default) The record has not been modified or has been updated successfully.</span></span></p></td>
</tr>
</tbody>
</table>
