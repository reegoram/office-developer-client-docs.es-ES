---
title: Enviar un correo electrónico según la dirección SMTP de una cuenta
TOCTitle: Send an email given the SMTP address of an account
ms:assetid: 4ff4aaac-54ba-45c7-8b2e-aeba35af1e56
ms:mtpsurl: https://msdn.microsoft.com/library/Ff462095(v=office.15)
ms:contentKeyID: 55119865
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 01eef87c70e27425182b8a2f9f849c9736d43a31
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406396"
---
# <a name="send-an-email-given-the-smtp-address-of-an-account"></a><span data-ttu-id="3432c-102">Enviar un correo electrónico según la dirección SMTP de una cuenta</span><span class="sxs-lookup"><span data-stu-id="3432c-102">Send an E-mail Given the SMTP Address of an Account</span></span>

<span data-ttu-id="3432c-103">En este tema se muestra cómo crear un correo electrónico y enviarlo desde una cuenta de Microsoft Outlook según la dirección del protocolo simple de transferencia de correo (SMTP, Simple Mail Transfer Protocol) de esa cuenta.</span><span class="sxs-lookup"><span data-stu-id="3432c-103">This topic shows how to create an e-mail and send it from a Microsoft Outlook account, given the Simple Mail Transfer Protocol (SMTP) address of that account.</span></span>

## <a name="example"></a><span data-ttu-id="3432c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3432c-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="3432c-105">Helmut Obertanner proporciona los siguientes ejemplos de código.</span><span class="sxs-lookup"><span data-stu-id="3432c-105">Helmut Obertanner provided the following code examples.</span></span> <span data-ttu-id="3432c-106">Los conocimientos de Helmut están en Office Developer Tools para Visual Studio y Outlook.</span><span class="sxs-lookup"><span data-stu-id="3432c-106">Helmut's expertise is in Office Developer Tools for Visual Studio and Outlook.</span></span> 


<span data-ttu-id="3432c-107">Los siguientes ejemplos de código contienen los métodos SendEmailFromAccount y GetAccountForEmailAddress de la clase Sample, implementados como parte de un proyecto de complemento de Outlook.</span><span class="sxs-lookup"><span data-stu-id="3432c-107">The following code examples contain the SendEmailFromAccount and GetAccountForEmailAddress methods of the Sample class, implemented as part of an Outlook add-in project.</span></span> <span data-ttu-id="3432c-108">Cada proyecto agrega una referencia al ensamblado de interoperabilidad primario de Outlook, que se basa en el espacio de nombres [Microsoft.Office.Interop.Outlook](https://msdn.microsoft.com/library/bb610835\(v=office.15\)).</span><span class="sxs-lookup"><span data-stu-id="3432c-108">The following code examples contain the GetApplicationObject method of the Sample class, implemented as part of an Outlook add-in project. Each project adds a reference to the Outlook Primary Interop Assembly, which is based on the [N:Microsoft.Office.Interop.Outlook](https://msdn.microsoft.com/library/bb610835\(v=office.15\)) namespace.</span></span> <span data-ttu-id="3432c-109">El método SendEmailFromAccount acepta como argumentos de entrada un objeto [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) de confianza y cadenas que representan el asunto, el cuerpo, una lista delimitada por punto y coma de los destinatarios y la dirección SMTP de una cuenta de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3432c-109">The SendEmailFromAccount method accepts as input arguments a trusted [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) object, and strings that represent the subject, body, a semicolon-delimited list of recipients, and the SMTP address of an email account.</span></span> <span data-ttu-id="3432c-110">SendEmailFromAccount crea un objeto [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) e inicializa las propiedades [To](https://msdn.microsoft.com/library/bb624372\(v=office.15\)), [Subject](https://msdn.microsoft.com/library/bb611353\(v=office.15\)), y [Body](https://msdn.microsoft.com/library/bb646600\(v=office.15\)) con los determinados argumentos.</span><span class="sxs-lookup"><span data-stu-id="3432c-110">SendEmailFromAccount creates a [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) object and initializes the [To](https://msdn.microsoft.com/library/bb624372\(v=office.15\)), [Subject](https://msdn.microsoft.com/library/bb611353\(v=office.15\)), and [Body](https://msdn.microsoft.com/library/bb646600\(v=office.15\)) properties with the given arguments.</span></span> <span data-ttu-id="3432c-111">Para buscar el objeto [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) desde el que se envíe el correo electrónico, SendEmailFromAccount llama al método GetAccountForEmailAddress, que permite a la dirección SMTP determinada coincidir con la propiedad [SmtpAddress](https://msdn.microsoft.com/library/bb623516\(v=office.15\)) de cada cuenta del perfil actual.</span><span class="sxs-lookup"><span data-stu-id="3432c-111">To find the [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) object from which to send the email, SendEmailFromAccount calls the GetAccountForEmailAddress method, which matches the given SMTP address with the [SmtpAddress](https://msdn.microsoft.com/library/bb623516\(v=office.15\)) property of each account for the current profile.</span></span> <span data-ttu-id="3432c-112">El objeto **Account** coincidente se devuelve a SendEmailFromAccount que, luego, inicializa la propiedad [SendUsingAccount](https://msdn.microsoft.com/library/bb623679\(v=office.15\)) del **MailItem** con este objeto **Account** y envía el **MailItem**.</span><span class="sxs-lookup"><span data-stu-id="3432c-112">The matching **Account** object is returned to SendEmailFromAccount, which then initializes the [SendUsingAccount](https://msdn.microsoft.com/library/bb623679\(v=office.15\)) property of the **MailItem** with this **Account** object, and sends the **MailItem**.</span></span>

<span data-ttu-id="3432c-113">A continuación, el ejemplo de código de Visual Basic, seguido por el ejemplo de código de C\#.</span><span class="sxs-lookup"><span data-stu-id="3432c-113">The following is the Visual Basic code example, followed by the C# code example.</span></span>

<span data-ttu-id="3432c-114">Si usa Visual Studio para probar este ejemplo de código, primero debe agregar una referencia al componente de la biblioteca de objetos de Microsoft Outlook 15.0 y especificar la variable de Outlook al importar el espacio de nombres **Microsoft.Office.Interop.Outlook**.</span><span class="sxs-lookup"><span data-stu-id="3432c-114">
    If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the \*\*Microsoft.Office.Interop.Outlook\*\* namespace. The using statement must not occur directly before the functions in the code example but must be added before the public Class declaration. The following line of code shows how to do the import and assignment in C#.
</span></span> <span data-ttu-id="3432c-115">Las instrucciones **Imports** o **using** no deben producirse directamente antes de las funciones en el ejemplo de código, pero deben agregarse antes de la declaración de Clase pública.</span><span class="sxs-lookup"><span data-stu-id="3432c-115">The **Imports** or **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="3432c-116">Las líneas de código siguientes muestran cómo llevar a cabo la importación y la asignación en Visual Basic y C\#.</span><span class="sxs-lookup"><span data-stu-id="3432c-116">The following lines of code show how to do the import and assignment in Visual Basic and C\#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Imports Outlook = Microsoft.Office.Interop.Outlook

Namespace OutlookAddIn2
    Class Sample
        
        Shared Sub SendEmailFromAccount(ByVal application As Outlook.Application, _
            ByVal subject As String, ByVal body As String, ByVal recipients As String, ByVal smtpAddress As String)

            ' Create a new MailItem and set the To, Subject, and Body properties.
            Dim newMail As Outlook.MailItem = DirectCast(application.CreateItem(Outlook.OlItemType.olMailItem), Outlook.MailItem)
            newMail.To = recipients
            newMail.Subject = subject
            newMail.Body = body

            ' Retrieve the account that has the specific SMTP address.
            Dim account As Outlook.Account = GetAccountForEmailAddress(application, smtpAddress)
            ' Use this account to send the email.
            newMail.SendUsingAccount = account
            newMail.Send()
        End Sub

        Shared Function GetAccountForEmailAddress(ByVal application As Outlook.Application, ByVal smtpAddress As String) As Outlook.Account

            ' Loop over the Accounts collection of the current Outlook session.
            Dim accounts As Outlook.Accounts = application.Session.Accounts
            Dim account As Outlook.Account
            For Each account In accounts
                ' When the email address matches, return the account.
                If account.SmtpAddress = smtpAddress Then
                    Return account
                End If
            Next
            Throw New System.Exception(String.Format("No Account with SmtpAddress: {0} exists!", smtpAddress))
        End Function

    End Class
End Namespace
```


```csharp
using System;
using System.Text;
using Outlook = Microsoft.Office.Interop.Outlook;

namespace OutlookAddIn1
{
    class Sample
    {
        public static void SendEmailFromAccount(Outlook.Application application, string subject, string body, string to, string smtpAddress)
        {

            // Create a new MailItem and set the To, Subject, and Body properties.
            Outlook.MailItem newMail = (Outlook.MailItem)application.CreateItem(Outlook.OlItemType.olMailItem);
            newMail.To = to;
            newMail.Subject = subject;
            newMail.Body = body;

            // Retrieve the account that has the specific SMTP address.
            Outlook.Account account = GetAccountForEmailAddress(application, smtpAddress);
            // Use this account to send the email.
            newMail.SendUsingAccount = account;
            newMail.Send();
        }


        public static Outlook.Account GetAccountForEmailAddress(Outlook.Application application, string smtpAddress)
        {

            // Loop over the Accounts collection of the current Outlook session.
            Outlook.Accounts accounts = application.Session.Accounts;
            foreach (Outlook.Account account in accounts)
            {
                // When the email address matches, return the account.
                if (account.SmtpAddress == smtpAddress)
                {
                    return account;
                }
            }
            throw new System.Exception(string.Format("No Account with SmtpAddress: {0} exists!", smtpAddress));
        }

    }
}
```

## <a name="see-also"></a><span data-ttu-id="3432c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3432c-117">See also</span></span>

- [<span data-ttu-id="3432c-118">Correo</span><span class="sxs-lookup"><span data-stu-id="3432c-118">Mail</span></span>](mail.md)
