---
title: "使用工具箱 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.chooseitems
- vs.toolboxpages.activexcontrols
- VS.CHOOSEITEMS.windowsuixamlcomponents
- VS.chooseitems.silverlightcomponents
- VC.EDITORS.RIBBON
- vs.customizetoolbox
- VS.chooseitems.System.Workflow_Components
- vs.chooseitems.frameworkcomponents
- VS.ToolboxPages..NET_Framework_Components
- VS.chooseitems.Microsoft.VisualStudio.Toolbox.VsToolboxPage
- vs.chooseitems.comcomponents
- vs.toolboxpages.NGWS_components
helpviewer_keywords:
- toolbox, adding items
- Visual Studio, toolbox
- toolbox, tabs
- toolbox
ms.assetid: 82e7cb43-4d0b-4e17-b7b0-43f96c22c3c2
caps.latest.revision: 20
author: kempb
ms.author: kempb
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 5ea9179ad37514ffad4876177b05150eecc22def
ms.openlocfilehash: 8941dd8635b32d9e02ab75256cbe8e2894f762f4
ms.contentlocale: zh-cn
ms.lasthandoff: 05/24/2017

---
# <a name="using-the-toolbox"></a>使用工具箱
可以使用工具箱将控件和其他项添加到项目中。 还可以将不同的控件拖到和放置到你使用的设计器的图面上，然后调整控件的大小并将它们定位。  
  
 工具箱与设计器视图一起显示，如 XAML 文件的设计器视图。 工具箱仅显示可在当前设计器中使用的那些控件。  
  
 你的项目面向的 .NET Framework 版本还会影响工具箱中可见的控件组。 默认情况下，[!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)] 项目面向 .NET Framework 4.5.1。 通过选择“解决方案资源管理器”中的项目节点，然后浏览到“属性/应用程序/目标框架”，可将项目设置为面向不同版本的 .NET Framework。  
  
## <a name="managing-the-toolbox-and-its-controls"></a>管理“工具箱”及其控件  
 默认情况下，将工具箱折叠在 Visual Studio IDE 左侧，并当光标移至该控件上方时显示。 可固定工具箱（通过单击工具箱工具栏上的“固定”图标），以便在移动光标时它仍保持打开。 也可以取消停靠该工具箱窗口并将其拖动到屏幕上的任何位置。 可以通过右击工具箱的工具栏并选择其中一个选项，停靠、取消停靠和隐藏该工具箱。  
  
 可以通过使用上下文菜单上的以下命令，重新排列工具箱选项卡中的项或添加自定义的选项卡和项：  
  
-   重命名项 - 重命名所选的项。  
  
-   显示所有 - 显示所有可能的控件（不只是适用于当前设计器的控件）。  
  
-   列表视图 - 显示垂直列表中的控件。 如果未选中，则这些控件水平显示。  
  
-   选择项 - 打开“选择工具箱项”对话框即可指定“工具箱”中显示的项。 可以通过选中或清除复选框显示或隐藏项。  
  
-   按字母顺序对项排序 - 按名称对项排序。  
  
-   重置工具栏 - 还原默认工具箱设置和项。  
  
-   添加选项卡 - 添加新的工具箱选项卡。  
  
-   上移 - 将所选项上移。  
  
-   下移 - 将所选项下移。  
  
## <a name="creating-and-distributing-custom-toolbox-controls"></a>创建和分布自定义工具箱控件  
 可在 Visual Basic 或 Visual C# 中创建自定义工具箱控件，可以从创建基于 [Windows Presentation Foundation](../extensibility/creating-a-wpf-toolbox-control.md) 或 [Windows 窗体](../extensibility/creating-a-windows-forms-toolbox-control.md)的项目模板开始。 然后，可使用[工具箱控件安装程序](http://download.microsoft.com/download/8/3/6/836657BD-9CCB-4ED4-B9D2-FB769473B284/TCI_whitepaper.docx)将控件分发给团队成员或将它发布到 Web 上。