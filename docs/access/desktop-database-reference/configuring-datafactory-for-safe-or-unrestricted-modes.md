---
title: Configurar DataFactory para los modos seguros o no restringidos
TOCTitle: Configuring DataFactory for Safe or Unrestricted Modes
ms:assetid: 1516068f-1b02-3236-f6a9-9fdeff098e52
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248915(v=office.15)
ms:contentKeyID: 48543400
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: abb461473d15f163fac6ea00f2af5d39f7b40d0a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486395"
---
# <a name="configuring-datafactory-for-safe-or-unrestricted-modes"></a><span data-ttu-id="67352-102">Configurar DataFactory para los modos seguros o no restringidos</span><span class="sxs-lookup"><span data-stu-id="67352-102">Configuring DataFactory for Safe or Unrestricted Modes</span></span>


<span data-ttu-id="67352-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="67352-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="67352-p101">ADO se instala de forma predeterminada con una configuración "segura" para [RDSServer.DataFactory](datafactory-object-rdsserver.md). El modo seguro para componentes de servidor RDS significa lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="67352-p101">By default, ADO is installed with a "safe" [RDSServer.DataFactory](datafactory-object-rdsserver.md) configuration. Safe mode for RDS Server components means that the following are true:</span></span>

1.  <span data-ttu-id="67352-106">Se requiere un controlador con el RDSServer.DataFactory (mediante un valor de clave del Registro).</span><span class="sxs-lookup"><span data-stu-id="67352-106">Handler is required with the RDSServer.DataFactory (this is mandated by a registry key setting).</span></span>

2.  <span data-ttu-id="67352-107">El controlador predeterminado, msdfmap.handler, está registrado, presente en la lista de controladores seguros y marcado como el controlador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="67352-107">The default handler, msdfmap.handler, is registered, present in the safe-handler list, and marked as the default handler.</span></span>

3.  <span data-ttu-id="67352-p102">El archivo Msdfmap.ini se instala en el directorio de Windows. Deberá configurar este archivo según sus necesidades antes de utilizar RDS en el modo de tres niveles.</span><span class="sxs-lookup"><span data-stu-id="67352-p102">Msdfmap.ini file is installed in the Windows directory. You must configure this file according to your needs, before using RDS in three-tier mode.</span></span>

<span data-ttu-id="67352-p103">Opcionalmente, puede configurar una instalación de **DataFactory** no restringida. **DataFactory** se puede utilizar directamente sin el controlador personalizado. Los usuarios pueden seguir utilizando un controlador personalizado modificando las cadenas de conexión, pero no es necesario. Para obtener más información sobre las implicaciones de utilizar el objeto **RDSServer.DataFactory**, vea [Proteger aplicaciones RDS](securing-rds-applications.md).</span><span class="sxs-lookup"><span data-stu-id="67352-p103">Optionally, you can configure an unrestricted **DataFactory** installation. **DataFactory** can be used directly without the custom handler. Users can still use a custom handler by modifying the connection strings, but it is not required. For more information on the implications of using the **RDSServer.DataFactory** object, see [Securing RDS Applications](securing-rds-applications.md).</span></span>

<span data-ttu-id="67352-p104">El archivo de Registro, handsafe.reg, se ha proporcionado para configurar las entradas de controlador del Registro para una configuración segura. Para un funcionamiento en modo seguro, ejecute handsafe.reg. El archivo de Registro, handunsf.reg, se ha proporcionado para configurar las entradas de controlador del Registro para una configuración segura. Para un funcionamiento en modo no restringido, ejecute handunsf.reg.</span><span class="sxs-lookup"><span data-stu-id="67352-p104">The registry file handsafe.reg has been provided to set up the handler registry entries for a safe configuration. To run in safe mode, run handsafe.reg. The registry file handunsf.reg has been provided to set up the handler registry entries for an unrestricted configuration. To run in unrestricted mode, run handunsf.reg.</span></span>

<span data-ttu-id="67352-117">Después de ejecutar handsafe.reg o handunsf.reg, deberá detener y reiniciar el servicio de publicación Web en el servidor Web escribiendo los comandos siguientes en una ventana de comandos: "NET STOP W3SVC" y "NET START W3SVC".</span><span class="sxs-lookup"><span data-stu-id="67352-117">After running either handsafe.reg or handunsf.reg, you must stop and restart the World Wide Web Publishing Service on the Web server by typing the following commands in a command window: "NET STOP W3SVC" and "NET START W3SVC".</span></span>

<span data-ttu-id="67352-118">Para obtener más información acerca del uso de la característica de personalización de controladores de RDS, vea el artículo técnico "Using the Customization Handler Feature in RDS 2.1" (en inglés).</span><span class="sxs-lookup"><span data-stu-id="67352-118">For more information about using the customization handler feature of RDS, see the technical article Using the Customization Handler Feature in RDS 2.1.</span></span>
