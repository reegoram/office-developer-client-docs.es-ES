---
title: Elemento de celda (fila NURBSTo) ('XML de Visio')
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e76bae8f-b9de-39ef-1f56-b00a6cd2ba6c
description: Contiene las coordenadas x o y, la posición del segundo al último nodo, la posición del último grosor, la posición del primer nodo, la posición del primer grosor o la fórmula para una B-spline racional no uniforme (NURBS).
ms.openlocfilehash: f23f73d67d72f9536dc7ffe9e083058ea9306217
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392805"
---
# <a name="cell-element-nurbsto-row-visio-xml"></a>Elemento de celda (fila NURBSTo) ('XML de Visio')

Contiene las coordenadas x o y, la posición del segundo al último nodo, la posición del último grosor, la posición del primer nodo, la posición del primer grosor o la fórmula para una B-spline racional no uniforme (NURBS).
  
## <a name="element-information"></a>Información del elemento

|||
|:-----|:-----|
|**Tipo de elemento** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**Namespace** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**Archivo de esquema** <br/> |VisioSchema15.xsd  <br/> |
|**Elementos de documento** <br/> |master # .xml, # .xml de página  <br/> |
   
## <a name="definition"></a>Definición

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>Elementos y atributos

Si el esquema define requisitos específicos, como **sequence**, **minOccurs**, **maxOccurs**y **choice**, consulte la sección definición. 
  
### <a name="parent-elements"></a>Elementos principales

|**Element**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|[Elemento de fila (geometría)](row-element-geometry-sectionvisio-xml.md) <br/> |[NURBSTo_Type](nurbsto_type-complextypevisio-xml.md) <br/> |Contiene las coordenadas x o y, la posición del segundo al último nodo, la posición del último grosor, la posición del primer nodo, la posición del primer grosor o la fórmula para una B-spline racional no uniforme (NURBS).  <br/> |
   
### <a name="child-elements"></a>Elementos secundarios

|**Element**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|[RefBy](refby-element-cell_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |Especifica una referencia a una página de dibujo.  <br/> |
   
### <a name="attributes"></a>Atributos

|**Attribute**|**Tipo**|**Obligatorio**|**Descripción**|**Valores posibles**|
|:-----|:-----|:-----|:-----|:-----|
|E  <br/> |xsd: String  <br/> |opcional  <br/> |Indica que la fórmula da como resultado un error. El valor de **E** es el valor actual (una cadena de mensaje de error); el valor del atributo **V** es el último valor válido.  <br/> |Una cadena de mensaje de error.  <br/> |
|F  <br/> |xsd: String  <br/> |opcional  <br/> | Representa la fórmula del elemento. Este atributo puede contener uno de las siguientes cadenas:  <br/>  '(algunos fórmula)' Si la fórmula existe localmente  <br/>  `No Formula`Si la fórmula se ha eliminado localmente o bloqueada  <br/>  `Inh`Si la fórmula es heredada.  <br/> |Una fórmula.  <br/> |
|N  <br/> |xsd: String  <br/> |necesario  <br/> |Representa el nombre de la celda ShapeSheet.  <br/> |El nombre de la celda ShapeSheet.  <br/> Vea la sección comentarios que aparece a continuación.  <br/> |
|U  <br/> |xsd: String  <br/> |opcional  <br/> |Representa una unidad de medida, el valor predeterminado es DL.  <br/> |Las unidades de la celda.  <br/> |
|V  <br/> |xsd: String  <br/> |opcional  <br/> |Representa el valor de la celda.  <br/> |El valor de la celda ShapeSheet.  <br/> |
   
## <a name="remarks"></a>Comentarios

El atributo **N** de este elemento de **celda** debe ser uno de un conjunto limitado de valores que corresponden a las celdas de ShapeSheet. Hacer referencia a la tabla siguiente para determinar los valores del atributo **N** permitidas para este elemento de **celda** . 
  
|**Valor**|**Descripción**|**Más información**|
|:-----|:-----|:-----|
|X  <br/> |Coordenada x del último punto de control de una NURBS.  <br/> |[Fila NURBSTo (Sección de Geometría)](nurbsto-row-geometry-section.md) <br/> |
|v  <br/> |Coordenada y del último punto de control de una NURBS.  <br/> |[Fila NURBSTo (Sección de Geometría)](nurbsto-row-geometry-section.md) <br/> |
|A  <br/> |Penúltimo nodo de una NURBS.  <br/> |[Fila NURBSTo (Sección de Geometría)](nurbsto-row-geometry-section.md) <br/> |
|B  <br/> |Último grosor de una NURBS.  <br/> |[Fila NURBSTo (Sección de Geometría)](nurbsto-row-geometry-section.md) <br/> |
|C  <br/> |Primer nodo de una NURBS.  <br/> |[Fila NURBSTo (Sección de Geometría)](nurbsto-row-geometry-section.md) <br/> |
|D  <br/> |Primer grosor de una NURBS.  <br/> |[Fila NURBSTo (Sección de Geometría)](nurbsto-row-geometry-section.md) <br/> |
|E  <br/> |Fórmula de NURBS.  <br/> |[Fila NURBSTo (Sección de Geometría)](nurbsto-row-geometry-section.md) <br/> |
   

