---
title: MoveRecord (método, ADO)
TOCTitle: MoveRecord Method (ADO)
ms:assetid: efc341a2-0e08-a838-5925-8d4c46377e48
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250217(v=office.15)
ms:contentKeyID: 48548588
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d6955bca1bf693386d1f5edb4bac04cee311d78e
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "25606965"
---
# <a name="moverecord-method-ado"></a>MoveRecord (método, ADO)


**Se aplica a**: Access 2013 | Office 2013
 

Mueve a otra ubicación la entidad representada por un objeto [Record](record-object-ado.md).

## <a name="syntax"></a>Sintaxis

*Registro*. MoveRecord (*origen*, *destino*, *nombre de usuario*, *contraseña*, *Opciones*, *Async*)

## <a name="parameters"></a>Parámetros

  - *Source*

  - Es opcional. Valor de tipo **String** con una dirección URL que identifica el objeto **Record** que se va a mover. Si se omite *Source* o se especifica una cadena vacía, se mueve el objeto representado por este objeto **Record**. Por ejemplo, si el objeto **Record** representa un archivo, el contenido del archivo se mueve hacia la ubicación especificada por *Destination*.

  - *Destination*

  - Es opcional. Un valor de **tipo String** que contiene una dirección URL que especifica la ubicación donde se va a mover *Source* .

  - *UserName*

  - Es opcional. Valor de tipo **String** con el identificador de usuario que, en caso de que sea necesario, autoriza el acceso a *Destination*.

  - *Password*

  - Es opcional. Valor de tipo **String** con la contraseña que, en caso de que sea necesario, comprueba *UserName*.

  - *Options*

  - Es opcional. Valor de [MoveRecordOptionsEnum](moverecordoptionsenum.md), cuyo valor predeterminado es **adMoveUnspecified**. Especifica el comportamiento de este método.

  - *Async*

  - Es opcional. Valor de tipo **Boolean** que, cuando es **True**, especifica que esta operación debe ser asincrónica.

<<<<<<< HEAD
## <a name="return-value"></a>Valor devuelto
=======
## <a name="return-value"></a>Valor devuelto
>>>>>>> master

Valor de tipo **String**. Normalmente, se devuelve el valor de *destino* . Sin embargo, el valor devuelto exacto depende del proveedor.

## <a name="remarks"></a>Comentarios

Los valores de *origen* y de *destino* no pueden ser idénticos; de lo contrario, se produce un error en tiempo de ejecución. Al menos los nombres de servidor, ruta de acceso o recurso deben ser diferentes.

En el caso de los archivos que se mueven mediante el proveedor de publicaciones en Internet, este método actualiza todos los vínculos de hipertexto en los archivos que se están moviendo, a menos que se especifique lo contrario en *Options*. Este método genera un error si *Destination* identifica un objeto existente (por ejemplo, un archivo o directorio), a menos que se especifique **adMoveOverWrite**.


> [!NOTE]
> <P>[!NOTA] Utilice la opción <STRONG>adMoveOverWrite</STRONG> con criterio. Por ejemplo, si especifica esta opción cuando mueve un archivo a un directorio, se eliminará el directorio y se reemplazará con el archivo.</P>



Algunos atributos del objeto **Record**, como la propiedad [ParentURL](parenturl-property-ado.md), no se actualizarán tras finalizar esta operación. Actualice las propiedades del objeto **Record** cerrando el objeto **Record** y abriéndolo de nuevo con la dirección URL de la ubicación a la que se ha movido el archivo o directorio.

Si este objeto **Record** se ha obtenido de un objeto [Recordset](recordset-object-ado.md), la nueva ubicación del archivo o directorio que se ha movido no se reflejará inmediatamente en el objeto **Recordset**. Actualice el objeto **Recordset** cerrando y abriéndolo de nuevo.


> [!NOTE]
<<<<<<< HEAD
> <P>[!NOTA] Las direcciones URL que utilicen el esquema http invocarán automáticamente <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>. Para obtener más información, vea <A href="absolute-and-relative-urls.md">Direcciones URL absolutas y relativas</A>.</P>
=======
> [!NOTA] Las direcciones URL que utilicen el esquema http invocarán automáticamente [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md). Para obtener más información, vea [direcciones URL absolutas y relativas](absolute-and-relative-urls.md).
>>>>>>> master


