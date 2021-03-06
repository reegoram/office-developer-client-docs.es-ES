---
title: Open (método, objeto Recordset de ADO)
TOCTitle: Open Method (ADO Recordset)
ms:assetid: 87ef19a4-28e1-dec7-ed33-4ae500b9c460
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249591(v=office.15)
ms:contentKeyID: 48546119
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: dd5a956d5a978a374e10c85e7803715f81d48f2a
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603081"
---
# <a name="open-method-ado-recordset"></a>Open (método, objeto Recordset de ADO)


**Se aplica a**: Access 2013 | Office 2013


Abre un cursor.

## <a name="syntax"></a>Sintaxis

*conjunto de registros*. Abrir*origen*, *ActiveConnection*, *CursorType*, *LockType*, *Opciones*

## <a name="parameters"></a>Parámetros

  - *Source*

  - Es opcional. Valor de tipo **Variant** que da como resultado un objeto [Command](command-object-ado.md) válido, una instrucción SQL, un nombre de tabla, una llamada a un procedimiento almacenado, una dirección URL, o bien el nombre de un archivo u objeto [Stream](stream-object-ado.md) que contiene un objeto [Recordset](recordset-object-ado.md) almacenado de manera persistente.

  - *ActiveConnection*

  - Es opcional. Valor de tipo **Variant** que da como resultado una variable de objeto [Connection](connection-object-ado.md) válida o valor de tipo **String** que contiene los parámetros [ConnectionString](connectionstring-property-ado.md).

  - *CursorType*

  - Es opcional. Valor de [CursorTypeEnum](cursortypeenum.md) que determina el tipo de cursor que el proveedor debe usar cuando se abre el objeto **Recordset**. El valor predeterminado es **adOpenForwardOnly**.

  - *LockType*

  - Es opcional. Valor de [LockTypeEnum](locktypeenum.md) que determina el tipo de bloqueo (concurrencia) que el proveedor debe utilizar cuando se abre el objeto **Recordset**. El valor predeterminado es **adLockReadOnly**.

  - *Options*

  - Es opcional. Un valor de **tipo Long** que indica cómo debe evaluar el proveedor el argumento *Source* si representa algo distinto de un objeto **Command** , o que el **objeto Recordset** debe restaurarse desde un archivo donde se guardó anteriormente. Puede ser uno o varios valores de [CommandTypeEnum](commandtypeenum.md) o [ExecuteOptionEnum](executeoptionenum.md), que se pueden combinar con un operador AND bit a bit.


> [!NOTE]
> <P>[!NOTA] Si abre un objeto <STRONG>Recordset</STRONG> de un objeto <STRONG>Stream</STRONG> que contiene un objeto <STRONG>Recordset</STRONG> almacenado, el uso del valor <STRONG>adAsyncFetchNonBlocking</STRONG> de <STRONG>ExecuteOptionEnum</STRONG> no tendrá ningún efecto; la recuperación será sincrónica y de bloqueo.</P>



Los valores **adExecuteNoRecords** y **adExecuteStream** de **ExecuteOpenEnum** no deben utilizarse con **Open**.

## <a name="remarks"></a>Comentarios

El cursor predeterminado de un objeto **Recordset** de ADO es un cursor de sólo avance y de sólo lectura ubicado en el servidor.

Si se utiliza el método **Open** en un objeto **Recordset**, se abre un cursor que representa los registros de una tabla base, los resultados de una consulta o un objeto **Recordset** anteriormente guardado.

Use el argumento *Source* opcional para especificar un origen de datos mediante uno de los siguientes: una variable del objeto **Command** , una instrucción SQL, un procedimiento almacenado, un nombre de tabla, una dirección URL o un nombre de ruta de acceso completa del archivo. Si el *origen* es un nombre de ruta de acceso de archivo, puede ser una ruta de acceso completa ("c:\\dir\\file.rst"), una ruta de acceso relativa ("... \\file.rst "), o una dirección URL ("https://files/file.rst").

<<<<<<< HEAD no resulta una buena idea utilizar el argumento *Source* del método **Open** para realizar una consulta de acción que no devuelve registros porque no hay ninguna forma sencilla de determinar si la llamada se ha realizado correctamente. El objeto **Recordset** devuelto por esa consulta se cerrará. Llame al método [Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) de un objeto **Command** o al método [Execute](https://msdn.microsoft.com/library/jj249832\(v=office.15\)) de un objeto **Connection** para realizar una consulta que no devuelve registros, como una instrucción SQL INSERT.
=== No resulta una buena idea utilizar el argumento *Source* del método **Open** para realizar una consulta de acción que no devuelve registros porque no hay ninguna forma sencilla de determinar si la llamada se ha realizado correctamente. El objeto **Recordset** devuelto por esa consulta se cerrará. Llame al método [Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) de un objeto **Command** o al método [Execute](https://msdn.microsoft.com/library/jj249832\(v=office.15\)) de un objeto **Connection** para realizar una consulta que no devuelve registros, como una instrucción SQL INSERT.
>>>>>>> master

El argumento *ActiveConnection* corresponde a la propiedad [ActiveConnection](activeconnection-property-ado.md) y especifica en qué conexión para abrir el **conjunto de registros** del objeto. Si pasa una definición de conexión para este argumento, ADO abre una conexión nueva con los parámetros especificados. Después de abrir el **objeto Recordset** con un cursor de cliente (**CursorLocation** = **adUseClient**), puede cambiar el valor de esta propiedad para enviar actualizaciones a otro proveedor. O bien, puede establecer el valor de esta propiedad en **Nothing** (en Microsoft Visual Basic) o en NULL para desconectar el objeto **Recordset** de todos los proveedores. Sin embargo, si se cambia el valor de **ActiveConnection** en el caso de un cursor de servidor, se generará un error.

Para los demás argumentos que se corresponden directamente con las propiedades de un objeto **Recordset** (*Source*, *CursorType* y *LockType*), la relación entre los argumentos y las propiedades es la siguiente:

  - La propiedad es de lectura y de escritura antes de abrirse el objeto **Recordset**.

  - Se utilizan los valores de configuración de las propiedades, a menos que se pasen los argumentos correspondientes cuando se ejecute el método **Open**. Si se pasa un argumento, éste invalida el valor de la propiedad correspondiente y el valor de la propiedad se actualiza con el valor del argumento.

  - Una vez abierto el objeto **Recordset**, estas propiedades son de solo lectura.


> [!NOTE]
> <P>[!NOTA] La propiedad <STRONG>ActiveConnection</STRONG> es de sólo lectura para los objetos <STRONG>Recordset</STRONG> cuya propiedad <A href="source-property-ado-recordset.md">Source</A> esté establecida en un objeto <STRONG>Command</STRONG> válido, incluso si no está abierto el objeto <STRONG>Recordset</STRONG>.</P>



Si se pasa un objeto **Command** en el argumento *Source* y también pasa un argumento *ActiveConnection* , se produce un error. La propiedad **ActiveConnection** del objeto **Command** ya debe estar establecida en un objeto **Connection** válido o en una cadena de conexión válida.

Si se pasa un valor distinto de un objeto **Command** en el argumento *Source* , puede usar el argumento *Options* para optimizar la evaluación del argumento *origen* . Si no se ha definido el argumento *Options* , puede experimentar una disminución del rendimiento porque ADO debe realizar llamadas al proveedor para determinar si el argumento es una instrucción SQL, un procedimiento almacenado, una dirección URL o un nombre de tabla. Si se conoce el tipo de *origen* , la configuración del argumento *Options* indica a ADO que salte directamente al código relevante. Si el argumento *Options* no coincide con el tipo de *origen* , se produce un error.

Si se pasa un objeto **Stream** en el argumento *Source* , no debe pasarse información en los demás argumentos. En caso contrario, se generará un error. La información de **ActiveConnection** no se conserva cuando se abre un objeto **Recordset** de un objeto **Stream**.

**AdCmdFile** es el valor predeterminado para el argumento *Options* si no hay ninguna conexión está asociada con el **conjunto de registros**. Este suele ser el caso para los objetos **Recordset** almacenados de manera persistente.

Si el origen de datos no devuelve ningún registro, el proveedor establece las propiedades [BOF](bof-eof-properties-ado.md) y [EOF](bof-eof-properties-ado.md) en **True**, y la posición de registro actual está sin definir. Se pueden agregar datos nuevos a este objeto **Recordset** vacío si el tipo de cursor lo permite.

Una vez finalizadas las operaciones en un objeto **Recordset** abierto, use el método [Close](close-method-ado.md) para liberar los recursos del sistema asociados. Cerrar un objeto no lo quita de la memoria; puede cambiar los valores de sus propiedades y volver a abrirlo más adelante mediante el método **Open**. Para eliminar completamente un objeto de la memoria, establezca el valor de la variable del objeto en *Nothing*.

Antes de establece la propiedad **ActiveConnection** , llame a **Open** sin operandos para crear una instancia de un **objeto Recordset** creado anexando campos a la colección de [campos](fields-collection-ado.md) del **objeto Recordset** .

Si el valor de la propiedad [CursorLocation](cursorlocation-property-ado.md) es **adUseClient**, se pueden recuperar las filas asincrónicamente de una sola manera. Es el método recomendado establecer *las opciones* en **adAsyncFetch**. Asimismo, se puede utilizar la propiedad dinámica "Asynchronous Rowset Processing" de la colección [Properties](properties-collection-ado.md), pero se pueden perder los eventos recuperados relacionados si no se establece el valor del parámetro **Options** en **adAsyncFetch**.


> [!NOTE]
> <P>Recuperación en segundo plano en el proveedor MS Remote se admite sólo a través del parámetro <EM>Options</EM> del método <STRONG>Open</STRONG> .</P>


<<<<<<< HEAD


> [!NOTE]
> <P>[!NOTA] Las direcciones URL que utilicen el esquema http invocarán automáticamente <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>. Para obtener más información, vea <A href="absolute-and-relative-urls.md">Direcciones URL absolutas y relativas</A>.</P>
=======
> [!NOTE]
> [!NOTA] Las direcciones URL que utilicen el esquema http invocarán automáticamente [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md). Para obtener más información, vea [direcciones URL absolutas y relativas](absolute-and-relative-urls.md).
>>>>>>> master


