---
title: EliminarRegistro (acción de macro)
TOCTitle: DeleteRecord Macro Action
ms:assetid: c656a72c-c037-76a5-dc07-f6eccb6590dd
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823132(v=office.15)
ms:contentKeyID: 48547624
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 536369082a5abb94914d78d8bc64c5f9b45e8b0d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485560"
---
# <a name="deleterecord-macro-action"></a>EliminarRegistro (acción de macro)

**Se aplica a**: Access 2013 | Office 2013

Puede usar la acción **EliminarRegistro** para eliminar un registro.

## <a name="setting"></a>Valores

El bloque de datos **CrearRegistro** tiene los siguientes argumentos.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Argumento</p></th>
<th><p>Descripción</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Alias del registro</strong></p></td>
<td><p>Una cadena que identifica el registro que hay que eliminar. Si no se especifica el argumento <em>Alias</em>, se elimina el registro actual.</p></td>
</tr>
</tbody>
</table>

## <a name="remarks"></a>Comentarios

Puede utilizar la variable local **ÚltimaIdentidadDeRegistroCreada** para trabajar con el último registro creado en un bloque de datos **CrearRegistro**. Por ejemplo, utilice la siguiente sintaxis para hacer referencia al registro creado más recientemente:

`[LastCreateRecordIdentity]`

