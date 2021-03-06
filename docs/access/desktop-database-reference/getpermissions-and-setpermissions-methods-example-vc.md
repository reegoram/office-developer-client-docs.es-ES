---
title: Ejemplo de métodos GetPermissions y SetPermissions (VC++)
TOCTitle: GetPermissions and SetPermissions Methods Example (VC++)
ms:assetid: 3713165f-7dc6-6965-b0d9-fb8e6a315a86
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249128(v=office.15)
ms:contentKeyID: 48544184
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 17c267067bdd993e8bf5874cce49662e45b42f57
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484284"
---
# <a name="getpermissions-and-setpermissions-methods-example-vc"></a>Ejemplo de métodos GetPermissions y SetPermissions (VC++)


**Se aplica a**: Access 2013 | Office 2013

En este ejemplo, se muestran los métodos [GetPermissions](getpermissions-method-adox.md) y [SetPermissions](setpermissions-method-adox.md). El código siguiente proporciona al usuario Administrador acceso total a la tabla Pedidos.

```cpp 
 
// BeginGrantPermissionCpp 
#import "c:\Program Files\Common Files\system\ado\msado15.dll" 
#import "c:\Program Files\Common Files\system\ado\msadox.dll" no_namespace 
 
#include "iostream.h" 
#include "stdio.h" 
#include "conio.h" 
 
//Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void GrantPermissionsX(void); 
 
////////////////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
////////////////////////////////////////////////////////// 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 GrantPermissionsX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// GrantPermissionsX Function // 
// // 
////////////////////////////////////////////////////////// 
void GrantPermissionsX() 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADOX object pointers. 
 // Initialize pointers on define. 
 // These are in the ADOX:: namespace. 
 _CatalogPtr m_pCatalog = NULL; 
 
 //Define ADODB object pointers; 
 ADODB::_ConnectionPtr m_pCnn = NULL; 
 
 //Define other variables here. 
 try 
 { 
 TESTHR(hr = m_pCnn.CreateInstance(__uuidof(ADODB::Connection))); 
 
 //Opens a connection to the northwind database 
 //using the Microsoft Jet 4.0 provider 
 m_pCnn->PutProvider("Microsoft.Jet.OLEDB.4.0"); 
 m_pCnn->Open("data source='c:\\Program Files\\" "Microsoft Office\\Office\\Samples\\Northwind.mdb';" "jet oledb:system database='c:\\Program Files\\Microsoft Office\\Office\\system.mdw'", 
 "","",NULL); 
 
 TESTHR(hr = m_pCatalog.CreateInstance(__uuidof(Catalog))); 
 
 m_pCatalog->PutActiveConnection(_variant_t((IDispatch *)m_pCnn)); 
 
 //Retrieve original permissions 
 long lngPerm = m_pCatalog->Users->GetItem("admin")-> 
 GetPermissions("Orders",adPermObjTable); 
 long lngOrgPerm = lngPerm; 
 cout << "Original Permissions: " << lngPerm << "\n" << endl; 
 
 //Revoke all permissions 
 m_pCatalog->Users->GetItem("admin")->SetPermissions("Orders", 
 adPermObjTable,adAccessRevoke,adRightFull,adInheritNone); 
 
 //Display permissions 
 lngPerm = m_pCatalog->Users->GetItem("admin")-> 
 GetPermissions("Orders",adPermObjTable); 
 cout << "Revoked permissions: " << lngPerm << "\n" << endl; 
 
 //Give the Admin user full rights on the orders object 
 m_pCatalog->Users->GetItem("admin")->SetPermissions("Orders", 
 adPermObjTable,adAccessSet,adRightFull,adInheritNone); 
 
 //Display permissions 
 lngPerm = m_pCatalog->Users->GetItem("admin")-> 
 GetPermissions("Orders",adPermObjTable); 
 cout << "Full permissions: " << lngPerm << "\n" << endl; 
 
 //Restore original permissions 
 m_pCatalog->Users->GetItem("admin")->SetPermissions("Orders", 
 adPermObjTable,adAccessSet,(RightsEnum) lngOrgPerm, 
 adInheritNone); 
 
 //Display permissions 
 lngPerm = m_pCatalog->Users->GetItem("admin")-> 
 GetPermissions("Orders",adPermObjTable); 
 cout << "Final permissions: " << lngPerm << "\n" << endl; 
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
 cout << "Error occured in GrantPermissionsX...."<< endl; 
 } 
} 
// EndGrantPermissionCpp 
```

