---
title: Utilizar ADO con ADO MD
TOCTitle: Using ADO with ADO MD
ms:assetid: 93d1d270-b8d0-4489-d441-11a61887291c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249655(v=office.15)
ms:contentKeyID: 48546405
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 492efdcef5f71daf50ac84eec5e61ef4ed07fd5a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485186"
---
# <a name="using-ado-with-ado-md"></a>Utilizar ADO con ADO MD


**Se aplica a**: Access 2013 | Office 2013

ADO y ADO MD son modelos de objetos relacionados pero independientes. ADO proporciona objetos para conectarse a orígenes de datos, ejecutar comandos, recuperar datos tabulares y metadatos de esquema en formato de tabla, y ver información de errores del proveedor. ADO MD proporciona objetos para recuperar datos multidimensionales y ver metadatos de esquema multidimensional.

Cuando trabaje con un proveedor de datos multidimensionales (MDP), podrá optar por utilizar ADO, ADO MD, o ambos con su aplicación. Si hace referencia a las dos bibliotecas dentro de su proyecto, tendrá acceso total a la funcionalidad proporcionada por su MDP.

Con frecuencia, resulta útil para los usuarios obtener una vista de tabla en dos dimensiones de un conjunto de datos multidimensionales. Para ello, utilice el objeto [Recordset](recordset-object-ado.md) de ADO. Especificar el origen de su [conjunto de celdas](cellset-object-ado-md.md) como el parámetro ***Source*** del método [Open](open-method-ado-recordset.md) de un **conjunto de registros**, en lugar de como el origen para un **conjunto de celdas**de ADO MD.

También puede resultar útil ver los metadatos de esquema en una vista tabular en lugar de como una jerarquía de objetos. El método [OpenSchema](openschema-method-ado.md) de ADO en el objeto [Connection](connection-object-ado.md) permite al usuario abrir un **conjunto de registros** que contiene información de esquema. El parámetro ***QueryType*** del método **OpenSchema** tiene varios valores [SchemaEnum](schemaenum.md) que se relacionan específicamente con proveedores de datos multidimensionales. Estos valores son:

  - **adSchemaCubes**

  - **adSchemaDimensions**

  - **adSchemaHierarchies**

  - **adSchemaLevels**

  - **adSchemaMeasures**

  - **adSchemaMembers**

Para utilizar valores de enumeración de ADO con propiedades o métodos de ADO MD, su proyecto debe hacer referencia a las bibliotecas de ADO y de ADO MD. Por ejemplo, puede utilizar los valores de enumeración **adState** de ADO con la propiedad [State](state-property-ado-md.md) de ADO MD. Para obtener más información acerca del establecimiento de referencias a bibliotecas, vea la documentación de su herramienta de desarrollo.

Para obtener más información acerca de los objetos y los métodos de ADO, vea la [referencia de API de ADO](ado-api-reference.md).

