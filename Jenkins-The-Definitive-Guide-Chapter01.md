# Jenkins权威指南 #

内容提要编辑
《Jenkins权威指南》从实践者的角度，在讲解Jenkins基本原理的同时，深入到持续集成、持续交付领域，为读者梳理出如何使用Jenkins设计和实现一个自动化的、周期性的集成测试过程，帮助读者理解Jenkins适用于什么场景。《Jenkins权威指南》中首先介绍Jenkins以及持续集成、持续交付的基础知识；然后安装Jenkins和配置Jenkins服务器，使用Jenkins建立构建作业、进行自动化测试，介绍Jenkins支持的几种安全模式，如何使用Jenkins进行消息通知，如何确保代码质量；最后进阶展示如何建立高级的和分布式的构建，如何进行自动化的部署和交付以及对Jenkins的运维。
《Jenkins权威指南》适合想要了解Jenkins工具以及持续集成、持续交付理念的开发和测试人员阅读，也非常适合基于Jenkins构建持续集成、持续交付平台的技术人员阅读。 [1] 
目录编辑
序 xvii
前言 xix
## 第1 章 Jenkins 简介 1 ##
简介 1
持续集成基础 1
Jenkins 简介（née Hudson） 3
从Hudson 到Jenkins——一个简短的故事 3
应该使用Jenkins 还是Hudson 4
引进持续集成到你的公司 5
阶段1——无构建服务器 5
阶段2——夜间构建 6
阶段3——夜间构建加自动化测试 6
阶段4——加入度量指标 6
阶段5——更认真地对待测试 6
阶段6——自动化验收测试和自动化部署 7
阶段7——持续部署 7
接下来做什么呢 7
## 第2 章 迈入Jenkins 的第一步 9 ##
简介 9
准备环境 9
安装Java 10
安装Git 11
创建GitHub 账号 11
配置SSH 密钥 11
创建代码库分支 12
启动Jenkins 13
配置工具 17
![](https://raw.githubusercontent.com/CoderDream/order/master/snapshot/Jenkins_0101.png)
配置你的Maven 设置 18

![](https://raw.githubusercontent.com/CoderDream/order/master/snapshot/Jenkins_0102.png)


![](https://raw.githubusercontent.com/CoderDream/order/master/snapshot/Jenkins_0103.png)


![](https://raw.githubusercontent.com/CoderDream/order/master/snapshot/Jenkins_0104.png)


![](https://raw.githubusercontent.com/CoderDream/order/master/snapshot/Jenkins_0105.png)

![](https://raw.githubusercontent.com/CoderDream/order/master/snapshot/Jenkins_0106.png)

![](https://raw.githubusercontent.com/CoderDream/order/master/snapshot/Jenkins_0107.png)

![](https://raw.githubusercontent.com/CoderDream/order/master/snapshot/Jenkins_0108.png)


![](https://raw.githubusercontent.com/CoderDream/order/master/snapshot/Jenkins_0108.png)


配置JDK 19
通知 20
设置Git 20
你的第一个Jenkins 构建作业 21
你的第一个构建作业 26
更多的报告——显示Javadoc 33
添加代码覆盖率和其他度量 34
小结 40
## 第3 章 安装Jenkins 41 ##
简介 41
下载和安装Jenkins 41
为Jenkins 准备好构建服务器 44
Jenkins 主目录 45
在Debian 或者Ubuntu 系统上安装Jenkins 47
在Red Hat、Fedora 或者CentOS 上安装Jenkins 48
在SUSE 或者OpenSUSE 上安装Jenkins 49
以单机应用形式运行Jenkins 49
基于Apache 服务器运行Jenkins 53
在应用服务器上运行Jenkins 54
内存方面的考虑 54
安装Jenkins 为一个Windows 服务 55
Jenkins 主目录里有什么 59
备份Jenkins 数据 62
升级Jenkins 安装 63
小结 64
第4 章 配置Jenkins 服务器 65
简介 65
配置面板——Manage Jenkins 界面 65
配置系统环境 68
配置全局属性 69
配置JDK 70
配置构建工具 72
Maven 73
Ant 74
Shell 脚本 75
配置版本控制工具 75
配置Subversion 75
配置CVS 75
配置邮件服务器 76
配置代理 77
小结 78
第5 章 设置构建作业 79
简介 79
Jenkins 构建作业 79
创建自由式构建作业 80
通用选项 81
高级项目选项 82
配置源代码管理 83
用Subversion 工作 84
使用Git 86
Build Triggers 96
构建作业完成后触发下一个 97
计划构建作业 97
轮询SCM 98
远程触发构建 99
手工构建作业 101
构建步骤 101
Maven 构建步骤 102
Ant 构建步骤 103
执行Shell 或Windows 批处理命令 104
在构建中使用Jenkins 环境变量 105
运行Groovy 脚本 108
用其他语言构建项目 110
构建后的操作 110
报告测试结果 110
归档构建产物 110
通知 114
构建其他的项目 114
运行新的构建作业 115
使用Maven 构建作业 115
每当SNAPSHOT（快照）依赖被建立时都要进行构建 116
配置Maven 构建 116
构建后期操作 118
部署到企业仓库管理器 118
部署到商业企业仓库管理器 122
管理模块 122
Maven 构建作业中额外的构建步骤 122
用其他语言使用Jenkins 124
用Grails 构建项目 124
用Gradle 构建项目 126
用Visual Studio MSBuild 构建项目 129
用NAnt 构建项目 130
使用Ruby 和Ruby on Rails 构建项目 130
小结 132
第6 章 自动化测试 133
简介 133
自动化单元和集成测试 134
在Jenkins 中配置测试报告 135
显示测试结果 137
忽略测试 140
代码覆盖率 142
使用Cobertura 测量代码覆盖率 143
使用Clover 测量代码覆盖率 152
自动化验收测试 154
JMeter 自动化性能测试 157
请求帮助！我的测试运行得太慢了 165
添加更多的硬件 166
运行更少的集成/ 功能测试 166
并行运行测试 167
小结 167
第7 章 Jenkins 安全 169
简介 169
激活Jenkins 安全 169
Jenkins 安全实例 170
安全域——定义Jenkins 用户 171
使用Jenkins 内置用户数据库 171
使用LDAP 仓库 174
使用微软活动目录 176
使用UNIX 用户和用户组 177
Servlet 容器授权 177
使用Atlassian Crowd 178
与其他系统集成 179
授权——谁可以做什么 181
安全矩阵 181
基于项目的安全 185
基于角色的安全 188
审计——跟踪用户行为 190
小结 193
第8 章 通知 195
简介 195
电子邮件通知 195
更高级的电子邮件通知 197
声明构建 200
RSS 订阅 202
构建分发器 202
即时消息 204
用Jabber 进行IM 通知 204
使用IRC 的IM 通知 209
IRC 通知 209
桌面通知器 212
通过Notifo 通知 213
移动通知 216
短信通知 216
制造噪声 219
极端反馈设备 221
小结 222
第9 章 代码质量 225
简介 225
构建过程中的代码质量 226
受欢迎的Java 和Groovy 代码质量分析工具 227
Checkstyle 227
PMD/CPD230
FindBugs 235
CodeNarc237
使用Violations 插件报告代码质量问题 238
与自由风格下的构建作业一起工作 239
使用Maven 构建作业 242
使用Checkstyle、PMD 和FindBugs 报告 244
报告代码复杂度 247
报告未完成的任务 248
集成Sonar 249
小结 253
第10 章 高级构建 255
简介 255
参数化构建作业 255
创建一个参数化构建作业 256
为构建适配参数化构建脚本 257
高级参数类型 259
使用Subversion 标签构建 260
使用Git 标签构建 261
远程启动参数化构建作业 262
参数化构建作业历史 263
参数化触发263
多重结构的构建作业 266
搭建多重结构构建 266
配置从节点轴 267
配置JDK 轴 268
自定义轴 268
执行多重结构构建 268
自动生成Maven 构建作业 271
配置作业 271
使用继承复用作业配置 273
插件支持 275
自由式作业 278
构建协作 278
在Jenkins 中并行构建 279
依赖关系图 279
连接 280
Locks and Latches 插件 281
构建管道及优化 282
通过M2Release 插件管理Maven 版本发布 283
复制构建产物 286
构建进阶 289
汇总测试结果 295
构建管道 296
小结 299
第11 章 分布式构建 301
简介 301
Jenkins 分布式构建架构 301
Jenkins 主/ 从策略 302
主节点使用SSH 启动从节点代理 303
使用Java Web Start 手工启动从代理 307
把Jenkins 从节点安装为Windows 服务 309
无主节点模式启动从节点 310
以远程服务方式启动Windows 从节点 310
把构建作业与一个或一组从节点关联 311
节点监控 313
云计算 314
使用Amazon EC2 314
使用CloudBees DEV@cloud 服务 318
小结 319
第12 章 自动化部署和持续交付 321
简介 . 321
实现自动化和持续部署 322
部署脚本 322
数据库更新 322
冒烟测试 325
回滚更改 326
部署到应用程序服务器上 326
部署一个Java 应用 327
部署像Ruby 和PHP 这样基于脚本的应用程序 336
小结 339
第13 章 Jenkins 的维护341
简介 341
监控磁盘空间 341
使用Disk Usage 插件 343
磁盘使用及Jenkins Maven 项目类型 344
监控服务器负载 345
备份配置 346
Jenkins 备份基础 346
使用备份插件 348
更为轻量的自动备份 350
构建作业归档 350
构建迁移 351
小结 355
附录A 自动化你的单元和集成测试 357
索引 367 [1] 