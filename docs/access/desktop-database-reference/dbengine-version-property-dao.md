---
title: DBEngine.Version Property (DAO)
TOCTitle: Version Property
ms:assetid: b2807dc1-604f-4423-289a-ff38a3d9f31b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822024(v=office.15)
ms:contentKeyID: 48547171
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052986
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 3516a25623b6838286969c51f2d9346321f3326e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25483539"
---
# <a name="dbengineversion-property-dao"></a>DBEngine.Version Property (DAO)


**Se aplica a**: Access 2013 | Office 2013

Devuelve la versión de DAO que se está utilizando. **String** de sólo lectura.

## <a name="syntax"></a>Sintaxis

*expresión* . Versión

*expresión* Variable que representa un objeto **DBEngine** .

## <a name="remarks"></a>Comentarios

El valor devuelto es un tipo de datos String que se evalúa en un número de versión en el formato "major.minor". Por ejemplo, "3.0". El número de versión del producto consta del número de versión (3), un punto y el número de lanzamiento (0).

