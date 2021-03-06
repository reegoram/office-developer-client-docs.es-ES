---
title: Ejemplo XML de amigos
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 83afbdef-4f12-4673-a0c1-bbf86274558f
description: El ejemplo de XML de este tema es una cadena XML de amigo devuelta a Outlook Social Connector (OSC) después de que llama al método ISocialPerson::GetFriendsAndColleagues. En el ejemplo se muestra el XML de amigos para dos amigos, que cada uno delimitado por el elemento person. Cada uno de ellos especifica un valor único para el elemento de identificador de usuario en la red social.
ms.openlocfilehash: 5dbda1e4439f807ccc6e7abddd0ef654ae801fe0
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395213"
---
# <a name="friends-xml-example"></a>Ejemplo XML de amigos

El ejemplo de XML de este tema es una cadena XML de amigo devuelta a Outlook Social Connector (OSC) después de que llama al método [ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) . El ejemplo muestra el XML **amigos** para dos amigos, que cada uno delimitado por el elemento de la **persona** . Cada uno de ellos especifica un valor único para el elemento de **identificador de usuario** en la red social. 
  
Los elementos restantes de **amigos** XML tienen nombres explican por sí solos. Para una descripción detallada de estos elementos, vea [XML para amigos](xml-for-friends.md). 
  
## <a name="xml-example"></a>Ejemplo de XML

En el ejemplo siguiente se muestra el XML **amigos** para dos personas en la red social. 
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<friends xmlns="https://schemas.microsoft.com/office/outlook/2010/06/socialprovider.xsd">
  <person>
    <userID>4667647</userID>
    <firstName>Melissa</firstName>
    <lastName>MacBeth</lastName>
    <nickname></nickname>
    <fileAs>MacBeth, Melissa (Contoso Ltd.)</fileAs>
    <company>Contoso Ltd.</company>
    <title>Product Manager</title>
    <anniversary>2005-05-17</anniversary>
    <birthday>1979-08-09</birthday>
    <emailAddress>melissa@contoso.com</emailAddress>
    <emailAddress2>melissa@fabrikam.com</emailAddress2>
    <emailAddress3>melissa@adventureworks.com</emailAddress3>
    <webProfilePage>https://contoso.com/melissa</webProfilePage>
    <phone>800-555-1212</phone>
    <cell>888-555-1212</cell>
    <workPhone>425-555-1212</workPhone>
    <creationTime>2010-01-08T08:30:20-08:00</creationTime>
    <lastModificationTime>2010-01-08T11:40:14-08:00</lastModificationTime>
    <expirationTime>2010-01-09T11:40:14-08:00</expirationTime>
    <gender>female</gender>
    <index>0</index>
  </person>
  <person>
    <userID>5015012</userID>
    <firstName>Michael</firstName>
    <lastName>Affronti</lastName>
    <nickname>Mr. Social</nickname>
    <fileAs>Affronti, Michael (Contoso Ltd.)</fileAs>
    <company>Contoso Ltd.</company>
    <title>Sales Director</title>
    <anniversary>2009-06-21</anniversary>
    <birthday>1980-09-10</birthday>
    <emailAddress>michael@contoso.com</emailAddress>
    <emailAddress2>michael@fabrikam.com</emailAddress2>
    <emailAddress3>michael@adventureworks.com</emailAddress3>
    <webProfilePage>https://contoso.com/michael</webProfilePage>
    <phone>800-555-1212</phone>
    <cell>888-555-1212</cell>
    <workPhone>425-555-1212</workPhone>
    <creationTime>2010-01-08T08:30:20-08:00</creationTime>
    <lastModificationTime>2010-01-08T11:40:14-08:00</lastModificationTime>
    <expirationTime>2010-01-09T11:40:14-08:00</expirationTime>
    <gender>male</gender>
    <index>1</index>
  </person>
</friends>

```

## <a name="see-also"></a>Vea también

- [Ejemplos XML de proveedor OSC](osc-provider-xml-examples.md)  
- [Ejemplo de XML de capacidades](capabilities-xml-example.md) 
- [Ejemplo de XML de fuentes de actividades](activity-feed-xml-example.md) 
- [Esquema XML de proveedor de Outlook Social Connector](outlook-social-connector-provider-xml-schema.md)

