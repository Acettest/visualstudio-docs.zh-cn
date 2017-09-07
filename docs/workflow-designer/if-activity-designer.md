---
title: "If 活动设计器 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.If.UI"
ms.assetid: 930a8fa2-db98-43e9-ad6d-a85cc7a6519a
caps.latest.revision: 4
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# If 活动设计器
<xref:System.Activities.Statements.If> 活动计算条件并根据该计算结果执行活动。当使用编程的过程建模样式时，此活动最有用。例如，<xref:System.Activities.Statements.If> 活动可嵌套在 <xref:System.Activities.Statements.Sequence> 活动或 <xref:System.Activities.Statements.Parallel> 活动内。如果您使用的是 <xref:System.Activities.Statements.Flowchart> 活动，请考虑改用 <xref:System.Activities.Statements.FlowDecision> 活动。  
  
## 工作流设计器中的 If 属性  
 下表列出最有用的 <xref:System.Activities.Statements.If> 活动属性并说明如何在设计器中使用它们。  
  
|属性名|必需|用法|  
|---------|--------|--------|  
|<xref:System.Activities.Statements.If.Condition%2A>|True|用于确定要执行哪个子活动的条件。若要设置 <xref:System.Activities.Statements.If.Condition%2A>，请在**“If”**活动设计器或属性网格中的**“Condition”**框中键入 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 表达式。|  
|<xref:System.Activities.Statements.If.Else%2A>|False|当 <xref:System.Activities.Statements.If.Condition%2A> 为 **false** 时要执行的活动。若要添加由 <xref:System.Activities.Statements.If.Else%2A> 分支执行的活动，请将活动从**“工具箱”**拖放到**“If”**活动设计器上带提示文本“在此处放置活动”的**“Else”**框中。|  
|<xref:System.Activities.Statements.If.Then%2A>|False|当 <xref:System.Activities.Statements.If.Condition%2A> 为 **true** 时要执行的活动。若要添加由 <xref:System.Activities.Statements.If.Then%2A> 分支执行的活动，请将活动从**“工具箱”**拖放到**“If”**活动设计器上带提示文本“在此处放置活动”的**“Then”**框中。|  
  
## 请参阅  
 [Sequence](../workflow-designer/sequence-activity-designer.md)   
 [Parallel](../workflow-designer/parallel-activity-designer.md)   
 [控制流](../workflow-designer/control-flow-activity-designers.md)