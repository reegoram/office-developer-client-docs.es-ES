---
title: 'Capítulo 14: Conceptos básicos de ADO MD'
TOCTitle: 'Chapter 14: ADO MD Fundamentals'
ms:assetid: 129baa54-0bc1-985d-4bfd-25a1c1c3018e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248899(v=office.15)
ms:contentKeyID: 48543346
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5d595136c229234dfa0cb04a44fbe45f58cd79fe
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484241"
---
# <a name="chapter-14-ado-md-fundamentals"></a>Capítulo 14: Conceptos básicos de ADO MD


**Se aplica a**: Access 2013 | Office 2013

Microsoft ActiveX Data Objects (MultiDimensional) (ADO MD) proporciona acceso sencillo a datos multidimensionales de lenguajes como Microsoft Visual Basic, Microsoft Visual C++ y Microsoft Visual J++. ADO MD es una ampliación de Microsoft ActiveX Data Objects (ADO) que incluye objetos específicos de datos multidimensionales, como los objetos [CubeDef](cubedef-object-ado-md.md) y [Cellset](cellset-object-ado-md.md). Con ADO MD, puede explorar un esquema multidimensional, consultar un cubo y recuperar los resultados.

Al igual que ADO, ADO MD usa un proveedor OLE DB subyacente para obtener acceso a datos. Para trabajar con ADO MD, debe usarse un proveedor de datos multidimensionales (MDP) según se define en las especificaciones de OLE DB para OLAP. Los proveedores de datos multidimensionales presentan datos en vistas multidimensionales, al contrario que los proveedores de datos tabulares (TDP), que presentan datos en vistas tabulares. Vea la documentación correspondiente de su proveedor OLE DB para OLAP para obtener información más detallada acerca de la sintaxis y los comportamientos específicos que admite su proveedor.

En este documento, se supone que se tiene un conocimiento práctico del lenguaje de programación Visual Basic y conocimientos generales de ADO y de OLAP. Para obtener más información, vea la [Guía del programador de ADO](ado-programmer-s-guide.md) y la Referencia del programador de OLE DB para OLAP. Para obtener más información general acerca de ADO MD, vea los temas siguientes:

  - [Descripción general de esquemas y datos multidimensionales](overview-of-multidimensional-schemas-and-data.md)

  - [Trabajar con datos multidimensionales](working-with-multidimensional-data.md)

  - [Utilizar ADO con ADO MD](using-ado-with-ado-md.md)

  - [Programar con ADO MD](programming-with-ado-md.md)

