---
title: currentType complexType (esquema de información de meteorología de Outlook)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9f4663ac-13d3-6c46-f839-ba6bca4047a3
description: Define los parámetros acerca de las condiciones del tiempo actual de una ubicación.
ms.openlocfilehash: 16d3e23375f68315c9b9f3a7e914d93f4fec9d0a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387037"
---
# <a name="currenttype-complextype-outlook-weather-information-schema"></a>currentType complexType (esquema de información de meteorología de Outlook)

Define los parámetros acerca de las condiciones del tiempo actual de una ubicación.
  
## <a name="type-information"></a>Información de tipos

|||
|:-----|:-----|
|**Namespace** <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|**Archivo de esquema** <br/> |GetWeatherInfo.xsd  <br/> |
|**Base de extensión** <br/> |Ninguna  <br/> |
   
## <a name="definition"></a>Definición

```XML
       <xs:complexType name="currentType">
     <xs:attribute name="winddisplay"   type="xs:string"      use="required"     />
     <xs:attribute name="windspeed"   type="xs:integer"      use="required"     />
     <xs:attribute name="humidity"   type="xs:integer"      use="required"     />
     <xs:attribute name="feelslike"   type="xs:integer"      use="required"     />
     <xs:attribute name="observationpoint"   type="xs:string"      use="required"     />
     <xs:attribute name="observationtime"   type="xs:time"      use="required"     />
     <xs:attribute name="date"   type="xs:date"      use="required"     />
     <xs:attribute name="skytext"   type="xs:string"      use="required"     />
     <xs:attribute name="skycode"   type="xs:integer"      use="required"     />
     <xs:attribute name="temperature"   type="xs:integer"      use="required"     />
     <xs:attribute name="shortday"   type="xs:string"      use="optional"     />
     <xs:attribute name="day"   type="xs:string"      use="optional"     />
       </xs:complexType>

```

## <a name="elements-and-attributes"></a>Elementos y atributos

Si el esquema define requisitos específicos, como **sequence**, **minOccurs**, **maxOccurs**y **choice**, consulte la sección definición. 
  
### <a name="child-elements"></a>Elementos secundarios

Ninguno.
  
### <a name="attributes"></a>Atributos

|**Attribute**|**Tipo**|**Obligatorio**|**Descripción**|**Valores posibles**|
|:-----|:-----|:-----|:-----|:-----|
|date  <br/> |xs: Date  <br/> |necesario  <br/> |Especifica la fecha de hoy.  <br/> |Un valor de tipo de xs: Date  <br/> |
|día  <br/> |xs:string  <br/> |opcional  <br/> |Especifica un día para la previsión.  <br/> |Un valor del tipo xs: String  <br/> |
|feelslike  <br/> |xs:integer  <br/> |necesario  <br/> |Especifica la temperatura de cómo se siente la meteorología actual como.  <br/> |Un valor del tipo xs: Integer  <br/> |
|humedad  <br/> |xs:integer  <br/> |necesario  <br/> |Especifica el valor numérico humedad actual.  <br/> |Un valor del tipo xs: Integer  <br/> |
|observationpoint  <br/> |xs:string  <br/> |necesario  <br/> |Especifica dónde se observa la información meteorológica actual desde.  <br/> |Un valor del tipo xs: String  <br/> |
|observationtime  <br/> |xs: Time  <br/> |necesario  <br/> |Especifica cuándo se observa la información meteorológica actual en.  <br/> |Un valor del tipo de xs: Time  <br/> |
|shortday  <br/> |xs:string  <br/> |opcional  <br/> |Especifica un día de forma abreviada.  <br/> |Un valor del tipo xs: String  <br/> |
|skycode  <br/> |xs:integer  <br/> |necesario  <br/> |Especifica un código de número entero para las condiciones del tiempo actual.  <br/> |Un valor del tipo xs: Integer  <br/> |
|skytext  <br/> |xs:string  <br/> |necesario  <br/> |Especifica las palabras de uno o dos que describa las condiciones de tiempo actual.  <br/> |Un valor del tipo xs: String  <br/> |
|temperatura  <br/> |xs:integer  <br/> |necesario  <br/> |Especifica la temperatura de la ubicación actual.  <br/> |Un valor del tipo xs: Integer  <br/> |
|winddisplay  <br/> |xs:string  <br/> |necesario  <br/> |Una cadena que describe las condiciones de aire actual.  <br/> |Un valor del tipo xs: String  <br/> |
|velocidad del viento  <br/> |xs:integer  <br/> |necesario  <br/> |Especifica el valor actual de la velocidad de aire numéricos.  <br/> |Un valor del tipo xs: Integer  <br/> |
   

