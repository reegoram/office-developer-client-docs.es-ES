---
title: UPFLD
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6da9d6b6-a016-ccef-77da-3e037c30450d
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 34d6eb0653c3eb550bf03242a2c1b2acc3330a13
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572294"
---
# <a name="upfld"></a>UPFLD

**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Información para cargar una carpeta durante la [carga de estado de la carpeta](upload-folder-state.md).
  
## <a name="quick-info"></a>Información rápida

```cpp
struct UPFLD 
{ 
    ULONG ulFlags; 
    LPMAPIFOLDER pfld; 
    FEID feid; 
}; 

```

## <a name="members"></a>Members

_ulFlags_
  
>  [out] / [in] indicadores para determinar las acciones adecuadas para el uplaod. 
    
  - UPF_NEW
    
    - [out] Carpeta es nueva.
    
  - UPF_MOD_PARENT
    
    - [out] Se ha movido la carpeta.
    
  - UPF_MOD_PROPS
    
    - [out] Propiedades de la carpeta se han modificado.
    
  - UPF_DEL
    
    - [out] Se eliminó la carpeta.
    
  - UPF_OK
    
    - [entrada] Carga fue correcta. El cliente establece esto después de cargar la información de la carpeta en el servidor.
    
_pfld_
  
> [out] El objeto de carpeta abierta para cargar.
    
_feid_
  
> [out] Identificador de entrada de la carpeta.
    
## <a name="see-also"></a>Recursos adicionales

- [Información sobre la API de replicación](about-the-replication-api.md) 
- [Información sobre la máquina de estados de replicación](about-the-replication-state-machine.md)
- [Constantes MAPI](mapi-constants.md)

