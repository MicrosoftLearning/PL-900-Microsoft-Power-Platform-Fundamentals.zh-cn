---
lab:
  title: 实验室：验证实验室环境
  module: 'Module 0: Course introduction'
ms.openlocfilehash: f98bf8aee0be31934acee15f3b5668d3e6e6108a
ms.sourcegitcommit: ef58c858463b890e923ef808b1d43405423943fd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2022
ms.locfileid: "137898831"
---
<a name="module-0-course-introduction"></a>模块 0：课程简介
=================================

<a name="scenario"></a>方案
--------

Bellows College 是一所教育机构，校园内有多座建筑。 当前，校园访客被记录在纸质日记中。 无法始终如一地捕获信息，也无法收集和分析有关整个校园的访问数据。

校园管理部门希望对其访客登记系统进行现代化改造。在该系统中，由安全人员控制对建筑物的访问，所有访问都必须由主办人预先登记和记录。

在整个课程中，你将生成应用程序并执行自动化，以使 Bellows College 的管理和安全人员可以管理和控制校园建筑的出入情况。

在此模块 0 实验室中，你将获得 Power Platform 试用版租户并可以访问 Power Platform 管理中心。 在管理中心中，你将创建自己的“实践”环境，你将在该环境中开展大部分实验室工作。

## <a name="exercise-1--setup"></a>练习 1 - 设置

### <a name="task-1---acquire-your-microsoft-power-platform-trial-tenant"></a>任务 1 - 获取你的 Microsoft Power Platform 试用版租户

1. 复制授权实验室主机托管服务商提供的 Microsoft 365 凭据 。

2. 导航到 <https://powerapps.microsoft.com> 并单击“免费开始”。

3. 在“开始使用”下，在提示“输入你的工作电子邮件地址”的文本框中输入你的 Microsoft 365 凭据中的电子邮件地址。

4. 将会显示一条说明你已经拥有 Microsoft 帐户的提示。 选择“登录”。

5. 输入授权实验室主机托管服务提供商提供的密码。 

6. 选择“是”保持登录状态。

7. 填写你的帐户信息，然后选择“开始”以注册 Microsoft Power Platform 试用版。  

### <a name="task-2--create-environment"></a>任务 \#2 - 创建环境

1. 如果系统再次提示，请访问 <https://admin.powerplatform.microsoft.com> 并使用你的 Microsoft 365 凭据登录。

2. 选择“环境”，然后单击“+新建”。

    - 对于“名称”，输入“[我的姓名缩写] 实践”。 （示例：AJ 实践。）
    
    - 对于“类型”，选择“试用版”（请勿选择“试用版(基于订阅)”选项）。
    
    - 将“为此环境创建数据库?”的切换开关更改为“是”。
    
    - 将所有其他选择保留为默认设置，然后单击“下一步”。
    
    - 在下一个选项卡上，将所有选择保留为默认设置，然后单击“保存”。

3. 你的“实践”环境现在应该显示在“环境”列表中。 

    > 完成部署可能需要几分钟的时间。 根据需要刷新页面。

# <a name="exercise-2-provision-a-power-apps-portal"></a>练习 \#2：预配 Power Apps 门户

**目的：** 预配 Power Apps 门户可能需要一些时间。 在本练习中，你将在自己的环境中创建 Power Apps 门户，以便可以启动预配过程。 你将在后续实验室中使用该门户。

## <a name="task-1-create-power-apps-portal"></a>任务 \#1：创建 Power Apps 门户

1.  登录到 <https://make.powerapps.com>

2.  如果右上角显示的“环境”不是你的练习环境，请单击选择你的“环境”。

3.  在“主页”上，单击“生成自己的应用”下面的“空白门户”面板 

    > 如果看不到此选项，请尝试缩小。

4.  提供新门户详细信息

    -   输入 ```Bellows College Visitors``` 作为门户“名称” 

    -   提供唯一 URL： **something**.powerappsportals.com（如果该名称已占用，请选择其他名称）

    -   选择一个基本门户“语言”

    -   单击“创建” 

    > 门户预配过程可能需要 30 到 45 分钟。 不必一直等待，因为在继续下一个模块时，该过程将继续。
