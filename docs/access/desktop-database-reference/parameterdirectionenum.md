---
title: ParameterDirectionEnum
TOCTitle: ParameterDirectionEnum
ms:assetid: 73a97522-010e-d8f4-1a30-15df2469cad4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249473(v=office.15)
ms:contentKeyID: 48545643
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b3da089a1369905b78d1a0724990afc22eb1d0dc
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484247"
---
# <a name="parameterdirectionenum"></a>ParameterDirectionEnum


**Se aplica a**: Access 2013 | Office 2013

Especifica si el objeto [Parameter](parameter-object-ado.md) representa un parámetro de entrada, un parámetro de salida, ambos o el valor devuelto desde un procedimiento almacenado.

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
<td><p><strong>adParamInput</strong></p></td>
<td><p>1</p></td>
<td><p>Valor predeterminado. Indica que el parámetro representa un parámetro de entrada.</p></td>
</tr>
<tr class="even">
<td><p><strong>adParamInputOutput</strong></p></td>
<td><p>3</p></td>
<td><p>Indica que el parámetro representa un parámetro de entrada y de salida.</p></td>
</tr>
<tr class="odd">
<td><p><strong>adParamOutput</strong></p></td>
<td><p>2</p></td>
<td><p>Indica que el parámetro representa un parámetro de salida.</p></td>
</tr>
<tr class="even">
<td><p><strong>adParamReturnValue</strong></p></td>
<td><p>4</p></td>
<td><p>Indica que el parámetro representa un valor devuelto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>adParamUnknown</strong></p></td>
<td><p>0</p></td>
<td><p>Indica que se desconoce la dirección del parámetro.</p></td>
</tr>
</tbody>
</table>


**Equivalente ADO/WFC**

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
<td><p>AdoEnums.ParameterDirection.INPUT</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ParameterDirection.INPUTOUTPUT</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ParameterDirection.OUTPUT</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ParameterDirection.RETURNVALUE</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ParameterDirection.UNKNOWN</p></td>
</tr>
</tbody>
</table>

