---
lab:
  title: 实验室 2：如何生成画布应用
  module: 'Module 3: Get started with Power Apps'
---

# <a name="lab-2-how-to-build-a-canvas-app"></a>实验室 2：如何生成画布应用

## <a name="scenario"></a>方案

Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Currently, campus administration is leveraging an Excel spreadsheet to track visitor registration. They would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

在整个课程中，你将生成应用程序并执行自动化，以使 Bellows College 的管理和安全人员可以管理和控制校园建筑的出入情况。

## <a name="high-level-lab-steps"></a>概要实验室步骤

我们将按照以下概要设计画布应用：

- 通过 Visit 表中的数据创建画布应用

- 配置访客在浏览屏幕上的显示方式

- 对应用进行一些基本更改

- 测试应用功能

## <a name="prerequisites"></a>先决条件

- 完成“模块 0 实验室 0 - 验证实验室环境”
- 完成“模块 2 实验室 1 - 数据建模”

## <a name="exercise-1-create-visits-canvas-app"></a>练习 1：创建访问画布应用

目的：在本练习中，你将通过连接之前创建的 Visits 表来创建画布应用。

### <a name="task-1-create-the-visits-app"></a>任务 \#1：创建 Visits 应用

1.  Navigate to <ph id="ph1">&lt;https://make.powerapps.com&gt;</ph>. You may need to reauthenticate - click <bpt id="p1">**</bpt>Sign in<ept id="p1">**</ept> and follow instructions if needed.

2.  如果尚未选择“[我的初始] 练习”环境，请在右上角选择它。

3.  If necessary, click the <bpt id="p1">**</bpt>Home<ept id="p1">**</ept> icon on the left side of the screen. Under the <bpt id="p1">**</bpt>Start from<ept id="p1">**</ept> section, select <bpt id="p2">**</bpt>Dataverse<ept id="p2">**</ept>.

4.  选择 Dataverse 连接。

    > **注意：** *如果 Dataverse 连接不存在，请执行以下操作：*
    > - 选择“新建连接”
    > - 找到“Microsoft Dataverse”
    > - 单击“创建” 

5.  查找并选择在上一个实验室中创建的 Visits 表。

6.  选择右下角的“连接”按钮。

7.  创建应用后，在“欢迎使用 Power Apps Studio”屏幕上，选中“不再向我显示此内容”框，然后选择“跳过” 。

8.  创建完成后，它应如下图所示。

![通过访问数据创建的画布应用。](media/2-canvas-app-from-data.png)

9. Bellows College 是一所教育机构，校园内有多座建筑。

10. 通过选择屏幕右上角的 X 关闭应用预览。

目前，校园访问记录在纸质日报上。

### <a name="task-2-modify-and-theme-the-newly-created-app"></a>任务 \#2：修改新创建的应用并为其添加主题

在此任务中，你将在应用的三个屏幕（“浏览”、“详细信息”和“编辑”）上分别自定义标题文本并更改应用主题。

1.  无法始终如一地捕获信息，也无法收集和分析有关整个校园的访问数据。

1.  在屏幕右侧的“属性”选项卡下，将“文本”控件属性更新为“Bellows College 访客” 。

1. 在属性中，将“字体大小”更改为“24” 。

1.  单击屏幕的空白背景以在“浏览”屏幕上查看更新后的文本。

1.  使用左侧导航中的树状视图，选择“DetailScreen1”。

1.  选择屏幕上的“访问”标签。

1.  在屏幕右侧的“属性”选项卡下，将“文本”控件属性更新为“访客详细信息” 。

1.  单击屏幕的空白背景以在“详细信息”屏幕上查看更新后的文本。

1.  使用左侧导航中的树状视图，选择“EditScreen1”（可能需要向下滚动才能在树状视图上看到此选项）。

1.  选择屏幕上的“访问”标签。

1.  在屏幕右侧的“属性”选项卡下，将“文本”控件属性中的文本 Table1 替换为“编辑详细信息” 。

1.  单击屏幕的空白背景以在“编辑”屏幕上查看更新后的文本。

1. 使用左侧导航中的树状视图，选择“BrowseScreen1”。

1. 在命令工具栏上，选择“主题”按钮，然后从显示的列表中选择“红色”主题颜色 。

### <a name="task-3-test-your-visits-app"></a>任务 \#3：测试 Visits 应用

在此任务中，你将测试新应用。

1.  在应用程序设计器中打开应用程序后，选择“文件”，将该应用的名称更新为“Visits App”，然后选择“保存”  。

2.  选择后退箭头返回到应用。

3.  使用左侧的导航，选择“BrowseScreen1”。

4.  In the app designer, select the <bpt id="p1">**</bpt>preview the app<ept id="p1">**</ept> button (Play icon) on the command bar. <bpt id="p1">*</bpt>(You can also preview the app by pressing F5 on your keyboard.)<ept id="p1">*</ept>

4.  应用打开后，在“搜索项”字段中输入文本“Maria
    ”（请注意，库中的项如何根据在搜索字段中键入的内容进行筛选） 。

5.  目前，校园管理部门正在利用 Excel 电子表格来跟踪访客登记情况。

6.  若要编辑记录，请选择应用右上角的“铅笔”图标。

7.  可以在此处编辑“访问名称”，然后单击右上角的复选标记图标保存更改。

8.  在屏幕右上角，单击 X 图标以返回到画布应用编辑器。

他们希望对其访客登记系统进行现代化改造。在该系统中，由安全人员控制对建筑物的访问，所有访问都必须由主办人预先登记和记录。

## <a name="challenges"></a>挑战

- 将以下列添加到 DetailScreen1 和 EditScreen1 中的表单：实际开始时间、实际结束时间、代码、计划开始时间和计划结束时间