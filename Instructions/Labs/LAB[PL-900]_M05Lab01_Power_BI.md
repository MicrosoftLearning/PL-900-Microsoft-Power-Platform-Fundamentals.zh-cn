---
lab:
  title: 实验室 5：如何生成简单仪表板
  module: 'Module 5: Get Started with Power BI'
ms.openlocfilehash: 1df94fcda0e59554c10ed772314e5138936b73a8
ms.sourcegitcommit: 50e1a519a6893e02a4a0c2c6bef93cafd2513611
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "147125733"
---
# <a name="module-5-get-started-with-power-bi"></a>模块 5：Power BI 入门
## <a name="lab-how-to-build-a-simple-dashboard"></a>实验室：如何生成简单仪表板

# <a name="scenario"></a>方案

Bellows College 是一所教育机构，校园内有多座建筑。 当前，校园访客被记录在纸质日记中。 无法始终如一地捕获信息，也无法收集和分析有关整个校园的访问数据。

校园管理部门希望对其访客登记系统进行现代化改造。在该系统中，由安全人员控制对建筑物的访问，所有访问都必须由主办人预先登记和记录。

在整个课程中，你将生成应用程序并执行自动化，以使 Bellows College 的管理和安全人员可以管理和控制校园建筑的出入情况。

在本实验室中，你将构建一个 Power BI 仪表板，以可视化方式显示有关校园访问的数据。

# <a name="high-level-lab-steps"></a>概要实验室步骤

我们将按照以下步骤设计和创建 Power BI 仪表板：

-   连接到 Dataverse

-   转换数据以包括对相关行（查找）的用户友好描述

-   创建并发布包含各种校园访问信息可视化效果的报表

-   利用用户自然语言查询来生成额外的可视化效果

-   生成 Power BI 仪表板的移动视图

## <a name="prerequisites"></a>先决条件

-   完成“模块 0 实验室 0 - 验证实验室环境”

-   完成“模块 2 实验室 1 - Microsoft Dataverse 简介”

## <a name="things-to-consider-before-you-begin"></a>开始前要考虑的事项

-   报告的目标受众是谁？

-   受众将如何使用报告？ 典型的设备？ 位置？

-   你是否有足够的数据进行可视化？

-   可以使用哪些可能的特征来分析访问数据？

# <a name="exercise-1-create-power-bi-report"></a>练习 \#1：创建 Power BI 报表

**目的：** 在本练习中，你将根据在上一个练习中使用的 Excel 电子表格的数据创建 Power BI 报表。

## <a name="task-1-prepare-power-bi-service"></a>任务 \#1：准备 Power BI 服务

1.  在计算机上下载并保存 [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix)。

2.  根据需要导航到 <https://app.powerbi.com/> 并登录。

3.  在屏幕的左下角，选择“获取数据”

4.  在“新建内容”部分的“文件”下选择“获取”按钮  。

5.  选择“本地文件”。

6.  找到并选择你之前下载的 visits.pbix 文件。

7.  数据加载完成后，选择 visits 报表（请注意，“类型”设置为“报表”）。 

8.  单击 **“编辑”** 。 如果“编辑”菜单项不可见，请单击“...”，然后选择“编辑”。  

现在，你已经设置了 Power BI 服务以用于你的实验室。 

## <a name="task-2-create-chart-and-time-visualizations"></a>任务 \#2：创建图表和时间可视化

1.  按“可视化效果”面板中的“饼图”图标插入图表 。

2.  按“字段”窗格中 bc_name 旁边的下拉箭头。 拖动“建筑”字段并将其放入“图例” 框。

3.  按“字段”窗格中 bc_Visit 旁边的下拉箭头。 将“访问”字段拖放到“值”框中 。

4.  使用角柄调整饼图的大小，以便所有图表组件均可见。

5.  单击饼图外的报表以取消选择它，然后选择“可视化效果”窗格中的堆积柱形图。

6.  按“字段”窗格中 bc_Visit 旁边的下拉箭头。 拖动“访问”字段并将其放入“Y 轴”目标框。

7.  拖动“开始”字段并将其放入“X 轴”目标框。

8.  在“可视化效果”窗格中，单击“年”和“季度”旁边的 x，只为轴留下“月”和“天”总计    。

9.  根据需要使用角柄调整图表大小。

10. 测试报告交互性：

    1.  在饼图上单击各种构建切片，并观察时间报告上的变化。

    2.  单击柱形图。 按向下箭头打开“向下钻取”模式（或右键单击图表，然后选择“向下钻取”），然后单击一列以向下钻取到下一个级别（天）。  
    
    3.  向上和向下钻取，选择时间柱形图上的各种条形，以观察饼图报告中的变化。

11. 按下“保存”以保存进行中的工作。

# <a name="exercise-2-create-power-bi-dashboard"></a>练习 \#2：创建 Power BI 仪表板

## <a name="task-1-create-power-bi-dashboard"></a>任务 \#1：创建 Power BI 仪表板

1.  打开上一个任务中生成的报表。

2.  在菜单上选择“固定到仪表板”。 根据布局，你可能需要按“...”以显示其他菜单项。

3.  在“固定到仪表板”提示上选择“新建仪表板” 。

4.  输入“校园管理”作为“仪表板名称”， 然后按“固定活动页”。

5.  依次选择顶部的“我的工作区”、“[你的姓氏] 校园管理”仪表板。

6.  弹出窗口将提示你仪表板已创建。 选择“转到仪表板”。

7.  测试显示的饼图和条形图的交互性。

## <a name="task-2-add-visualizations-using-natural-language"></a>任务 \#2：使用自然语言添加可视化

1.  在“校园管理”仪表板内，选择顶部的“提出与数据有关的问题”栏。

2.  输入问答区域中“按访问次数划分的建筑”。 将显示条形图。

3.  选择“固定视觉对象”。

4.  依次选择“现有仪表板”和“校园管理”仪表板，然后按“固定”  。

5.  单击“退出问答”。

“校园管理”仪表板上应会显示三个视觉对象。 可能需要向下滚动才能看到新的“问答”视觉对象。

你的仪表板应类似如下所示：

![](media/5-powerbi-result.png)
