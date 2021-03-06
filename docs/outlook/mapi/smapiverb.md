---
title: SMAPIVerb
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SMAPIVerb
api_type:
- COM
ms.assetid: 45066528-2447-4178-aaa3-7513ed0b3ba4
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 11f11ae2d90a951a119895f3e0e3e3ca0dbc0fc5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573701"
---
# <a name="smapiverb"></a>SMAPIVerb

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Describe un verbo MAPI.
  
|||
|:-----|:-----|
|Archivo de encabezado:  <br/> |MAPIForm.h  <br/> |
   
```cpp
typedef struct
{
  ULONG lVerb;
  LPSTR szVerbname;
  DWORD fuFlags;
  DWORD grfAttribs;
  ULONG ulFlags; /* Either 0 or MAPI_UNICODE */
} SMAPIVerb, FAR * LPMAPIVERB;

```

## <a name="members"></a>Members

 **lVerb**
  
> Código que representa el verbo que se pasa a [IMAPIForm::DoVerb](imapiform-doverb.md). Los verbos estándar se definen en el archivo de encabezado Exchform.h.
    
 **szVerbname**
  
> Nombre para mostrar del verbo tal como aparece en el menú formulario.
    
 **fuFlags**
  
> Marcas para el verbo.
    
 **grfAttribs**
  
> Atributos del verbo. 
    
 **ulFlags**
  
> Marca que indica el formato de nombre para mostrar del verbo. Se puede establecer la marca siguiente:
    
MAPI_UNICODE. 
  
> Es el nombre para mostrar en formato Unicode. Si no está establecido el indicador MAPI_UNICODE., el nombre para mostrar está en formato ANSI.
    
## <a name="remarks"></a>Comentarios

La estructura **SMAPIVerb** se pasa como un parámetro en los métodos siguientes: 
  
- [IMAPIFormContainer::ResolveMultipleMessageClasses](imapiformcontainer-resolvemultiplemessageclasses.md)
    
- [IMAPIFormMgr::ResolveMultipleMessageClasses](imapiformmgr-resolvemultiplemessageclasses.md)
    
## <a name="see-also"></a>Recursos adicionales



[CbMessageClassArray](cbmessageclassarray.md)


[Estructuras MAPI](mapi-structures.md)

