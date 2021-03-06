---
title: Conjuntos de registros filtrados y jerárquicos persistentes
TOCTitle: Persisting Filtered and Hierarchical Recordsets
ms:assetid: 3648a997-dac7-d8a3-3cca-a6827f26a4f0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249120(v=office.15)
ms:contentKeyID: 48544162
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d29fe867933bdff93d064a95a4fc95c65e8605f8
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484464"
---
# <a name="persisting-filtered-and-hierarchical-recordsets"></a>Conjuntos de registros filtrados y jerárquicos persistentes


**Se aplica a**: Access 2013 | Office 2013

Si la propiedad [Filter](filter-property-ado.md) está activada para el **conjunto de registros**, solo se guardarán las filas para las que se tenga acceso con el filtro. Si el **conjunto de registros** es jerárquico, se guardará el **conjunto de registros** secundario y sus elementos secundarios, incluido el **conjunto de registros** principal. Si se llama al método **Save** de un **conjunto de registros** secundario, se guarda el secundario y todos sus secundarios, pero el principal, no. Para obtener más información acerca de los **conjuntos de registros** jerárquicos, vea el [Capítulo 9: Forma de datos](chapter-9-data-shaping.md).


> [!NOTE]
> <P>[!NOTA] Existen algunas limitaciones para guardar <STRONG>conjuntos de registros</STRONG> jerárquicos (formas de datos) en formato XML. Para obtener más información, vea <A href="hierarchical-recordsets-in-xml.md">Conjuntos de registros jerárquicos en XML</A>.</P>


