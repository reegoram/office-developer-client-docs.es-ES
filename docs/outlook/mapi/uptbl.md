---
title: UPTBL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 39d9ad3b-ff4b-8378-a3ac-d5621c7ef7f1
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: bdfabdf02fc0fa6222418bd0fb87e9b6c17d936a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580442"
---
# <a name="uptbl"></a>UPTBL

**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Información para cargar el contenido de una carpeta durante la [carga de estado de la tabla](upload-table-state.md).
  
## <a name="quick-info"></a>Información rápida

```cpp
struct UPTBL 
{ 
    ULONG ulFlags; 
    LPSTREAM pstmReserved; 
    LPSTR pszName; 
    FEID feid; 
    UINT uintReserved; 
    UPTBLE rgte[2]; 
    UINT iEnt; 
    UINT cEnt; 
    PUPMOV pupmovHead; 
    void* pReserved; 
};
```

## <a name="members"></a>Members

_ulFlags_
  
> [entrada] Marcas para determinar el comportamiento adecuado durante la carga.
    
  - UPT_OK
    
    - [entrada] Carga fue correcta. El cliente establece esto después de cargar el contenido de la carpeta en el servidor.
    
_pstmReserved_
  
> [out] Este miembro está reservado para el uso interno de Outlook y no se admite. 
    
_pszName_
  
> [out] Nombre de la carpeta.
    
_feid_
  
> [out] Identificador de entrada de la carpeta.
    
_uintReserved_
  
> [out] Este miembro está reservado para el uso interno de Outlook y no se admite. 
    
_rgte_
  
> [out] Estructura para contener la siguiente información para elementos normales (o no ocultos) y elementos asociados (u ocultos) en la carpeta: _rgte [0]_ es para los elementos normales y _rgte [1]_ es para los elementos asociados. 
    
   - el número de elementos nuevos o modificados
   - el número de elementos leídos 
   - el número de elementos eliminados
    
 _iEnt_
  
> [out] Índice que se va a realizar un seguimiento de cargar el número de cambios especificado por _ciento_.
    
_cEnt_
  
> [out] Número de los cambios realizados en la carpeta.
    
_pupmovHead_
  
> [out] Cadena de estructuras [UPMOV](upmov.md) . 
    
_Conserva_
  
> [out] Este miembro está reservado para el uso interno de Outlook y no se admite.
    
## <a name="see-also"></a>Recursos adicionales

- [Información sobre la API de replicación](about-the-replication-api.md)
- [Información sobre la máquina de estados de replicación](about-the-replication-state-machine.md)
- [Constantes MAPI](mapi-constants.md)
- [UPTBLE](uptble.md)

