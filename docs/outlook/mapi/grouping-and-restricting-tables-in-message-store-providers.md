---
title: Agrupar y restringir las tablas de proveedores de almacenamiento de mensajes
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 01df4be4-98a1-4159-a06d-9ccf4337198f
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: ec1c07a8d2c88680ebd94cf8ecd6901ed86ad100
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578790"
---
# <a name="grouping-and-restricting-tables-in-message-store-providers"></a>Agrupar y restringir las tablas de proveedores de almacenamiento de mensajes

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Con frecuencia, las aplicaciones cliente de permiten a los usuarios cierto control sobre cómo se muestra el contenido de una carpeta. Normalmente, un usuario puede elegir para que los mensajes se agrupan según el valor de una o varias propiedades del mensaje, o puede optar por excluir los mensajes que coinciden con determinados criterios. Esto se realiza mediante la [IMAPITable: IUnknown](imapitableiunknown.md) interfaz. Las aplicaciones cliente pueden restringir las filas devueltas desde la tabla a cualquier criterio especifica el usuario. Por lo tanto, un mensaje de almacenar las necesidades del proveedor para implementar los métodos **IMAPITable** siguientes. 
  
|IMAPITable ** (método) **|**Descripción**|
|:-----|:-----|
|[IMAPITable::FindRow](imapitable-findrow.md) <br/> |Devuelve la tabla de las filas que coinciden con los criterios especificados.  <br/> |
|[IMAPITable::QueryColumns](imapitable-querycolumns.md) <br/> |Devuelve el conjunto de columnas en una tabla o el conjunto de columnas usados actualmente.  <br/> |
|[IMAPITable::QueryRows](imapitable-queryrows.md) <br/> |Devuelve una o varias filas de una tabla, a partir de una posición determinada.  <br/> |
|[IMAPITable::Restrict](imapitable-restrict.md) <br/> |Se aplica una restricción a una tabla para que las llamadas subsiguientes a **FindRow** devolverán sólo las filas que coinciden con la restricción.  <br/> |
|[IMAPITable::SetColumns](imapitable-setcolumns.md) <br/> |Especifica las columnas que se deben devolver cuando se recuperan las filas de la tabla.  <br/> |
   
Restricciones pueden ser difíciles implementar; Para obtener más información, vea [Acerca de las restricciones](about-restrictions.md). Para obtener más información acerca de cómo implementar las tablas, vea [Tablas de MAPI](mapi-tables.md).
  
## <a name="see-also"></a>Recursos adicionales



[Caracter�sticas de almac�n de mensajes](message-store-features.md)

