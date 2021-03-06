---
title: HrGetGALFromEmsmdbUID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9b824e70-ed9a-490c-b777-8902a793fece
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 4b05baf1f819a821da3496cc63c2b2980894efd7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575717"
---
# <a name="hrgetgalfromemsmdbuid"></a>HrGetGALFromEmsmdbUID

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Devuelve el identificador de entrada de la libreta de direcciones global para el servicio de Exchange identificado por _pEmsmdbUID_. Debe liberar el identificador de la entrada devuelta mediante [MAPIFreeBuffer](mapifreebuffer.md).
  
|||
|:-----|:-----|
|Archivo de encabezado:  <br/> |abhelp.h  <br/> |
|Se implementa mediante:  <br/> |MAPI  <br/> |
|Llamado por:  <br/> |Las aplicaciones cliente y los proveedores de servicios  <br/> |
   
```cpp
HRESULT HrGetGALFromEmsmdbUID(
  LPMAPISESSION pSess,
  LPADRBOOK lpAdrBook,
  const MAPIUID * pEmsmdbUID,
  ULONG * lpcbeid,
  LPENTRYID * lppeid
);
```

## <a name="parameters"></a>Parámetros

 _pSess_
  
> [entrada] La ha iniciado la sesión IMAPISession. No puede ser NULL.
    
 _pAddrBook_
  
> [entrada] La libreta de direcciones que se usó para abrir el identificador de entrada. No puede ser NULL.
    
 _pEmsmdbUID_
  
> [entrada] Un puntero a un **emsmdbUID** que identifica la lista global de direcciones del servicio de Exchange que se va a recuperar. Si _pEmsmdbUID_ es NULL o el UID cero, esta función obtiene la LGD heredada del servicio de Exchange. 
    
 _lpcbeid_
  
> [out] Un puntero para el número de bytes del identificador de entrada de la lista global de direcciones.
    
 _lppeid_
  
> [out] Un puntero al identificador de entrada de la lista global de direcciones. Esto debe liberarse mediante [MAPIFreeBuffer](mapifreebuffer.md).
    

