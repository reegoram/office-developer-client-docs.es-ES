---
title: Ejemplo de método Create (VC++)
TOCTitle: Create Method Example (VC++)
ms:assetid: 8a826d78-7219-27de-8560-7cd4b8284751
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249609(v=office.15)
ms:contentKeyID: 48546195
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c7e77cfe959eb1f97bc9b0262a78c91f56d44356
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486517"
---
# <a name="create-method-example-vc"></a>Ejemplo de método Create (VC++)


**Se aplica a**: Access 2013 | Office 2013

El código siguiente muestra cómo crear una nueva base de datos de Microsoft Jet con el método [Create](create-method-adox.md).

```cpp 
 
// BeginCreateDatabaseCpp 
#import "c:\Program Files\Common Files\system\ado\msadox.dll" no_namespace 
#import "c:\Program Files\Common Files\system\ado\msado15.dll" 
 
#define TESTHR(x) if FAILED(x) _com_issue_error(x); 
 
#include "iostream.h" 
#include "stdio.h" 
#include "conio.h" 
 
//Function declarations 
void CreateDatabaseX(void); 
 
//------------------------------------------------------------// 
//Main Function 
//Purpose: Test Driver 
//------------------------------------------------------------// 
void main() 
{ 
 HRESULT hr = S_OK; 
 
 hr = ::CoInitialize(NULL); 
 if(SUCCEEDED(hr)) 
 { 
 CreateDatabaseX(); 
 
 //Wait here for the user to see the output 
 printf("Press any key to continue..."); 
 getch(); 
 
 ::CoUninitialize(); 
 } 
} 
 
//------------------------------------------------------------// 
//CreateDatabaseX 
//Purpose: create a new Jet database with the Create method 
//------------------------------------------------------------// 
void CreateDatabaseX() 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADOX object pointers. 
 // Initialize pointers on define. 
 // These are in the ADOX:: namespace. 
 
 _CatalogPtr m_pCatalog = NULL; 
 
 
 //Set ActiveConnection of Catalog to this string 
 _bstr_t strcnn("Provider='Microsoft.JET.OLEDB.4.0';" 
 "Data source = c:\\new.mdb"); 
 try 
 { 
 TESTHR(hr = m_pCatalog.CreateInstance(__uuidof (Catalog))); 
 m_pCatalog->Create(strcnn); 
 printf("Database 'c:\\new.mdb' is created.\n"); 
 } 
 catch(_com_error &e) 
 { 
 // Notify the user of errors if any. 
 _bstr_t bstrSource(e.Source()); 
 _bstr_t bstrDescription(e.Description()); 
 
 printf("\n\tSource : %s \n\tdescription : %s \n ", 
 (LPCSTR)bstrSource,(LPCSTR)bstrDescription); 
 
 } 
 catch(...) 
 { 
 cout << "Error occured in CreateDatabaseX...."<< endl; 
 } 
 
} 
// EndCreateDatabaseCpp 
```

