---
<<<<<<< Título HEAD: DataSource (propiedad) (ADO) TOCTitle: DataSource (propiedad) (ADO) === título: DataSource (propiedad, ADO) TOCTitle: DataSource (propiedad, ADO)
>>>>>>> Master ms:assetid: 5c5d6c9b-b7d4-45a5-0f6a-a5580a74361e ms:mtpsurl: https://msdn.microsoft.com/library/JJ249325(v=office.15) ms:contentKeyID: ms.date 48545087: 18/09/2015 mtps_version: Office.15
---

<<<<<<< HEAD
# <a name="datasource-property-ado"></a>DataSource (propiedad, ADO)
=======
# <a name="datasource-property-ado"></a>DataSource (propiedad, ADO)
>>>>>>> master


**Se aplica a**: Access 2013 | Office 2013

Indica un objeto que contiene los datos que se van a representar como un objeto [Recordset](recordset-object-ado.md).

## <a name="remarks"></a>Comentarios

Esta propiedad se usa para crear controles enlazados a datos con el Entorno de datos. El Entorno de datos mantiene colecciones de datos (orígenes de datos) que contienen objetos con nombre (*miembros de datos*) que se representarán como un objeto ** Recordset**. **

Las propiedades [DataMember](datamember-property-ado.md) y **DataSource** deben utilizarse conjuntamente.

El objeto al que se hace referencia debe implementar la interfaz **IDataSource** y contener una interfaz **IRowset**.

**Uso**

```vb
    Dim rs as New ADODB.Recordset
    rs.DataMember = "Command"     'Name of the rowset to bind to
    Set rs.DataSource = myDE      'Name of the object containing an IRowset
```
