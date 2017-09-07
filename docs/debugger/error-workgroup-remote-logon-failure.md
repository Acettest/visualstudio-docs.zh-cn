---
title: 'Error: Workgroup Remote Logon Failure | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.error.workgroup_remote_logon_failure
dev_langs:
- CSharp
- VB
- FSharp
- JScript
- C++
helpviewer_keywords:
- logon failure, remote debugging
- remote debugging, logon failure
ms.assetid: 7be2c5bb-40fe-48d6-8cfc-c231fbd3d64e
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
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
ms.translationtype: HT
ms.sourcegitcommit: 9e6c28d42bec272c6fd6107b4baf0109ff29197e
ms.openlocfilehash: d0ebccfdb523661ba04a103bf6999e9c6546d1c7
ms.contentlocale: zh-cn
ms.lasthandoff: 08/22/2017

---
# <a name="error-workgroup-remote-logon-failure"></a>Error: Workgroup Remote Logon Failure
This error reads:  
  
 Logon failure: unknown user name or bad password  
  
 **Cause**  
  
 This error can occur when you are debugging from a machine on a workgroup and you try to connect to remote machine. Possible causes include:  
  
-   There is no account with the matching name and password on the remote machine.  
  
-   If both the Visual Studio computer and the remote machine are on workgroups, this error may occur due to the default **Local Security Policy** setting on the remote machine. The default setting for the **Local Security Policy** setting is **Guest only - local users authenticate as Guest**. To debug on this setup, you must change the setting on the remote machine to **Classic - local users authenticate as themselves**.  
  
> [!NOTE]
>  You must be an administrator to carry out the following tasks.  
  
### <a name="to-open-the-local-security-policy-window"></a>To open the Local Security Policy window  
  
1.  Start the **secpol.msc** Microsoft Management Console snap-in. Type secpol.msc in Windows search, the Windows Run box, or at a command prompt.  
  
### <a name="to-add-user-rights-assignments"></a>To add user rights assignments  
  
1.  Open the **Local Security Policy** window.  
  
2.  Expand the **Local Policies** folder.  
  
3.  Click **User Rights Assignment**.  
  
4.  In the **Policy** column, double-click **Debug programs** to view current local group policy assignments in the **Local Security Policy Setting** dialog box.  
  
     ![Local Security Policy User Rights](../debugger/media/dbg_err_localsecuritypolicy_userrightsdebugprograms.png "DBG_ERR_LocalSecurityPolicy_UserRightsDebugPrograms")  
  
5.  To add new users, click the **Add User or Group** button.  
  
### <a name="to-change-the-sharing-and-security-model"></a>To change the Sharing and Security Model  
  
1.  Open the **Local Security Policy** window.  
  
2.  Expand the **Local Policies** folder.  
  
3.  Click **Security Options**.  
  
4.  In the **Policy** column, double-click **Network access: Sharing and security model for local accounts**.  
  
5.  In the **Network access: Sharing and security model for local accounts** dialog box, change the value to **Classic - local users authenticate as themselves** and click the **Apply** button.  
  
     ![Local Security Policy Security Options](../debugger/media/dbg_err_localsecuritypolicy_securityoptions_networkaccess.png "DBG_ERR_LocalSecurityPolicy_SecurityOptions_NetworkAccess")  
  
## <a name="see-also"></a>See Also  
 [Remote Debugging Errors and Troubleshooting](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Remote Debugging](../debugger/remote-debugging.md)