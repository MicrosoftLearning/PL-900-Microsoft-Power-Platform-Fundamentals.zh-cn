---
lab:
  title: 实验室 4：如何构建自动解决方案
  module: 'Module 4: Get Started with Power Automate'
ms.openlocfilehash: 9b07c81fad82867bb54c2889687075fa7a463b81
ms.sourcegitcommit: 36c8fda9cdc6f448416d7000e38c1606bea87d2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2022
ms.locfileid: "144812942"
---
# <a name="module-4-get-started-with-power-automate"></a>模块 4：Power Automate 入门
## <a name="lab-how-to-build-an-automated-solution"></a>实验室：如何构建自动解决方案

## <a name="scenario"></a>方案

Bellows College 是一所教育机构，校园内有多座建筑。 当前，校园访客被记录在纸质日记中。 无法始终如一地捕获信息，也无法收集和分析有关整个校园的访问数据。

校园管理部门希望对其访客登记系统进行现代化改造。在该系统中，由安全人员控制对建筑物的访问，所有访问都必须由主办人预先登记和记录。

在整个课程中，你将生成应用程序并执行自动化，以使 Bellows College 的管理和安全人员可以管理和控制校园建筑的出入情况。

在此实验室中，你将创建一个 Power Automate 流，以在计划访问时向访客发送电子邮件。

# <a name="high-level-lab-steps"></a>概要实验室步骤

以下已被确定为完成项目必须满足的要求：

-   计划访问时，需要通过电子邮件通知联系人。

## <a name="prerequisites"></a>先决条件

-   完成“模块 0 实验室 0 - 验证实验室环境”

-   完成“模块 2 实验室 1 - Microsoft Dataverse 简介”

-   创建了 John Doe 联系人并填充了个人电子邮件地址

# <a name="exercise-1-create-visit-notification-flow"></a>练习 \#1：创建访问通知流

**目的：** 在本练习中，你将创建一个实现要求的 Power Automate 流。 应向访客发送一封电子邮件，其中包含创建访问时分配给访问的唯一代码。

## <a name="task-1-create-a-flow"></a>任务 \#1：创建流

1.  导航到 <https://make.powerapps.com>。 你可能需要重新进行验证身份 - 单击“登录”并根据需要按照说明进行操作。

2.  如果尚未选择“[我的初始] 练习”环境，请在右上角选择它。

2.  在左侧导航栏中，选择“流”。

4.  如果出现提示，请选择“开始”。

5.  单击“新建流”，然后选择“自动化的云端流” 。

6.  为“流名称”输入“访问通知”。

7.  在“选择流的触发器”中，搜索 Dataverse 。

8.  选择触发器“添加、修改或删除行时”，然后单击“创建”。

9.  填充流的触发条件：

    1.  为“更改类型”选择“已添加”

    2.  为“表名称”选择“Visits” 

    3.  为“范围”选择“组织” 

    4.  在触发步骤上，单击省略号 (…)，然后单击“重命名” 。
        将此触发器重命名为“添加访问时”。 这是一个很好的习惯，这样你和其他流编辑可以理解步骤的目的，而不必深入研究细节。

## <a name="task-2-create-a-step-to-get-the-visitor-row"></a>任务 \#2：创建用于获取访客行的步骤

1.  选择“新建步骤”。 必须执行此步骤来检索访客信息，包括电子邮件地址。

2.  搜索“Dataverse”。

3.  选择“按 ID 获取行”操作。

4.  选择“Contacts”作为“表名称”

5.  选择“行 ID”字段。 请注意，此时会弹出一个窗口，用于选择“动态内容”或“表达式”。 

6.  在“行 ID”字段中，选择动态内容列表中的“访客(值)”。 在此步骤中，你将查找创建的“访问的联系人”行以触发此流。 由于电子邮件地址是“联系人”表的一部分，因此需要此信息才能将电子邮件发送给访客。 

7.  在此操作上，单击省略号 (...)，然后单击“重命名” 。
        将此操作重命名为“获取访客”。 这是一个很好的习惯，这样你和其他流编辑可以理解步骤的目的，而不必深入研究细节。

## <a name="task-3-create-a-step-to-send-an-email-to-the-visitor"></a>任务 \#3：创建用于向访客发送电子邮件的步骤

1.  单击“新建步骤”。 这是向访客发送电子邮件的步骤。

2.  搜索“邮件”，选择“Office 365 Outlook”连接器和“发送电子邮件 (V2)”操作 。

3.  如果要求接受使用此操作的条款和条件，请单击“接受”。

4.  在“收件人”字段下选择“添加动态内容” 。 
    
5.  从动态内容列表中选择“电子邮件”。
        > Notice that it is beneath the **Get the visitor** header. This means you
        are selecting the Email that is related to the Visitor that you looked
        up in the previous step.

6.  在“主题”字段中输入“你对 Bellows College 的计划访问”。

7.  在“电子邮件正文”中输入以下文本：

>   需将动态内容置于方括号中命名字段的位置。 建议先复制并粘贴所有文本，然后在正确的位置添加动态内容。

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   Dear {First Name},

   You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

   Best regards,

   Campus Administration
   Bellows College
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

8.  突出显示 {First Name} 文本。 将该文本替换为“获取访客”步骤中的“名字”字段 。

9.  突出显示 {Scheduled Start} 文本。 将其替换为“添加访问”步骤中的“计划开始时间”字段。 

10.  突出显示 {Scheduled End} 文本。 将其替换为“添加访问”步骤中的“计划结束时间”字段。 

11.  单击“ **保存**”。

将此流选项卡保持打开状态以用于下一个任务。 流大致如下所示：

![流步骤示例。](media/4-Flow.png)

## <a name="task-4-validate-and-test-the-flow"></a>任务 \#4：验证并测试流

1.  在浏览器中打开新选项卡并导航到 <https://make.powerapps.com>。

2.  如果尚未选择“[我的初始] 练习”环境，请在右上角选择它。

3.  单击“应用”，然后选择之前创建的校园管理模型驱动应用 。

3.  保持此浏览器标签页处于打开状态，然后导航回到流的上一个选项卡。

4.  在命令栏上，单击“测试”。 选择“手动”，然后单击“测试”。 .

5.  导航到打开了模型驱动应用的浏览器标签页。 

6.  使用左侧导航栏，选择“访问”

6. 按“+ 新建”按钮添加新的“访问”记录 。

7. 完成访问记录，如下所示：

    -   **名称：** 测试访问

    -   **访客：** John Doe

    -   **计划开始时间：** 明天上午 8:00

    -   **计划结束时间：** 明天上午 9:00

8. 选择“保存并关闭”按钮。

9. 导航到正在运行流测试的浏览器标签页。 在短暂的延迟之后，你应该会看到流正在运行。 你可以在这里发现流中的任何问题，或确认它已成功运行。 

在短暂的延迟之后，你应会在收件箱中看到一封电子邮件，因为你将 John Doe 的电子邮件填充为了你的个人电子邮件。 请注意，该电子邮件可能会进入“垃圾邮件”文件夹。

# <a name="challenges"></a>挑战

-   在电子邮件中进行格式设置。 如何使电子邮件看起来更专业？ 
