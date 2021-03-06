---
<<<<<<< Título HEAD: CacheSize (propiedad) (ADO) TOCTitle: CacheSize (propiedad) (ADO) === título: CacheSize (propiedad, ADO) TOCTitle: CacheSize (propiedad, ADO)
>>>>>>> Master ms:assetid: 42f86cc0-30dc-669b-9e65-5e7ecd52c4d7 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249200(v=office.15) ms:contentKeyID: ms.date 48544491: 18/09/2015 mtps_version: Office.15
---

<<<<<<< HEAD
# <a name="cachesize-property-ado"></a>CacheSize (propiedad, ADO)
=======
# <a name="cachesize-property-ado"></a>CacheSize (propiedad, ADO)
>>>>>>> master


**Se aplica a**: Access 2013 | Office 2013

Indica el número de registros de un objeto [Recordset](recordset-object-ado.md) que están almacenados en la memoria caché local.

<<<<<<< HEAD
## <a name="settings-and-return-values"></a>Configuración y valores devueltos
=======
## <a name="settings-and-return-values"></a>Configuración y valores devueltos
>>>>>>> master

Establece o devuelve un valor de tipo **Long** que debe ser mayor que 0. El valor predeterminado es 1.

## <a name="remarks"></a>Comentarios

Use la propiedad **CacheSize** para controlar el número de registros que se van a recuperar a la vez en la memoria local del proveedor. Por ejemplo, si el valor de **CacheSize** es 10, tras abrir el objeto **Recordset**, el proveedor recupera los 10 primeros registros en la memoria local. Cuando el usuario se mueve por el objeto **Recordset**, el proveedor devuelve los datos desde el búfer de memoria local. Cuando el usuario se desplaza hasta un punto situado más allá del último registro de la caché, el proveedor recupera en la memoria caché los 10 siguientes registros del origen de datos.


> [!NOTE]
> <P>[!NOTA] <STRONG>CacheSize</STRONG> se basa en la propiedad específica del proveedor <STRONG>Número máximo de filas abiertas</STRONG> (en la colección <STRONG>Properties</STRONG> del objeto <STRONG>Recordset</STRONG> ). No se puede establecer <STRONG>CacheSize</STRONG> en un valor mayor que el valor de <STRONG>Número máximo de filas abiertas</STRONG>. Para modificar el número de registros que el proveedor puede abrir, establezca el valor de <STRONG>Número máximo de filas abiertas</STRONG>.</P>



El valor de **CacheSize** se puede ajustar a lo largo del ciclo de vida del objeto **Recordset**, pero al cambiar este valor, sólo se ve afectado el número de registros en la memoria caché después de recuperaciones subsiguientes desde el origen de datos. Al cambiar sólo el valor de esta propiedad, no se modificará el actual contenido de la memoria caché.

Si hay menos registros para recuperar que la cantidad especificada con **CacheSize**, el proveedor devuelve los registros restantes y no se produce ningún error.

No se puede establecer **CacheSize** en cero, ya que devolvería un error.

Los registros recuperados de la caché no reflejan los cambios concurrentes realizados por otros usuarios en el origen de datos. Para que se actualicen todos los datos almacenados en la caché, utilice el método [Resync](resync-method-ado.md).

Si el valor de **CacheSize** es mayor que 1, los métodos de navegación ([Move](move-method-ado.md), [MoveFirst, MoveLast, MoveNext y MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)) pueden dar como resultado la navegación a un registro eliminado si la eliminación se ha producido después de recuperarse los registros. Después de la recuperación inicial, las eliminaciones posteriores no se reflejarán en la memoria caché de datos hasta que intente obtener acceso a un valor de datos de una fila eliminada. Sin embargo, si se establece el valor de **CacheSize** en 1, ya no existirá este problema ya que no se podrán recuperar las filas eliminadas.

