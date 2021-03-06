---
title: CompareBookmarks (método, ADO)
TOCTitle: CompareBookmarks Method (ADO)
ms:assetid: 826cb3c7-2f5c-284f-421d-6b7b07f14dec
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249564(v=office.15)
ms:contentKeyID: 48545977
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9fc4cf3540d22d3981bb13a7af3251dd625c2c99
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "25606251"
---
# <a name="comparebookmarks-method-ado"></a>CompareBookmarks (método, ADO)


**Se aplica a**: Access 2013 | Office 2013

Compara dos marcadores y devuelve una indicación de sus valores relativos.

## <a name="syntax"></a>Sintaxis

*resultado de* = *conjunto de registros*. CompareBookmarks (*Bookmark1*, *Bookmark2*)

<<<<<<< HEAD
## <a name="return-value"></a>Valor devuelto
=======
## <a name="return-value"></a>Valor devuelto
>>>>>>> master

Devuelve un valor de [CompareEnum](compareenum.md) que indica la posición de fila relativa de dos registros representados por sus marcadores.

## <a name="parameters"></a>Parámetros

  - *Bookmark1*

  - Marcador de la primera fila.

  - *Bookmark2*

  - Marcador de la segunda fila.

## <a name="remarks"></a>Comentarios

Los marcadores deben aplicarse al mismo objeto [Recordset](recordset-object-ado.md), o bien, a un objeto **Recordset** y su [duplicado](clone-method-ado.md). No se pueden comparar de manera confiable los marcadores de diferentes objetos **Recordset**, aunque se crearon a partir del mismo origen o comando. Tampoco se pueden comparar los marcadores de un objeto **Recordset** cuyo proveedor subyacente no admite comparaciones.

Un marcador identifica de manera única una fila de un objeto **Recordset**. Use la propiedad [Bookmark](bookmark-property-ado.md) de la fila actual para obtener su marcador.

Dado que el tipo de datos de un marcador es específico del proveedor, ADO lo expone como Variant. Por ejemplo, los marcadores de SQL Server son de tipo DBTYPE\_R8 (Double). ADO expondrá este tipo como Variant con un subtipo Double.

Cuando se comparan marcadores, ADO no intenta aplicar ningún tipo de conversión. Los valores se pasan simplemente al proveedor donde se lleva a cabo la comparación. Si los marcadores que se pasan al método **CompareBookmarks** están almacenados en variables de diferentes tipos, puede que se genere el error de inconsistencia de tipos "Argumentos incorrectos, fuera del intervalo permitido o en conflicto con otros".

Un marcador no válido o incorrectamente creado generará un error.

