---
title: Catalog (objeto) (ADO MD)
TOCTitle: Catalog Object (ADO MD)
ms:assetid: 708c4082-3589-7f3b-5ea3-f3705f3d3ff1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249445(v=office.15)
ms:contentKeyID: 48545559
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 68af66ad00567e06649df6003eeac482eacd6686
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485125"
---
# <a name="catalog-object-ado-md"></a>Catalog (objeto) (ADO MD)


**Se aplica a**: Access 2013 | Office 2013

Contiene información de esquema multidimensional (es decir, cubos y dimensiones subyacentes, jerarquías, niveles y elementos) específica de un proveedor de datos multidimensionales (MDP).

## <a name="remarks"></a>Comentarios

Con las colecciones y las propiedades de un objeto **Catalog**, puede hacer lo siguiente:

  - Abrir el catálogo estableciendo la propiedad [ActiveConnection](activeconnection-property-ado-md.md) en un objeto [Connection](connection-object-ado.md) de ADO estándar o en una cadena de conexión válida.

  - Identificar el **catálogo** con la propiedad [Name](name-property-ado-md.md).

  - Recorrer en iteración los cubos de un catálogo mediante la colección [CubeDefs](cubedefs-collection-ado-md.md).

