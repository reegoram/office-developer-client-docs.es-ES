---
title: Cursores con conjunto de claves (referencia de escritorio de la base de datos de Access)
TOCTitle: Keyset Cursors
ms:assetid: 4b6e5f90-4413-4fb3-0a08-2cb89d3c61f7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249236(v=office.15)
ms:contentKeyID: 48544690
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7bdb03b4a205e1b4954e86368c3af4aa62f773b2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25483302"
---
# <a name="keyset-cursors"></a>Cursores con conjunto de claves


**Se aplica a**: Access 2013 | Office 2013

El cursor con conjunto de claves proporciona una funcionalidad intermedia entre un cursor estático y uno dinámico en cuanto a su capacidad para detectar cambios. Del mismo modo que un cursor estático, no siempre detecta los cambios en la pertenencia y el orden del conjunto de resultados. Como un cursor dinámico, detecta cambios en los valores de filas del conjunto de resultados.

Los cursores controlados por conjuntos de claves se controlan mediante un conjunto de identificadores únicos (claves), que se conocen como el conjunto de claves. Las claves se generan a partir de un conjunto de columnas que identifican las filas del conjunto de resultados de manera exclusiva. El conjunto de claves es el conjunto de valores de clave de todas las filas devueltas por la instrucción de consulta.

Con cursores controlados por conjuntos de claves, se genera y se guarda una clave para cada fila del cursor, y se almacena en la estación de trabajo cliente o en el servidor. Cuando se obtiene acceso a cada fila, la clave almacenada se utiliza para recuperar los valores de datos actuales desde el origen de datos. En un cursor controlado por conjuntos de claves, la pertenencia al conjunto de resultados se paraliza cuando el conjunto de claves se llena completamente. Por lo tanto, las incorporaciones o actualizaciones que afectan a la pertenencia no forman parte del conjunto de resultados hasta que se vuelve a abrir.

Los cambios en valores de datos (realizados por el propietario del conjunto de claves o mediante otros procesos) se van haciendo visibles a medida que el usuario se desplaza por el conjunto de resultados. Las inserciones efectuadas fuera del cursor (mediante otros procesos) sólo se hacen visibles si se cierra el cursor y se vuelve a abrir. Las inserciones realizadas desde dentro del cursor están visibles al final del conjunto de resultados.

Cuando un cursor controlado por conjunto de claves intenta recuperar una fila que se ha eliminado, la fila aparece como un "hueco" en el conjunto de resultados. La clave para la fila existe en el conjunto de claves, pero la fila ya no existe en el conjunto de resultados. Si se actualizan los valores de clave de una fila, la fila se considera como eliminada y luego insertada, de forma que dichas filas también aparecen como huecos en el conjunto de resultados. Mientras que un cursor controlado por conjunto de claves siempre puede detectar filas eliminadas por otros procesos, puede quitar opcionalmente las claves correspondientes a las filas que elimina. Los cursores controlados por conjuntos de claves que actúan así no pueden detectar sus propias eliminaciones porque se ha borrado la prueba.

Una actualización de una columna de clave funciona como una eliminación de la clave antigua seguida de una inserción de la clave nueva. El nuevo valor de clave no está visible si la actualización no se ha realizado a través del cursor. Si la actualización se efectuó a través del cursor, el nuevo valor de clave aparece visible al final del conjunto de resultados.

Hay una variación de los cursores controlados por conjuntos de claves, que son los denominados cursores estándar controlados por conjuntos de claves. En un cursor estándar controlado por conjunto de claves, la pertenencia de filas al conjunto de resultados y el orden de las filas son fijos en el momento de abrirse el cursor, pero los cambios en valores que realiza el propietario del cursor y los cambios confirmados realizados por otros procesos están visibles. Si un cambio descalifica a una fila para la pertenencia o si afecta al orden de una fila, la fila no desaparece ni se mueve a menos que se cierre el cursor y se vuelva a abrir. Los datos insertados no aparecen, pero los cambios en datos existentes sí que aparecen cuando se recuperan las filas.

Es difícil utilizar correctamente el cursor controlado por conjunto de claves, puesto que la sensibilidad a los cambios en los datos depende de muchas circunstancias diferentes, como se ha indicado anteriormente. Sin embargo, si a una aplicación no le afectan las actualizaciones simultáneas, si puede controlar claves incorrectas mediante programación y si debe obtener acceso directamente a ciertas filas con clave, el cursor controlado por conjunto de claves podría funcionar. Utilice el valor **adOpenKeyset** de **CursorTypeEnum** para indicar que desea utilizar un cursor con conjunto de claves en ADO.

