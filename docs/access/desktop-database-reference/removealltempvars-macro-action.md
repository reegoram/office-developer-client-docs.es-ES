---
title: QuitarTodasLasVariablesTemporales (acción de macro)
TOCTitle: RemoveAllTempVars Macro Action
ms:assetid: 409fd836-4a53-cefd-4264-8cee0fa8ac52
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192877(v=office.15)
ms:contentKeyID: 48544430
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm117413
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 42217fea05b29fdf127945d1547adbac28346cc9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484822"
---
# <a name="removealltempvars-macro-action"></a>QuitarTodasLasVariablesTemporales (acción de macro)


**Se aplica a**: Access 2013 | Office 2013


Puede usar la acción **QuitarTodasLasVariablesTemporales** para quitar todas las variables temporales creadas mediante la acción **DefinirVariableTemporal**.

## <a name="setting"></a>Configuración

La acción **QuitarTodasLasVariablesTemporales** no tiene argumentos.

## <a name="remarks"></a>Comentarios

  - Puede haber hasta 255 variables temporales definidas a la vez. Si no se quita una variable temporal, se mantiene en la memoria hasta que se cierre la base de datos o el proyecto. Se recomienda quitar las variables temporales cuando termine de usarlas.

  - Access quita automáticamente todas las variables temporales cuando se cierra la base de datos o el proyecto.

  - Para quitar una sola variable temporal, use la acción **QuitarVariableTemporal** y establezca su argumento en el nombre de la variable temporal que desee quitar.

  - Para ejecutar la acción **QuitarTodasLasVariablesTemporales** en un módulo de VBA, use el método **RemoveAll** del objeto **TempVars**.

## <a name="example"></a>Ejemplo

En la siguiente macro se muestra cómo crear una variable temporal, cómo usarla en una condición y un cuadro de mensaje y, a continuación, cómo quitarla mediante la acción **QuitarTodasLasVariablesTemporales**.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Condición</p></th>
<th><p>Acción</p></th>
<th><p>Argumentos</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><strong>DefinirVariableTemporal</strong></p></td>
<td><p><strong>Nombre</strong>: MiVar<strong>expresión</strong>: CuadroEntr (&quot;escriba un número distinto de cero.&quot;)</p></td>
</tr>
<tr class="even">
<td><p>[TempVars]![MyVar]&lt;&gt;0</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>Mensaje</strong>: =&quot;ha escrito &quot; &amp; [variables temporales]! [MiVar] &amp; &quot;. &quot; <strong>Bip</strong>: <strong>YesType</strong>: <strong>información</strong></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><strong>QuitarTodasLasVariablesTemporales</strong></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

