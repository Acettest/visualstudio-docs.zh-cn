---
title: IDebugProperty3::SetValueAsStringWithError | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProperty3::SetValueAsStringWithError
helpviewer_keywords:
- IDebugProperty3::SetValueAsStringWithError
ms.assetid: b378368f-4a45-4b2f-8e3d-3bff7a18ab17
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: cec26257ab5c283c82846ff477b3e929e40194f1
ms.contentlocale: zh-cn
ms.lasthandoff: 08/28/2017

---
# <a name="idebugproperty3setvalueasstringwitherror"></a>IDebugProperty3::SetValueAsStringWithError
Sets the value of this property and returns an error message, if necessary.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetValueAsStringWithError(  
   LPCOLESTR pszValue,  
   DWORD     dwRadix,  
   DWORD     dwTimeout,  
   BSTR*     errorString  
);  
```  
  
```csharp  
int SetValueAsStringWithError(  
   string     pszValue,  
   uint       dwRadix,  
   uint       dwTimeout,  
   out string errorString  
);  
```  
  
#### <a name="parameters"></a>Parameters  
 `pszValue`  
 [in] Value to set.  
  
 `dwRadix`  
 [in] The radix of the value being set.  
  
 `dwTimeout`  
 [in] The length of time to wait for the value to be set (`INFINITE` means wait forever).  
  
 `errorString`  
 [out] If there was an error setting the value, this holds the reason for the failure.  
  
## <a name="return-value"></a>Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## <a name="remarks"></a>Remarks  
 The incoming value could be an expression to be evaluated.  
  
## <a name="example"></a>Example  
 The following example shows how to implement this method for a **CProperty** object that exposes the [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) interface.  
  
```cpp  
HRESULT CProperty::SetValueAsStringWithError(   
    LPCOLESTR in_szValue,  
    DWORD in_RADIX,  
    DWORD in_TIMEOUT,   
    BSTR * out_ERRORTEXT  
)  
{  
    // precondition  
    REQUIRE( NULL != in_szValue );  
  
    if (NULL == in_szValue)  
        return E_INVALIDARG;  
  
    INVARIANT( this );  
    if (!this->ClassInvariant())  
        return E_UNEXPECTED;  
  
    if (NULL == m_pPropertyContext->m_pCEE->m_LanguageSpecificUseCases.pfSetValue)  
        return S_OK;  
  
    // function body  
    DEBUG_PROPERTY_INFO dpInfo,dpInfo2;  
    HRESULT HR = this->GetPropertyInfo(DEBUGPROP_INFO_FULLNAME | DEBUGPROP_INFO_ATTRIB | DEBUGPROP_INFO_TYPE | DEBUGPROP_INFO_VALUE_AUTOEXPAND,  
                                       in_RADIX,  
                                       in_TIMEOUT,  
                                       NULL,  
                                       0,  
                                       &dpInfo);  
  
    if (ENSURE( S_OK == HR ))  
    {  
        REQUIRE( NULL != dpInfo.bstrFullName );  
        REQUIRE( NULL != dpInfo.bstrType );  
  
        REQUIRE( NULL == dpInfo.bstrName );  
        REQUIRE( NULL == dpInfo.bstrValue );  
        REQUIRE( NULL == dpInfo.pProperty );  
  
        BSTR bstrError = NULL;  
  
        UINT ichError = 0;  
        IDebugProperty2* pProperty = NULL;  
        IDebugParsedExpression* pParsedExpression = NULL;  
  
        CComBSTR bstrValue = dpInfo.bstrFullName;  
        bstrValue += L" = ";  
        bstrValue += in_szValue;  
        HR = this->m_pPropertyContext->m_pCEE->  
                Parse(bstrValue, 0, in_RADIX, &bstrError, &ichError, &pParsedExpression);  
        if (S_OK == HR)  
        {  
            REQUIRE( NULL == bstrError );  
            HR = pParsedExpression->EvaluateSync(EVAL_NOEVENTS | EVAL_RETURNVALUE,  
                                                 in_TIMEOUT,  
                                                 m_pPropertyContext->m_pSymbolProvider,  
                                                 m_pPropertyContext->m_pAddress,  
                                                 m_pPropertyContext->m_pBinder,  
                                                 NULL,  
                                                 &pProperty);  
  
            dpInfo2.dwAttrib = DBG_ATTRIB_VALUE_ERROR;  
            if (pProperty)  
            {  
                pProperty->GetPropertyInfo(DEBUGPROP_INFO_ATTRIB | DEBUGPROP_INFO_VALUE,10,in_TIMEOUT,NULL,0,&dpInfo2);  
            }  
            if (DBG_ATTRIB_VALUE_ERROR & dpInfo2.dwAttrib)  
            {  
                HR = E_FAIL;  
                bstrError = dpInfo2.bstrValue;  
            }  
            else  
            {  
                ::SysFreeString(dpInfo.bstrValue);  
            }  
            EXTERNAL_RELEASE(pProperty);  
            EXTERNAL_RELEASE(pParsedExpression);          
        }  
  
        if (bstrError)  
        {  
            if(out_ERRORTEXT)  
            {  
                *out_ERRORTEXT = bstrError;  
                bstrError = NULL;  
            }  
            else  
            {  
                ::SysFreeString(bstrError);  
            }  
        }  
        ::SysFreeString(dpInfo.bstrFullName);  
        ::SysFreeString(dpInfo.bstrType);  
    }  
  
    // postcondition  
    INVARIANT( this );  
  
    return HR;  
}  
```  
  
## <a name="see-also"></a>See Also  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)