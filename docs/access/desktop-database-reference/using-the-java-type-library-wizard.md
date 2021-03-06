---
title: Utilizar el Asistente para bibliotecas de tipos de Java
TOCTitle: Using the Java Type Library Wizard
ms:assetid: 96af770c-c7c2-c905-3c3e-383a5b99cab2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249670(v=office.15)
ms:contentKeyID: 48546455
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 931434288cbc14da5d3d9d9d53cd250555c7a767
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486465"
---
# <a name="using-the-java-type-library-wizard"></a>Utilizar el Asistente para bibliotecas de tipos de Java


**Se aplica a**: Access 2013 | Office 2013

El Asistente para bibliotecas de tipos de Java es una característica de Visual J++ 1.x integrada en el menú **Herramientas** del entorno de desarrollo. Su propósito es buscar en una biblioteca de tipos y crear una interfaz Java que permita obtener acceso a objetos COM. Para Visual J++ 6.0, el Asistente para bibliotecas de tipos de Java se ha reemplazado con [ADO para Windows Foundation Classes](ado-wfc-programming.md).

El Asistente para bibliotecas de tipos de Java genera resultados similares a las herramientas de línea de comandos incluidas en [Microsoft SDK para Java](using-the-microsoft-sdk-for-java.md). Sin embargo, no se pueden ejecutar paso a paso los contenedores de clase que genera el Asistente, a diferencia de los contenedores de clase generados por Microsoft SDK para Java.

El Asistente para la biblioteca de tipos de Java genera las clases en la siguiente ubicación: \\ \<windows Active\>\\Java\\bibliotecas de confianza\\msado15. El archivo Summary.txt, ubicado en el directorio donde se han generado las clases, muestra las definiciones de clase generadas.

El Asistente para bibliotecas de tipos de Java convierte los tipos enumerados, que se encuentran en cualquier biblioteca de tipos especificado, en el tipo INT (entero). También define una interfaz correspondiente a cada tipo enumerado en la biblioteca de tipos. Se puede hacer referencia a los valores de un tipo enumerado de ADO con la sintaxis siguiente:

```vb 
 
msado15.<Enum Name>.<constant Name> 
```

Un ejemplo de esto aparece en el siguiente fragmento de código para establecer el valor de la propiedad **CommandType** de un objeto **Command**:

```vb 
 
Cmd1.putCommandType( msado15.CommandTypeEnum.adCmdStoredProc ); 
```

Asimismo, se puede heredar del contenedor de tipos enumerados generado por el Asistente para bibliotecas de tipos de Java. En ese caso, se puede quitar "msado15." de la sintaxis. Sin embargo, la clase deberá heredar de cada objeto Java e interfaz de tipos enumerados a los que haga referencia para que no sea necesario hacer referencia a msado15.\* delante de todos los valores enumerados y objetos de ADO.

Para obtener más código de ejemplo, vea [Contenedores de clase Java de ADO](ado-java-class-wrappers.md).

**Para ejecutar al Asistente para la biblioteca de tipos de Java desde Visual J ++ versión 1.*x***

1.  En el menú **Herramientas**, seleccione **Asistente para bibliotecas de tipos de Java**.

2.  Seleccione "Biblioteca de objetos de datos de Microsoft ActiveX" y haga clic en **Aceptar**. En este momento (re) genera archivos en el \\directorio de bibliotecas de confianza para ADO (de manera predeterminada en c:\\winnt\\java\\bibliotecas de confianza\\msado15). Si ha utilizado Microsoft SDK para Java para generar clases para ADO, éstas se reemplazarán con las clases del Asistente para bibliotecas de tipos de Java.

3.  Para utilizar estos archivos, abra un proyecto en Visual J++. En el menú **Proyecto**, elija **Agregar al proyecto**. Seleccione **archivos**y agregue todos los. Archivos de JAVA generados en el \\directorio de bibliotecas de confianza (de forma predeterminada en c:\\winnt\\java\\bibliotecas de confianza\\msado15) a su proyecto.

