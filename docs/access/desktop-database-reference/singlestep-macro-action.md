---
title: PasoAPaso (acción de macro)
TOCTitle: SingleStep Macro Action
ms:assetid: 2836fe1d-fb9b-6b42-acfd-c52e468161d4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191989(v=office.15)
ms:contentKeyID: 48543855
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm47687
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 747df6327dd73c51722b985c441feca08e1f4f42
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484604"
---
# <a name="singlestep-macro-action"></a><span data-ttu-id="6cfa4-102">PasoAPaso (acción de macro)</span><span class="sxs-lookup"><span data-stu-id="6cfa4-102">SingleStep Macro Action</span></span>


<span data-ttu-id="6cfa4-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="6cfa4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6cfa4-104">Puede usar la acción **PasoAPaso** para pausar la ejecución de una macro y abrir el cuadro de diálogo **Macro paso a paso**.</span><span class="sxs-lookup"><span data-stu-id="6cfa4-104">You can use the **SingleStep** action to pause macro execution and open the **Macro Single Step** dialog box.</span></span>

## <a name="setting"></a><span data-ttu-id="6cfa4-105">Configuración</span><span class="sxs-lookup"><span data-stu-id="6cfa4-105">Setting</span></span>

<span data-ttu-id="6cfa4-106">La acción **PasoAPaso** no tiene ningún argumento.</span><span class="sxs-lookup"><span data-stu-id="6cfa4-106">The **SingleStep** action does not have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="6cfa4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6cfa4-107">Remarks</span></span>

  - <span data-ttu-id="6cfa4-p101">Use la acción **PasoAPaso** para solucionar los problemas de una macro que no funciona correctamente. Puede agregar la acción **PasoAPaso** a una macro justo antes de una acción de la que sospecha que puede ser la causa del problema. La acción pausa la macro y abre el cuadro de diálogo **Macro paso a paso**. En este cuadro de diálogo se muestra información sobre la actual acción de macro, como el nombre de la macro, las condiciones especificadas, el nombre de la acción, los argumentos y el número de error, si procede. En el cuadro de diálogo, puede hacer clic en **Paso a paso** para ir a la siguiente acción de macro, en **Detener todas las macros** para detener la actual macro y cualquier otra macro que se esté ejecutando, o bien, en **Continuar** para detener el procedimiento paso a paso y reanudar el funcionamiento normal de la macro.</span><span class="sxs-lookup"><span data-stu-id="6cfa4-p101">Use the **SingleStep** action to troubleshoot a macro that is not working properly. You can add the **SingleStep** action to a macro just before an action that you suspect may be the cause of the problem. The action pauses the macro and opens the **Macro Single Step** dialog box. This dialog box displays information about the current macro action, such as the macro name, any specified conditions, the action name, arguments, and the error number, if applicable. In the dialog box, you can click **Step** to advance to the next macro action, **Stop All Macros** to stop the current macro and any other macros that are running, or **Continue** to stop single stepping and resume normal operation of the macro.</span></span>

  - <span data-ttu-id="6cfa4-p102">La acción **PasoAPaso** es similar a hacer clic en **Paso a paso** del grupo **Herramientas** en la ficha **Diseño** del Generador de macros. La diferencia entre este procedimiento y la ejecución de la acción **PasoAPaso** reside en que al ejecutarse la acción, se puede colocarla dentro de la macro en el lugar exacto donde debe comenzar el paso a paso. De ese modo, no es preciso recorrer todas las acciones anteriores para llegar a la acción que se desea examinar. Por otro lado, cuando se opta por clic en **Paso a paso** en el Generador de macros, es preciso hacerlo antes de ejecutar la macro. En ese caso, el paso a paso comienza con la primera acción de la macro.</span><span class="sxs-lookup"><span data-stu-id="6cfa4-p102">The **SingleStep** action has a similar effect to clicking **Single Step** in the **Tools** group on the **Design** tab of the Macro Builder. The difference between doing this and running the **SingleStep** action is that by running the action, you can place the action in the macro exactly where you want single stepping to begin. That way, you don't have to step through all the previous actions to get to the one you want to examine. On the other hand, when you click **Single Step** in the Macro Builder, you must do so before running the macro. In that case, single stepping begins at the first action in the macro.</span></span>


> [!NOTE]
> <P><span data-ttu-id="6cfa4-p103">[!NOTA] Si recorre paso a paso una macro hasta el final sin hacer clic en <STRONG>Continuar</STRONG>, el paso a paso estará aún vigente cuando termine la macro. Cualquier macro subsiguiente que ejecute comenzará en modo paso a paso. Para desactivarlo, haga clic en <STRONG>Continuar</STRONG> del cuadro de diálogo <STRONG>Macro paso a paso</STRONG>, o bien, con una macro abierta en la vista Diseño, en la ficha <STRONG>Diseño</STRONG>, en el grupo <STRONG>Herramientas</STRONG>, haga clic en <STRONG>Paso a paso</STRONG> de modo que la opción ya no esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6cfa4-p103">If you single-step all the way to the end of a macro without clicking <STRONG>Continue</STRONG>, single stepping will still be in effect when the macro ends. Any subsequent macro you run will start in single step mode. To turn off single stepping, either click <STRONG>Continue</STRONG> in the <STRONG>Macro Single Step</STRONG> dialog box, or, with a macro open in Design view, on the <STRONG>Design</STRONG> tab, in the <STRONG>Tools</STRONG> group, click <STRONG>Single Step</STRONG> so that it is no longer selected.</span></span></P>

