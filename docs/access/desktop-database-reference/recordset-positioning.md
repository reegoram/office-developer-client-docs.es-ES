---
title: Colocación de un conjunto de registros
TOCTitle: Recordset Positioning
ms:assetid: 1b8b08d5-a11c-ec6e-201c-1405171a1264
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248955(v=office.15)
ms:contentKeyID: 48543546
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 10586c711b9931c1cac93401111f4d477ca8a987
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486445"
---
# <a name="recordset-positioning"></a>Colocación de un conjunto de registros


**Se aplica a**: Access 2013 | Office 2013

Use la propiedad **AbsolutePosition** para desplazarse a un registro basándose en su posición ordinal en el objeto **Recordset**, o bien, para especificar la posición ordinal del registro actual. El proveedor debe admitir la funcionalidad adecuada para que esta propiedad esté disponible.

**AbsolutePosition** es de base uno y es igual a 1 cuando el registro activo es el primero del **conjunto de registros**. Como se indicó previamente, el número total de registros del objeto **Recordset** se puede obtener a partir de la propiedad **RecordCount**.

Cuando se establece la propiedad **AbsolutePosition**, incluso aunque sea en un registro en la caché actual, ADO vuelve a cargar la caché con un nuevo grupo de registros empezando por el registro que se haya especificado. La propiedad **CacheSize** determina el tamaño de este grupo.


> [!NOTE]
> <P>[!NOTA] No es aconsejable usar la propiedad <STRONG>AbsolutePosition</STRONG> como número de registro suplente. La posición de un registro determinado cambia cuando se elimina un registro anterior. Además, no se tiene la certeza de que un registro dado tenga el mismo valor de <STRONG>AbsolutePosition</STRONG> si se vuelve a consultar y a abrir el objeto <STRONG>Recordset</STRONG>. Los marcadores son el método recomendado para retener cierta posición y volver a ella, y son la única manera de establecer un posicionamiento a través de todos los tipos de objetos <STRONG>Recordset</STRONG>.</P>


