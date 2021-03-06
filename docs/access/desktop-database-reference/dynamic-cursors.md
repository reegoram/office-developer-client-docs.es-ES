---
title: Cursores dinámicos (referencia de escritorio de la base de datos de Access)
TOCTitle: Dynamic Cursors
ms:assetid: ae599d86-6b89-6103-fda1-c899a6138e1d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249823(v=office.15)
ms:contentKeyID: 48547068
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6c324923f0e702ad59ac120ea5de2eebcccd260e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25483320"
---
# <a name="dynamic-cursors"></a>Cursores dinámicos


**Se aplica a**: Access 2013 | Office 2013

Los cursores dinámicos detectan todos los cambios realizados en las filas del conjunto de resultados, independientemente de que los cambios se produzcan desde dentro del cursor o los realicen otros usuarios ajenos al cursor. Todas las instrucciones para inserción, actualización y eliminación realizadas por todos los usuarios se pueden ver a través del cursor. El cursor dinámico puede detectar cualquier cambio realizado en las filas, en el orden y en los valores del conjunto de resultados después de abrirse el cursor. Las actualizaciones realizadas fuera del cursor no son visibles hasta que se confirman (a menos que el nivel de aislamiento de la transacción del cursor esté establecido en "no guardados").

Por ejemplo, suponga que un cursor dinámico recupera dos filas y otra aplicación y que, a continuación, actualiza una de esas filas y elimina la otra. Si, luego, el cursor dinámico recupera esas filas, no encontrará la fila eliminada pero mostrará los valores nuevos de la fila actualizada.

El cursor dinámico es una buena elección si una aplicación debe detectar todas las actualizaciones simultáneas realizadas por otros usuarios. Utilice el valor **adOpenDynamic** de **CursorTypeEnum** para indicar que desea utilizar un cursor dinámico en ADO.

[Cursores de sólo avance](forward-only-cursors.md) | [Cursores estáticos](static-cursors.md) | [Cursores con conjunto de claves](keyset-cursors.md)

