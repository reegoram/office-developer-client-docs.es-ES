---
title: RecordStatusEnum (referencia de escritorio de la base de datos de Access)
TOCTitle: RecordStatusEnum
ms:assetid: 302915b8-494d-0be2-6dce-eaf91a0ea8ae
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249080(v=office.15)
ms:contentKeyID: 48544022
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 88929ced56583316c42f2d5195054e51e98a1d5b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484730"
---
# <a name="recordstatusenum"></a>RecordStatusEnum


**Se aplica a**: Access 2013 | Office 2013

Especifica el estado de un registro con respecto a actualizaciones por lotes y otras operaciones masivas.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Constante</p></th>
<th><p>Valor</p></th>
<th><p>Descripción</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adRecCanceled</strong></p></td>
<td><p>0 x 100</p></td>
<td><p>Indica que no se guardó el registro porque se canceló la operación.</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecCantRelease</strong></p></td>
<td><p>0 x 400</p></td>
<td><p>Indica que no se guardó el nuevo registro porque el registro existente estaba bloqueado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecConcurrencyViolation</strong></p></td>
<td><p>0 x 800</p></td>
<td><p>Indica que no se guardó el registro porque se estaba aplicando concurrencia optimista.</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecDBDeleted</strong></p></td>
<td><p>0 x 40000</p></td>
<td><p>Indica que el registro ya se ha eliminado del origen de datos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecDeleted</strong></p></td>
<td><p>0 x 4</p></td>
<td><p>Indica que se eliminó el registro.</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecIntegrityViolation</strong></p></td>
<td><p>0x1000</p></td>
<td><p>Indica que no se guardó el registro porque el usuario infringió restricciones de integridad.</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecInvalid</strong></p></td>
<td><p>0 x 10</p></td>
<td><p>Indica que no se guardó el registro porque su marcador no es válido.</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecMaxChangesExceeded</strong></p></td>
<td><p>0 x 2000</p></td>
<td><p>Indica que no se guardó el registro porque había demasiados cambios pendientes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecModified</strong></p></td>
<td><p>0x2</p></td>
<td><p>Indica que se modificó el registro.</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecMultipleChanges</strong></p></td>
<td><p>0 x 40</p></td>
<td><p>Indica que el registro no se guardó debido a que habría afectado a varios registros.</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecNew</strong></p></td>
<td><p>0x1</p></td>
<td><p>Indica que el registro es nuevo.</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecObjectOpen</strong></p></td>
<td><p>0x4000</p></td>
<td><p>Indica que no se guardó el registro debido a un conflicto con un objeto de almacenamiento abierto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecOK</strong></p></td>
<td><p>0</p></td>
<td><p>Indica que el registro se actualizó correctamente.</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecOutOfMemory</strong></p></td>
<td><p>0 x 8000</p></td>
<td><p>Indica que no se guardó el registro a causa de que el equipo se ha quedado sin memoria.</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecPendingChanges</strong></p></td>
<td><p>0 x 80</p></td>
<td><p>Indica que no se guardó el registro debido a que hace referencia a una inserción pendiente.</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecPermissionDenied</strong></p></td>
<td><p>0 x 10000</p></td>
<td><p>Indica que no se guardó el registro porque el usuario no tiene permisos suficientes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRecSchemaViolation</strong></p></td>
<td><p>0 x 20000</p></td>
<td><p>Indica que el registro no se guardó debido a que no satisface la estructura de la base de datos subyacente.</p></td>
</tr>
<tr class="even">
<td><p><strong>adRecUnmodified</strong></p></td>
<td><p>0 x 8</p></td>
<td><p>Indica que no se modificó el registro.</p></td>
</tr>
</tbody>
</table>


**Equivalente ADO/WFC**

AdoEnums.RecordStatus.

Paquete: **com.ms.wfc.data**

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Constante</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AdoEnums.RecordStatus.CANCELED</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.RecordStatus.CANTRELEASE</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.RecordStatus.CONCURRENCYVIOLATION</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.RecordStatus.DBDELETED</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.RecordStatus.DELETED</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.RecordStatus.INTEGRITYVIOLATION</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.RecordStatus.INVALID</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.RecordStatus.MAXCHANGESEXCEEDED</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.RecordStatus.MODIFIED</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.RecordStatus.MULTIPLECHANGES</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.RecordStatus.NEW</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.RecordStatus.OBJECTOPEN</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.RecordStatus.OK</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.RecordStatus.OUTOFMEMORY</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.RecordStatus.PENDINGCHANGES</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.RecordStatus.PERMISSIONDENIED</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.RecordStatus.SCHEMAVIOLATION</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.RecordStatus.UNMODIFIED</p></td>
</tr>
</tbody>
</table>

