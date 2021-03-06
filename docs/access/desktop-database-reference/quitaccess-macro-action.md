---
title: SalirDeAccess (acción de macro)
TOCTitle: QuitAccess Macro Action
ms:assetid: af063f65-d3b1-fa9a-4bc1-04b0d21d62b9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821759(v=office.15)
ms:contentKeyID: 48547089
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm96777
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 5fa3b7ffc97f69b1ebc85799a8b2a27b6acc1d90
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25483507"
---
# <a name="quitaccess-macro-action"></a>SalirDeAccess (acción de macro)


**Se aplica a**: Access 2013 | Office 2013

Puede usar la acción **SalirDeAccess** para salir de Microsoft Access. La acción **SalirDeAccess** también puede especificar una de las varias opciones para guardar objetos de base de datos antes de salir de Access.


> [!NOTE]
> <P>[!NOTA] Esta acción no estará permitida si la base de datos no es de confianza. Si desea más información sobre la activación de macros, consulte los vínculos de la sección See Also de este artículo.</P>



## <a name="setting"></a>Configuración

La acción **SalirDeAccess** tiene el siguiente argumento.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Argumento de la acción</p></th>
<th><p>Descripción</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Options</strong></p></td>
<td><p>Especifica lo que ocurre con los objetos no guardados cuando se sale de Access. Haga clic en <strong>Preguntar</strong> (para que se muestren cuadros de diálogo en los que se pregunta si se desea guardar cada objeto), <strong>Guardar todo</strong> (para guardar todos los objetos sin que se muestren los cuadros de diálogo) o <strong>Salir</strong> (para abandonar sin guardar ningún objeto) en el cuadro <strong>Opciones</strong> de la sección <strong>Argumentos de acción</strong> del panel Generador de macros. El valor predeterminado es <strong>Guardar todo</strong>.</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>Comentarios

Access no ejecuta ninguna acción que siga a la acción **SalirDeAccess** de una macro.

Puede usar esta acción para salir de Access sin que se muestren los cuadros de diálogo **Guardar** mediante un comando de menú personalizado o un botón de un formulario. Por ejemplo, supongamos que tiene un formulario principal para mostrar los objetos en un área de trabajo personalizada. Este formulario podría tener un botón **Salir** que ejecutase una macro que contenga la acción **Salir** con el argumento **Opciones** establecido en **Guardar todo**.

Esta acción tiene el mismo efecto que hacer clic en la pestaña **Archivo** y, a continuación, hacer clic en **Salir**. Si, al hacer clic en este comando, hay algún objeto que no se haya guardado, los cuadros de diálogo que aparecen son los mismos que los que se presentan cuando se usa **Preguntar** para el argumento **Opciones** de la acción **SalirDeAccess**.

Puede usar la acción **GuardarObjeto** en una macro para guardar un objeto determinado sin tener que salir de Access o cerrar el objeto.

Para ejecutar la acción **SalirDeAccess** en un módulo de Visual Basic para Aplicaciones (VBA), use el método **Quit** del objeto **DoCmd**.

