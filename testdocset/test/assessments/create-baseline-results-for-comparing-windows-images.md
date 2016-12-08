---
title: "创建基线结果"
description: "创建基线结果"
MSHAttr:
- PreferredSiteName:MSDN
- PreferredLib:/library/windows/hardware
ms.assetid: 4aa70366-047d-4381-b592-fe6e66696a9f
ms.prod: W10
ms.mktglfcycl: plan
ms.sitesec: msdn
ms.openlocfilehash: 4ee92c55b96572f529555bc0c886840ef88528b6
ms.sourcegitcommit: d33e870dc4850bf0ea47fdae0d163b04c1c90f15
translationtype: MT
---
# <a name="create-baseline-results"></a>创建基线结果


本主题介绍如何评估已安装未修改的 Windows 映像的计算机，然后将结果保存到共享位置或外部驱动器。 然后，本主题介绍如何评估了自定义的 Windows 映像 （或第三方软件和硬件） 的计算机，并从同一台计算机或另一台计算机对其他结果比较的结果。

我们的原始设备制造商 (Oem) 推荐这种方案和系统构建者需要建立基线评估结果，若要确定自定义对特定硬件配置的系统性能的影响。

有关如何使用 Windows 评估控制台来评估计算机的一般信息，请参阅[Windows 评估控制台的分步指南](windows-assessment-console-step-by-step-guide.md)。

**若要创建基线结果**

1.  在裸机参考计算机上安装 Windows 8 或 Windows 10 干净 （或非自定义） 版本。 裸机参考计算机没有操作系统或安装软件，并且硬件可表示特定类型的计算机制造或销售的计算机模型。

2.  当 Windows 安装完成后时，从下载并安装 Windows 评估 Toolkit 的 Windows 评估和部署工具包 (Windows ADK)。

3.  单击**开始**，键入**评估控制台**，然后单击**控制台窗口评估**。 评估 Windows 控制台打开。

4.  在 Windows 评估控制台中，从**主页**页中选择作业，选择单一的评估，或创建新的作业。 例如，可以创建新的作业，并使用制造和部署模板来识别问题驱动程序和设备，包括徽标要求，并确定在最终用户首次启动体验的延迟。

5.  评估 Windows 控制台右上角，单击**选项**，然后单击**配置结果**。

6.  在**评估结果库位置**对话框中，单击**添加**。 **在评估结果中包括文件夹**的对话框将打开。

7.  选择您可以在这里存储为便于稍后进行比较，例如，网络共享上，评估结果，然后单击**包含文件夹**的位置。

    **重要**  
    如果您打算在此参考计算机上重新安装 Windows，必须将结果保存到网络共享。 如果重新映像的引用的计算机，结果被覆盖，并且不会可供比较，如果它们存储在本地。

     

8.  选择默认结果位置 (**%userprofile%\\文档\\评估结果**)，然后单击**删除**。

9.  验证新的保存位置显示在列表中为默认保存位置，然后再单击**确定**。

10. 单击**运行**以启动计算机评估。

11. 在该作业完成后，结果显示在 Windows 评估控制台中**查看结果**页上。

12. 在**查看结果**页上，单击**配置作业**。

13. 在**配置作业**页面的右下角，单击**包**。

14. 在**包作业**对话框中，输入注释，可帮助您识别您的作业时选择要打开并查看结果。

15. 在**包路径**框中，键入要用来存储作业包的位置。 此位置应该是可移动媒体，如 USB 闪存驱动器。

16. 在**结果路径**框中，键入要用来存储结果的位置。 默认情况下，这是相对路径，\\在同一位置运行该作业时结果文件夹。

17. 单击**确定**。

**若要在自定义 Windows 映像上运行同一个作业**

1.  自定义 Windows 映像并将其安装在相同的参考计算机上。 有关 Windows 自定义和部署的详细信息，请参阅[部署和图像处理工具技术参考](http://go.microsoft.com/fwlink/?LinkId=214548)。

2.  Windows 安装完成后，打开包装的作业的存储位置的文件夹，将文件夹复制到本地计算机，然后双击运行您在上一个过程中运行的相同作业的**RunJob.cmd**文件。

    **重要**  
    从网络共享位置，但为获得最佳效果，从减少运行时失败的本地计算机中运行作业或由网络引起的性能问题，可以运行打包的作业

     

3.  在该作业完成后，结果显示在控制台窗口中评估。

**比较结果**

1.  在 Windows 评估控制台中，单击**选项**，然后单击**打开结果**。

2.  在**选择的结果**窗口中，单击**浏览**。

3.  文件资源管理器中浏览到结果文件存储的位置，选择所需的.xml 文件，然后单击**打开**Windows 评估控制台中查看结果。

    当您选择多个结果文件时，结果出现并排放置在 Windows 评估控制台，以便您可以轻松地比较基准结果为所有后面的结果。

基于结果的比较，您可以对自定义图像的改进。 可以继续运行，审查并修订进程，直到获得所需结果。

## <a name="related-topics"></a>相关的主题


[评估服务](assessments.md)

[评估 Windows 控制台](windows-assessment-console.md)

[评估 Windows 控制台的常见方案](windows-assessment-console-common-scenarios.md)

 

 






