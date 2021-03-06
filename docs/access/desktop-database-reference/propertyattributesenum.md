---
title: PropertyAttributesEnum
TOCTitle: PropertyAttributesEnum
ms:assetid: cbe93f65-a3ee-4741-1ac7-1c98ac53cdde
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250012(v=office.15)
ms:contentKeyID: 48547726
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8f01efcc98ed12858712c28f080fb066d3dc1b41
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484611"
---
# <a name="propertyattributesenum"></a>PropertyAttributesEnum


**Se aplica a**: Access 2013 | Office 2013

Especifica los atributos de un objeto [Property](property-object-ado.md).

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
<td><p><strong>adPropNotSupported</strong></p></td>
<td><p>0</p></td>
<td><p>Indica que la propiedad no es admitida por el proveedor.</p></td>
</tr>
<tr class="even">
<td><p><strong>adPropRequired</strong></p></td>
<td><p>1</p></td>
<td><p>Indica que el usuario debe especificar un valor para esta propiedad antes de que se inicialice el origen de datos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>adPropOptional</strong></p></td>
<td><p>2</p></td>
<td><p>Indica que el usuario no necesita especificar un valor para esta propiedad antes de que se inicialice el origen de datos.</p></td>
</tr>
<tr class="even">
<td><p><strong>adPropRead</strong></p></td>
<td><p>512</p></td>
<td><p>Indica que el usuario puede leer la propiedad.</p></td>
</tr>
<tr class="odd">
<td><p><strong>adPropWrite</strong></p></td>
<td><p>1024</p></td>
<td><p>Indica que el usuario puede establecer la propiedad.</p></td>
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
<td><p>AdoEnums.PropertyAttributes.NOTSUPPORTED</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.PropertyAttributes.REQUIRED</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.PropertyAttributes.OPTIONAL</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.PropertyAttributes.READ</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.PropertyAttributes.WRITE</p></td>
</tr>
</tbody>
</table>

