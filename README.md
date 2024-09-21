# [首页查询更多项目](https://github.com/GraduationProject-weixin) 包安装运行


# 50488wxapp短文写作竞赛管理系统_r653y小程序

![picture](https://raw.githubusercontent.com/GraduationProject-springboot/.github/main/img/wx.png)

### 点击播放视频 ▼
[![Watch the video](https://i.sstatic.net/Vp2cE.png)](https://www.bilibili.com/video/BV1NvtMeFEiw?p=131)


# 系统概述
短文写作竞赛管理系统小程序的设计与开发是指对该系统的各个功能模块进行详细设计，力求每个模块都能够满足用户的要求，系统开发完成后还需对系统进行单元测试和系统测试，发现系统中存在的问题并解决，确保系统正常稳定的运行。短文写作竞赛管理系统小程序工作原理图如图4-1所示：

![](/md/blog.011.png)

图4-1 系统工作原理图
## 4.2 系统结构设计
系统结构设计必须要满足管理员、学生、评委和负责人的业务需求，系统结构设计完成后要形成系统结构设计文档，开发人员就可根据模块接口说明进行接口开发，接口开发完需进行功能测试，目的是发现并解决系统漏洞，同时还得保证系统的可扩展性和稳定性，满足用户对系统的要求。系统设计需满足以下要求：

1. 安全性
1. 易用性
1. 柔软性
1. 柔软性
1. 扩展性

短文写作竞赛管理系统小程序的整体结构设计主要分为四大部分：管理员、学生、评委和负责人。管理员的职责是管理学生信息、评委信息和负责人信息以及设置权限，发布资讯等其他基础功能的管理；整体结构设计如图4-2所示。

![](/md/blog.012.png)

图4-2 整体结构设计图
## 4.3 数据库设计
本系统依赖于MySQL数据库来储存信息，系统完成后，所有需要的数据都要从数据库中读取，这也意味着无论是插入、更新还是删除操作，只要对数据有改动的操作都需要与数据库交互，因此，系统的全部数据都要储存在数据库，必须保证数据库在未经授权情况下不得进行删除表结构等危险操作，而且要保证表中字段的准确性。
### 4.3.1 数据库设计原则
1. 从上而下
1. 从下至上
1. 逐渐扩大
1. 结合方法
### 4.3.2 数据库实体
E-R图，即实体-联系图，它是一种通过对实例进行抽象，以可视化的方式来描述现实世界的概念模型。根据需求分析绘制出数据库的E-R图，能够直观地映射出各个表之间的关系。

本系统的实体属性图如下图所示：

1、竞赛信息实体图如图4-3所示：

![](/md/blog.013.png)

图4-3竞赛信息实体图

2、竞赛成果实体图如图4-4所示：

![](/md/blog.014.png)

图4-4竞赛成果实体图

3、竞赛报名实体图如图4-5所示：

![](/md/blog.015.png)

图4-5竞赛报名实体图
### 4.3.3 数据库表设计
数据库的主要作用是储存和管理整个系统的数据。数据库中的数据在保证一定的独立性和安全性的前提下，也要有某种程度的共享，在一定条件范围内可以共享某些数据。必须保证数据库中每张表里存储的数据是安全的，如果没有经过身份认证，就无法查阅及使用。在进行数据库设计时，应根据具体情况，进行有针对性的数据库开发和设计。下面列举主要数据库表结构。

表4-1：学生

|字段名称|类型|长度|字段说明|主键|默认值|
| :-: | :-: | :-: | :-: | :-: | :-: |
|id|bigint||主键|主键||
|addtime|timestamp||创建时间||CURRENT\_TIMESTAMP|
|xueshengxuehao|varchar|200|学生学号|||
|xueshengxingming|varchar|200|学生姓名|||
|mima|varchar|200|密码|||
|xingbie|varchar|200|性别|||
|zhuanye|varchar|200|专业|||
|banji|varchar|200|班级|||
|shouji|varchar|200|手机|||
|youxiang|varchar|200|邮箱|||
|touxiang|longtext|4294967295|头像|||
表4-2：配置文件

|字段名称|类型|长度|字段说明|主键|默认值|
| :-: | :-: | :-: | :-: | :-: | :-: |
|id|bigint||主键|主键||
|name|varchar|100|配置参数名称|||
|value|varchar|100|配置参数值|||
表4-3：用户表

|字段名称|类型|长度|字段说明|主键|默认值|
| :-: | :-: | :-: | :-: | :-: | :-: |
|id|bigint||主键|主键||
|username|varchar|100|用户名|||
|password|varchar|100|密码|||
|role|varchar|100|角色||管理员|
|addtime|timestamp||新增时间||CURRENT\_TIMESTAMP|
表4-4：班级

|字段名称|类型|长度|字段说明|主键|默认值|
| :-: | :-: | :-: | :-: | :-: | :-: |
|id|bigint||主键|主键||
|addtime|timestamp||创建时间||CURRENT\_TIMESTAMP|
|banji|varchar|200|班级|||
表4-5：token表

|字段名称|类型|长度|字段说明|主键|默认值|
| :-: | :-: | :-: | :-: | :-: | :-: |
|id|bigint||主键|主键||
|userid|bigint||用户id|||
|username|varchar|100|用户名|||
|tablename|varchar|100|表名|||
|role|varchar|100|角色|||
|token|varchar|200|密码|||
|addtime|timestamp||新增时间||CURRENT\_TIMESTAMP|
|expiratedtime|timestamp||过期时间||CURRENT\_TIMESTAMP|
表4-6：评委

|字段名称|类型|长度|字段说明|主键|默认值|
| :-: | :-: | :-: | :-: | :-: | :-: |
|id|bigint||主键|主键||
|addtime|timestamp||创建时间||CURRENT\_TIMESTAMP|
|pingweizhanghao|varchar|200|评委账号|||
|pingweixingming|varchar|200|评委姓名|||
|mima|varchar|200|密码|||
|xingbie|varchar|200|性别|||
|lianxifangshi|varchar|200|联系方式|||
|touxiang|longtext|4294967295|头像|||
表4-7：公告栏

|字段名称|类型|长度|字段说明|主键|默认值|
| :-: | :-: | :-: | :-: | :-: | :-: |
|id|bigint||主键|主键||
|addtime|timestamp||创建时间||CURRENT\_TIMESTAMP|
|title|varchar|200|标题|||
|introduction|longtext|4294967295|简介|||
|picture|longtext|4294967295|图片|||
|content|longtext|4294967295|内容|||
表4-8：竞赛信息

|字段名称|类型|长度|字段说明|主键|默认值|
| :-: | :-: | :-: | :-: | :-: | :-: |
|id|bigint||主键|主键||
|addtime|timestamp||创建时间||CURRENT\_TIMESTAMP|
|jingsaibianhao|varchar|200|竞赛编号|||
|jingsaimingcheng|varchar|200|竞赛名称|||
|jingsaileibie|varchar|200|竞赛类别|||
|tupian|longtext|4294967295|图片|||
|baomingkaishishijian|datetime||报名开始时间|||
|baomingjiezhishijian|datetime||报名截止时间|||
|baomingtiaojian|longtext|4294967295|报名条件|||
|fabushijian|datetime||发布时间|||
|fuzerenzhanghao|varchar|200|负责人账号|||
|fuzerenxingming|varchar|200|负责人姓名|||
表4-9：竞赛评分

|字段名称|类型|长度|字段说明|主键|默认值|
| :-: | :-: | :-: | :-: | :-: | :-: |
|id|bigint||主键|主键||
|addtime|timestamp||创建时间||CURRENT\_TIMESTAMP|
|jingsaibianhao|varchar|200|竞赛编号|||
|jingsaimingcheng|varchar|200|竞赛名称|||
|jingsaileibie|varchar|200|竞赛类别|||
|tupian|longtext|4294967295|图片|||
|jingsaifenshu|float||竞赛分数|||
|pingfenbeizhu|varchar|200|评分备注|||
|pingfenshijian|datetime||评分时间|||
|fuzerenzhanghao|varchar|200|负责人账号|||
|fuzerenxingming|varchar|200|负责人姓名|||
|xueshengxuehao|varchar|200|学生学号|||
|xueshengxingming|varchar|200|学生姓名|||
|zhuanye|varchar|200|专业|||
|banji|varchar|200|班级|||
|shouji|varchar|200|手机|||
|pingweizhanghao|varchar|200|评委账号|||
|pingweixingming|varchar|200|评委姓名|||
表4-10：竞赛类别

|字段名称|类型|长度|字段说明|主键|默认值|
| :-: | :-: | :-: | :-: | :-: | :-: |
|id|bigint||主键|主键||
|addtime|timestamp||创建时间||CURRENT\_TIMESTAMP|
|jingsaileibie|varchar|200|竞赛类别|||
表4-11：竞赛成果

|字段名称|类型|长度|字段说明|主键|默认值|
| :-: | :-: | :-: | :-: | :-: | :-: |
|id|bigint||主键|主键||
|addtime|timestamp||创建时间||CURRENT\_TIMESTAMP|
|jingsaimingcheng|varchar|200|竞赛名称|||
|chengguomingcheng|varchar|200|成果名称|||
|tupian|longtext|4294967295|图片|||
|chengguoleibie|varchar|200|成果类别|||
|niandu|varchar|200|年度|||
|fujian|longtext|4294967295|附件|||
|beizhu|varchar|200|备注|||
|tijiaoshijian|datetime||提交时间|||
|fuzerenzhanghao|varchar|200|负责人账号|||
|fuzerenxingming|varchar|200|负责人姓名|||
|xueshengxuehao|varchar|200|学生学号|||
|xueshengxingming|varchar|200|学生姓名|||
|zhuanye|varchar|200|专业|||
|banji|varchar|200|班级|||
|shouji|varchar|200|手机|||
|sfsh|varchar|200|是否审核||待审核|
|shhf|longtext|4294967295|审核回复|||
表4-12：竞赛报名

|字段名称|类型|长度|字段说明|主键|默认值|
| :-: | :-: | :-: | :-: | :-: | :-: |
|id|bigint||主键|主键||
|addtime|timestamp||创建时间||CURRENT\_TIMESTAMP|
|jingsaibianhao|varchar|200|竞赛编号|||
|jingsaimingcheng|varchar|200|竞赛名称|||
|jingsaileibie|varchar|200|竞赛类别|||
|tupian|longtext|4294967295|图片|||
|baomingziliao|longtext|4294967295|报名资料|||
|beizhu|varchar|200|备注|||
|baomingshijian|datetime||报名时间|||
|fuzerenzhanghao|varchar|200|负责人账号|||
|fuzerenxingming|varchar|200|负责人姓名|||
|xueshengxuehao|varchar|200|学生学号|||
|xueshengxingming|varchar|200|学生姓名|||
|zhuanye|varchar|200|专业|||
|banji|varchar|200|班级|||
|shouji|varchar|200|手机|||
|crossuserid|bigint||跨表用户id|||
|crossrefid|bigint||跨表主键id|||
|sfsh|varchar|200|是否审核||待审核|
|shhf|longtext|4294967295|审核回复|||
表4-13：专业

|字段名称|类型|长度|字段说明|主键|默认值|
| :-: | :-: | :-: | :-: | :-: | :-: |
|id|bigint||主键|主键||
|addtime|timestamp||创建时间||CURRENT\_TIMESTAMP|
|zhuanye|varchar|200|专业|||
表4-14：负责人

|字段名称|类型|长度|字段说明|主键|默认值|
| :-: | :-: | :-: | :-: | :-: | :-: |
|id|bigint||主键|主键||
|addtime|timestamp||创建时间||CURRENT\_TIMESTAMP|
|fuzerenzhanghao|varchar|200|负责人账号|||
|fuzerenxingming|varchar|200|负责人姓名|||
|mima|varchar|200|密码|||
|xingbie|varchar|200|性别|||
|shoujihao|varchar|200|手机号|||
|touxiang|longtext|4294967295|头像|||



# 5界面设计与功能实现
## 5.1小程序端实现
### 5.1.1登录界面的实现
首先双击打开小程序客户端，连上网络之后会显示出本系统的登录界面，这是进入小程序的初始页面“登录”，能成功进入到该登录界面则代表小程序的开启是成功的，接下来就可以操作本系统所带有的其他所有的功能。登录界面如图5-1所示。

![](/md/blog.016.jpeg)

图5-1 登录界面
### 5.1.2 小程序首页功能的实现
小程序首页是学生注册登录后进入的第一个界面，在这里，人们能够看到小程序的导航条，内容包括首页、竞赛信息、竞赛成果、我的等。小程序首页界面如图5-2所示。

![](/md/blog.017.png)

图5-2 小程序首页界面图

竞赛信息；在竞赛信息页面可以查看到竞赛名称、竞赛编号、竞赛类别、报名开始时间、报名截止时间、发布时间、负责人账号、负责人姓名、报名条件等详细信息，并根据需要进行报名操作；如图5-3所示。

![](/md/blog.018.jpeg)

图5-3竞赛信息界面图

竞赛成果；在竞赛成果页面可以查看到竞赛名称、成果名称、成果类别、年度、附件、备注、提交时间、学生学号、学生姓名、专业、班级、手机等详细信息；如图5-4所示。

![](/md/blog.019.png)

图5-4竞赛成果界面图
### 5.1.3学生功能
学生登录成功后，点击“我的”进入我的页面，在我的页面可以对个人中心、竞赛报名、竞赛成果、竞赛评分等进行详细操作。学生功能界面如图5-5所示。

![](/md/blog.020.png)

图5-5学生功能界面图
## 5.2 后台功能的实现
后台登录，系统用户在登录页面通过选择角色，正确填写账号和密码等信息进行登录操作，如图5-6所示。

![](/md/blog.021.jpeg)

图5-6后台登录界面图
### 5.2.1 管理员功能的实现
管理员登录进入小程序可以查看到系统首页、个人中心、负责人管理、学生管理、评委管理、专业管理、班级管理、竞赛类别管理、竞赛信息管理、竞赛报名管理、竞赛成果管理、竞赛评分管理、系统管理等功能并进行详细操作，如图5-7所示。

![](/md/blog.022.png)

图5-7管理员功能界面图

管理员点击负责人管理。在负责人页面输入负责人账号、负责人姓名进行查询、新增或删除负责人列表，并根据需要对负责人详情信息进行详情、修改或删除操作；如图5-8所示：

![](/md/blog.023.png)

图5-8负责人管理界面

管理员点击学生管理。在学生页面输入学生学号、学生姓名进行查询、新增或删除学生列表，并根据需要对学生详情信息进行详情、修改或删除操作；如图5-9所示：

![](/md/blog.024.png)

图5-9学生管理界面

管理员点击评委管理。在评委页面输入评委账号、评委姓名进行查询、新增或删除评委列表，并根据需要对评委详情信息进行详情、修改或删除操作；如图5-10所示：

![](/md/blog.025.png)

图5-10评委管理界面

管理员点击专业管理。在专业页面输入专业进行查询、新增或删除专业列表，并根据需要对专业详情信息进行详情、修改或删除操作；如图5-11所示：

![](/md/blog.026.png)

图5-11专业管理界面

管理员点击班级管理。在班级页面输入班级进行查询、新增或删除班级列表，并根据需要对班级详情信息进行详情、修改或删除操作；如图5-12所示：

![](/md/blog.027.png)

图5-12班级管理界面

管理员点击竞赛类别管理。在竞赛类别页面输入竞赛类别进行查询、新增或删除竞赛类别列表，并根据需要对竞赛类别详情信息进行详情、修改或删除操作；如图5-13所示：

![](/md/blog.022.png)

图5-13竞赛类别管理界面

管理员点击竞赛信息管理。在竞赛信息页面输入竞赛名称进行查询、新增或删除竞赛信息列表，并根据需要对竞赛详情信息进行详情、修改或删除操作；如图5-14所示：

![](/md/blog.028.png)

图5-14竞赛信息管理界面

管理员点击竞赛报名管理。在竞赛报名页面输入竞赛名称和选择是否通过进行查询、删除或批量审核竞赛报名列表，并根据需要对竞赛报名详情信息进行详情、修改或删除操作；如图5-15所示：

![](/md/blog.029.png)

图5-15竞赛报名管理界面

管理员点击竞赛成果管理。在竞赛成果页面输入竞赛名称、成果名称、成果类别和选择是否通过进行查询、删除或批量审核竞赛成果列表，并根据需要对竞赛成果详情信息进行详情、修改或删除操作；如图5-16所示：

![](/md/blog.030.png)

图5-16竞赛成果管理界面

管理员点击竞赛评分管理。在竞赛评分页面输入竞赛名称进行查询或删除竞赛评分列表，并根据需要对竞赛评分详情信息进行详情、修改或删除操作；如图5-17所示：

![](/md/blog.031.png)

图5-17竞赛评分管理界面

管理员点击系统管理。在轮播图管理页面可以对序号、名称、值进行详情、修改操作；还可以对公告栏进行操作；如图5-18所示：

![](/md/blog.032.png)

图5-18系统管理界面

### 5.2.2 评委功能的实现
评委登录进入小程序可以查看到系统首页、个人中心、竞赛信息管理、竞赛报名管理、竞赛评分管理等功能并进行详细操作，如图5-19所示。

![](/md/blog.033.png)

图5-19评委功能界面图

评委点击竞赛信息管理。在竞赛信息页面输入竞赛名称进行查询竞赛信息列表，并根据需要对竞赛详情信息进行详情操作；如图5-20所示：

![](/md/blog.034.png)

图5-20竞赛信息管理界面

### 5.2.3负责人功能的实现
负责人登录进入小程序可以查看到系统首页、个人中心、竞赛信息管理、竞赛报名管理、竞赛成果管理、竞赛评分管理等功能并进行详细操作，如图5-21所示。

![](/md/blog.035.png)

图5-21负责人功能界面图












