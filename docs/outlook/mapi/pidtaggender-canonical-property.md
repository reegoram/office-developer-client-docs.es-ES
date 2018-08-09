---
title: Propiedad canónica PidTagGender
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagGender
api_type:
- HeaderDef
ms.assetid: a79a139a-6813-49f6-b622-bb66d62c4462
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: b2ac7aa4fca8583fc59d727c55433108bee62dee
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19819562"
---
# <a name="pidtaggender-canonical-property"></a>Propiedad canónica PidTagGender

  
  
**Hace referencia a**: Outlook 
  
Contiene el género del usuario de mensajería.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_GENDER  <br/> |
|Identificador:  <br/> |0x3A4D  <br/> |
|Tipo de datos:  <br/> |PT_I2  <br/> |
|Área:  <br/> |Usuario de correo MAPI  <br/> |
   
## <a name="remarks"></a>Comentarios

Esta propiedad proporciona acceso a información sobre un usuario de mensajería e identificación y el contenido es. El contenido es definido por el usuario de mensajería y organización de mensajería del usuario. 
  
Los valores posibles para esta propiedad se definen en la enumeración género. Aparecen en la siguiente manera:
  
|**Enumeración de género**|**Valor**|**Descripción**|
|:-----|:-----|:-----|
|genderUnspecified  <br/> |0x0000  <br/> |No se especifica el sexo del contacto.  <br/> |
|genderFemale  <br/> |0 x 0001  <br/> |El contacto está femenino.  <br/> |
|genderMale  <br/> |0x0002  <br/> |El contacto está masculino.  <br/> |
   
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona referencias a las especificaciones del protocolo de Exchange Server relacionadas.
    
[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> Especifica las propiedades y operaciones que se permiten para los contactos y las listas de distribución personal.
    
[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> Especifica las propiedades y operaciones para las listas de los usuarios, contactos, grupos y recursos.
    
### <a name="header-files"></a>Archivos de encabezado

Mapidefs.h
  
> Proporciona definiciones de tipo de datos.
    
Mapitags.h
  
> Contiene las definiciones de las propiedades que aparecen como nombres alternativos.
    
## <a name="see-also"></a>Vea también



[Propiedades MAPI](mapi-properties.md)
  
[Propiedades MAPI canónicas](mapi-canonical-properties.md)
  
[Asignar nombres de propiedad canónicos a nombres MAPI](mapping-canonical-property-names-to-mapi-names.md)
  
[Asignar nombres MAPI a los nombres de propiedad canónico](mapping-mapi-names-to-canonical-property-names.md)
