---
title: Eventos de ActiveX Data Objects (ADO)
TOCTitle: ADO Events
ms:assetid: 84ca9525-99cb-4ba6-2a4d-172414b8f0cc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249576(v=office.15)
ms:contentKeyID: 48546041
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5938ed58e3b0074f69a4380fd4a0ac0be857084b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486386"
---
# <a name="ado-events"></a>Eventos de ADO


**Se aplica a**: Access 2013 | Office 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><a href="begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado.md">BeginTransComplete</a></p></td>
<td><p>Se utiliza (recibe una llamada) después de la operación <strong>BeginTrans</strong>.</p></td>
</tr>
<tr class="even">
<td><p><a href="begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado.md">CommitTransComplete</a></p></td>
<td><p>Se utiliza (recibe una llamada) después de la operación <strong>CommitTrans</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><a href="connectcomplete-and-disconnect-events-ado.md">ConnectComplete</a></p></td>
<td><p>Se utiliza (recibe una llamada) después de iniciar una conexión.</p></td>
</tr>
<tr class="even">
<td><p><a href="connectcomplete-and-disconnect-events-ado.md">Desconectar</a></p></td>
<td><p>Se utiliza (recibe una llamada) después de finalizar una conexión.</p></td>
</tr>
<tr class="odd">
<td><p><a href="endofrecordset-event-ado.md">EndOfRecordset</a></p></td>
<td><p>Se usa (recibe una llamada) cuando se produce un intento de mover una fila más allá del final del objeto <strong>Recordset</strong>.</p></td>
</tr>
<tr class="even">
<td><p><a href="executecomplete-event-ado.md">ExecuteComplete</a></p></td>
<td><p>Se utiliza (recibe una llamada) después de que un comando ha terminado de ejecutarse.</p></td>
</tr>
<tr class="odd">
<td><p><a href="fetchcomplete-event-ado.md">FetchComplete</a></p></td>
<td><p>Se usa (recibe una llamada) después de que todos los registros implicados en una operación asincrónica prolongada se recuperaron e insertado en el objeto <strong>Recordset</strong>.</p></td>
</tr>
<tr class="even">
<td><p><a href="fetchprogress-event-ado.md">FetchProgress</a></p></td>
<td><p>Se usa (recibe una llamada) periódicamente durante una operación asincrónica prolongada para informar de cuántas filas se recuperaron e insertado actualmente en el objeto <strong>Recordset</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><a href="willchangefield-and-fieldchangecomplete-events-ado.md">FieldChangeComplete</a></p></td>
<td><p>Se utiliza (recibe una llamada) después de que el valor de uno o varios objetos <strong>Field</strong> haya cambiado.</p></td>
</tr>
<tr class="even">
<td><p><a href="infomessage-event-ado.md">InfoMessage</a></p></td>
<td><p>Se utiliza (recibe una llamada) siempre que se produce una advertencia durante una operación <strong>ConnectionEvent</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><a href="willmove-and-movecomplete-events-ado.md">MoveComplete</a></p></td>
<td><p>Se usa (recibe una llamada) después de un cambio de la posición actual en el objeto <strong>Recordset</strong>.</p></td>
</tr>
<tr class="even">
<td><p><a href="willchangerecord-and-recordchangecomplete-events-ado.md">RecordChangeComplete</a></p></td>
<td><p>Se utiliza (recibe una llamada) después de cambiar uno o más registros.</p></td>
</tr>
<tr class="odd">
<td><p><a href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">RecordsetChangeComplete</a></p></td>
<td><p>Se usa (recibe una llamada) después de un cambio en el objeto <strong>Recordset</strong>.</p></td>
</tr>
<tr class="even">
<td><p><a href="begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado.md">A RollbackTransComplete</a></p></td>
<td><p>Se utiliza (recibe una llamada) después de la operación <strong>RollbackTrans</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><a href="willchangefield-and-fieldchangecomplete-events-ado.md">WillChangeField</a></p></td>
<td><p>Se utiliza (recibe una llamada) antes de que una operación pendiente cambie el valor de uno o varios objetos <strong>Field</strong> en el objeto <strong>Recordset</strong>.</p></td>
</tr>
<tr class="even">
<td><p><a href="willchangerecord-and-recordchangecomplete-events-ado.md">WillChangeRecord</a></p></td>
<td><p>Se usa (recibe una llamada) antes de cambiar uno o más registros (filas) en el objeto <strong>Recordset</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><a href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">WillChangeRecordset</a></p></td>
<td><p>Se usa (recibe una llamada) antes de que una operación pendiente cambie el objeto <strong>Recordset</strong>.</p></td>
</tr>
<tr class="even">
<td><p><a href="willconnect-event-ado.md">WillConnect</a></p></td>
<td><p>Se utiliza (recibe una llamada) antes de iniciar una conexión.</p></td>
</tr>
<tr class="odd">
<td><p><a href="willexecute-event-ado.md">WillExecute</a></p></td>
<td><p>Se utiliza (recibe una llamada) antes de que un comando pendiente se ejecute en esta conexión y ofrece al usuario una oportunidad de examinar y modificar los parámetros de la ejecución.</p></td>
</tr>
<tr class="even">
<td><p><a href="willmove-and-movecomplete-events-ado.md">WillMove</a></p></td>
<td><p>El evento <strong>WillMove recibe</strong> se denomina <em>antes de</em> una operación pendiente cambie la posición actual en el <strong>conjunto de registros</strong>.</p></td>
</tr>
</tbody>
</table>

