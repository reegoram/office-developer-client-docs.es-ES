---
title: OpenIMsgSession
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.OpenIMsgSession
api_type:
- COM
ms.assetid: f75229e3-5f44-4298-8706-9eddf0ef124c
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 607105bd58a14a3510f1ae71246069440a4f05cb
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389627"
---
# <a name="openimsgsession"></a>OpenIMsgSession

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Crea y se abre una sesión de mensajería que agrupa los mensajes creados dentro de él. 
  
|||
|:-----|:-----|
|Archivo de encabezado:  <br/> |IMessage.h  <br/> |
|Implementado por:  <br/> |MAPI  <br/> |
|Llamado por:  <br/> |Las aplicaciones cliente y los proveedores de servicios  <br/> |
   
```cpp
SCODE OpenIMsgSession(
  LPMALLOC lpMalloc,
  ULONG ulFlags,
  LPMSGSESS FAR * lppMsgSess
);
```

## <a name="parameters"></a>Parámetros

 _lpMalloc_
  
> [entrada] Puntero a un objeto del asignador de memoria exposición de la interfaz de OLE [IMalloc](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-imalloc) . Debe usar este método de asignación al trabajar con la interfaz OLE [IStorage](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istorage) MAPI. 
    
 _ulFlags_
  
> [entrada] Reservado; debe ser cero. 
    
 _lppMsgSess_
  
> [out] Puntero a un puntero al objeto de sesión del mensaje devuelto.
    
## <a name="return-value"></a>Valor devuelto

S_OK
  
> Se abrió la sesión.
    
MAPI_E_INVALID_PARAMETER
  
>  _lpMalloc_ o _lppMsgSess_ es NULL. 
    
MAPI_E_INVALID_FLAGS
  
> Se pasaron indicadores no válidos.
    
MAPI_UNICODE.
  
> Cuando se llama a esta función, un proveedor de servicio o cliente establece el indicador MAPI_UNICODE para crear archivos .msg de Unicode. El archivo [Imessage](imessageimapiprop.md) resultante muestra STORE_UNICODE_OK en su PR_STORE_SUPPORT_MASK y es compatible con propiedades de Unicode. 
    
## <a name="remarks"></a>Comentarios

Una sesión de mensajería se usa por las aplicaciones cliente y proveedores de servicios que desean para abordar los problemas con varios relacionados con MAPI [IMessage: IMAPIProp](imessageimapiprop.md) objetos fundamentan objetos OLE **IStorage** subyacentes. El cliente o el proveedor utiliza las funciones **OpenIMsgSession** y [CloseIMsgSession](closeimsgsession.md) para ajustar la creación de este tipo de mensajes dentro de una sesión de mensajería. Una vez que se abre la sesión de mensajería, el cliente o el proveedor pasa un puntero a ella en una llamada a [OpenIMsgOnIStg](openimsgonistg.md) para crear un nuevo **IMessage**- en - objeto **IStorage** . 
  
Una sesión de mensajería realiza un seguimiento de todos los **IMessage**- en - objetos **IStorage** creados durante la duración de la sesión, además de todos los datos adjuntos y otras propiedades de los mensajes. Cuando un cliente o un proveedor de llamadas **CloseIMsgSession**, cierra todos estos objetos. Al llamar a **CloseIMsgSession** es la única forma de cerrar **IMessage**- en - objetos **IStorage** . 
  
 **OpenIMsgSession** se usa en los clientes y proveedores que requieren la capacidad para manejar varios mensajes relacionados como objetos OLE **IStorage** . Si sólo hay un mensaje de este tipo esté abierto en un momento, no es necesario realizar un seguimiento de varios mensajes y no hay motivo para crear una sesión de mensajería con **OpenIMsgSession**. 
  
Debido a que se trata de un objeto OLE subyacente, MAPI debe usar la asignación de memoria OLE. Para obtener más información acerca de los objetos de almacenamiento estructurado OLE y asignación de memoria OLE, vea [OLE y la transferencia de datos](https://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx). 
  

