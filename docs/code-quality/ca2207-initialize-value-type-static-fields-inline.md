---
title: CA2207：以内联方式初始化值类型的静态字段
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- InitializeValueTypeStaticFieldsInline
- CA2207
helpviewer_keywords:
- CA2207
- InitializeValueTypeStaticFieldsInline
ms.assetid: d1ea9d8b-ecc2-46ca-86e2-c41dd0e76658
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a5730acf02cf12dce6d98e7cbd1b6f38f7ece05e
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45550565"
---
# <a name="ca2207-initialize-value-type-static-fields-inline"></a>CA2207：以内联方式初始化值类型的静态字段
|||
|-|-|
|TypeName|InitializeValueTypeStaticFieldsInline|
|CheckId|CA2207|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 值类型声明显式静态构造函数。

## <a name="rule-description"></a>规则说明
 当声明值类型时，它将接受其中所有值类型字段都设置为零并且所有引用类型字段都都设置为默认值初始化`null`(`Nothing`在 Visual Basic 中)。 只能保证在实例构造函数之前运行的显式静态构造函数或调用静态成员的类型。 因此，如果无需调用实例构造函数创建类型时，静态构造函数无法保证运行。

 如果初始化以内联形式的所有静态数据，并且没有显式静态构造函数声明，添加 C# 和 Visual Basic 编译器`beforefieldinit`到 MSIL 类定义的标志。 编译器还会添加包含静态初始化代码的私有静态构造函数。 保证此专用的静态构造函数运行之前访问类型的任何静态字段。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突初始化所有静态数据时它声明并移除静态构造函数。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="related-rules"></a>相关的规则
 [CA1810：以内联方式初始化引用类型的静态字段](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)