---
title: IMAPIFormContainer IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormContainer
api_type:
- COM
ms.assetid: 437c8a75-1121-4919-8bd4-d57c0d6f4b9a
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 3f03412c9ab639678c68016ec1a8eff937b6c1a0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590991"
---
# <a name="imapiformcontainer--iunknown"></a>IMAPIFormContainer : IUnknown

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Administra formularios en las bibliotecas de formularios. Esta interfaz se usa para crear bibliotecas de formularios específicos de la aplicación. 
  
|||
|:-----|:-----|
|Archivo de encabezado:  <br/> |MAPIForm.h  <br/> |
|Expuestos por:  <br/> |Objetos de contenedor de formulario  <br/> |
|Se implementa mediante:  <br/> |Proveedores de biblioteca de formulario  <br/> |
|Llamado por:  <br/> |Aplicaciones cliente  <br/> |
|Identificador de interfaz:  <br/> |IID_IMAPIFormContainer  <br/> |
|Tipo de puntero:  <br/> |LPMAPIFORMCONTAINER  <br/> |
   
## <a name="vtable-order"></a>Orden vtable

|||
|:-----|:-----|
|[InstallForm](imapiformcontainer-installform.md) <br/> |Instala un formulario en un contenedor de formulario.  <br/> |
|[RemoveForm](imapiformcontainer-removeform.md) <br/> |Quita un formulario en particular de un contenedor de formulario.  <br/> |
|[ResolveMessageClass](imapiformcontainer-resolvemessageclass.md) <br/> |Una clase de mensaje se resuelve en su formulario en un contenedor de formulario y devuelve un objeto de información de formulario para ese formulario.  <br/> |
|[ResolveMultipleMessageClasses](imapiformcontainer-resolvemultiplemessageclasses.md) <br/> |Se resuelve un grupo de clases de mensajes en sus formularios en un contenedor de formulario y devuelve una matriz de formulario objetos de información para los formularios.  <br/> |
|[CalcFormPropSet](imapiformcontainer-calcformpropset.md) <br/> |Devuelve una matriz de las propiedades de todos los formularios instalados en un contenedor de formulario.  <br/> |
|[GetDisplay](imapiformcontainer-getdisplay.md) <br/> |Devuelve el nombre para mostrar de un contenedor de formulario.  <br/> |
|[GetLastError](imapiformcontainer-getlasterror.md) <br/> |Devuelve una estructura [MAPIERROR](mapierror.md) que contiene información sobre el error anterior que se producen en el objeto de contenedor de formulario.  <br/> |
   
## <a name="see-also"></a>Recursos adicionales



[Interfaces MAPI](mapi-interfaces.md)

