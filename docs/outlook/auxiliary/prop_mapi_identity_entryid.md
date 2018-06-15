---
title: PROP_MAPI_IDENTITY_ENTRYID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c64db8ea-d6ad-4fb9-97aa-958e5a0daf8f
description: Recupera o establece el identificador de entrada de la libreta de direcciones para la cuenta.
ms.openlocfilehash: d85a779da36c2780fe058f906086f61cfc47d5d1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19816322"
---
# <a name="propmapiidentityentryid"></a>PROP_MAPI_IDENTITY_ENTRYID

Recupera o establece el identificador de entrada de la libreta de direcciones para la cuenta.
  
## <a name="quick-info"></a>Información rápida

Vea [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|Identificador:  <br/> |0 x 2002  <br/> |
|Tipo de propiedad:  <br/> |PT_BINARY  <br/> |
|Etiqueta de la propiedad:  <br/> |0x20020102  <br/> |
|Access:  <br/> |Es de lectura y escritura.  <br/> |
   
## <a name="remarks"></a>Notas

 **Propiedades\_MAPI\_identidad\_ENTRYID** no se espera que existen en cada cuenta. Por ejemplo, podría tener una cuenta de Exchange **propiedades\_MAPI\_identidad\_ENTRYID** establecer y no [propiedades\_ACCT_USER_EMAIL_ADDR](prop_acct_user_email_addr.md), mientras que para una cuenta POP3/SMTP se invierte la situación. **PROPIEDADES\_MAPI_IDENTITY_ENTRYID** devuelve un identificador de entrada que es similar al valor devuelto por _lppEntryID_ en [IMAPISession::QueryIdentity](http://msdn.microsoft.com/library/a2cdda90-5457-49a7-b98c-7273ffe5cbbc%28Office.15%29.aspx). 
  
## <a name="see-also"></a>Ver también

- [Acerca de la API de administración de cuenta](about-the-account-management-api.md)
