---
title: Elemento de RefreshConflict (DataRecordSet_Type complexType) ('XML de Visio')
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 373983f7-fc0c-95f6-7665-7ed47de82e5e
description: Indica una fila en el conjunto de registros de datos vinculada a una forma que está en conflicto después de actualiza el conjunto de registros de datos.
ms.openlocfilehash: 2da6f98cf7b047564331aaf5a4167e392927a155
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397404"
---
# <a name="refreshconflict-element-datarecordsettype-complextype-visio-xml"></a>Elemento de RefreshConflict (DataRecordSet_Type complexType) ('XML de Visio')

Indica una fila en el conjunto de registros de datos vinculada a una forma que está en conflicto después de actualiza el conjunto de registros de datos.
  
## <a name="element-information"></a>Información del elemento

|||
|:-----|:-----|
|**Tipo de elemento** <br/> |[RefreshConflict_Type](refreshconflict_type-complextypevisio-xml.md) <br/> |
|**Namespace** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**Archivo de esquema** <br/> |VisioSchema15.xsd  <br/> |
|**Elementos de documento** <br/> |Recordsets.Xml  <br/> |
   
## <a name="definition"></a>Definición

```XML
< xs:element name="RefreshConflict" type="RefreshConflict_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element>
```

## <a name="elements-and-attributes"></a>Elementos y atributos

Si el esquema define requisitos específicos, como **sequence**, **minOccurs**, **maxOccurs**y **choice**, consulte la sección definición. 
  
### <a name="parent-elements"></a>Elementos principales

|**Element**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|[DataRecordSet](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[DataRecordSet_Type](datarecordset_type-complextypevisio-xml.md) <br/> |Almacena, actualiza, expone y da formato a los datos consultados en una base de datos de Microsoft Visio.  <br/> |
   
### <a name="child-elements"></a>Elementos secundarios

Ninguno.
  
### <a name="attributes"></a>Atributos

|**Attribute**|**Tipo**|**Obligatorio**|**Descripción**|**Valores posibles**|
|:-----|:-----|:-----|:-----|:-----|
|PageID  <br/> |xsd:unsignedInt  <br/> |necesario  <br/> |Identificador de página de la forma implica en el conflicto.  <br/> |Valores del tipo xsd:unsignedInt.  <br/> |
|RowID  <br/> |xsd:unsignedInt  <br/> |necesario  <br/> |El identificador de fila original de la fila ahora en conflicto después de que se actualizan los datos.  <br/> |Valores del tipo xsd:unsignedInt.  <br/> |
|ShapeID  <br/> |xsd:unsignedInt  <br/> |necesario  <br/> |Identificador de la forma de la forma implica en el conflicto.  <br/> |Valores del tipo xsd:unsignedInt.  <br/> |
   

