---
lab:
  title: 实验室 3：如何构建模型驱动的应用
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# 实验室 3：如何构建模型驱动的应用

**WWL 租户 - 使用条款** 如果在讲师引导式培训过程中向你提供租户，请注意，提供租户的目的是支持讲师引导式培训中的动手实验室。 租户不应共享或用于动手实验室以外的用途。 本课程使用的租户为试用租户，课程结束后将无法使用或访问，并且不符合延期条件。 租户不得转换为付费订阅。 在本课程中获得的租户仍然是 Microsoft Corporation 的财产，我们保留随时获取访问权限和收回的权利。 

## 场景

Bellows College 是一所教育机构，拥有多个校园并开设有多门课程。 许多 Bellows College 的讲师和管理员都需要参加活动，并购买项目。 从以往看来，跟踪这些费用并非易事。

校园管理层希望通过向员工提供一种报告费用的数字方式，以实现费用报告系统的现代化。

在整个课程中，你将构建应用程序并执行自动化，使 Bellows College 员工能够管理费用。

## 概要实验室步骤

作为创建模型驱动应用的一部分，你将完成以下操作：

- 新建一个名为“员工支出管理”的模型驱动应用。

- 编辑应用导航以引用所需的表。

- 自定义应用所需表的表单和视图。

我们将使用以下组件：

- **视图**：视图允许用户显示表单表中的现有数据。

- **窗体**：用户在此处创建/更新表中的新记录。

两者都将集成到模型驱动应用中，以提供更好的用户体验。

### 先决条件

- 完成“模块 1 实验室 0 - 验证实验室环境”****

**开始前要考虑的事项**

- 应该进行哪些更改以改善用户体验？

- 基于我们生成的数据模型，我们应该在模型驱动应用中包括哪些内容？

- 可以在模型驱动应用的网站图上进行哪些自定义？

## 练习 1：自定义视图和表单

**目的：** 在本练习中，你将自定义将在模型驱动应用中使用的自定义创建表的视图和表单。

### 任务 #1：编辑“支出报表”表单

1. 如果尚未登录，请登录到 https://make.powerapps.com

1. 选择右上角的“**Dev One**”环境（如果尚未选择）。

1. 使用左侧的导航，选择“表”，然后打开“支出报表”表。********

    >如果未看到“支出报表”表，请确保你位于正确的环境中（步骤 2）。

1. 在“数据体验”部分下，选择“窗体”，然后打开窗体类型为“Main”的信息窗体   。 （重要提示：请确保选择窗体类型为“Main”的窗体。）

    >**重要提示：** 由于默认情况下所有表单都称为“信息”，因此请确保验证所选表单的表单类型为“主要”而不是其他类型。 表单默认有两个字段：“名称”和“所有者”。

1. 在屏幕右侧的“**属性**”面板上，选择“**显示名称**”字段，并将其更改为 `Report Information`。

1. 从左侧导航窗格中选择“表列”，在“所有者”字段下添加以下字段，方法是将列拖动到窗体或单击列名称：

    - **描述**

    - **报表用途**

    - **报表截止日期**

    - **报表总金额**

1. 将**状态描述**列拖放到窗体标头中。

    >标题是表单的右上角区域。 你可能需要折叠屏幕右侧的“属性”面板才能看到表单上的字段。

1. 选择“所有者”字段。 在“属性”面板中将“**标签**”更改为 `Requestor`。

1. 选择右上角的“保存并发布”按钮，等待直到保存并发布完成。

1. 如果在新的浏览器标签页或窗口中打开了“编辑”视图，请将其关闭。 否则，选择屏幕左上方的“🡠 返回”。 你现在应该回到了“支出报表”表窗体。****

1. 使用左上角的痕迹导航（“表” > “支出报表” > “窗体”）。************ 选择“支出报表”以返回到“支出报表”的表属性屏幕。********

## 任务 #2：编辑“活动支出报表”视图

在此任务中，我们将修改默认的“活动支出报表”视图，并为今天到期的支出报表新建视图。

1. 在“数据体验”部分下，选择“视图”，然后打开“活动支出报表”视图************。

1. 通过单击或拖放字段，将以下字段添加到视图中：

    - **报表用途**

    - **报表截止日期**

    - **报表总金额**

1. 选择“创建时间”列上的下拉菜单，然后选择“删除” 。 现在将从视图中删除“创建时间”字段。

1. 根据需要重设各个列的宽度以适应数据。

1. 在“排序依据...”下， 选择“X”移除“**报表名称**”，并改为选择“**报表总金额**”。

1. 选择“**报表总金额**”，将排序顺序更改为“**从大到小**”。

1. 选择右上角的“保存并发布”按钮，等待直到发布完成。

### 任务 #3：为今天到期的报表新建视图

现在我们将克隆视图，为今天到期的报表创建一个新视图。

>    **重要提示：** 请确保不要关闭“活动支出报表”视图，因为我们将利用它创建“今天到期的报表”视图。

1. 选择“另存为”。

1. 将“名称”更改为 `Expense Reports Due Today`，然后选择“保存” 。

1. 在“属性”面板中选择“编辑筛选器”。

1. 选择“+ 添加”，然后选择“添加行” 。

1. 选择“报表到期时间”作为字段，然后在下拉菜单中将“等于”更改为“今天”作为条件************。

1. 选择 “状态”行上的“... 更多命令”，然后选择“删除”以删除该筛选条件  。

1. 选择“**确定**”以保存该条件。 该视图现已经过筛选，仅显示“报表到期日期”为今天的记录。****

1. 向视图添加“报销金额”字段。****

1. 选择右上角的“保存并发布”按钮，等待直到发布完成。

## 练习 2：创建模型驱动应用

目的：在本练习中，你将创建模型驱动应用、自定义站点地图并测试该应用。

为简单起见和节约时间，我们不会讨论此实验室中的全部“报表支出”列。

### 任务 #1：创建应用

1. 如果尚未登录，请登录到 https://make.powerapps.com

1. 选择右上角的“Dev One”环境（如果尚未选择）。****

1. 在左侧导航上选择**解决方案**。

1. 打开**支出管理**解决方案。

1. 依次选择“**+ 新建**”、“**应用**”和“**模型驱动应用**”。

1. 输入 `Employee Expense Management` 作为名称，然后选择“创建” 。

1. 加载新的模型驱动应用程序后，选择“**+ 添加页面**”按钮。

1. 在“**添加页面**”屏幕上，选择“**Dataverse 表**”。

1. 选择下表：

    - 支出报表

    - 联系人

1. 拥有这两个表后，选择“添加”。

1. 使用屏幕左侧的导航图标，选择“导航”。

1. 在导航窗格上，选择下方显示“导航”的“新建组”。 可能需要展开左侧的菜单。

1. 在屏幕右侧的“**显示选项**”部分，将“**标题**”属性更改为`Reports`。

1. 选择“保存”，然后等待更改保存完毕。

1. “保存”完成后，选择“发布”按钮发布所做的更改 。 等待发布完成。

## 任务 #2：测试应用

**启动应用程序**

1. 选择“播放”按钮，模型驱动应用将在新选项卡中加载。

**创建新联系人**

1. 应用应该会打开“我的可用联系人”视图。 否则，请选择左侧导航中的“联系人”****。

1. 从命令栏中选择“+ 新建”。

1. 在“**名字**”中输入 `John`，并在“**姓氏**”中输入 `Doe`。

1. 在“电子邮件”中输入你的个人电子邮件。 这将在将来的实验室中使用，你将收到一封电子邮件。

1. 选择**保存并关闭**。

1. 现在应该可以在“我的可用联系人”视图中看到已创建的联系人。

**创建新的支出报表**

1. 从左侧导航（也称为站点地图）中，选择“支出报表”****。

1. 选择“+ 新建”  。

1. 按照如下所示输入字段信息：

    - **报表名称**：`New Test Report`

    - **报表用途**：选择“会议”****

    - **报表截止日期**：选择今天的日期

1. 选择**保存并关闭**。 此操作将会创建新的测试报表，你应该能够在“活动支出报表”视图中看到它。****

1. 使用“活动支出报表”旁边的下拉列表，将视图更改为“今天到期的支出报表”。******** 

1. 可以添加更多测试记录。

正在运行的模型驱动应用看上去大致如下图所示：

![刚刚创建的模型驱动应用的屏幕截图。](media/lab-3-create-a-model-app-01.png)

祝贺你！ 你已创建并配置了第一个模型驱动的应用。
