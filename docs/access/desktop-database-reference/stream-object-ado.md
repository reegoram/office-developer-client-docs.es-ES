---
title: Stream (objeto) (ADO)
TOCTitle: Stream Object (ADO)
ms:assetid: d49b1514-e0b4-0aca-d5c2-8266f3f4fe65
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250065(v=office.15)
ms:contentKeyID: 48547945
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f0a5ad4b50ed0548bad1f9a5482ee6755ecc9e2c
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603598"
---
# <a name="stream-object-ado"></a>Stream (objeto) (ADO)


**Se aplica a**: Access 2013 | Office 2013

Representa una secuencia de datos binarios o texto.

## <a name="remarks"></a>Comentarios

En jerarquías con estructura de árbol, como un sistema de archivos o un sistema de correo electrónico, un objeto [Record](record-object-ado.md) puede tener una secuencia binaria predeterminada de bits asociados que tenga el contenido del archivo o del correo electrónico. Para manipular campos o registros que contengan estas secuencias de datos se puede usar un objeto **Stream**, que se puede obtener de las maneras siguientes:****

  - Desde una dirección URL que señala un objeto (normalmente un archivo) que contiene datos de texto o binarios. Este objeto puede ser un documento simple, un objeto **Record** que representa un documento estructurado, o una carpeta.

  - Abriendo el objeto **Stream** predeterminado asociado a un objeto **Record**. Se puede obtener la secuencia predeterminada asociada al objeto **Record** cuando se abre el objeto **Record**, para eliminar un viaje de ida y vuelta en el momento de abrir la secuencia.

  - Creando instancias de un objeto **Stream**. Estos objetos **Stream** se pueden utilizar para almacenar datos necesarios para la aplicación. A diferencia de un objeto **Stream** asociado a una dirección URL, o el objeto **Stream** predeterminado de un objeto **Record**, un objeto **Stream** del que se han creado instancias no tiene asociación a un origen subyacente de forma predeterminada.

Con los métodos y las propiedades de un objeto **Stream**, se puede hacer lo siguiente:

  - Abrir un objeto **Stream** desde un objeto **Record** o una dirección URL con el método [Open](open-method-ado-stream.md).

  - Cerrar un objeto **Stream** con el método [Close](close-method-ado.md).

  - Especificar bytes o texto en un objeto **Stream** con los métodos [Write](write-method-ado.md) y [WriteText](writetext-method-ado.md).

  - Leer bytes del objeto **Stream** con los métodos [Read](read-method-ado.md) y [ReadText](readtext-method-ado.md).

  - Escribir datos del objeto **Stream**, que están todavía en el búfer de ADO, en el objeto subyacente con el método [Flush](flush-method-ado.md).

  - Copiar el contenido de un objeto **Stream** en otro objeto **Stream** con el método [CopyTo](copyto-method-ado.md).

  - Controlar cómo se leen las líneas del archivo de origen con el método [SkipLine](skipline-method-ado.md) y la propiedad [LineSeparator](lineseparator-property-ado.md).

  - Determinar el fin de la secuencia con la propiedad [EOS](eos-property-ado.md) y el método [SetEOS](seteos-method-ado.md).

  - Guardar y restaurar datos en archivos con los métodos [SaveToFile](savetofile-method-ado.md) y [LoadFromFile](loadfromfile-method-ado.md).

  - Especificar el juego de caracteres usado para almacenar el objeto **Stream** con la propiedad [Charset](charset-property-ado.md).

  - Detener una operación asincrónica del objeto **Stream** con el método [Cancel](cancel-method-ado.md).

  - Determinar el número de bytes de un objeto **Stream** con la propiedad [Size](https://msdn.microsoft.com/library/jj250128\(v=office.15\)).

  - Controlar la posición actual dentro de un objeto **Stream** con la propiedad [Position](position-property-ado.md).

  - Determinar el tipo de datos de un objeto **Stream** con la propiedad [Type](type-property-ado-stream.md).

  - Determinar el estado actual del objeto **Stream** (cerrado, abierto o en ejecución) con la propiedad [State](state-property-ado.md).

  - Especificar el modo de acceso para el objeto **Stream** con la propiedad [Mode](mode-property-ado.md).

<<<<<<< HEAD

> [!NOTE]
> <P>[!NOTA] Las direcciones URL que utilicen el esquema http invocarán automáticamente <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>. Para obtener más información, vea <A href="absolute-and-relative-urls.md">Direcciones URL absolutas y relativas</A>.</P>
=======
> [!NOTE]
> [!NOTA] Las direcciones URL que utilicen el esquema http invocarán automáticamente [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md). Para obtener más información, vea [direcciones URL absolutas y relativas](absolute-and-relative-urls.md).
>>>>>>> master


