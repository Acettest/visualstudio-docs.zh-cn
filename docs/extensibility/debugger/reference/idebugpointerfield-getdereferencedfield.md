---
title: IDebugPointerField::GetDereferencedField | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugPointerField::GetDereferencedField
helpviewer_keywords:
- IDebugPointerField::GetDereferencedField method
ms.assetid: 8de988ab-cd79-4287-be72-3c900f2fe407
caps.latest.revision: 7
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
ms.openlocfilehash: 3c431a56f1a678dc79bdfefeedf4bb65d1d93d36
ms.contentlocale: zh-cn
ms.lasthandoff: 08/28/2017

---
# <a name="idebugpointerfieldgetdereferencedfield"></a>IDebugPointerField::GetDereferencedField
This method returns the type of object to which this pointer object points.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDereferencedField(  
   IDebugField** ppField  
);  
```  
  
```csharp  
int GetDereferencedField(  
   out IDebugField ppField  
);  
```  
  
#### <a name="parameters"></a>Parameters  
 `ppField`  
 [out] Returns an [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) describing the type of target object.  
  
## <a name="return-value"></a>Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## <a name="remarks"></a>Remarks  
 If, for example, the [IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md) object points to an integer, the [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) type returned by this method describes that integer type.  
  
## <a name="see-also"></a>See Also  
 [IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)