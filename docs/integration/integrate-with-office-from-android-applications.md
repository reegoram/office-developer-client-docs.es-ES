---
title: Integración con Office desde aplicaciones de Android
manager: soliver
ms.date: 06/18/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: a765fa49-a272-4047-9147-59cc68e5dd27
description: Office para Android proporciona una solución extensible que permite la integración con aplicaciones de terceros. Puede integrarse con Office desde su aplicación de Android pasando usuarios de la aplicación a Office.
ms.openlocfilehash: 2fd60c7e86d3390bc5343f3e09fb2235f97e0b13
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19815984"
---
# <a name="integrate-with-office-from-android-applications"></a><span data-ttu-id="53245-104">Integración con Office desde aplicaciones de Android</span><span class="sxs-lookup"><span data-stu-id="53245-104">Integrate with Office from Android applications</span></span>

<span data-ttu-id="53245-p102">Office para Android proporciona una solución extensible que permite la integración con aplicaciones de terceros. Puede integrarse con Office desde su aplicación de Android pasando usuarios de la aplicación a Office.</span><span class="sxs-lookup"><span data-stu-id="53245-p102">Office for Android provides an extensible solution that enables integration with third-party applications. You can integrate with Office from your Android application by passing users from your application to Office.</span></span>
  
<span data-ttu-id="53245-p103">Puede permitir que los usuarios que ejecutan Office en un dispositivo Android abran y editen los archivos almacenados en SharePoint o OneDrive desde cualquier aplicación. Para ello, pase archivos a Office mediante controladores de protocolo y asegúrese de que Office se invoca de tal manera que Office pueda entender.</span><span class="sxs-lookup"><span data-stu-id="53245-p103">You can enable users who are running Office on an Android device to open and edit files stored in SharePoint or OneDrive from any application. To do this, you pass files to Office via protocol handlers, and you make sure that Office is invoked in a way that Office can understand.</span></span>
  
<span data-ttu-id="53245-109">Cuando un usuario termina de editar un archivo, puede elegir la tecla Atrás en el dispositivo para volver a la aplicación de almacenamiento original.</span><span class="sxs-lookup"><span data-stu-id="53245-109">When a user is done editing a file, they can choose the back key on the device to return to the original storage application.</span></span>
  
## <a name="verify-that-office-has-been-installed"></a><span data-ttu-id="53245-110">Compruebe que se haya instalado Office.</span><span class="sxs-lookup"><span data-stu-id="53245-110">Verify that Office has been installed</span></span>

<span data-ttu-id="53245-p104">La aplicación de referencia deberá comprobar primero que una determinada aplicación de Office está instalada. Las siguientes aplicaciones de Office se pueden instalar en dispositivos Android para la visualización y edición de documentos:</span><span class="sxs-lookup"><span data-stu-id="53245-p104">Your referring application will first need to verify that a particular Office application is installed. The following Office applications can be installed on Android devices for document viewing and editing:</span></span> 
  
- <span data-ttu-id="53245-113">Excel</span><span class="sxs-lookup"><span data-stu-id="53245-113">Excel</span></span>
    
- <span data-ttu-id="53245-114">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="53245-114">PowerPoint</span></span>
    
- <span data-ttu-id="53245-115">Word</span><span class="sxs-lookup"><span data-stu-id="53245-115">Word</span></span>
    
<span data-ttu-id="53245-p105">Use PackageManager de Android para determinar si una aplicación determinada de Office está instalada en el dispositivo. En la siguiente tabla se enumeran los nombres de paquete para las aplicaciones de Office que puede usar en este proceso.</span><span class="sxs-lookup"><span data-stu-id="53245-p105">Use Android PackageManager to determine whether a particular Office application is installed on the device. The following table lists the package names for the Office applications that you can use in this process.</span></span>
  
|<span data-ttu-id="53245-118">**Aplicación**</span><span class="sxs-lookup"><span data-stu-id="53245-118">**Application**</span></span>|<span data-ttu-id="53245-119">**Nombre del paquete**</span><span class="sxs-lookup"><span data-stu-id="53245-119">**Package name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="53245-120">Excel</span><span class="sxs-lookup"><span data-stu-id="53245-120">Excel</span></span>  <br/> |<span data-ttu-id="53245-121">com.microsoft.office.excel</span><span class="sxs-lookup"><span data-stu-id="53245-121">com.microsoft.office.excel</span></span>  <br/> |
|<span data-ttu-id="53245-122">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="53245-122">PowerPoint</span></span>  <br/> |<span data-ttu-id="53245-123">com.microsoft.office.powerpoint</span><span class="sxs-lookup"><span data-stu-id="53245-123">com.microsoft.office.powerpoint</span></span>  <br/> |
|<span data-ttu-id="53245-124">Word</span><span class="sxs-lookup"><span data-stu-id="53245-124">Word</span></span>  <br/> |<span data-ttu-id="53245-125">com.microsoft.office.word</span><span class="sxs-lookup"><span data-stu-id="53245-125">com.microsoft.office.word</span></span>  <br/> |
   
### <a name="prompt-the-user-to-install-office"></a><span data-ttu-id="53245-126">Solicitar al usuario que instale Office</span><span class="sxs-lookup"><span data-stu-id="53245-126">Prompt the user to install Office</span></span>

<span data-ttu-id="53245-p106">Si una aplicación determinada de Office no está instalada, puede solicitar al usuario que la instale. En la siguiente tabla se enumeran las ubicaciones de instalación disponibles para las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="53245-p106">If a particular Office application is not installed, you can prompt the user to install the application. The following table lists the available install locations for Office applications.</span></span>
  
|<span data-ttu-id="53245-129">**Aplicación**</span><span class="sxs-lookup"><span data-stu-id="53245-129">**Application**</span></span>|<span data-ttu-id="53245-130">**Google Play Store**</span><span class="sxs-lookup"><span data-stu-id="53245-130">**Google Play Store**</span></span>|
|:-----|:-----|
|<span data-ttu-id="53245-131">Excel</span><span class="sxs-lookup"><span data-stu-id="53245-131">Excel</span></span>  <br/> |[https://play.google.com/store/apps/details?id=com.microsoft.office.excel](https://play.google.com/store/apps/details?id=com.microsoft.office.excel) <br/> |
|<span data-ttu-id="53245-132">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="53245-132">PowerPoint</span></span>  <br/> |[https://play.google.com/store/apps/details?id=com.microsoft.office.powerpoint](https://play.google.com/store/apps/details?id=com.microsoft.office.powerpoint) <br/> |
|<span data-ttu-id="53245-133">Word</span><span class="sxs-lookup"><span data-stu-id="53245-133">Word</span></span>  <br/> |[https://play.google.com/store/apps/details?id=com.microsoft.office.word](https://play.google.com/store/apps/details?id=com.microsoft.office.word) <br/> |
   
## <a name="invoke-office"></a><span data-ttu-id="53245-134">Invocar a Office</span><span class="sxs-lookup"><span data-stu-id="53245-134">Invoke Office</span></span>

<span data-ttu-id="53245-135">Cuando la aplicación de Office está instalada, la aplicación de referencia puede invocar a Office pasando los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="53245-135">When the Office application is installed, your referring application can invoke Office by passing the following details:</span></span>
  
- <span data-ttu-id="53245-136">Protocolo de Office</span><span class="sxs-lookup"><span data-stu-id="53245-136">Office protocol</span></span>
    
- <span data-ttu-id="53245-137">Modo de apertura</span><span class="sxs-lookup"><span data-stu-id="53245-137">Open mode</span></span>
    
- <span data-ttu-id="53245-138">URL</span><span class="sxs-lookup"><span data-stu-id="53245-138">URL</span></span>
    
<span data-ttu-id="53245-139">Formato de esquema:</span><span class="sxs-lookup"><span data-stu-id="53245-139">Schema format:</span></span>
  
 `<Office protocol><open mode>|u|<URL>`
  
<span data-ttu-id="53245-140">El siguiente ejemplo muestra una solicitud para invocar un archivo de Word para su edición:</span><span class="sxs-lookup"><span data-stu-id="53245-140">The following example shows a request to invoke a Word file for editing.</span></span>
  
 `ms-word:ofe|u|https://contoso/Q4/budget.docx`
  
### <a name="office-protocols"></a><span data-ttu-id="53245-141">Protocolos de Office</span><span class="sxs-lookup"><span data-stu-id="53245-141">Office protocols</span></span>

<span data-ttu-id="53245-142">La siguiente tabla enumera los protocolos para cada aplicación de Office.</span><span class="sxs-lookup"><span data-stu-id="53245-142">The following table lists the protocols for each Office application.</span></span>
  
|<span data-ttu-id="53245-143">**Aplicación**</span><span class="sxs-lookup"><span data-stu-id="53245-143">**Application**</span></span>|<span data-ttu-id="53245-144">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="53245-144">**Protocol**</span></span>|
|:-----|:-----|
|<span data-ttu-id="53245-145">Excel</span><span class="sxs-lookup"><span data-stu-id="53245-145">Excel</span></span>  <br/> |<span data-ttu-id="53245-146">ms-excel:</span><span class="sxs-lookup"><span data-stu-id="53245-146">ms-excel:</span></span>  <br/> |
|<span data-ttu-id="53245-147">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="53245-147">PowerPoint</span></span>  <br/> |<span data-ttu-id="53245-148">ms-powerpoint:</span><span class="sxs-lookup"><span data-stu-id="53245-148">ms-powerpoint:</span></span>  <br/> |
|<span data-ttu-id="53245-149">Word</span><span class="sxs-lookup"><span data-stu-id="53245-149">Word</span></span>  <br/> |<span data-ttu-id="53245-150">ms-word:</span><span class="sxs-lookup"><span data-stu-id="53245-150">ms-word:</span></span>  <br/> |
   
### <a name="open-mode"></a><span data-ttu-id="53245-151">Modo de apertura</span><span class="sxs-lookup"><span data-stu-id="53245-151">Open mode</span></span>

<span data-ttu-id="53245-p107">Las aplicaciones de Office pueden abrir archivos directamente en el modo de visualización (ofv) o edición (ofe). El modo de edición es el predeterminado.</span><span class="sxs-lookup"><span data-stu-id="53245-p107">Office applications can open files directly into view (ofv) or edit (ofe) mode. Edit mode is the default.</span></span>
  
<span data-ttu-id="53245-154">Formato de esquema:</span><span class="sxs-lookup"><span data-stu-id="53245-154">Schema format:</span></span>
  
 `<ofv or ofe>`
  
### <a name="url"></a><span data-ttu-id="53245-155">URL</span><span class="sxs-lookup"><span data-stu-id="53245-155">URL</span></span>

<span data-ttu-id="53245-156">La dirección URL incluye tres partes:</span><span class="sxs-lookup"><span data-stu-id="53245-156">The URL includes three parts:</span></span>
  
- <span data-ttu-id="53245-157">La declaración de que el archivo se abrirá para su edición (ofe)</span><span class="sxs-lookup"><span data-stu-id="53245-157">The declaration that the file will be opened for edit (ofe)</span></span>
    
- <span data-ttu-id="53245-158">El descriptor de la dirección URL (|u|)</span><span class="sxs-lookup"><span data-stu-id="53245-158">The URL descriptor (|u|)</span></span>
    
- <span data-ttu-id="53245-159">La dirección URL</span><span class="sxs-lookup"><span data-stu-id="53245-159">The URL</span></span>
    
<span data-ttu-id="53245-p108">La dirección URL se debe codificar y debe ser un vínculo directo al archivo (no una redirección). Si la dirección URL está en un formato que Office no puede gestionar o simplemente se produce un error en la descarga, Office no devolverá al usuario a la aplicación que realizó la invocación.</span><span class="sxs-lookup"><span data-stu-id="53245-p108">The URL has to be encoded and must be a direct link to the file (not a redirect). If the URL is in a format that Office cannot handle, or the download simply fails, Office will not return the user to the invoking application.</span></span>
  
<span data-ttu-id="53245-162">Formato de esquema:</span><span class="sxs-lookup"><span data-stu-id="53245-162">Schema format:</span></span>
  
 `|u|<document URL>`
  
## <a name="see-also"></a><span data-ttu-id="53245-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="53245-163">See also</span></span>
<span data-ttu-id="53245-164"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="53245-164"></span></span>

- [<span data-ttu-id="53245-165">Integración con Office</span><span class="sxs-lookup"><span data-stu-id="53245-165">Integrate with Office</span></span>](integrate-with-office.md)
    
- [<span data-ttu-id="53245-166">PackageManager</span><span class="sxs-lookup"><span data-stu-id="53245-166">PackageManager</span></span>](http://developer.android.com/reference/android/content/pm/PackageManager.html)
    
- [<span data-ttu-id="53245-167">GetPackageManager()</span><span class="sxs-lookup"><span data-stu-id="53245-167">GetPackageManager()</span></span>](http://developer.android.com/reference/android/content/Context.html)
    
