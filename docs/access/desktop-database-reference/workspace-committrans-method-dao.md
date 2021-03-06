---
title: Workspace.CommitTrans Method (DAO)
TOCTitle: CommitTrans Method
ms:assetid: e6d129fb-a578-5c79-9c16-6444519f0daf
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835985(v=office.15)
ms:contentKeyID: 48548391
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 149727c7f7424a7508edb21bf486e6148cd12295
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25483536"
---
# <a name="workspacecommittrans-method-dao"></a>Workspace.CommitTrans Method (DAO)

**Se aplica a**: Access 2013 | Office 2013

Finaliza la transacción actual y guarda los cambios.

## <a name="syntax"></a>Sintaxis

*expresión* . CommitTrans (***Opciones***)

*expresión* Variable que representa un objeto **Workspace** .

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
<td><p>Opción</p></td>
<td><p>Opcional</p></td>
<td><p><strong>Long</strong></p></td>
<td><p>En un área de trabajo de Microsoft Access, puede incluir la constante <strong>dbForceOSFlush</strong> con <strong>CommitTrans</strong>. Esto fuerza al motor de base de datos a guardar de inmediato todas las actualizaciones en el disco, en lugar de guardarlas en la caché temporalmente. Si no utiliza esta opción, un usuario podría recuperar el control de inmediato después de que el programa de aplicación llame a <strong>CommitTrans</strong>, apagar el equipo y no haber escrito los datos en el disco. Aunque el uso de esta opción puede afectar al rendimiento de la aplicación, es útil en situaciones en las que el equipo puede apagarse antes de guardar en el disco las actualizaciones de la memoria caché.</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>Observaciones

Los métodos de transacción **BeginTrans**, **CommitTrans** y **Rollback** dirigen el procesamiento de las transacciones durante una sesión definida por un objeto **Workspace**. Utiliza estos métodos con un objeto **Workspace** cuando desea tratar una serie de cambios realizados en las bases de datos en una sesión como una sola unidad.

En general, las transacciones se utilizan para mantener la integridad de los datos cuando debe actualizar registros en dos o más tablas y asegurarse de que se han completado los cambios (se han aplicado) en todas las tablas o en ninguna (se han deshecho). Por ejemplo, si ha transferido dinero de una cuenta a otra, debe restar una cantidad de otra y sumar la cantidad a otra. Si alguna de las actualizaciones no se realiza correctamente, las cuentas ya no están equilibradas. Utilice el método **BeginTrans** antes de actualizar el primer registro y, luego, si no se realiza correctamente cualquier actualización posterior, puede utilizar el método **Rollback** para deshacer todas las actualizaciones. Utilice el método **CommitTrans** después de actualizar correctamente el último registro.

> [!NOTE]
> [!NOTA] Dentro de un objeto **Workspace**, las transacciones son siempre globales para **Workspace** y no están limitadas a un único objeto **Connection** o **Database**. Si realiza operaciones en varias conexiones o bases de datos dentro de una transacción de **Workspace**, la resolución de la transacción (es decir, el uso del método **CommitTrans** o **Rollback**) afecta a todas las operaciones de todas las conexiones y bases de datos incluidos en esta área de trabajo.

Tras utilizar **CommitTrans**, no puede deshacer los cambios realizados durante esta transacción a menos que la transacción esté anidada dentro de otra transacción que, a su vez, se haya deshecho. Si anida transacciones, debe resolver la transacción activa antes de poder resolver una transacción en un nivel de anidamiento superior.

Si desea tener transacciones simultáneas con ámbitos superpuestos y no anidados, debe crear objetos **Workspace** adicionales para contener las transacciones simultáneas.

Si cierra un objeto **Workspace** sin resolver las transacciones pendientes, las transacciones se deshacen automáticamente.

Si utiliza el método **CommitTrans** o **Rollback** sin utilizar primero el método **BeginTrans**, se produce un error.

Es posible que algunas bases de datos ISAM usadas en un área de trabajo de Microsoft Access no admitan transacciones, en este caso la propiedad **Transactions** del objeto **Database** o **Recordset** es **False**. Para asegurarse de que la base de datos admite transacciones, compruebe el valor de la propiedad **Transactions** del objeto **Database** antes de usar el método **BeginTrans**. Si usa un objeto **Recordset** basado en varias bases de datos, compruebe la propiedad **Transactions** del objeto **Recordset**. 

Si un objeto **Recordset** está totalmente basado en tablas del motor de base de datos de Microsoft Access, siempre puede usar transacciones. Es posible, no obstante, que los objetos **Recordset** basados en tablas creadas por otros productos de bases de datos no admitan transacciones. Por ejemplo, no puede utilizar transacciones en un objeto **Recordset** basado en una tabla Parados. En este caso, la propiedad **Transactions** es **False**. Si el objeto **Database** o **Recordset** no admite transacciones, los métodos se omiten y no se producen errores.

No puede anidar transacciones si tiene acceso a orígenes de datos ODBC a través del motor de base de datos de Microsoft Access.

En áreas de trabajo de ODBC, cuando usa **CommitTrans**, es posible que el cursor ya no sea válido. Use el método **Requery** para ver los cambios en **Recordset** o cierre y vuelva a abrir **Recordset**.

> [!NOTE]
> - A menudo, puede mejorar el rendimiento de su aplicación segmentando las operaciones que requieren acceso al disco en bloques de transacciones. Esto guarda en el búfer las operaciones y puede reducir significativamente el número de veces que se tiene acceso a un disco.
> - En un área de trabajo de Microsoft Access, las transacciones se registran en un archivo que se guarda en el directorio especificado por la variable de entorno TEMP en la estación de trabajo. Si el archivo de registro de transacciones agota el almacenamiento disponible en la unidad TEMP, el motor de base de datos activa un error en tiempo de ejecución. En ese momento, si utiliza **CommitTrans**, se aplica un número indeterminado de operaciones pero se pierden las operaciones restantes que no se hayan completado y es necesario reiniciar la operación. El uso del método **Rollback** libera el registro de transacciones y deshace todas las operaciones de la transacción.
> - Cerrar un objeto **Recordset** clon con una transacción pendiente provoca una operación **Rollback** implícita.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, se muestra cómo usar una transacción en un área de trabajo de objetos de acceso a datos (DAO).

**Código de ejemplo proporcionado por** la [referencia del programador de Microsoft Access 2010](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).


```vb
    Public Sub TransferFunds()
        Dim wrk As DAO.Workspace
        Dim dbC As DAO.Database
        Dim dbX As DAO.Database
        
        Set wrk = DBEngine(0)
        Set dbC = CurrentDb
        Set dbX = wrk.OpenDatabase("e:\books\acc2007vba\myDB.accdb")
        
        On Error GoTo trans_Err
        
        'Begin the transaction
        
        wrk.BeginTrans
        
        'Withdraw funds from one account table
        dbC.Execute "INSERT INTO tblAccounts ( Amount, Txn, TxnDate ) SELECT -20, 'DEBIT', Date()", dbFailOnError
    
        'Deposit funds into another account table
        dbX.Execute "INSERT INTO tblAccounts ( Amount, Txn, TxnDate ) SELECT 20, 'CREDIT', Date()", dbFailOnError
        
        'Commit the transaction
        wrk.CommitTrans dbForceOSFlush
        
    trans_Exit:
        'Clean up
        wrk.Close
        Set dbC = Nothing
        Set dbX = Nothing
        Set wrk = Nothing
        Exit Sub
        
    trans_Err:
        'Roll back the transaction
        wrk.Rollback
        Resume trans_Exit
        
    End Sub
```
