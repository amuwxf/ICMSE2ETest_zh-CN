---
title: "Windows 性能分析器的逐步式指南"
description: "Windows 性能分析器的逐步式指南"
MSHAttr:
- PreferredSiteName:MSDN
- PreferredLib:/library/windows/hardware
ms.assetid: 53b7dfe1-f39b-41b4-a7ff-6040f1ab318c
ms.prod: W10
ms.mktglfcycl: operate
ms.sitesec: msdn
ms.openlocfilehash: 8ad0e8f038f19c047dc2a9b20939c249667ac301
ms.sourcegitcommit: d33e870dc4850bf0ea47fdae0d163b04c1c90f15
translationtype: MT
---
# <a name="windows-performance-analyzer-step-by-step-guide"></a>Windows 性能分析器的逐步式指南


本部分介绍的 Windows 性能分析器 (WPA) 用户界面 (UI) 功能的详细的演练。

## <a name="step-1-opening-an-etl-file"></a>步骤 1︰ 打开 ETL 文件


WPA 可以打开使用 Windows 性能记录器 (WPR) 或 Xperf 创建任何事件跟踪日志 (ETL) 文件。

**在 WPA 打开 ETL 文件**

1.  在**文件**菜单上，单击**打开**。

2.  如果您 ETL 文件保存到非默认位置，则导航到该位置。

    默认情况下，WPR ETL 将文件保存在您的文档\\WPR 文件的文件夹。

3.  选择所需的文件，然后单击**打开**。

您还可以从使用评估平台创建的评估的结果页打开 WPA。

**若要打开 WPA 从评估**

-   在运行作业后，单击查看结果页上的**问题**窗格中的**WPA 深入分析**链接。 您可能需要展开要查看此链接的问题。

## <a name="step-2-selecting-graphs"></a>步骤 2︰ 选择关系图


在图形浏览器窗口中记录的所有可用图表是可见的。 通过单击小三角形展开所有节点。 然后，将图形拖到**分析**选项卡以查看关系图和它相关联的数据的表的完整版本。 也可以双击**分析**选项卡上打开该关系图。

通过使用版式图标图标题栏的右侧，您可以选择要查看只图仅模拟运算表，或两者。

## <a name="step-3-selecting-a-time-interval"></a>步骤 3︰ 选择时间间隔


在**分析**选项卡上，可以通过在关系图中的节间水平拖动指针选择时间间隔。 在时间轴底部的选项卡将应用于在选项卡上的所有图形。

## <a name="step-4-zooming-in-on-a-time-interval"></a>步骤 4︰ 在某个时间间隔内进行放大


您选择的时间间隔之后，您可以进行放大以展开该时间间隔对整个**分析**选项卡的宽度。 若要执行此操作，间隔，请用鼠标右键单击，然后选择**缩放到所选的时间范围**。 可以多次重复此步骤，以很小的时间间隔的非常精细的细节，请参阅。

在**分析**选项卡上的所有图形都使用的同一时间线。 因此，此操作将展开所有这些关系图的同一个时间间隔。

## <a name="step-5-highlighting-a-selected-time-interval"></a>步骤 5︰ 突出显示所选的时间间隔


您选择的时间间隔之后，您可以突出显示在**分析**选项卡上的所有图形和图形浏览器窗口中的时间间隔。 若要执行此操作，间隔，请用鼠标右键单击，然后选择**突出显示所选内容**。 此操作会冻结而不考虑在其他地方单击所选内容。 若要清除所选内容，间隔，请用鼠标右键单击，然后选择**清除所选内容**。

## <a name="step-6-customizing-a-data-table"></a>第 6 步︰ 自定义数据表格


可以将列拖动到数据表中的任意位置。 对任何列进行排序依据的列，您可以单击表格标题。 您还可以单击表格标题再次进行反向排序。 更改数据表时，所做的更改也都会在关系图的**图例**控件。 表的数据图例列匹配关系图的**图例**控件。

选择要显示哪些列，可以自定义数据的表。 若要打开**列选择器**框中，用鼠标右键单击表格标题。 然后可以单独选择列或创建或应用预设要显示的列的组合。

数据表是数据透视表。 金色的垂直栏左侧的列是键。 竖线金色和蓝色竖线之间的列是数据列。 如果看不到金色的竖线，向右滚动。

您可以拖动任意列左侧的垂直的黄金条使其键。 也可以拖动某些列右侧的垂直的蓝色条块以使它们的关系图元素。

可以通过右键单击以显示垂直灰色冻结条冻结小选定的列。 然后，滚动条将滚动之间冻结条列之间。 您可以拖动的冻结栏可以包含任意数量的列。

## <a name="step-7-opening-a-new-analysis-tab"></a>第 7 步︰ 打开一个新的分析选项卡


所有图形和**分析**选项卡上的表共享同一个时间轴，放大和缩小在一起显示。 如果您想要在不同的时间线查看某些图表，您可以打开一个附加的**分析**选项卡。 要做到这一点，在**窗口**菜单上，单击**新分析视图**，然后将所需的图形拖动到新建选项卡。

## <a name="step-8-opening-or-closing-windows"></a>步骤 8︰ 打开或关闭窗口


在**窗口**菜单中，选择您想要打开或关闭 windows。

## <a name="step-9-creating-and-applying-a-view-profile"></a>第 9 步︰ 创建并应用一个视图的配置文件


设置布局的方式的需要，您可以创建重现当前布局或者每次查看配置文件打开 WPA 后或只为特定类型的记录。 在**配置文件**菜单上，单击**导出**以创建视图的配置文件，单击**应用**以应用您以前创建的视图配置文件或单击**保存启动配置文件**以查看当前布局视图每次您打开 WPA。

## <a name="step-10-searching-and-filtering"></a>第 10 步︰ 搜索和筛选


您可以通过右击关系图**图例**控件并启用或禁用所需的项目筛选图表和它相关联的数据的表中的数据。 若要只选择的一行或多行显示，数据表中，用鼠标右键单击，然后单击**到选定内容筛选**。

若要选择要显示在数据表中的列，用鼠标右键单击表格标题，然后选择或清除**列选择器**框中的列。

若要在数据表中搜索文本，表中，用鼠标右键单击，然后选择**查找**、**查找下一个**，或**查找下一个**。

## <a name="step-11-setting-user-preferences"></a>第 11 步︰ 设置用户首选项


目前，您可以设置 WPA 加载符号，并可以设置符号路径。 这些选项是在**跟踪**菜单上可用。

## <a name="step-12-using-the-diagnostic-console"></a>第 12 步︰ 使用诊断控制台


此窗口列出了在分析工作流中发生的异常。 您可以诊断符号解码问题通过此控制台。

## <a name="step-13-viewing-assessment-analysis-and-issue-details"></a>步骤 13︰ 查看评估分析和问题详细信息


当您打开 WPA 从评估控制台中运行，并提供更多的分析评估时，评估发现的问题将出现在**问题**窗口。 如果您单击其中一个这样的问题，详细信息和建议的解决方案都将出现在下**问题详细信息**的**分析**选项卡中。

此外可以通过在问题窗口顶部的搜索选项来搜索问题的列表。 有关此功能的详细信息可在[问题窗口](issues-window.md)。

## <a name="related-topics"></a>相关的主题


[WPA 快速入门指南](wpa-quick-start-guide.md)

 

 






