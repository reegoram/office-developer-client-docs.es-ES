---
title: Detalles sobre HelloData (referencia de escritorio de la base de datos de Access)
TOCTitle: HelloData Details
ms:assetid: db51e15c-1b5b-c64a-2f84-34dd0e78c6cf
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250105(v=office.15)
ms:contentKeyID: 48548103
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c25197f0a8a45487f93f56543f73a2beeea062ff
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603158"
---
# <a name="hellodata-details"></a>Detalles sobre HelloData


**Se aplica a**: Access 2013 | Office 2013

La aplicación HelloData realiza las operaciones básicas de una aplicación ADO típica: obtener, examinar, editar y actualizar datos. Cuando inicie la aplicación, haga clic en el primer botón, **Obtener datos**. De esta forma, se ejecutará la subrutina GetData().

## <a name="getdata"></a>GetData

GetData coloca una cadena de conexión válida en una variable de nivel de módulo, *m\_sConnStr*. Para obtener más información sobre cadenas de conexión, vea [Crear la cadena de conexión](creating-the-connection-string.md).

Asigne un controlador de errores mediante una instrucción **OnError** de Visual Basic. Para obtener más información acerca del tratamiento de errores en ADO, vea [Capítulo 6: Tratamiento de errores](chapter-6-error-handling.md). Se crea un nuevo objeto **Connection** y la propiedad **CursorLocation** se establece en **adUseClient**, dado que el ejemplo de HelloData crea un objeto *Recordset desconectado*. Eso significa que una vez que se han recuperado los datos del origen de datos, se rompe la conexión física con el origen de datos, aunque se puede seguir trabajando con los datos almacenados en caché de forma local en el objeto **Recordset**.

Una vez establecida la conexión, asigne una cadena SQL a una variable (sSQL). A continuación, cree una instancia de un nuevo objeto **Recordset** , m\_oRecordset1. En la siguiente línea de código, abra el **objeto Recordset** a través de la existente **conexión**, pasando. En la siguiente línea de código, abra el **objeto Recordset** a través de la existente **conexión**, pasando sSQL como el origen del **objeto Recordset**. Ayude a ADO a tomar la determinación de que la cadena SQL que se acaba de pasar como origen del objeto **Recordset** es una definición textual de un comando al pasar **adCmdText** en el argumento al método **Open** del objeto **Recordset**. Esta línea también establece las propiedades **LockType** y **CursorType** asociadas al objeto **Recordset**.

<<<<<<< HEAD la siguiente línea de código establece la propiedad **MarshalOptions** en **adMarshalModifiedOnly**. **MarshalOptions** indica en qué registros se deben calcular las referencias en el nivel intermedio (o el servidor web). Para obtener más información acerca del cálculo de referencias, vea la documentación sobre COM. Cuando utilice **adMarshalModifiedOnly** con un cursor de cliente ([CursorLocation](cursorlocation-property-ado.md) = **adUseClient**), sólo los registros que se han modificado en el cliente se vuelven a escribir el nivel intermedio. El establecimiento de **MarshalOptions** en **adMarshalModifiedOnly** puede mejorar el rendimiento, dado que se calculan las referencias de menos filas.
=== La siguiente línea de código establece la propiedad **MarshalOptions** en **adMarshalModifiedOnly**. **MarshalOptions** indica qué registros deben calcularse en el nivel intermedio (o el servidor web). Para obtener más información acerca del cálculo de referencias, vea la documentación sobre COM. Cuando utilice **adMarshalModifiedOnly** con un cursor de cliente ([CursorLocation](cursorlocation-property-ado.md) = **adUseClient**), sólo los registros que se han modificado en el cliente se vuelven a escribir el nivel intermedio. El establecimiento de **MarshalOptions** en **adMarshalModifiedOnly** puede mejorar el rendimiento, dado que se calculan las referencias de menos filas.
>>>>>>> master

A continuación, desconecte el objeto **Recordset** al establecer su propiedad **ActiveConnection** en **Nothing**. Para obtener más información, vea [Desconectar y volver a conectar el objeto Recordset](disconnecting-and-reconnecting-the-recordset.md) en el capítulo 5: Actualizar y almacenar datos.

Cierre la conexión con el origen de datos y destruya el objeto **Connection** existente, con lo que se liberan los recursos que éste estaba utilizando.

El paso final consiste en establecer el objeto **Recordset** como **DataSource** de Microsoft DataBound Grid Control en el formulario para poder mostrar fácilmente los datos del objeto **Recordset** en el formulario.

Haga clic en el segundo botón, **Examinar datos**. De esta forma, se ejecuta la subrutina ExamineData.

## <a name="examinedata"></a>ExamineData

ExamineData emplea varios métodos y propiedades del objeto **Recordset** para mostrar información acerca de los datos del objeto **Recordset**. Informa acerca del número de registros mediante la propiedad **RecordCount**. Recorre el objeto **Recordset** e imprime el valor de la propiedad **AbsolutePosition** en el cuadro de texto del formulario que aparece. Además, durante el recorrido, el valor de la propiedad **Bookmark** del tercer registro se coloca en una variable de variante, *vBookmark*, para su uso posterior.

La rutina navega directamente al tercer registro mediante la variable de marcador almacenada anteriormente. La rutina llama a la subrutina WalkFields, que recorre la colección **Fields** del objeto **Recordset** y muestra detalles de cada objeto **Field** de la colección.

Por último, ExamineData utiliza la propiedad **Filter** del objeto **Recordset** para buscar sólo aquellos registros cuyo CategoryId sea igual a 2. El resultado de la aplicación de este filtro es visible inmediatamente en la cuadrícula del formulario.

Para obtener más información acerca de la funcionalidad de la subrutina ExamineData, vea el [Capítulo 3: Examinar datos](chapter-3-examining-data.md).

A continuación, haga clic en el tercer botón, **Modificar datos**. De esta forma, se ejecutará la subrutina EditData.

## <a name="editdata"></a>EditData

Cuando el código entra en la subrutina EditData, el objeto **Recordset** sigue estando filtrado por CategoryId igual a 2, de modo que sólo son visibles los elementos que satisfacen los criterios del filtro. En primer lugar recorre el objeto **Recordset** y aumenta el precio de cada elemento visible del objeto **Recordset** un 10 por ciento. El valor del campo **Price** cambia al establecer la propiedad **Value** de ese campo en una nueva cantidad válida.

Recuerde que el objeto **Recordset** está desconectado del origen de datos. Los cambios realizados en EditData sólo se efectúan de forma local en la copia almacenada en caché de los datos. Para obtener más información, vea el [Capítulo 4: Modificar datos](chapter-4-editing-data.md).

Los cambios no se realizarán en el origen de datos hasta que no se haga clic en el cuarto botón, **Actualizar datos**. Así se ejecutará la subrutina UpdateData.

## <a name="updatedata"></a>UpdateData

En primer lugar, UpdateData quita el filtro aplicado al objeto **Recordset**. El código quita y restablece como el **DataSource** de Microsoft Bound DataGrid del formulario para que el **objeto Recordset** sin filtrar aparezca en la cuadrícula.

A continuación, el código comprueba si es posible volver a desplazarse por el objeto **Recordset** mediante el método **Supports** con el argumento **adMovePrevious**.

La rutina se desplaza al primer registro mediante el método **MoveFirst** y muestra los valores originales y actuales del campo mediante las propiedades **OriginalValue** y **Value** del objeto **Field**. Puede obtener información sobre estas propiedades, junto a la propiedad **UnderlyingValue** (que no se utiliza aquí), en el [Capítulo 5: Actualizar y almacenar datos.](chapter-5-updating-and-persisting-data.md).

Después, se crea un nuevo objeto **Connection** que se utiliza para restablecer una conexión con el origen de datos. Se vuelve a conectar el objeto **Recordset** con el origen de datos al establecer el nuevo objeto **Connection** como **ActiveConnection** del objeto **Recordset**. Para enviar las actualizaciones al servidor, el código llama al método **UpdateBatch** del objeto **Recordset**.

Si la actualización por lotes se realiza correctamente, una variable de indicador de nivel de módulo, se establece en True. Eso le recordará más tarde que debe limpiar todos los cambios realizados en la base de datos.

Finalmente, el código se desplaza al primer registro del objeto **Recordset** y muestra los valores originales y actuales. Éstos son los mismos después de la llamada al método **UpdateBatch**.

Para obtener información más detallada acerca de la actualización de datos, incluido qué hacer cuando los datos del servidor cambian mientras el objeto **Recordset** está desconectado, vea el [Capítulo 5: Actualizar y almacenar datos.](chapter-5-updating-and-persisting-data.md).

## <a name="formunload"></a>Formulario\_Unload

El formulario\_subrutina Unload es importante por varias razones. Primero, puesto que se trata de una aplicación de ejemplo, formulario\_Unload limpia los cambios realizados en la base de datos antes de salir de la aplicación. En segundo lugar, el código muestra cómo se puede ejecutar un comando directamente desde un objeto **Connection** abierto mediante el método **Execute**. Por último, se muestra un ejemplo de la ejecución de una consulta que no devuelve filas (una consulta de actualización) en el origen de datos.

