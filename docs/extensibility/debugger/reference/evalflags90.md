---
title: EVALFLAGS90 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- EVALFLAGS90 enumeration
ms.assetid: 64fb0139-8b04-4726-b52c-db2e04d65498
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
ms.openlocfilehash: 25ff118d4cb3388798b456c516869d62b47ef4e3
ms.contentlocale: zh-cn
ms.lasthandoff: 08/28/2017

---
# <a name="evalflags90"></a>EVALFLAGS90
Enumerates the valid values for flags that control expression evaluation. This enumeration extends the [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) enumeration.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
enum enum_EVALFLAGS90  
{  
   // VS 8.0 values  
   EVAL90_RETURNVALUE                 = 0x0002,  
   EVAL90_NOSIDEEFFECTS               = 0x0004,  
   EVAL90_ALLOWBPS                    = 0x0008,  
   EVAL90_ALLOWERRORREPORT            = 0x0010,  
   EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,  
   EVAL90_NOFUNCEVAL                  = 0x0080,  
   EVAL90_NOEVENTS                    = 0x1000,  
   EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,  
   EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,  
  
   // Values added in VS 9.0  
   EVAL90_FORCE_EVALUATION_NOW        = 0x8000  
};  
typedef DWORD EVALFLAGS90;  
```  
  
```csharp  
public enum enum_EVALFLAGS90  
{  
   // VS 8.0 values  
   EVAL90_RETURNVALUE                 = 0x0002,  
   EVAL90_NOSIDEEFFECTS               = 0x0004,  
   EVAL90_ALLOWBPS                    = 0x0008,  
   EVAL90_ALLOWERRORREPORT            = 0x0010,  
   EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,  
   EVAL90_NOFUNCEVAL                  = 0x0080,  
   EVAL90_NOEVENTS                    = 0x1000,  
   EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,  
   EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,  
  
   // Values added in VS 9.0  
   EVAL90_FORCE_EVALUATION_NOW        = 0x8000  
};  
```  
  
#### <a name="parameters"></a>Parameters  
 EVAL90_RETURNVALUE  
 Specifies that the return value, if any, be evaluated.  
  
 EVAL90_NOSIDEEFFECTS  
 Specifies that side effects not be allowed.  
  
 EVAL90_ALLOWBPS  
 Specifies stopping on breakpoints.  
  
 EVAL90_ALLOWERRORREPORT  
 Specifies that error reporting to the host to be allowed. Primarily used for expression evaluation in script in Internet Explorer.  
  
 EVAL90_FUNCTION_AS_ADDRESS  
 Forces functions to be evaluated as addresses, instead of invoking the function.  
  
 EVAL90_NOFUNCEVAL  
 Prevents function from being evaluated. For example, consider the `int` token in the expression `myExpression(int) + 10`. This function can be correctly evaluated as an address, but not as a value.  
  
 EVAL90_NOEVENTS  
 Flag to indicate that events that occur during the expression evaluation should not be sent to the session debug manager (SDM) or to the IDE.  
  
 EVAL90_DESIGN_TIME_EXPR_EVAL  
 Enables design-time expression evaluation.  
  
 EVAL90_ALLOW_IMPLICIT_VARS  
 Allows implicit variable creation.  
  
 EVAL90_FORCE_EVALUATION_NOW  
 Forces evaluation to occur immediately. This is useful when servicing a request, such as a user request.  
  
## <a name="requirements"></a>Requirements  
 Header: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>See Also  
 [Enumerations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)