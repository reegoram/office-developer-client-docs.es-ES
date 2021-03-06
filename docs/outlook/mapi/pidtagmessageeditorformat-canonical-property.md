---
title: Propiedad canónica PidTagMessageEditorFormat
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageEditorFormat
api_type:
- HeaderDef
ms.assetid: 197b21ed-9f2f-425f-a6ed-cae1208fa2ca
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 029df4397f4d24c7c111d2017d34e6403df367d6
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401576"
---
# <a name="pidtagmessageeditorformat-canonical-property"></a>Propiedad canónica PidTagMessageEditorFormat

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Especifica el formato para un editor que desea utilizar para mostrar un mensaje.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_MSG_EDITOR_FORMAT  <br/> |
|Identificador:  <br/> |0x5909  <br/> |
|Tipo de datos:  <br/> |PT_LONG  <br/> |
|Área:  <br/> |Varios  <br/> |
   
## <a name="remarks"></a>Comentarios

Los valores posibles para **PR_MSG_EDITOR_FORMAT** pueden ser una de las siguientes opciones: 
  
|**Valor**|**Descripción**|
|:-----|:-----|
|**EDITOR_FORMAT_DONTKNOW** <br/> |El formato para el editor que desea utilizar es desconocido.  <br/> |
|**EDITOR_FORMAT_PLAINTEXT** <br/> |El editor debe mostrar el mensaje en formato de texto sin formato.  <br/> |
|**EDITOR_FORMAT_HTML** <br/> |El editor debe mostrar el mensaje en formato HTML.  <br/> |
|**EDITOR_FORMAT_RTF** <br/> |El editor debe mostrar el mensaje en formato de texto enriquecido.  <br/> |
   
De forma predeterminada, los mensajes (con la clase de mensaje IPM **de correo. Nota** o con una clase de mensaje personalizada derivada de **IPM. Tenga en cuenta**) enviados desde un correo POP3/SMTP cuenta se envían en formato de encapsulación neutro de transporte (TNEF). La propiedad **PR_MSG_EDITOR_FORMAT** puede utilizarse para exigir la aplicación de sólo texto sin formato y no TNEF, al enviar un mensaje. Si se establece **PR_MSG_EDITOR_FORMAT** en **EDITOR_FORMAT_PLAINTEXT**, el mensaje se envía como texto sin formato sin TNEF. Si se establece **PR_MSG_EDITOR_FORMAT** en **EDITOR_FORMAT_RTF**, la codificación TNEF está habilitada de forma implícita, y el mensaje se envía con el formato de Internet predeterminada que se especifica en el cliente de Outlook.
  
Existen otras dos formas para exigir el uso de TNEF al enviar un mensaje.
  
- Configuración de la **dispidUseTNEF** ([PidLidUseTnef](pidlidusetnef-canonical-property.md)) con el nombre de propiedad en True en un mensaje indica que TNEF se debe incluir al convertir el mensaje de MAPI a MIME/SMTP. Tenga en cuenta que **dispidUseTNEF** sólo se aplica cuando el mensaje se envía desde una cuenta de correo POP3/SMTP y no se aplica cuando se envía el mensaje por otros proveedores, como Microsoft Exchange Server. **dispidUseTNEF** reemplaza el valor de **PR_MSG_EDITOR_FORMAT**.
    
- Uso de la marca **CCSF_USE_TNEF** al llamar a [IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md) para convertir un mensaje MAPI saliente a una secuencia MIME, también puede aplicar TNEF. Esto se aplica incluso si no se ha establecido **dispidUseTNEF** . 
    
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona referencias a las especificaciones del protocolo de Exchange Server relacionadas.
    
[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> Define las estructuras de datos básicos que se usan en las operaciones remotas.
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> Especifica las propiedades y operaciones que se permiten para los objetos de mensaje de correo electrónico.
    
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

