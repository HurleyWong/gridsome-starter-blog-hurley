---
title: DevOps 初学者的入门指南
date: 2020-12-23T21:00:00+08:00
published: true
slug: devops-learning
tags:
- DevOps
cover_image: "./images/devops-learning.png"
canonical_url: false
description: 到底什么是 DevOps？流程和管理？运维和自动化？架构和服务？
---

:::note 👀 Background

随着软件发布迭代的频率越来越高，传统的「瀑布型」（开发-测试-发布）模式已经不能够满足快速交付的需求。2009 年 DevOps 应运而生，就是更好的优化**开发 (DEV)**、**测试 (QA)**、**运维 (OPS)** 的流程。这样就通过开发运维一体化，通过高度自动化工具与流程来使得软件构建、测试、发布更加快捷、频繁和可靠。

:::

## 区别

### DevOps 与传统的运维有什么不同？

下面我们就拿传统的瀑布式开发与 DevOps 进行一个对比：

|  瀑布式开发   | DevOps  |
|  ----  | ----  |
| 订购新的服务器后，开发团队需要进行测试。运维团队需要根据需求文档开始部署基础设施  | 订购新的服务器后，开发和运维团队根据需求文档共同调试部署新的服务器。这样开发人员也可以了解服务的基础机构 |
| 开发人员无法对故障转移、冗余策略、数据中心的位置和存储要求提供任何的协助  | 由于有开发人员的加入，有关故障转移、冗余策略、灾难恢复等的规划会非常的准确 |
| 运维团队对于开发团队的进展也是一无所知，只能根据运维团队的理解来指定监控的计划 | 在 DevOps 中，运维团队完全了解开发人员的进展。他们还可以使用应用程序性能监视的工具以优化应用 |

传统的运维人员把将近一半的时间都放在了与部署有关的工作中：

* 执行实际的部署工作
* 修复与部署工作有关的问题

为了改变这种状况，就必须实现两个关键的需求：

* 通过自动化部署将目前这种手动、人工的任务所需时间减少
* 通过产业化措施，将需要处理的这些与部署有关的问题减少

### DevOps 与敏捷开发有什么不同？

|  敏捷开发   | DevOps  |
|  ----  | ----  |
| 强调的是打破开发人员和管理层之间的障碍  | DevOps 主要是关于开发团队和运维团队的 |
| 解决了客户需求和开发团队之间的距离 | 解决了开发和运维团队之间的距离 |
| 敏捷开发管理 「**Sprint**」，时间更短 | DevOps 主要是争取主要版本的稳定和可靠，而不是频繁地发布新的小版本 |

DevOps 就像一颗神奇的子弹，将敏捷开发扩展至了生产端。DevOps 的共存实现了扩展敏捷开发实践，进一步完善软件变更在**构建**、**验证**、**部署**、**交付**等阶段中的流动。它鼓励软件开发人员和 IT 运维人员之间进行沟通、协作、集成和自动化。

> DevOps 实际上是向着大规模敏捷 (**Scaling Agility**) 迈出的另一步！

## 优势

DevOps 允许敏捷开发团队实施持续集成和持续交付。

* **可预测性**：DevOps 可以显著地降低新版本的故障率
* **自愈性**：可以随时将应用回滚到较早的版本
* **可维护性**：在新版本崩溃和当前系统不可用的情况下，可以进行恢复
* **上线时间**：通过简化交付流程可以缩短上线时间
* **更高的质量**：提供开发应用程序的质量
* **降低风险**：在软件交付的生命周期中包含安全检查，有助于减少整个软件生命周期中的安全风险
* **弹性**：软件系统的运行状态更加稳定，更加安全
* **将大的代码库分隔成小块**：是基于敏捷编程方法的，所以允许将大的代码块分解为更小且易于管理的块

## 生命周期

1. **开发**：在此阶段，整个开发过程分为最小的开发周期，这有利于 DevOps 团队加快软件开发和交付过程。
2. **测试**：QA 团队通过自动化测试工具来识别和修复新代码中的错误。
3. **集成**：在此阶段，新功能与主分支代码继承，并进行测试，只有持续集成和测试才能实现持续交付。
4. **部署**：在此阶段，部署过程持续进行，它的执行方式是任何时候在代码中进行的任何更改都不应该影响流量网站的运行。
5. **监测**：在此阶段，运维团队将负责处理不合适的系统行为或者生产中发现的错误。

![DevOps 生命周期](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F96b39a9b-1333-4694-840c-b33dabb41bf9%2FUntitled.png?table=block&id=8c05e053-4902-444e-b5dc-12e4f4fea9f3&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=3960&userId=&cache=v2)

### CI

CI (**Continuous Integration**)，持续集成。即开发人员在工作时不断地集成工作分支到主分支（一天内，频繁地将代码集成到主干）。这样不仅可以提高开发效率，还可以自动测试和构建工作，快速迭代的时候还可以及时地发现错误。同时，也防止分支大幅地偏离主干。因为如果不是经常集成的话，主干又在不断地更新，那么以后集成的难度也会增大，甚至难以集成。

### CD

CD (**Continuous Delivery**)，持续交付。即频繁地将集成的产品交付给质量团队或者用户进行下一步的评审，通过了才会部署到生产阶段。

CD 可以看成是 CI 的下一步。它强调的是，不管怎么更新，代码都是可以随时随地地交付的。

### Continuous Deployment

**持续交付 $\neq$ 持续部署**。持续部署是持续交付的下一步，指的是当代码通过评审后，可以自动部署到生产环境中。

持续部署的目标是「代码在任何是时刻都是可部署的，可以进入生产阶段」。

### 总结

CI/CD 是 DevOps 中的核心流程，但是在团队实际运用中（比如严选团队）仍然会存在以下几个问题：

* 分支管理策略的不一致：大部分是主干发布方式，但是也会存在分支发布方式。在主干发布策略中，分支命令方式也存在差异，分支合并的策略也存在差异
* CI/CD 工具的统一性：有些团队会使用比如 gitlab-ci，有些则可能会使用 Jenkins。gitlab-ci 可以和代码工程自然结合，可以省略在 Jenkins 上配置，易用性好；而用 Jenkins，则可以更好的管理必须的 CI 任务，并且可以使用到 Jenkins 中丰富的插件；
* 自动化测试覆盖率不足：能够真正达到比较高自动化程度的模块较少，很多情况下还是需要人工来触发，或者人工执行校验。

下面这个是严选团队的 DevOps 工具链建设的架构图：

![严选团队 DevOps 架构图](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F356ef626-9f83-4535-a89f-2703b92cc6c7%2FUntitled.png?table=block&id=2aa883c2-d0aa-482b-862b-25b318e2545d&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=2160&userId=&cache=v2)

## 技术栈与工具链

DevOps 有很多技术栈与工具的运用，如下所示：

* 版本控制：Github | GitLab | BitBucket | Coding
* 自动化构建和测试：Apache Ant | Maven | Gradle
* 持续集成和交付：Jenkins | Fabric | Gump | TinderBox
* 容器平台：Docker | AWS | 阿里云
* 配置管理：Chef | Bash | Powershell
* 微服务平台：[Kubernetes](https://kubernetes.io/)（管理云平台中多个主机的容器化应用） | [Cloud Foundry](https://www.cloudfoundry.org/)
* 服务开通：[Puppet](https://puppet.com/)（集中配置管理系统） | [OpenStack](https://www.openstack.org/)（开源的云计算管理平台）
* 日志管理：[Logstash](https://www.elastic.co/cn/logstash/)（服务器端数据处理管道） | [CollectD](https://collectd.org/)（系统监控和统计工具）
* 监控和警告： Nagios | Zabbix

但实际上，DevOps 并不是与 Chef 或者 Docker 容器的等工具的熟练运用划等号。它的范畴远远超过 Puppet 或者 Docker 等工具。

### Jenkins

> Jenkins 是一个自动化服务器，是比较成熟的 CI 工具能够实现自动化集成发布。在建立好流水线之后，可以无需专业运维人员介入，开发人员也可以参与部署。

**部分应用场景**：

* 集成 svn/git 客户端实现源代码的下载检出
* 集成 maven/ant/gradle/npm 等构建工具实现源代码的编译打包测试等
* 集成 sonarqube 对源代码进行质量检查
* 集成 SaltStack/Ansible 实现自动化部署发布
* 集成 Jmeter/Soar/Kubernetes 等
* 自定义插件或者脚本，通过 Jenkins 传参运行

### GitLab CI/CD

Github CI/CD 是 GitLab 内置的强大工具，允许将所有连续方法（持续集成，交付和部署）应用于软件，而无须集成或者使用其他第三方应用程序。

![GitLab CI/CD](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F57f9e2b6-26cf-4008-bad5-3b46cc7eebbf%2FUntitled.png?table=block&id=fdda01d3-e755-4a75-88ed-9e72690b615e&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=5990&userId=&cache=v2)

那么，一个常见的基于 GitLab CI/CD的开发工作流程是这样的。开发者已经在一个问题中讨论过代码的实现，并在本地处理了提出的更改。将提交推送到 GitLab 远程存储库中的 feature 分支后，就会触发 GitLab 的 CI/CD 流水线运行。这时候会：

* 运行自动脚本
  * 构建并测试应用
  * 预览各个合并请求的更改

如果对于代码的实施感到满意，那么就会

* 让代码提交审核并等待被批准
* 将 feature 分支合并到 default 分支
  * GitLab CI/CD 会自动将更改部署到生产环境中
* 最后，如果有问题，可以轻松地回滚

![](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F473d10c4-41c3-45b4-9b03-f4d4f00725df%2FUntitled.png?table=block&id=6a2271dc-46d3-4e68-89de-1f3f3a88007d&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=2400&userId=&cache=v2)

### Maven

> Apache Maven is a software project management and comprehension tool. Based on the concept of a project object model (POM), Maven can manage a project's build, reporting and documentation from a central piece of information.

![](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F582bad06-5202-42e6-bae8-e58758c54af9%2FUntitled.png?table=block&id=4378c00e-a986-4ebd-a494-3f2448b77463&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=550&userId=&cache=v2)

我们在日常开发中使用到 Maven 最多的地方就是管理第三方库的依赖等。实际上，

* Maven 是一个站点和文档工具
* Maven 扩展 Ant，让你下载依赖关系
* Maven 是一组可重用的 Ant 脚本

### Gradle

Gradle 是一个基于 Apache Ant 和 Apache Maven 概念的**项目自动化构建**开源工具。它使用一种基于 Groovy 的语言来声明项目配置，抛弃了基于 XML 的各种繁琐的配置，主要是面向以 Java 项目为主。

![](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F59b7c29a-a261-4c54-92db-8b1eca01453c%2FUntitled.png?table=block&id=3f1f6f34-e5ee-4910-9393-fe6cc196ab20&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=710&userId=&cache=v2)

* gradle 对多工程的构建支持很出色
* 支持局部构建
* 支持多方式依赖管理
* 轻松迁移
* 免费开源
* 是一种以语言为导向的，而非一个严格死板的框架

### SonarQube

SonarQube empowers all developers to write cleaner and safer code.

![](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F667dda74-77a1-45d5-a89d-34853df0e547%2FUntitled.png?table=block&id=e7adbc8c-6ed5-4bf1-8612-88f71610bab4&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=2040&userId=&cache=v2)

### Chef

> Automation for Web-Scale IT. Chef delivers fast, scalable, flexible IT automation.

简单来说，Chef 就是 IT 自动化服务器配置管理工具，它把服务器的环境（软件、依赖库、网络等）进行抽象，以特有的配置语法 (Ruby 语言) 进行管理，可以自动地进行服务器环境的初始化操作。

![](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fad32c700-804f-4c2f-8820-657065b3dd68%2FUntitled.png?table=block&id=7587074d-a03f-471d-bf7d-c1464e855e92&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=1000&userId=&cache=v2)

例如，刚入职一家新公司做开发时，首先要做的一件事就是**配置环境**，那么，如果只是每个人手动地安装，就很容易缺少了某个库或者某个包没有安装。即使有完整的文档说明描述，手动的安装也是不合理的。

环境管理可能是一个不太引起开发者重视的事情，然后如果生产环境发生了变更，开发环境却没有及时变更，就会带来不必要的麻烦了。所以环境管理和代码的版本控制其实一样重要。Chef 最主要做的事情就是：

> **以自动化的方式进行服务器初始化或者变更工作**

**组件**：

Chef 由三大组件组成：

* **Chef Server**：是核心服务器，维护了一套配置脚本 (Cookbook) ，与每个被管节点 (Chef Node) 交互并且给出配置的指令。
* **Chef Workstation**：提供了与 Chef Server 交互的接口，在 Workstation 上创建定义 Cookbook ，并将 Cookbook 上传到 Chef Server 上以保证 Chef Node 能从 Chef Server 上获得最新的配置指令。
* **Chef Node** 是安装了 Chef Client 并注册了的被管理的节点，可以是物理机或者虚拟机或者其它对象。Chef Node 每次运行 Chef Client 都会从 Chef Server 端取得最新的配置指令 (Cookbook)，并按照指令配置自己。

> 一套环境里包含一个 Chef Server，至少一个 Chef Workstation，以及多个 Chef Node。

### Puppet

Puppet 是一个 IT 基础设施自动化管理工具，它能够帮助系统管理员管理基础设施的整个生命周期，包括**供应 (provisioning)**、**配置 (configuration)**、**联动 (orchestration) **以及**报告 (reporting)**。

![](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F11c5c8ce-7b90-4cc0-b0e0-b410b717d219%2FUntitled.png?table=block&id=5de7e782-4708-4ce9-aa7c-c03dda2deb17&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=2400&userId=&cache=v2)

基于 Puppet，就可以实现自动化重复任务、快速部署关键性应用以及在本地或者云端完成主动管理变更和快速扩展架构规模等。

**工作模型**：

* 定义：通过 puppet 的声明性配置语言，定义基础设置配置的目标状态
* 模拟：强制应用改变的配置之前，先进行模拟性应用
* 强制：自动、强制部署达成目标状态，纠正任何偏离的配置
* 报告：报告当下状态以及目标状态的不同，以及达成目标状态所进行的任何强制性的改变

### Zabbix

Zabbix 是一个高度集成的网络监控解决方案，基于 web 界面，可以提供企业级的开源分布式监控解决方案。它能监控各种网络参数，保证服务器系统的安全运营，并提供灵活的通知机制让系统管理员快速定位、解决存在的各种问题。Zabbix 主要由 **zabbix server** 和 **zabbix agent**，以及可选组建 **zabbix proxy**。

![](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F8e7db5fb-c89e-4876-96ac-f649a378990f%2FUntitled.png?table=block&id=c6ff998f-180d-4304-b7ff-dacb172fe8a6&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=2070&userId=&cache=v2)

**优点**：

* 开源
* Server 对设备性能要求较低
* 支持设备多，自带多种监控模板
* 支持分布式集中管理，有自动发现的功能，可以实现自动化监控
* 开放式接口，扩展性强，容易编写插件
* 支持 API，方便与其他系统结合

**缺点**：

需要在监控主机上安装 agent，所有的数据都存储在数据库中，产生的数据源很大。

## 案例

只靠单纯的理论堆积对于学习技术来说是非常空洞的，在这根据这篇公众号中的文章————《[猪八戒网十年 DevOps 演进之路](https://mp.weixin.qq.com/s/475WM9KNbGglWsvuqNVUyg)》来活灵活现地对 DevOps 的使用方式和场景来进行说明。

### 初创期

初创期是从 09 年开始的。当时其实移动互联网还未完全兴起，除了许多已经规模庞大的公司之外，很多初创时期的潜力股们还并未在开发上形成一个优雅的规范。原作者甚至坦言，「连发布代码也是用的最传统的 FTP 上传方式」。这里不禁让我想到了我的本科毕设，将 jar 包通过 FTP 上传到阿里云服务器运行的方式，简直如出一辙。

当时该公司的第一版的“DevOps”如下图所示：

![初创期](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F1e72bdc6-efa7-4497-b9db-d5714d56581e%2FUntitled.png?table=block&id=a52f7721-0e9c-4246-9e85-81f391bd2710&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=1310&userId=&cache=v2)

流程可以说是再简单不过了。他们当时是使用 SVN 来管理代码，两个固定的分支，一个是测试环境，一个是发布的线上生产环境。逻辑就是代码编写完毕后，commit 到 SVN 服务器，然后推送到源码服务器，一个分支用来测试，另一个分支用来发布。

其实这个逻辑对于我们个人编写一些练手的应用，发布到 Github 上几乎是同样的方式。只不过我们个人编写应用可能还会省去测试的步骤。总之，非常好理解，「一路推送」，编写前从源码服务器中拉取进行同步即可。

### 业务增长期

当业务进行到增长期时，如果仅仅是简单地随意上传发布会导致线上的环境十分不稳定，配置文件的更新会导致线上环境服务器错误。举个简单的例子，如果我们从 Github 上 clone 一个前端项目或者是 Android 项目，那么有可能在我们本地运行时会跑不起来。前端项目有可能会需要更新相应的框架版本，Android 项目则有可能因为 gradle 的版本不一致而构建失败。为什么会出现这些原因呢？

这是因为项目开发并不是完全从零开始，而是会在线引入很多第三方优秀的框架或者组件。当这些框架的版本更新后，很有可能与开发环境和生产环境不一致，从而导致运行不起来或者某些功能失效。

当然，原作者介绍在这一时期最大的变化还是使用到了**虚拟化**技术。所以，他们引入了一个自己定义的 SYN 系统，作用如下：

* 权限控制（管理系统一般都需要权限控制）
* 引入`exclude_list`来解决配置文件变更的问题（之前提到的 Chef 和 Puppet 主要就是解决配置文件一致的问题）
* 工程代码映射关系
* 代码分发

![业务增长期](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fb409d106-bf7f-4e6c-82f3-197853ad7cdb%2FUntitled.png?table=block&id=e6729caf-c6ed-40b3-ae37-790affd2fa3f&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=1660&userId=&cache=v2)

如上图所以，还将应用进行了独立部署。

### 多语言

当业务规模继续庞大时，开发语言从单纯的 PHP 语言到大量引入 Java 语言，那么，就需要通过 Jenkins 来解决 CI问题。

这一阶段在代码提交上已经改用了 Git 来处理。通过将 Git 服务器与 Jenkins 连接，所有的推送服务都通过 Jenkins 来处理。除此之外，为了更方便地 CD，使用了多套测试环境。

![多语言开发时期](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fbf0c9a65-b2e0-4e23-99d7-4c9aa6354874%2FUntitled.png?table=block&id=3643c479-545d-4bec-aade-1f8e1887b181&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=1660&userId=&cache=v2)

### 微服务与容器化

时间来到了 2016 年，从这一年开始，其实才算是真正地通过 DevOps 来研发项目。下面是一个常见的 DevOps 的架构图：

![微服务与容器化](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Ffdd388c4-4cee-44e0-8ef5-0233291063f4%2FUntitled.png?table=block&id=82759e54-b374-4589-bfcc-a793dcfe486b&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&userId=&cache=v2)

简要说明一下。Developer push 代码到 GitLab，GitLab 与 Jenkins 相互连接，同时 Jenkins 拥有环境版本一致的开发组件库，保证生成的成品与线下开发环境的一致。CMDB 的作用主要是获取信息，确保信息完善，使得代码、工程、资源的 100% 关联。Ops 方面，可以通过基于 JIRA 的研发流程管控。通过 JIRA 管理研发流程，发布的时候严格校验状态，确保所有发布均符合研发规范。SonarQube 是什么作用呢？我们之前提到过，负责安全评审、每次提交代码的自动扫描以及发布的安全测试等，这样可以确保每次提交的代码是安全的（是代码安全，并非指测试完全通过、功能没有 BUG）。

回到 Jenkins 上，通过 build 生成成品并发布，一部分传递元数据到封装了流水线和多个 k8s 集群的容器中，一部分推送到虚拟化环境中。其中，90% 的工程都运行在容器中，因为容器化相比虚拟化有很多优势，例如减少资源、IT 成本，解决跨机房部署等。

让我们看看容器云项目的核心组件：

![容器云项目核心组件](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F4fe75e54-84a5-4a44-971a-1f4ee6fd4091%2FUntitled.png?table=block&id=c253e040-efc5-44cd-b4a1-8c30c9e8d5b9&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=2160&userId=&cache=v2)

最终经过测试后，通过 OpenStack 发布到华为云服务器中。最终运维人员可以通过监控中心对性能等进行实时的监控。

## 结论

DevOps 是一次革命，主要是是为了消除拥有大规模 IT 部门的大型企业中，开发团队和运维团队之间由于历史原因而产生的隔阂与孤立所造成的混乱现状。

例如，开发人员会说：

> 我无法帮助你解决问题，因为在我的 Tomcat 上工作很正常，而且我完全不懂你所用的 Websphere。

运维人员则会说：

> 我们不能从生产数据库中给你提取这张表，里面包含了与客户有关的机密数据。

所以，企业通过应用 DevOps 原则和实践，例如自动化部署、持续交付等，都能够获益匪浅。

![](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fdb9a6c8d-a5d9-4797-bb4c-6af83bff9265%2FUntitled.png?table=block&id=612d3d94-87c4-4bef-81ad-4ea6ba320c7c&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=1640&userId=&cache=v2)

