---
title: Guardar un mensaje en la Bandeja de entrada
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3df04d4e-7e80-4232-aadc-c05c99ab59cb
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: e79133ed4928495dcf75b59877a82d3228773883
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586287"
---
# <a name="saving-a-message-in-the-inbox"></a>Guardar un mensaje en la Bandeja de entrada

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
 **Para almacenar un mensaje en la Bandeja de entrada sin todos los destinatarios**
  
1. Llame a [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md) para recuperar el identificador de entrada de la Bandeja de entrada. 
    
2. Llame a [IMsgStore::OpenEntry](imsgstore-openentry.md) para abrir la Bandeja de entrada y recuperar un puntero a ella. 
    
3. Llamar al método [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) de la Bandeja de entrada para crear el mensaje. 
    
4. Llamar al método [IMAPIProp::SetProps](imapiprop-setprops.md) del mensaje para agregar la **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), **PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)), o **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) y **PR_SUBJECT** ([ PidTagSubject](pidtagsubject-canonical-property.md)) propiedades. 
    
5. Crear cada dato adjunto, establezca sus propiedades y vuelva a guardarla. Para obtener información detallada sobre cómo agregar datos adjuntos a los mensajes, vea [crear un datos adjuntos del mensaje](creating-a-message-attachment.md).
    
6. Llame a **IMessage::SaveChanges** para guardar el mensaje. En este momento aparecerá en la tabla de contenido de la Bandeja de entrada. 
    
Si desea guardar un intermittantly de mensaje antes de que se muestran en la tabla de contenido de la Bandeja de entrada, créelo en su lugar en una carpeta oculta, como la carpeta raíz del subárbol IPM y, a continuación, moverlo a la Bandeja de entrada. 
  

