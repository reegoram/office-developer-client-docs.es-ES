---
title: Propiedad canónica PidTagProviderDllName
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderDllName
api_type:
- COM
ms.assetid: 9ddb38eb-9a32-4dbe-b42c-6ea9db98acd2
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 3bf6347102fc0865b081847a0b66763ba2654665
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589486"
---
# <a name="pidtagproviderdllname-canonical-property"></a>Propiedad canónica PidTagProviderDllName

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Contiene el nombre de archivo de base de la biblioteca de vínculos dinámicos de proveedor de servicio MAPI (DLL).
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_PROVIDER_DLL_NAME, PR_PROVIDER_DLL_NAME_A, PR_PROVIDER_DLL_NAME_W  <br/> |
|Identificador:  <br/> |0x300A  <br/> |
|Tipo de datos:  <br/> |PT_STRING8, PT_UNICODE  <br/> |
|Área:  <br/> |MAPI comunes  <br/> |
   
## <a name="remarks"></a>Comentarios

MAPI utiliza una convención de nomenclatura del archivo DLL. El nombre de archivo base contiene hasta seis caracteres que identifican el archivo DLL. MAPI anexa la cadena 32 para el nombre base del archivo DLL para identificar la versión que se ejecuta en plataformas de 32 bits. Por ejemplo, cuando el nombre de MAPI. Se especifica el archivo DLL, el nombre MAPI32 las construcciones de MAPI. DLL para representar la versión de 32 bits correspondiente de la DLL.
  
Estas propiedades deben especificar el nombre base. MAPI anexa la cadena 32 según corresponda. Por ejemplo, la cadena de 32 como parte de este los resultados de la propiedad en un error.
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="header-files"></a>Archivos de encabezado

Mapidefs.h
  
> Proporciona definiciones de tipo de datos.
    
Mapitags.h
  
> Contiene las definiciones de las propiedades que aparecen como nombres alternativos.
    
## <a name="see-also"></a>Recursos adicionales



[Propiedades MAPI](mapi-properties.md)
  
[Propiedades MAPI canónicas](mapi-canonical-properties.md)
  
[Asignar nombres de propiedad canónicos a nombres MAPI](mapping-canonical-property-names-to-mapi-names.md)
  
[Asignar nombres MAPI a los nombres de propiedad canónico](mapping-mapi-names-to-canonical-property-names.md)

