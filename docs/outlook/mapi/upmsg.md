---
title: UPMSG
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 5fe3956b-819a-3edf-0e49-7a44bcfbabcd
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: fa8b84e7baed74bda25ec1b20bd79fb121a838fd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587575"
---
# <a name="upmsg"></a>UPMSG

**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Información para cargar un elemento de Outlook durante la [carga de estado del mensaje](upload-message-state.md).
  
## <a name="quick-info"></a>Información rápida

```cpp
struct UPMSG 
{ 
    ULONG ulFlags; 
    LPMESSAGE pmsg; 
    MEID meid; 
    SBinary binReserved1; 
    SBinary binReserved2; 
    FEID feid; 
    SBinary binChg; 
    SBinary binPcl; 
    SKEY skeySrc; 
};
```

## <a name="members"></a>Members

 _ulFlags_
  
> [out] o [in] indicadores para determinar el comportamiento adecuado durante la carga. 
    
  - UPM_ASSOC
    
    - [out] Elemento está asociado.
    
  - UPM_NEW
    
    - [out] Nuevo elemento. 
    
  - UPM_MOV
    
    - [out] Elemento se ha movido aquí.
    
  - UPM_MOD_PROPS
    
    - [out] Se modificaron las propiedades de elementos.
    
  - UPM_HEADER
    
    - [out] Item es un encabezado de mensaje.
    
  - UPM_OK
    
    - [entrada] Carga fue correcta. El cliente establece esto después de cargar información en el servidor.
    
  - UPM_MOVED
    
    - [entrada] Elemento se ha movido correctamente.
    
  - UPM_COMMIT
    
    - [entrada] Confirmar ahora el estado de carga.
    
  - UPM_DELETE
    
    - [entrada] Eliminar elemento ahora.
    
  - UPM_SAVE
    
    - [entrada] Guarde los cambios en el elemento.
    
_pMsg_
  
> [out] Objeto de elemento abierto. Vea mapidefs.h para la definición de tipo de **LPMESSAGE**. 
    
_meid_
  
> [out] Identificador de entrada del elemento.
    
_binReserved1_
  
> [entrada] Este miembro está reservado para el uso interno de Outlook y no se admite. 
    
_binReserved2_
  
> [entrada] Este miembro está reservado para el uso interno de Outlook y no se admite. 
    
_feid_
  
> [out] Identificador de entrada de la carpeta de origen, si el elemento se ha movido.
    
_binChg_
  
> [out] Cambiar la clave del elemento de destino, si el elemento se ha movido. Vea mapidefs.h para la definición de tipo de **SBinary**. 
    
_binPcl_
  
> [out] Cambiar la lista del elemento de destino, si el elemento se ha movido. Vea mapidefs.h para la definición de tipo de **SBinary**. 
    
_skeySrc_
  
> [out] Clave de origen del elemento de origen, si el elemento se ha movido.
    
## <a name="see-also"></a>Recursos adicionales

- [Información sobre la API de replicación](about-the-replication-api.md)
- [Información sobre la máquina de estados de replicación](about-the-replication-state-machine.md)
- [Constantes MAPI](mapi-constants.md)
- [FEID](feid.md)
- [MEID](meid.md)
- [SKEY](skey.md)

