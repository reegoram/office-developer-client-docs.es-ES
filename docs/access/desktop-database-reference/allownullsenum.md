---
title: AllowNullsEnum (referencia de escritorio de la base de datos de Access)
TOCTitle: AllowNullsEnum
ms:assetid: 7bb42b38-6b3b-5930-b1d7-16323a3bdf37
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249515(v=office.15)
ms:contentKeyID: 48545819
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 04e67584e0f0c2eeb5a12e34fdf98a84cc1da852
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485006"
---
# <a name="allownullsenum"></a>AllowNullsEnum


**Se aplica a**: Access 2013 | Office 2013

Especifica si se indizan registros con valores nulos.

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
<td><p><strong>adIndexNullsAllow</strong></p></td>
<td><p>0</p></td>
<td><p>El índice sí permite entradas en las que las columnas clave son nulas.

Si se escribe un valor nulo en una columna clave, la entrada se inserta en el índice.</p></td>
</tr>
<tr class="even">
<td><p><strong>adIndexNullsDisallow</strong></p></td>
<td><p>1</p></td>
<td><p>Valor predeterminado.

El índice no permite entradas en las que las columnas clave son nulas.

Si se escribe un valor nulo en una columna clave, se producirá un error.</p></td>
</tr>
<tr class="odd">
<td><p><strong>adIndexNullsIgnore</strong></p></td>
<td><p>2</p></td>
<td><p>El índice no inserta entradas que contengan claves nulas.

Si se escribe un valor nulo en una columna clave, la entrada se omite y no se produce ningún error.</p></td>
</tr>
<tr class="even">
<td><p><strong>adIndexNullsIgnoreAny</strong></p></td>
<td><p>4</p></td>
<td><p>El índice no inserta entradas en las que alguna columna clave contenga un valor nulo.

Para un índice que tenga una clave de varias columnas, si se escribe un valor nulo en alguna columna, la entrada se omite y no se produce ningún error.</p></td>
</tr>
</tbody>
</table>

