---
title: Cuentas
TOCTitle: Accounts
ms:assetid: 28df6dbd-4d24-42f3-91c1-fd8b3a4ea722
ms:mtpsurl: https://msdn.microsoft.com/library/office/ff184597(v=office.15)
ms:contentKeyID: 55119790
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: eb7c56a8a261f36628c3b440c1aeec31c7aec46e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406823"
---
# <a name="accounts"></a>Cuentas 

En esta sección se proporcionan tareas de ejemplo relacionadas con las cuentas de correo electrónico Las cuentas de correo electrónico pueden ser, por ejemplo, cuentas de Microsoft Exchange Server, Protocolo de oficina de correo 3 (POP3), Protocolo de acceso a mensajes de Internet (IMAP) y Protocolo de transferencia de hipertexto (HTTP). Una cuenta del perfil actual se representa con un objeto [Account](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.account?view=outlook-pia).


|Tema|Descripción|
|:----|:----------|
|[Obtener información de la cuenta](how-to-get-account-information.md) | Toma como argumento de entrada un objeto [Application](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.application?view=outlook-pia) de Microsoft Outlook de confianza y usa el objeto **Account** para mostrar los detalles de cada cuenta que está disponible para el perfil actual de Outlook.|
|[Crear un elemento que puede enviarse para una cuenta específica basándose en la carpeta actual](how-to-create-a-sendable-item-for-a-specific-account-based-on-the-current-folder.md) | Contiene dos ejemplos de código que muestran cómo crear un elemento de correo electrónico que se pueda enviar y una convocatoria de reunión y, a continuación, enviarlos usando una cuenta específica basada en la carpeta actual.|
|[Obtener la cuenta de una carpeta](how-to-get-the-account-for-a-folder.md) | Obtiene la cuenta que está asociada a una carpeta en la sesión actual.|
|[Obtener información de varias cuentas](how-to-get-information-about-multiple-accounts.md) | Obtiene y muestra información diversa sobre cada cuenta del perfil actual.|
|[Enviar un elemento de correo con una cuenta de Hotmail](how-to-send-a-mail-item-by-using-a-hotmail-account.md) | Usa la propiedad [SendUsingAccount](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook._mailitem.sendusingaccount?view=outlook-pia) para enviar un elemento de correo mediante una cuenta de Windows Live Hotmail.|

## <a name="see-also"></a>Vea también

- [Usuarios de Exchange](exchange-users.md)
- [Correo](mail.md)
- [Destinatarios](recipients.md)
- [¿Cómo se puede... (Referencia a PIA de Outlook 2013)](how-do-i-outlook-2013-pia-reference.md)

