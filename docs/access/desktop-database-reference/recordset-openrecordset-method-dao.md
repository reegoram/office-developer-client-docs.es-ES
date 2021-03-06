---
title: Método Recordset.OpenRecordset (DAO)
TOCTitle: OpenRecordset Method
ms:assetid: 7d5ca4d5-5a0b-c0c8-d8e8-2c4e6c5f361f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196402(v=office.15)
ms:contentKeyID: 48545853
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 223612be0b2fca457c9aa78af0394c19574096f0
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "25606524"
---
# <a name="recordsetopenrecordset-method-dao"></a>Método Recordset.OpenRecordset (DAO)


**Se aplica a**: Access 2013 | Office 2013

Crea un nuevo objeto **[Recordset](recordset-object-dao.md)** y lo anexa a la colección **Recordsets**.

## <a name="syntax"></a>Sintaxis

*expresión* . OpenRecordset (***tipo***, ***las opciones de***)

*expresión* Variable que representa un objeto **Recordset** .

### <a name="parameters"></a>Parámetros

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Nombre</p></th>
<th><p>Necesario/Opcional</p></th>
<th><p>Tipo de datos</p></th>
<th><p>Descripción</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre</p></td>
<td><p>Obligatorio</p></td>
<td><p><strong>String</strong></p></td>
<td><p>Origen de los registros para el nuevo <strong>Recordset</strong>. El origen puede ser un nombre de tabla o de consulta, o una instrucción SQL que devuelve registros. Para los objetos <strong>Recordset</strong> de tipo tabla en las bases de datos del motor de base de datos de Microsoft Access, el origen solo puede ser un nombre de tabla.  </p></td>
</tr>
<tr class="even">
<td><p>Tipo</p></td>
<td><p>Opcional</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>Una constante <strong><a href="recordsettypeenum-enumeration-dao.md">RecordsetTypeEnum</a></strong> que indica el tipo de <strong>Recordset</strong> para abrir.</p>

> [!NOTE]
> <P>Si abre un <STRONG>Recordset</STRONG> en un área de trabajo de Microsoft Access y no especifica un tipo, <STRONG>OpenRecordset</STRONG> crea un <STRONG>Recordset</STRONG> de tipo tabla, si es posible. Si especifica una tabla o una consulta vinculada, <STRONG>OpenRecordset</STRONG> crea un <STRONG>Recordset</STRONG> de tipo conjunto de registros dinámicos.</P>


</td>
</tr>
<tr class="odd">
<td><p>Options</p></td>
<td><p>Opcional</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>Una combinación de constantes <strong><a href="recordsetoptionenum-enumeration-dao.md">RecordsetOptionEnum</a></strong> que especifica las características del nuevo <strong>Recordset</strong>.</p>

> [!NOTE]
> <P>Las constantes <STRONG>dbConsistent</STRONG> y <STRONG>dbInconsistent</STRONG> son mutuamente exclusivas, y usar las dos producirá un error. Proporcionar un argumento lockedits cuando las opciones usan la constante <STRONG>dbReadOnly</STRONG> también produce un error.</P>


</td>
</tr>
<tr class="even">
<td><p>LockEdit</p></td>
<td><p>Opcional</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>Una constante <strong><a href="locktypeenum-enumeration-dao.md">LockTypeEnum</a></strong> que determina el bloqueo de <strong>Recordset</strong>.</p>

> [!NOTE]
> <P>Puede usar <STRONG>dbReadOnly</STRONG> en el argumento options o en el argumento lockedits, pero no en ambos. Si lo usa para los dos argumentos, ocurre un error en tiempo de ejecución.</P>


</td>
</tr>
</tbody>
</table>


<<<<<<< HEAD
### <a name="return-value"></a>Valor devuelto
=======
### <a name="return-value"></a>Valor devuelto
>>>>>>> master

Recordset

## <a name="remarks"></a>Comentarios

En general, si el usuario obtiene este error mientras actualiza un registro, el código debe actualizar el contenido de los campos y recuperar los valores recién modificados. Si el error se produce al eliminar un registro, el código puede mostrar los nuevos datos de registros al usuario y un mensaje en el que se indica que los datos han cambiado recientemente. En ese momento, el código puede pedir una confirmación de que aún se desea eliminar el registro.

Debe usar también la constante **dbSeeChanges** si abre un objeto **Recordset** en el área de trabajo de ODBC conectado por el motor de base de datos de Microsoft Access contra una tabla de Microsoft SQL Server 6.0 (o posterior) que tiene una columna IDENTITY o, de lo contrario, puede producirse un error.

Al abrir más de un objeto **Recordset** en un origen de datos ODBC, se puede producir un error si la conexión está ocupada con una llamada **OpenRecordset** anterior. Un modo de solucionar este problema es rellenar completamente el objeto **Recordset** mediante el método **MoveLast** en cuanto se abra el objeto **Recordset**.

Cerrar un objeto **Recordset** con el método **[Close](connection-close-method-dao.md)** lo elimina automáticamente de la colección **Recordsets**.


> [!NOTE]
> <P>Si <EM>origen</EM> hace referencia a una instrucción SQL consta de una cadena que se concatena con un valor no entero, y los parámetros del sistema especifican un carácter decimal que no sean-US como una coma (por ejemplo, strSQL = "PRICE &gt; " &amp; lngPrice y lngPrice = 125,50), se produce un error al intentar abrir el <STRONG>conjunto de registros</STRONG>. Esto se debe a que, durante la concatenación, el número se convierte en una cadena con el carácter decimal predeterminado del sistema, y SQL solo acepta los caracteres decimales de Estados Unidos.</P>


