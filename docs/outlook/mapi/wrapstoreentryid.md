---
title: WrapStoreEntryID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- WrapStoreEntryID
api_type:
- HeaderDef
ms.assetid: b20107e3-5e23-4cde-9cd6-670c914ea70a
description: '�ltima modificaci�n: lunes, 9 de marzo de 2015'
ms.openlocfilehash: aff46cca7a7d530b2eede1790176058e3b91abc8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19820983"
---
# <a name="wrapstoreentryid"></a>WrapStoreEntryID

  
  
**Se aplica a**: Outlook 
  
Convierte el identificador de entrada interno de un almacén de mensajes en un identificador de entrada más utilizable por el sistema de mensajería. 
  
|||
|:-----|:-----|
|Archivo de encabezado:  <br/> |Mapidefs.h  <br/> |
|Se implementa mediante:  <br/> |MAPI  <br/> |
|Llamado por:  <br/> |Las aplicaciones cliente y los proveedores de servicios  <br/> |
   
```cpp
WrapStoreEntryID(
  ULONG ulFlags,
  LPSTR szDLLName,
  ULONG cbOrigEntry,
  LPENTRYID lpOrigEntry,
  ULONG * lpcbWrappedEntry,
  LPENTRYID * lppWrappedEntry
);
```

## <a name="parameters"></a>Par�metros

 _ulFlags_
  
> [entrada] Máscara de bits de indicadores. Se puede establecer la marca siguiente:
    
MAPI_UNICODE. 
  
> Las cadenas están en formato Unicode. Si no está establecido el indicador MAPI_UNICODE., las cadenas están en formato ANSI. 
    
 _szDLLName_
  
> [entrada] El nombre del proveedor de almacén de DLL de mensaje. 
    
 _cbOrigEntry_
  
> [entrada] Tamaño, en bytes, del identificador de entrada original para el almacén de mensajes. 
    
 _lpOrigEntry_
  
> [entrada] Puntero a una estructura [ENTRYID](entryid.md) que contiene el identificador de entrada original. 
    
 _lpcbWrappedEntry_
  
> [out] Puntero al tamaño, en bytes, del nuevo identificador de entrada. 
    
 _lppWrappedEntry_
  
> [out] Puntero a un puntero a una estructura **ENTRYID** que contiene el nuevo identificador de entrada. 
    
## <a name="return-value"></a>Valor devuelto

Ninguno.
  
## <a name="remarks"></a>Observaciones

Un objeto de almacén de mensajes mantiene un identificador interno de entrada que es significativo sólo a coresident de proveedores de servicio con ese almacén de mensajes. Para otros componentes de mensajería MAPI proporciona una versión ajustada del identificador de entrada interna que hace que sea reconocible como que pertenecen al almacén de mensajes. Proveedores de servicios de coresident siempre se deben proporcionar el identificador de entrada de almacén de mensajes no ajustado original; siempre se deben proporcionar a las aplicaciones cliente de la versión ajustada, que es, a continuación, puede utilizar en cualquier lugar en el dominio de mensajería y en otros dominios. 
  
Puede ajustar un identificador de entrada del almacén de mensaje mediante la función **WrapStoreEntryID** o el método [IMAPISupport::WrapStoreEntryID](imapisupport-wrapstoreentryid.md) , que llama a la función **WrapStoreEntryID** en un proveedor de servicios. El proveedor debe ajustar el identificador de entrada al exponer de **entrada del objeto** ([PidTagEntryId](pidtagentryid-canonical-property.md)) del almacén de mensajes (propiedad) o escribir en una sección de perfil y cuando se exponen **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) propiedad. MAPI ajusta a un identificador de entrada del almacén de mensaje al responder a una llamada de [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) . 
  
Cuando una aplicación cliente pasa un identificador de entrada del almacén de mensaje ajustadas a MAPI, por ejemplo en una llamada [IMAPISession::OpenEntry](imapisession-openentry.md) , MAPI desajusta el identificador de entrada antes de usar para llamar a un método de proveedor, como [IMSProvider::Logon](imsprovider-logon.md) o [ IMSProvider::CompareStoreIDs](imsprovider-comparestoreids.md). 
  
