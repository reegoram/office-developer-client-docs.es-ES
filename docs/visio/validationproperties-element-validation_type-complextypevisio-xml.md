---
title: Elemento de propiedadesla (Validation_Type complexType) ('XML de Visio')
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a51a60c9-479b-7d7b-860f-bb46fc8b4d63
description: Encapsula las propiedades que están relacionadas con la validación del documento.
ms.openlocfilehash: 9eccb85bd7463411d81c867eda3216d6c9a207f2
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385224"
---
# <a name="validationproperties-element-validationtype-complextype-visio-xml"></a>Elemento de propiedadesla (Validation_Type complexType) ('XML de Visio')

Encapsula las propiedades que están relacionadas con la validación del documento.
  
## <a name="element-information"></a>Información del elemento

|||
|:-----|:-----|
|**Tipo de elemento** <br/> |[ValidationProperties_Type](validationproperties_type-complextypevisio-xml.md) <br/> |
|**Namespace** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**Archivo de esquema** <br/> |VisioSchema15.xsd  <br/> |
|**Elementos de documento** <br/> |Validation.Xml  <br/> |
   
## <a name="definition"></a>Definición

```XML
< xs:element name="ValidationProperties" type="ValidationProperties_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>Elementos y atributos

Si el esquema define requisitos específicos, como **sequence**, **minOccurs**, **maxOccurs**y **choice**, consulte la sección definición. 
  
### <a name="parent-elements"></a>Elementos principales

|**Element**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|[Validación](validation-elementvisio-xml.md) <br/> |[Validation_Type](validation_type-complextypevisio-xml.md) <br/> |Almacena información sobre la validación del diagrama para el documento.  <br/> |
   
### <a name="child-elements"></a>Elementos secundarios

Ninguno.
  
### <a name="attributes"></a>Atributos

|**Attribute**|**Tipo**|**Obligatorio**|**Descripción**|**Valores posibles**|
|:-----|:-----|:-----|:-----|:-----|
|LastValidated  <br/> |xsd: DateTime  <br/> |necesario  <br/> |La fecha y hora en que el documento se ha validado por última vez.  <br/> |Valores del tipo XSD: DateTime.  <br/> |
|ShowIgnored  <br/> |Boolean con tipo  <br/> |necesario  <br/> |Especifica si se muestran los problemas de validación omitidos en la ventana problemas.  <br/> |Valores del tipo Boolean con tipo.  <br/> |
   

