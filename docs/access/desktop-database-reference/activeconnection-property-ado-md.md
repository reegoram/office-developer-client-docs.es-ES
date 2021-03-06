---
<<<<<<< Título HEAD: ActiveConnection (propiedad, ADO MD) TOCTitle: ActiveConnection (propiedad, ADO MD) ms:assetid: d09f0f91-5e1d-01ed-4d83-eaf58ff718a2 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250043(v=office.15) ms:contentKeyID: ms.date 48547845: 18/09/2015 mtps_ versión: Office.15
---

# <a name="activeconnection-property-ado-md"></a>ActiveConnection (propiedad, ADO MD)

=== título: ActiveConnection (propiedad, ADO MD) TOCTitle: ActiveConnection (propiedad, ADO MD) ms:assetid: d09f0f91-5e1d-01ed-4d83-eaf58ff718a2 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250043(v=office.15) ms:contentKeyID: ms.date 48547845: 17/10/2018 mtps_version: Office.15
---

# <a name="activeconnection-property-ado-md"></a>ActiveConnection (propiedad, ADO MD)
>>>>>>> master

**Se aplica a**: Access 2013 | Office 2013

Indica a qué objeto [Connection](connection-object-ado.md) de ADO pertenece el conjunto de celdas o el catálogo activo.

<<<<<<< HEAD
## <a name="settings-and-return-values"></a>Configuración y valores devueltos
=======
## <a name="settings-and-return-values"></a>Configuración y valores devueltos
>>>>>>> master

Establece o devuelve un valor de tipo **Variant** que contiene una cadena que define una conexión o un objeto **Connection**. El valor predeterminado es una cadena vacía.

## <a name="remarks"></a>Comentarios

Esta propiedad se puede establecer en un objeto **Connection** de ADO válido o en una cadena de conexión válida. Cuando esta propiedad se establece en una cadena de conexión, el proveedor crea un nuevo objeto **Connection** que utiliza esta definición y abre la conexión.

Si usa el argumento **ActiveConnection** del método [Open](open-method-ado-md.md) para abrir un objeto [Cellset](cellset-object-ado-md.md), la propiedad **ActiveConnection** heredará el valor del argumento.

Si se establece la propiedad **ActiveConnection** de un objeto [Catalog](catalog-object-ado-md.md) en **Nothing**, se liberarán los datos asociados, incluidos los datos de la colección [CubeDefs](cubedefs-collection-ado-md.md) y cualquier objeto [Dimension](dimension-object-ado-md.md), [Hierarchy](hierarchy-object-ado-md.md), [Level](level-object-ado-md.md) y [Member](member-object-ado-md.md) asociado. Cerrar un objeto **Connection** que se haya utilizado para abrir un **catálogo** tiene el mismo efecto que establecer la propiedad **ActiveConnection** en **Nothing**.

Si se cambia la base de datos predeterminada de la conexión a la que se hace referencia con la propiedad **ActiveConnection** de un objeto **Catalog**, el contenido del **catálogo** pierde su validez.

Si intenta cambiar la propiedad **ActiveConnection** para un objeto **Cellset** abierto, se producirá un error.

<<<<<<< HEAD

> [!NOTE]
> <P>[!NOTA] En Visual Basic, recuerde utilizar la palabra clave <STRONG>Set</STRONG> al establecer la propiedad <STRONG>ActiveConnection</STRONG> en un objeto <STRONG>Connection</STRONG>. Si omite la palabra clave <STRONG>Set</STRONG>, en realidad estará estableciendo la propiedad <STRONG>ActiveConnection</STRONG> igual que la propiedad predeterminada del objeto <STRONG>Connection</STRONG>, <STRONG>ConnectionString</STRONG>. El código funcionará, pero se creará una conexión adicional al origen de datos, lo que puede afectar negativamente al rendimiento.</P>


=======
> [!NOTE]
> [!NOTA] En Visual Basic, recuerde utilizar la palabra clave **Set** al establecer la propiedad **ActiveConnection** en un objeto **Connection**. Si omite la palabra clave **Set**, en realidad estará estableciendo la propiedad **ActiveConnection** igual que la propiedad predeterminada del objeto **Connection**, **ConnectionString**. El código funcionará, pero se creará una conexión adicional al origen de datos, lo que puede afectar negativamente al rendimiento.
>>>>>>> master

Si usa el proveedor de datos MSOLAP, establezca el origen de datos de una cadena de conexión en un nombre de servidor y establezca el catálogo inicial en el nombre de un catálogo del origen de datos. Para conectarse a un archivo de cubo que esté desconectado de un servidor, establezca la ubicación en la ruta completa de acceso al archivo .CUB. En cualquier caso, establezca el proveedor en el nombre de proveedor. Por ejemplo, la cadena siguiente establece una conexión a un catálogo que se denomina Bobs Video Store en un servidor denominado Servername con el proveedor MSOLAP:

`"Data Source=Servername;Initial Catalog=Bobs Video Store;Provider=msolap"`

La siguiente cadena se conecta a un archivo de cubo local en la ubicación C:\\MSDASDK\\ejemplos\\oledb\\olap\\datos\\bobsvid.cub:

`"Location=C:\MSDASDK\samples\oledb\olap\data\bobsvid.cub;Provider=msolap"`

