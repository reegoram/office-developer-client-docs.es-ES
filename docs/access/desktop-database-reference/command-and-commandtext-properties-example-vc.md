---
<<<<<<< Título HEAD: comando y ejemplo de las propiedades CommandText (VC ++) TOCTitle: comando y ejemplo de las propiedades CommandText (VC ++) === título: ejemplo de propiedades comando y CommandText (VC ++) TOCTitle: comando y CommandText ejemplo de las propiedades (VC ++)
>>>>>>> Master ms:assetid: 99eac61e-22fe-0e2c-542a-7f6ad14f3d60 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249692(v=office.15) ms:contentKeyID: ms.date 48546525: 18/09/2015 mtps_version: Office.15
---

<<<<<<< HEAD
# <a name="command-and-commandtext-properties-example-vc"></a>Ejemplo de propiedades Comando y CommandText (VC++)
=======
# <a name="command-and-commandtext-properties-example-vc"></a>Ejemplo de propiedades comando y CommandText (VC ++)
>>>>>>> master


**Se aplica a**: Access 2013 | Office 2013

El código siguiente muestra cómo utilizar la propiedad [Comando](command-property-adox.md) para actualizar el texto de un procedimiento.

```cpp 
 
// BeginCommandTextCpp 
// This sample runs correctly only if procedure 'CustomerById' 
// exists. If the procedure doesn't exist, please use 
// 'ADOXProceduresAppend.cpp' to creat it. 
 
#import "c:\Program Files\Common Files\system\ado\msadox.dll" no_namespace 
#import "c:\Program Files\Common Files\system\ado\msado15.dll" 
 
#include "iostream.h" 
#include "stdio.h" 
#include "conio.h" 
 
//Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void ProcedureTextX(void); 
 
////////////////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
////////////////////////////////////////////////////////// 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 ProcedureTextX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// ProcedureTextX Function // 
// // 
////////////////////////////////////////////////////////// 
void ProcedureTextX() 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADOX object pointers. 
 // Initialize pointers on define. 
 // These are in the ADOX:: namespace. 
 _CatalogPtr m_pCatalog = NULL; 
 
 // Define ADODB object pointers. 
 ADODB::_ConnectionPtr m_pCnn = NULL; 
 ADODB::_CommandPtr m_pCommand = NULL; 
 
 try 
 { 
 //Open the Connection 
 TESTHR(hr = m_pCnn.CreateInstance(__uuidof(ADODB::Connection))); 
 TESTHR(hr = m_pCatalog.CreateInstance(__uuidof(Catalog))); 
 TESTHR(hr = m_pCommand.CreateInstance(__uuidof(ADODB::Command))); 
 m_pCnn->Open("Provider='Microsoft.JET.OLEDB.4.0';" 
 "data source='c:\\Program Files\\Microsoft Office" 
 "\\Office\\Samples\\Northwind.mdb';","","",NULL); 
 
 // Open the catalog 
 m_pCatalog->PutActiveConnection(_variant_t((IDispatch *)m_pCnn)); 
 
 // Get the Command 
 m_pCommand = m_pCatalog->Procedures->GetItem("CustomerById")->GetCommand(); 
 
 // Update the CommandText 
 m_pCommand->PutCommandText("PARAMETERS [CustId] Text;select " 
 "CustomerId, CompanyName, ContactName " 
 "from Customers where CustomerId = [CustId]"); 
 printf("CommandText is updated.\n"); 
 
 // Update the Procedure 
 m_pCatalog->Procedures->GetItem("CustomerById")->PutCommand( 
 _variant_t((IDispatch *)m_pCommand)); 
 printf("Procedure 'CustomerById' is updated.\n"); 
 } 
 catch(_com_error &e) 
 { 
 // Notify the user of errors if any. 
 _bstr_t bstrSource(e.Source()); 
 _bstr_t bstrDescription(e.Description()); 
 
 printf("\n\tSource : %s \n\tdescription : %s \n ",(LPCSTR)bstrSource,(LPCSTR)bstrDescription); 
 } 
 catch(...) 
 { 
 cout << "Error occured in ProcedureTextX...."<< endl; 
 } 
} 
// EndCommandTextCpp 
```

