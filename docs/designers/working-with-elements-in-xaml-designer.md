---
title: Working with elements in XAML Designer
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: a29690bf-f212-4ac6-a77a-adc53d14102e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 97063229e2ba72263975247b71686492ee8c64f6
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44279656"
---
# <a name="working-with-elements-in-xaml-designer"></a>Working with elements in XAML Designer
可以使用 XAML 代码或 XAML 设计器向你的应用程序添加控件、布局和形状等元素。 本主题介绍如何在 Visual Studio 或 Blend for Visual Studio 中使用 XAML 设计器中的元素。

## <a name="adding-an-element-to-a-layout"></a>将元素添加到布局
 布局是调整元素在 UI 中的大小和位置的过程。 若要放置可视元素，必须将这些元素置于布局[面板](/uwp/api/Windows.UI.Xaml.Controls.Panel)中。 `Panel` 具有一个子属性，该子属性是 [FrameworkElement](/uwp/api/Windows.UI.Xaml.FrameworkElement) 类型的集合。 可使用各种 `Panel` 子元素（如 [Canvas](/uwp/api/Windows.UI.Xaml.Controls.Canvas)[StackPanel](/uwp/api/Windows.UI.Xaml.Controls.StackPanel) 和 [Grid](/uwp/api/Windows.UI.Xaml.Controls.Grid)）来充当布局容器以及在页面上放置和排列元素。

 默认情况下，`Grid` 面板用作页面或窗体中的顶级布局容器。 可以添加布局面板、控件或顶级页面布局中的其他元素。

#### <a name="to-add-an-element-to-a-layout"></a>将元素添加到布局的步骤

-   在 XAML 设计器中，执行以下操作：

    -   双击“工具箱”的某个元素（或选择“工具箱”中的某个元素，然后按 Enter）。

    -   将元素从“工具箱”拖到美工板 。

    -   在“工具箱”中，选择一种绘制工具（例如，[椭圆形](/uwp/api/Windows.UI.Xaml.Shapes.Ellipse)或[矩形](/uwp/api/Windows.UI.Xaml.Shapes.Rectangle)），然后在活动面板上绘制元素。

## <a name="changing-the-layering-order-of-elements"></a>更改元素的分层顺序
 当 XAML 设计器中的美工板上有两个元素时，其中一个元素将以分层顺序显示于另一个元素之前。 文档大纲窗口中的元素列表底部是最靠前的元素（除了在设置了元素的 ZIndex 属性时）。 当将元素插入页面、窗体或布局容器时，元素将自动放置在活动容器元素中的其他元素之前。 若要更改元素的顺序，可使用“排序”命令，或将元素拖入文档大纲窗口的对象树中。

#### <a name="to-change-the-layering-order"></a>更改分层顺序的步骤

-   执行下列操作之一：

    -   在“文档大纲”窗口中，向上或向下拖动元素，以创建所需的分层顺序。

    -   右键单击文档大纲窗口中或美工板上想要更改其分层顺序的元素，指向“顺序”，然后单击以下选项之一：

        -   “置于顶层”：将元素一直移动到顺序的顶层。

        -   “上移一层”，使元素在顺序中上移一层。

        -   “下移一层”，使元素在顺序中下移一层。

        -   “置于底层”：将元素一直移到顺序的底层。

     更改属性窗口中“布局”部分的“ZIndex”属性。 对于重叠元素，“ZIndex”属性优先于文档大纲窗口中显示的元素的顺序。 当元素重叠时，“ZIndex”值较大的元素将显示在前面。

## <a name="changing-the-alignment-of-an-element"></a>更改元素的对齐方式
 可以通过使用菜单命令或通过将元素拖到对齐线，对齐美工板中的元素。

 对齐线是一个视觉提示，有助于将某个元素相对于应用中的其他元素进行对齐。

#### <a name="to-align-two-or-more-elements-by-using-menu-commands"></a>使用菜单命令对齐两个或多个元素的步骤

1.  选择想要对齐的元素。 可以通过按住 Ctrl 键的同时选择元素来选择多个元素。

2.  在属性窗口中“布局”部分的“HorizontalAlignment”下，选择以下属性之一：“左”、“中心”、“右”或“拉伸”。

3.  在属性窗口中，在“布局”部分的“VerticalAlignment”下，选择以下属性之一：“顶部”、“中心”、“底部”或“拉伸” , 。

#### <a name="to-align-two-or-more-elements-by-using-snaplines"></a>使用对齐线对齐两个或多个元素的步骤

-   在 XAML 设计器中，在至少包含有两个元素的布局中拖动元素或调整一个元素的大小，以便其边缘与另一个元素对齐。

     当边缘对齐时，将显示“对齐边界”以指示对齐方式。 对齐边界是红色的虚线。 仅当启用了“对齐线对齐”  时，才会显示对齐边界。 有关显示对齐边界的美工板图示，请参阅[使用 XAML 设计器创建 UI](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)。

## <a name="changing-an-elements-margins"></a>更改元素的边距
 XAML 设计器中的边距决定了美工板上元素周围的空白空间量。 例如，边距指定了元素外边缘与包含该元素的 `Grid` 面板的边界之间的空间量。 边距还指定包含于 `StackPanel` 中的元素之间的空间量。

#### <a name="to-change-an-elements-margins-in-the-properties-window"></a>在“属性”窗口中更改元素边距的步骤

1.  选择想要更改边距的元素。

2.  在属性窗口中的“布局”下，更改任何“边距”属性（“顶部”、“左”、“右”或“底部”）的值（以像素为单位或与设备无关的单位，大约 1/96 英寸）。

#### <a name="to-change-an-elements-margins-in-the-artboard"></a>更改美工板中元素边距的步骤

-   若要更改元素相对于其布局容器的边距，请在元素处于选中状态且位于布局容器内时，单击美工板中元素周围出现的“边距装饰器”。 有关显示边距装饰器的图示，请参阅[使用 XAML 设计器创建 UI](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)。

     如果边距装饰器已打开，呈垂直或水平时，则未设置该边距。 如果边距装饰器已关闭，则已设置该边距。

     打开边距装饰器但未设置相反的边距时，将根据元素在美工板中的位置将相反的边距设置为正确的值。 对于相反的边距（如“左侧”和“右侧”边距），将始终至少设置一个属性。

    > [!IMPORTANT]
    >  置于某些布局容器中的元素（如 <xref:Windows.UI.Xaml.Controls.Canvas>）没有边距装饰器。 放置于 <xref:Windows.UI.Xaml.Controls.StackPanel> 中的元素有用于左边距和右边距或顶部和底部边距的边距装饰器，具体取决于 `StackPanel` 的方向。

## <a name="grouping-and-ungrouping-elements"></a>分组和取消分组元素
 对 XAML 设计器中的两个或多个元素进行分组，可创建新的布局容器，并将这些元素置于该容器中。 将两个或多个元素一起置于一个布局容器，让你可轻松地选择、移动和转换组，似乎该组中的元素是一个元素一样。 分组在某种程度上对于标识彼此相关的元素也很有用，如组成导航元素的按钮。 当对元素进行取消分组时，只需删除包含这些元素的布局容器。

#### <a name="to-group-elements-into-a-new-layout-container"></a>将元素分组到一个新布局容器的步骤

1.  选择想要分组的元素。 （若要选择多个元素，请在按住 Ctrl 键的同时单击这些元素。）

2.  右键单击选定的元素，指向“分组”，然后单击想要在其中放置该组的布局容器的类型。

    > [!TIP]
    >  如果选择 <xref:Windows.UI.Xaml.Controls.Viewbox><xref:Windows.UI.Xaml.Controls.Border>, 或 <xref:Windows.UI.Xaml.Controls.ScrollViewer> 来分组元素，则元素将被放置于 <xref:Windows.UI.Xaml.Controls.Viewbox>、<xref:Windows.UI.Xaml.Controls.Border> 或 <xref:Windows.UI.Xaml.Controls.ScrollViewer> 内的一个新 <xref:Windows.UI.Xaml.Controls.Grid> 面板中。 如果在这些布局容器的其中之一取消分组，则仅将删除 <xref:Windows.UI.Xaml.Controls.Viewbox><xref:Windows.UI.Xaml.Controls.Border> 或 <xref:Windows.UI.Xaml.Controls.ScrollViewer>，而将保留 <xref:Windows.UI.Xaml.Controls.Grid> 面板。 若要删除 `Grid` 面板，请再次取消分组该元素。

#### <a name="to-ungroup-elements-and-delete-the-layout"></a>对元素进行取消分组并删除布局的步骤

-   右键单击想要取消分组的组并单击“取消分组” 。

 还可以通过右键单击文档大纲窗口中选定的项，然后单击“分组”或“取消分组”，以对元素进行分组或取消分组 。

## <a name="resetting-the-element-layout"></a>重置元素布局
 可以通过使用“布局重置”命令还原某个元素特定布局属性的默认值。 通过使用此命令，可以单独或一起重置边距、对齐方式、宽度、高度和元素大小。

#### <a name="to-reset-the-element-layout"></a>重置元素布局的步骤

-   在文档大纲窗口或美工板中，右键单击该元素，选择“布局” > “重置 PropertyName”，其中 PropertyName 是想要重置的属性（或者选择“布局” > “全部重置”，重置该元素的所有布局属性）。

## <a name="see-also"></a>请参阅

- [使用 XAML 设计器创建 UI](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)
