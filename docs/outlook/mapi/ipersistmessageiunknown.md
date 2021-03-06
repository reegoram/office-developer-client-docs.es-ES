---
title: IPersistMessage IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage
api_type:
- COM
ms.assetid: 40ec6dd4-2206-4e59-aafe-53aaf693f973
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 7eb65bbae2fca6648c3a701dfa5c83c5bf297ec5
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396186"
---
# <a name="ipersistmessage--iunknown"></a>IPersistMessage : IUnknown

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Permite que los visores de formulario controlar el almacenamiento de un formulario y para la transición entre los distintos Estados.
  
|||
|:-----|:-----|
|Archivo de encabezado:  <br/> |MAPIForm.h  <br/> |
|Expuestos por:  <br/> |Conservar los objetos de mensaje  <br/> |
|Implementado por:  <br/> |Objetos de formulario  <br/> |
|Llamado por:  <br/> |Visores de formulario  <br/> |
|Identificador de interfaz:  <br/> |IID_IPersistMessage  <br/> |
|Tipo de puntero:  <br/> |LPPERSISTMESSAGE  <br/> |
   
## <a name="vtable-order"></a>Orden vtable

|||
|:-----|:-----|
|[GetLastError](ipersistmessage-getlasterror.md) <br/> |Devuelve una estructura [MAPIERROR](mapierror.md) que contiene información sobre el error anterior en el objeto de formulario.  <br/> |
|[GetClassID](ipersistmessage-getclassid.md) <br/> |Devuelve un identificador que representa el servidor de formulario que puede administrar el formulario.  <br/> |
|[IsDirty](ipersistmessage-isdirty.md) <br/> |Comprueba el formulario para que los cambios realizados desde la última vez que guardó.  <br/> |
|[InitNew](ipersistmessage-initnew.md) <br/> |Inicializa un nuevo mensaje.  <br/> |
|[Load](ipersistmessage-load.md) <br/> |Carga el formulario para un mensaje especificado.  <br/> |
|[Save](ipersistmessage-save.md) <br/> |Guarda un formulario revisado el mensaje desde la que se ha cargado o creado.  <br/> |
|[SaveCompleted](ipersistmessage-savecompleted.md) <br/> |Se notifica el formulario que guarda una operación se ha completado.  <br/> |
|[HandsOffMessage](ipersistmessage-handsoffmessage.md) <br/> |Hace que el formulario liberar su mensaje actual.  <br/> |
   
## <a name="remarks"></a>Comentarios

Todos los formularios necesarios para implementar la interfaz **IPersistMessage** . 
  
 **IPersistMessage** funciona de manera similar a la interfaz OLE [IPersistStorage](https://msdn.microsoft.com/library/1c1a20fc-c101-4cbc-a7a6-30613aa387d7%28Office.15%29.aspx) . Para obtener más información, vea los métodos **IPersistStorage** . 
  
## <a name="see-also"></a>Vea también



[Interfaces MAPI](mapi-interfaces.md)

