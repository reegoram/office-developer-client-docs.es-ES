---
title: 'Capítulo 15: Conceptos básicos de ADOX'
TOCTitle: 'Chapter 15: ADOX Fundamentals'
ms:assetid: 973d7579-4f34-3b31-a761-a951ab29e850
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249673(v=office.15)
ms:contentKeyID: 48546464
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3869f23b93df78fd207812a85f91dd3272bd255f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486389"
---
# <a name="chapter-15-adox-fundamentals"></a>Capítulo 15: Conceptos básicos de ADOX


**Se aplica a**: Access 2013 | Office 2013

Microsoft® ActiveX® Extensiones de ADO para lenguaje de definición de datos y seguridad (ADOX) es una extensión de los objetos y el modelo de programación de ADO. ADOX incluye objetos para creación y modificación de esquemas, así como de seguridad. Dado que se trata de un enfoque basado en objetos para la manipulación de esquemas, se puede escribir código que funcionará con diversos orígenes de datos, independientemente de las diferencias de sus sintaxis nativas.

ADOX es una biblioteca complementaria a los objetos ADO básicos. Expone objetos adicionales para crear, modificar y eliminar objetos de esquema, como tablas y procedimientos. También incluye objetos de seguridad para mantener usuarios y grupos, y para conceder y revocar permisos en objetos.

Para utilizar ADOX con su herramienta de desarrollo, debe establecer una referencia a la biblioteca de tipos ADOX. La descripción de la biblioteca ADOX es "Microsoft ADO Ext. para DDL y seguridad". El nombre de archivo de biblioteca ADOX es Msadox.dll y el identificador de programa (ProgID) es "ADOX". Para obtener más información acerca del establecimiento de referencias a bibliotecas, vea la documentación de su herramienta de desarrollo.

El Proveedor OLE DB de Microsoft para el motor de base de datos Microsoft Jet es totalmente compatible con ADOX. Es posible que algunas características de ADOX no sean compatibles, dependiendo de cuál sea su proveedor de datos. Para obtener más información acerca de las características compatibles con el Proveedor OLE DB de Microsoft para ODBC, el Proveedor OLE DB de Microsoft para Oracle o el Proveedor OLE DB de Microsoft para SQL Server, vea el archivo Léame de MDAC.

En este documento, se supone que se tiene un conocimiento práctico del lenguaje de programación Microsoft® Visual Basic® y conocimientos generales de ADO. Para obtener más información acerca de ADO, vea la [Guía del programador de ADO](ado-programmer-s-guide.md). Para obtener más información general acerca de ADOX, vea los temas siguientes:

  - [Objetos de ADOX](adox-objects.md)

  - [Colecciones de ADOX](adox-collections.md)

  - [Propiedades de ADOX](adox-properties.md)

  - [Métodos de ADOX](adox-methods.md)

  - [Ejemplos de ADOX](adox-code-examples.md)

