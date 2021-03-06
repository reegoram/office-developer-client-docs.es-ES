---
title: PROP_ACCT_PREFERENCES_UID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ec0aac33-624e-48f7-8177-8f7b8db6af7d
description: Recupera el identificador exclusivo (UID) de la sección de perfil que almacena las preferencias de cuenta.
ms.openlocfilehash: 97f1a858c8f58e13b72b8d5f052b35359581b718
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395297"
---
# <a name="propacctpreferencesuid"></a>PROP_ACCT_PREFERENCES_UID

Recupera el identificador exclusivo (UID) de la sección de perfil que almacena las preferencias de cuenta. 
  
## <a name="quick-info"></a>Información rápida

Vea [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|Identificador:  <br/> |0 x 0022  <br/> |
|Tipo de propiedad:  <br/> |PT_BINARY  <br/> |
|Etiqueta de la propiedad:  <br/> |0x00220102  <br/> |
|Access:  <br/> |Solo lectura  <br/> |
   
## <a name="remarks"></a>Comentarios

Use **PROP_ACCT_PREFERENCES_UID** en las llamadas a [IMAPISupport::OpenProfileSection](https://msdn.microsoft.com/library/cd1fa994-9531-46c4-94e5-505e7f90b884%28Office.15%29.aspx) para recuperar la sección de perfil que contiene las preferencias de cuenta. 
  
## <a name="see-also"></a>Vea también

- [Acerca de la API de administración de cuenta](about-the-account-management-api.md)
- [Acerca de la configuración de bloqueo de correo basura](about-anti-spam-settings.md)

