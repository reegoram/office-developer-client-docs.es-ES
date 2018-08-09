---
title: Propiedad canónica PidTagAccount
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAccount
api_type:
- HeaderDef
ms.assetid: bec199b5-abfd-4686-ad59-21092212e1a5
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: ab2efebe91f871452b243150367b83a1d53f8a52
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19819181"
---
# <a name="pidtagaccount-canonical-property"></a>Propiedad canónica PidTagAccount

  
  
**Hace referencia a**: Outlook 
  
Contiene el nombre de la cuenta del destinatario. 
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_ACCOUNT, PR_ACCOUNT_A, PR_ACCOUNT_W  <br/> |
|Identificador:  <br/> |0x3A00  <br/> |
|Tipo de datos:  <br/> |PT_STRING8, PT_UNICODE  <br/> |
|Área:  <br/> |Libreta de direcciones  <br/> |
   
## <a name="remarks"></a>Comentarios

Estas propiedades proporcionan identificación y obtener acceso a información de un destinatario. Se definen por el destinatario y su organización.
  
Estas propiedades con frecuencia contienen el nombre de correo electrónico del destinatario, es decir, el último componente de la dirección de correo electrónico, que identifica de forma exclusiva el destinatario de la organización local. El nombre de correo electrónico se corresponde con el nombre distintivo (DN) de X.400, que está pensado para ser un nombre corto garantizado que es único dentro de un dominio de mensajería.
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona referencias a las especificaciones del protocolo de Exchange Server relacionadas.
    
[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> Especifica las propiedades y operaciones que se permiten para los contactos y las listas de distribución personal.
    
[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> Especifica las propiedades y operaciones para las listas de los usuarios, contactos, grupos y recursos.
    
### <a name="header-files"></a>Archivos de encabezado

mapitags.h
  
> Contiene las definiciones de propiedades que se muestran como propiedades asociadas.
    
mapidefs.h
  
> Proporciona definiciones de tipo de datos.
    
## <a name="see-also"></a>Vea también



[IMailUser : IMAPIProp](imailuserimapiprop.md)


[Propiedades MAPI canónicas](mapi-canonical-properties.md)
  
[Asignar nombres de propiedad canónicos a nombres MAPI](mapping-canonical-property-names-to-mapi-names.md)
  
[Asignar nombres MAPI a los nombres de propiedad canónico](mapping-mapi-names-to-canonical-property-names.md)
