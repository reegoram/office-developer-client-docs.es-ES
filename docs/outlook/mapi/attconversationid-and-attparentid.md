---
title: attConversationID y attParentID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bed36900-e44d-434b-a4f2-d10f2d6f70da
description: 'Última modificación: 12 de marzo de 2013'
ms.openlocfilehash: 14b93a952e4776716c333dc730144b55bcc61259
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582717"
---
# <a name="attconversationid-and-attparentid"></a>attConversationID y attParentID

**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Las ventanas de clave de conversación de correo de trabajo en grupo 3.1 son una cadena de texto. El equivalente MAPI es un valor binario. Para proporcionar compatibilidad con versiones anteriores, la implementación de TNEF convierte los datos binarios en texto y agrega un carácter nulo.
  
> [!NOTE]
> Las propiedades correspondientes en MAPI para que se asignan estos atributos TNEF, PR_CONVERSATION_KEY y PR_PARENT_KEY, han quedado obsoletos en Microsoft Exchange Server: uso de **PR_CONVERSATION_KEY**, el [PidTagConversationKey canónico Propiedad](pidtagconversationkey-canonical-property.md), se conserva en Outlook sólo, para localizar **IPM. Objeto** los mensajes. 
  
## <a name="remarks"></a>Comentarios

La propiedad **PR_CONVERSATION_KEY** es el precursor en caso contrario, obsoleto **PR_CONVERSATION_INDEX**, [Propiedad canónico PidTagConversationIndex](pidtagconversationindex-canonical-property.md) y **PR_CONVERSATION_TOPIC**, [PidTagConversationTopic canónico Propiedad](pidtagconversationtopic-canonical-property.md), que se debe usar en su lugar.
  
## <a name="see-also"></a>Vea también

- [Subárbol IPM](ipm-subtree.md)
- [Carpetas especiales de MAPI](mapi-special-folders.md)

