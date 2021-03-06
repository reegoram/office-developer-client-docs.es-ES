---
title: Supports (método, ADO)
TOCTitle: Supports Method (ADO)
ms:assetid: 2b4062ce-44df-4e84-1ce9-d6618c10c2af
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249059(v=office.15)
ms:contentKeyID: 48543924
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ceeab22cda05738fdcec090acb5b4a2d6fc88a5b
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "25604263"
---
# <a name="supports-method-ado"></a>Supports (método, ADO)


**Se aplica a**: Access 2013 | Office 2013

Determina si el objeto [Recordset](recordset-object-ado.md) especificado admite un determinado tipo de funcionalidad.

## <a name="syntax"></a>Sintaxis

*booleano* = *conjunto de registros*. Admite (*CursorOptions*)

<<<<<<< HEAD
## <a name="return-value"></a>Valor devuelto
=======
## <a name="return-value"></a>Valor devuelto
>>>>>>> master

Devuelve un valor **booleano** que indica si el proveedor admite todas las características identificadas por el argumento *CursorOptions* .

## <a name="parameters"></a>Parámetros

  - *CursorOptions*

  - Expresión de tipo **Long** formada por uno o varios valores de [CursorOptionEnum](cursoroptionenum.md).

## <a name="remarks"></a>Comentarios

Use el método **Supports** para determinar los tipos de funcionalidad compatibles con un objeto **Recordset**. Si el objeto **Recordset** es compatible con las características cuyas correspondientes constantes están en *CursorOptions*, el método **Supports** devuelve el valor **True**. En caso contrario, devuelve **False**.


> [!NOTE]
> <P>[!NOTA] Si bien el método <STRONG>Supports</STRONG> devuelve <STRONG>True</STRONG> para una determinada funcionalidad, esto no garantiza que el proveedor tenga disponible la característica en todas las circunstancias. El método <STRONG>Supports</STRONG> devuelve simplemente un valor que indica si el proveedor admite la funcionalidad especificada, suponiendo que se cumplen ciertas condiciones. Por ejemplo, puede que el método <STRONG>Supports</STRONG> indique que un objeto <STRONG>Recordset</STRONG> admita actualizaciones, aun cuando el cursor esté basado en una combinación de varias tablas, en las que algunas de las columnas no son actualizables.</P>


