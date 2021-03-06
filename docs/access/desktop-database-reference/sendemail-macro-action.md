---
title: EnviarCorreoElectrónico (acción de macro)
TOCTitle: SendEmail Macro Action
ms:assetid: 84ff6b46-d239-4716-9964-5b909656d347
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196780(v=office.15)
ms:contentKeyID: 48546046
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: db82c2d0c8350d517044df5848f8c264b92e928d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484392"
---
# <a name="sendemail-macro-action"></a>EnviarCorreoElectrónico (acción de macro)


**Se aplica a**: Access 2013 | Office 2013

La acción **EnviarCorreoElectrónico** envía un mensaje de correo electrónico.


> [!NOTE]
> <P>[!NOTA] La acción <STRONG>EnviarCorreoElectrónico</STRONG> solo está disponible en macros de datos.</P>



## <a name="setting"></a>Valores

La acción **EnviarCorreoElectrónico** utiliza los siguientes argumentos.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Argumento</p></th>
<th><p>Obligatorio</p></th>
<th><p>Descripción</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>To</strong></p></td>
<td><p>Sí</p></td>
<td><p>Los destinatarios del mensaje cuyos nombres desee indicar en la línea <strong>para</strong> del mensaje. Separe los nombres de los destinatarios que especifique en este argumento (y en los argumentos <em>Cc</em> y <em>CCO</em> ) con un punto y coma (;).</p></td>
</tr>
<tr class="even">
<td><p><strong>CC</strong></p></td>
<td><p>No</p></td>
<td><p>Los destinatarios del mensaje cuyos nombres desee indicar en el campo Cc (&quot;copia carbón&quot;) línea del mensaje.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Bcc</strong></p></td>
<td><p>No</p></td>
<td><p>Los destinatarios del mensaje cuyos nombres desee indicar en la CCO (&quot;copia carbón oculta&quot;) línea del mensaje.</p></td>
</tr>
<tr class="even">
<td><p><strong>Subject</strong></p></td>
<td><p>No</p></td>
<td><p>Asunto del mensaje. Este texto aparece en la línea <strong>Asunto</strong> del mensaje.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Body</strong></p></td>
<td><p>No</p></td>
<td><p>El texto que desea incluir en el cuerpo principal del mensaje de correo. Si deja en blanco este argumento, no se incluirá ningún texto adicional en el mensaje.</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>Comentarios

La acción **EnviarCorreoElectrónico** solo está disponible en los eventos de macro **[Después de eliminar](after-delete-macro-event.md)**, **[Después de insertar](after-insert-macro-event.md)** y **[Después de actualizar](after-update-macro-event.md)**.

La acción **EnviarCorreoElectrónico** no muestra el mensaje para su edición.

