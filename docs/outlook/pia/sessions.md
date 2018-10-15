---
title: Sesiones
TOCTitle: Sessions
ms:assetid: d81121bb-5bf8-49fb-83c4-8d3a2ffeb978
ms:mtpsurl: https://msdn.microsoft.com/library/Ff462099(v=office.15)
ms:contentKeyID: 55119890
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: eb47a9edb0dbbef7c1aaabcc38672f2028558c6c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405892"
---
# <a name="sessions"></a><span data-ttu-id="62381-102">Sesiones</span><span class="sxs-lookup"><span data-stu-id="62381-102">Sessions</span></span>

<span data-ttu-id="62381-103">Esta sección incluye una tarea de ejemplo que hace referencia a las sesiones de Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="62381-103">This section includes a sample task that pertains to Microsoft Outlook sessions.</span></span> <span data-ttu-id="62381-104">Una sesión es un período de tiempo durante el cual un usuario inicia sesión en Outlook.</span><span class="sxs-lookup"><span data-stu-id="62381-104">A session is a period of time during which a user logs on to Outlook.</span></span> <span data-ttu-id="62381-105">Una sesión se representa en Outlook mediante la clase [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)).</span><span class="sxs-lookup"><span data-stu-id="62381-105">A session is represented in Outlook by the [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) class.</span></span> <span data-ttu-id="62381-106">Esta clase admite el inicio y el cierre de sesión, tener acceso a los objetos de almacenamiento directamente mediante su id., tener acceso directamente a algunas carpetas predeterminadas especiales y tener acceso a los orígenes de datos que son propiedad de otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="62381-106">The object itself provides methods for logging in and out, accessing storage objects directly by ID, accessing certain special default folders directly, and accessing data sources owned by other users.</span></span> <span data-ttu-id="62381-107">El único origen de datos admitido es MAPI, que permite el acceso a todos los datos de Outlook almacenados en los almacenes de correo del usuario.</span><span class="sxs-lookup"><span data-stu-id="62381-107">The only data source supported is MAPI, which allows access to all Outlook data stored in the user's mail stores.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="62381-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="62381-108">In this section</span></span>

|<span data-ttu-id="62381-109">Tema</span><span class="sxs-lookup"><span data-stu-id="62381-109">Topic</span></span>|<span data-ttu-id="62381-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="62381-110">Description</span></span>|
|:----|:----------|
|[<span data-ttu-id="62381-111">Obtener e iniciar sesión en una instancia de Outlook</span><span class="sxs-lookup"><span data-stu-id="62381-111">Get and sign in to an instance of Outlook</span></span>](how-to-get-and-log-on-to-an-instance-of-outlook.md)  |<span data-ttu-id="62381-112">Obtiene un objeto [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) que representa una instancia activa de Outlook, si hay una que se ejecute en el equipo local, o crea una nueva instancia de Outlook, inicia sesión en el perfil predeterminado y devuelve esa instancia de Outlook.</span><span class="sxs-lookup"><span data-stu-id="62381-112">Obtains an [T:Microsoft.Office.Interop.Outlook.Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) object that represents an active instance of Outlook, if there is one running on the local computer, or creates a new instance of Outlook, logs on to the default profile, and returns that instance of Outlook.</span></span>|

## <a name="see-also"></a><span data-ttu-id="62381-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="62381-113">See also</span></span>

- <span data-ttu-id="62381-114">[How do I... (Outlook 2013 PIA reference)](how-do-i-outlook-2013-pia-reference.md) (¿Cómo se puede... [Referencia a PIA de Outlook 2013])</span><span class="sxs-lookup"><span data-stu-id="62381-114">[How do I... (Outlook 2013 PIA reference)](how-do-i-outlook-2013-pia-reference.md)</span></span>
