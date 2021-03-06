---
title: PidTagPrimarySendAccount
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: e1bc4900-d261-f692-386b-139ef6960212
description: Especifica el accountsendstamp principal para un mensaje.
ms.openlocfilehash: 902c71bd4a1bd5a25ab50c4b26bcfa6d5e8489e6
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394088"
---
# <a name="pidtagprimarysendaccount"></a>PidTagPrimarySendAccount

Especifica la marca de "Enviar" de la cuenta principal de un mensaje.
  
## <a name="quick-info"></a>Información rápida

|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_PRIMARY_SEND_ACCOUNT  <br/> |
|Identificador:  <br/> |0x0E28  <br/> |
|Tipo de datos:  <br/> |PT_UNICODE  <br/> |
|Área:  <br/> |Cuenta  <br/> |
   
## <a name="remarks"></a>Comentarios

Esta propiedad se aplica a un objeto de mensaje MAPI. Para un mensaje recibido, la marca de "Enviar" de la cuenta principal indica qué cuenta se debe enviar una directa o bien una respuesta con. Para un mensaje saliente, determina en qué cuenta para enviar el mensaje con. Su valor es el valor [PROP_ACCT_SEND_STAMP](prop_acct_send_stamp.md) desde la interfaz de [IOlkAccount](iolkaccount.md) de la cuenta con la que se envía el mensaje. 
  
## <a name="see-also"></a>Vea también

- [Constantes (API de administración de cuenta)](constants-account-management-api.md)
- [Propiedades MAPI](https://msdn.microsoft.com/library/3b980217-b65b-442b-8c18-b8b9f3ff487a%28Office.15%29.aspx)
- [Propiedad canónica PidTagPrimarySendAccount](https://msdn.microsoft.com/library/2f268b3b-2e4c-4aea-8879-bdd0ac1df35c%28Office.15%29.aspx)

