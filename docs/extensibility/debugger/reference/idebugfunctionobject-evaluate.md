---
title: IDebugFunctionObject::Evaluate |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugFunctionObject::Evaluate
helpviewer_keywords:
- IDebugFunctionObject::Evaluate method
ms.assetid: 29349ea3-d5c1-4135-aa76-ced073ab9683
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4f717a61e79e9f91f9f79a32d1da5020b0084516
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31111124"
---
# <a name="idebugfunctionobjectevaluate"></a>IDebugFunctionObject::Evaluate
调用函数并返回一个对象作为生成的值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Evaluate(   
   IDebugObject** ppParams,  
   DWORD          dwParams,  
   DWORD          dwTimeout,  
   IDebugObject** ppResult  
);  
```  
  
```csharp  
int Evaluate(  
   IDebugObject[]   ppParams,   
   IntPtr           dwParams,   
   uint             dwTimeout,   
   out IDebugObject ppResult  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppParams`  
 [in]数组[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)表示输入的参数的对象。 每个这些参数创建的其中一条`Create`中的方法[IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)接口。  
  
 `dwParams`  
 [in]中的参数数目`ppParams`数组。  
  
 `dwTimeout`  
 [in]指定以毫秒为单位，从此方法返回前等待的最长时间。 使用`INFINITE`无限期等待。  
  
 `ppResult`  
 [out]返回[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)表示对象的函数的值。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法将设置和执行对所表示的函数的调用[IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)对象。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)