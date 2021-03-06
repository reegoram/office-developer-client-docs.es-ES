---
title: Implementar verbos estándar del formulario
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f89f7c58-6358-4523-9788-676f189b5e69
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 46585859e1dde4ecf38262f99cac5e3a9d29e5db
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568752"
---
# <a name="implementing-standard-form-verbs"></a>Implementar verbos estándar del formulario

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
MAPI define un conjunto de verbos estándar o acciones llevadas a cabo cuando un usuario realiza una selección de menú o hace clic en un botón, que deben admitir todos los visores de formulario. Cada verbo tiene una constante asociada para la identificación, definido en el EXCHFORM. Archivo de encabezado H. En la siguiente tabla se enumera los verbos de formulario estándar y sus constantes asociadas:
  
|**Verbo**|**Valor**|
|:-----|:-----|
|Abrir  <br/> |EXCHIVERB_OPEN  <br/> |
|Responder  <br/> |EXCHIVERB_REPLYTOSENDER  <br/> |
|Responder a todos  <br/> |EXCHIVERB_REPLYTOALL  <br/> |
|Forward  <br/> |EXCHIVERB_FORWARD  <br/> |
|Imprimir  <br/> |EXCHIVERB_PRINT  <br/> |
|Guardar como  <br/> |EXCHIVERB_SAVEAS  <br/> |
|Responder en carpeta  <br/> |EXCHIVERB_REPLYTOFOLDER  <br/> |
   
Cuando un usuario elige un verbo, pase la constante en la llamada al método de [IMAPIForm::DoVerb](imapiform-doverb.md) del formulario que realice su acción correspondiente. 
  
Además de obtener acceso a los verbos de a través de su Visor de formulario, los usuarios pueden acceder a veces verbos directamente desde el formulario. Por ejemplo, algunos objetos de formulario permiten al usuario invocar el verbo **Imprimir** haciendo doble clic en el formulario y eligiendo **Print** en un menú contextual. 
  

