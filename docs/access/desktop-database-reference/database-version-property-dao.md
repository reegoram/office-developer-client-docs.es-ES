---
title: Database.Version Property (DAO)
TOCTitle: Version Property
ms:assetid: 40faaa0c-e764-e968-f606-7e06ded80c3f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192887(v=office.15)
ms:contentKeyID: 48544440
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4bcb360caa71131f4892409805c7afe3ceb2dcce
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486670"
---
# <a name="databaseversion-property-dao"></a>Database.Version Property (DAO)


**Se aplica a**: Access 2013 | Office 2013

En un área de trabajo de Microsoft Access, devuelve la versión del motor de base de datos de Microsoft Jet o Microsoft Access que creó la base de datos. **String** de solo lectura.

## <a name="syntax"></a>Sintaxis

*expresión* . Versión

*expresión* Variable que representa un objeto de **base de datos** .

## <a name="remarks"></a>Observaciones

El valor devuelto es un valor de tipo String que da como resultado un número de versión, con el formato siguiente.

  - El área de trabajo de Microsoft Access representa el número de versión en la forma "*principal.secundario*". Por ejemplo, "3.0". El número de versión del producto consta del número de versión (3), un punto y el número de publicación (0).

En la tabla siguiente se muestra la versión del motor de base de datos que se incluye en diversas versiones de productos de Microsoft.

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Motor de base de datos</p></th>
<th><p>Versión (año de publicación)</p></th>
<th><p>Microsoft Access</p></th>
<th><p>Microsoft Visual Basic</p></th>
<th><p>Microsoft Excel</p></th>
<th><p>Microsoft Visual C++</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft Jet</p></td>
<td><p>1.0 (1992)</p></td>
<td><p>1.0</p></td>
<td><p>N/D</p></td>
<td><p>N/D</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Jet</p></td>
<td><p>1.1 (1993)</p></td>
<td><p>1.1</p></td>
<td><p>3.0</p></td>
<td><p>N/D</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Jet</p></td>
<td><p>2.0 (1994)</p></td>
<td><p>2.0</p></td>
<td><p>N/D</p></td>
<td><p>N/D</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Jet</p></td>
<td><p>2.5 (1995)</p></td>
<td><p>N/D</p></td>
<td><p>4.0 (16 bits)</p></td>
<td><p>N/D</p></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Jet</p></td>
<td><p>3.0 (1995)</p></td>
<td><p>' 95 (7.0)</p></td>
<td><p>4.0 (32 bits)</p></td>
<td><p>' 95 (7.0)</p></td>
<td><p>4.x</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Jet</p></td>
<td><p>3.5 (1996)</p></td>
<td><p>' 97 (8.0)</p></td>
<td><p>5.0</p></td>
<td><p>' 97 (8.0)</p></td>
<td><p>5.0</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Jet</p></td>
<td><p>4.0 (2000)</p></td>
<td><p>2000 (9.0)</p></td>
<td><p></p></td>
<td><p>2000 (9.0)</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Motor de base de datos de Microsoft Access</p></td>
<td><p>12.0 (2007)</p></td>
<td><p>2007</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

