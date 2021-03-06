---
title: Propiedad canónica PidLidCustomFlag
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidCustomFlag
api_type:
- COM
ms.assetid: bfb7fd1e-774f-9a2f-fbbe-ba7f68ed8663
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 9a131c633b8dcf9b0e5070f01de8fcab90a18ade
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384202"
---
# <a name="pidlidcustomflag-canonical-property"></a>Propiedad canónica PidLidCustomFlag

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Una máscara de bits que especifica cómo se personaliza un mensaje, por ejemplo, guarda con propiedades personalizadas.
  
## 

|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |dispidCustomFlag  <br/> |
|Identificador de tipo Long (LID):  <br/> |0x00008251  <br/> |
|Tipo de datos:  <br/> |PT_LONG  <br/> |
   
## <a name="remarks"></a>Comentarios

Para recuperar el valor de esta propiedad, en primer lugar utilice **[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)** para obtener la etiqueta de propiedad y, a continuación, especifique esta etiqueta de propiedad en **[IMAPIProp::GetProps](imapiprop-getprops.md)** para obtener el valor. 
  
Indicadores de posibles son los siguientes:
  
****

|**Constante**|**Valor**|
|:-----|:-----|
|INSP_ONEOFFFLAGS  <br/> |0x0D000000  <br/> |
|INSP_PROPDEFINITION  <br/> |0x02000000  <br/> |
   
Cuando se llama a **IMAPIProp::GetIDsFromNames**, especifique los siguientes valores de la estructura **[MAPINAMEID](mapinameid.md)** indicada por el parámetro de entrada *lppPropNames* . 
  
****

|**Elemento**|**Valor**|
|:-----|:-----|
|lpGuid:  <br/> |PSETID_Common  <br/> |
|ulKind:  <br/> |MNID_ID  <br/> |
|Kind.lID:  <br/> |dispidCustomFlag  <br/> |
   
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona definiciones de conjunto de propiedades.
    
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

