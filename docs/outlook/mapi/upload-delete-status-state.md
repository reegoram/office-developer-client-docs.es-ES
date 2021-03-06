---
title: Cargar estado de eliminación del estado
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: dee566ad-b46d-1015-4b0b-6c3313060142
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 4a45cfafec5126c72f365858e41963bc95fa707a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574548"
---
# <a name="upload-delete-status-state"></a>Cargar estado de eliminación del estado

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
 En este tema se describe qué ocurre durante la carga Eliminar estado de estado de la máquina de estado de replicación. 
  
## <a name="quick-info"></a>Información rápida

|||
|:-----|:-----|
|Identificador de estado:  <br/> |**LR_SYNC_UPLOAD_MESSAGE_DEL** <br/> |
|Estructura de datos relacionados:  <br/> |**[UPDEL](updel.md)** <br/> |
|Desde este estado:  <br/> |[Cargar el estado de la tabla](upload-table-state.md) <br/> |
|En este estado:  <br/> |Cargar el estado de la tabla  <br/> |
   
> [!NOTE]
> La máquina de estado de replicación es una máquina de estado determinista. Un cliente sale de un estado a otro finalmente debe volver a la primera desde el último. 
  
## <a name="description"></a>Descripción

Este estado inicia la actualización en un servidor de los elementos de Outlook (correo, calendario, contacto, tarea, nota o diario) que se han eliminado en una carpeta en un almacén local especificado en un estado de tabla de carga anterior. Durante este estado, Outlook inicializa a los miembros de la estructura de datos **UPDEL** asociado con información para los elementos que se han eliminado o movido de la carpeta. 
  
El cliente, a continuación, elimina los elementos especificados en la carpeta en el servidor. Para distinguir los elementos que se han movido en lugar de tener que se ha eliminado, el cliente debe comprobar a los miembros de *pupmov* identificados en la estructura **UPDEL** . 
  
Cuando finaliza este estado, Outlook borra la información interna que indica que se ha eliminado el elemento; Por consiguiente, Outlook ya no tendrá un registro del elemento. Devuelve el almacén local en el estado de la tabla de carga.
  
## <a name="see-also"></a>Recursos adicionales



[Información sobre la API de replicación](about-the-replication-api.md)
  
[Constantes MAPI](mapi-constants.md)
  
[Información sobre la máquina de estados de replicación](about-the-replication-state-machine.md)
  
[ESTADO DE SINCRONIZACIÓN](syncstate.md)

