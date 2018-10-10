---
title: Consideraciones de seguridad XML
TOCTitle: XML Security Considerations
ms:assetid: ef2c7f59-f5a2-98d1-37c6-42cb35b26a40
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250214(v=office.15)
ms:contentKeyID: 48548575
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3120db77ba89aee1036de4d6fa85df73c21d26d9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485990"
---
# <a name="xml-security-considerations"></a><span data-ttu-id="9724d-102">Consideraciones de seguridad XML</span><span class="sxs-lookup"><span data-stu-id="9724d-102">XML Security Considerations</span></span>


<span data-ttu-id="9724d-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="9724d-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="xml-security-considerations"></a><span data-ttu-id="9724d-104">Consideraciones de seguridad XML</span><span class="sxs-lookup"><span data-stu-id="9724d-104">XML Security Considerations</span></span>

<span data-ttu-id="9724d-p101">Los métodos **Save** y **Open** de ADO del objeto **Recordset** no se consideran operaciones seguras para ejecutarse en Internet Explorer. Por ello, si estos métodos se usan en código de script que se ejecuta en una aplicación o en un control hospedado en un explorador, la configuración de seguridad del explorador influirá en su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="9724d-p101">The ADO **Save** and **Open** methods on the **Recordset** object are not considered safe operations to run in Internet Explorer. Thus, if these methods are used in a script code that is running in an application or control that is hosted in a browser, the security configuration of the browser will have an effect on its behavior.</span></span>

<span data-ttu-id="9724d-p102">Internet Explorer 5 proporciona restricciones de seguridad para dichas operaciones de forma predeterminada en las zonas de Internet. En esa configuración, el objeto **Recordset** no puede obtener acceso al sistema de archivos local en el cliente ni tener acceso a ningún origen de datos fuera del dominio del servidor desde el que se ha descargado la página. Específicamente, cuando se ejecuta en el equipo que hospeda el explorador, un objeto **Recordset** sólo se puede guardar en un archivo si se encuentra en el mismo servidor desde el que se descargó la página. Del mismo modo, se puede abrir un objeto **Recordset** cargándolo desde un archivo únicamente si ese archivo está en el mismo servidor desde el que se descargó la página.</span><span class="sxs-lookup"><span data-stu-id="9724d-p102">Internet Explorer 5 provides security restrictions for such operations by default in the Internet zones. Under that configuration, the **Recordset** cannot make any access to the local file system on the client or access any data sources outside the domain of the server from which the page has been downloaded. Specifically, when running inside the browser host, a **Recordset** can be saved back to a file only if it is on the same server from which the page was downloaded. Similarly, you can open a **Recordset** by loading it from a file only if that file is on the same server from which the page was downloaded.</span></span>

<span data-ttu-id="9724d-111">Para obtener más información sobre la seguridad en Internet Explorer, vea el artículo técnico "ADO and RDS Security Issues in Microsoft Internet Explorer" (en inglés).</span><span class="sxs-lookup"><span data-stu-id="9724d-111">For more information about security in Internet Explorer, see the technical article "ADO and RDS Security Issues in Microsoft Internet Explorer."</span></span>
