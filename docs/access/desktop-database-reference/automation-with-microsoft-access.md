---
título: automatización con Microsoft Access TOCTitle: automatización con Microsoft Access <<<<<<< HEAD ms:assetid: 39fde349-3ba3-7c7a-3c92-316641dc8712 ms:mtpsurl: https://msdn.microsoft.com/library/Ff192643(v=office.15) ms:contentKeyID: ms.date 48544258: 18/09/2015 === Descripción: Microsoft Access es un componente COM que admite la automatización, anteriormente denominada automatización OLE.
MS:AssetId: 39fde349-3ba3-7c7a-3c92-316641dc8712 ms:mtpsurl: https://msdn.microsoft.com/library/Ff192643(v=office.15) ms:contentKeyID: ms.date 48544258: 16/10/2018
>>>>>>> maestro mtps_version: Office.15 f1_keywords:
- vbaac10.chm13783 f1_categories:
- Office.Version=v15
---

# <a name="automation-with-microsoft-access"></a>Automatización con Microsoft Access

<<<<<<< HEAD

=======
>>>>>>> Master **se aplica a**: Access 2013 | Office 2013

Microsoft Access es un componente COM compatible con la Automatización, denominada anteriormente Automatización OLE. Microsoft Access admite la Automatización de dos formas. Desde Microsoft Access, puede trabajar con los objetos suministrados por otro componente. Microsoft Access suministra también sus objetos a otros componentes COM.

Puede usar la palabra clave **New** o el método **CreateObject** para crear una nueva instancia de un componente. Puede usar el método **GetObject** para asignar una variable a una instancia existente de un componente.

En Microsoft Access, puede establecer una referencia a la biblioteca de tipos de un componente para mejorar el rendimiento cuando trabaje con ese componente a través de Automatización. Microsoft Access incluye también el Examinador de objetos, una herramienta que le permite ver los objetos de la biblioteca de tipos de otro componente, así como sus métodos y propiedades.

<<<<<<< Biblioteca de tipos de cabeza la Microsoft Access proporciona información acerca de los objetos de Microsoft Access a otros componentes. Se puede [establecer una referencia](https://msdn.microsoft.com/library/ff194944\(v=office.15\)) a la Microsoft Access escriba biblioteca desde un componente y ver sus objetos en el Examinador de objetos.

Para trabajar con los objetos de Microsoft Access a través de Automatización, debe crear una instancia del objeto **[Application](https://msdn.microsoft.com/library/ff821758\(v=office.15\))** de Microsoft Access. Por ejemplo, suponga que desea mostrar datos de Microsoft Excel en un formulario o informe de Microsoft Access. Para ejecutar Microsoft Access desde Microsoft Excel, puede usar la palabra clave **New** para crear una instancia del objeto **Application** de Microsoft Access. También puede usar el método **CreateObject** para crear una nueva instancia del objeto **Application** de Microsoft Access, o puede usar el método **GetObject** para apuntar una variable de objeto a una instancia existente de Microsoft Access. Compruebe la documentación del componente para determinar la sintaxis con la que es compatible.

Una vez iniciada una instancia de Microsoft Access, si desea controlar cualquier objeto de Microsoft Access, deberá abrir una base de datos o un proyecto (.adp) en la ventana de Microsoft Access, con el método **[OpenCurrentDatabase](https://msdn.microsoft.com/library/ff837226\(v=office.15\))** o **[NewCurrentDatabase](https://msdn.microsoft.com/library/ff195271\(v=office.15\))** para una base de datos, o bien con el método **[OpenAccessProject](https://msdn.microsoft.com/library/ff837249\(v=office.15\))** o **[NewAccessProject](https://msdn.microsoft.com/library/ff835758\(v=office.15\))** para un proyecto.

Si sólo ha abierto Microsoft Access como una forma de usar los objetos de acceso a datos proporcionados por Microsoft DAO, entonces no es necesario que abra una base de datos en la ventana de Microsoft Access. Puede usar la propiedad **[DBEngine](https://msdn.microsoft.com/library/ff821724\(v=office.15\))** del objeto **Application** de Microsoft Access para tener acceso a los objetos de la biblioteca de objetos del motor de base de datos de Microsoft Office 2007 Access durante una operación de Automatización.
=======
La biblioteca de tipos de Microsoft Access ofrece información sobre los objetos de Microsoft Access a otros componentes. Se puede [establecer una referencia](https://docs.microsoft.com/office/vba/access/Concepts/Settings/set-references-to-type-libraries) a la Microsoft Access escriba biblioteca desde un componente y ver sus objetos en el Examinador de objetos.

Para trabajar con los objetos de Microsoft Access a través de Automatización, debe crear una instancia del objeto **[Application](https://docs.microsoft.com/office/vba/api/Access.Application)** de Microsoft Access. Por ejemplo, suponga que desea mostrar datos de Microsoft Excel en un formulario o informe de Microsoft Access. Para ejecutar Microsoft Access desde Microsoft Excel, puede usar la palabra clave **New** para crear una instancia del objeto **Application** de Microsoft Access. También puede usar el método **CreateObject** para crear una nueva instancia del objeto **Application** de Microsoft Access, o puede usar el método **GetObject** para apuntar una variable de objeto a una instancia existente de Microsoft Access. Compruebe la documentación del componente para determinar la sintaxis con la que es compatible.

Una vez iniciada una instancia de Microsoft Access, si desea controlar los objetos de Microsoft Access, debe abrir una base de datos o un proyecto (.adp) en la ventana de Microsoft Access mediante el **[OpenCurrentDatabase](https://docs.microsoft.com/office/vba/api/Access.Application.OpenCurrentDatabase)** o la **[NewCurrentDatabase ](https://docs.microsoft.com/office/vba/api/Access.Application.NewCurrentDatabase)**(método) para una base de datos o mediante la **[OpenAccessProject](https://docs.microsoft.com/office/vba/api/Access.Application.OpenAccessProject)** o el método **[NewAccessProject](https://docs.microsoft.com/office/vba/api/Access.Application.NewAccessProject)** para un proyecto.

Si ha abierto Microsoft Access como una forma de usar los objetos de acceso a datos proporcionados por Microsoft DAO, no es necesario abrir una base de datos en la ventana de Microsoft Access. Puede usar la propiedad **[DBEngine](https://docs.microsoft.com/office/vba/api/Access.Application.DBEngine)** del objeto **Application** de Microsoft Access en objetos de access en la biblioteca de objetos de Microsoft Office 12.0 Access base de datos de motor durante una operación de automatización.
>>>>>>> master

