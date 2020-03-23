# DevOps

<details>
<summary>什么是DevOps?</summary><br><b>

Amazon:
"DevOps 集文化理念、实践和工具于一身，可以提高组织高速交付应用程序和服务的能力，与使用传统软件开发和基础设施管理流程相比，能够帮助组织更快地发展和改进产品。这种速度使组织能够更好地服务其客户，并在市场上更高效地参与竞争。"

Microsoft:
"DevOps 是人员，流程和产品的结合，可为我们的最终用户持续交付价值。 “Dev”和“Ops”的收缩是指取代孤立的开发和运营来创建多学科的团队，这些团队现在可以与共享的高效实践和工具一起工作。 DevOps 的基本实践包括敏捷计划，持续集成，持续交付以及对应用程序的监视。"

Red Hat:
"DevOps 描述了加速想法（例如新软件功能，增强要求或错误修复）从开发到在生产环境中进行部署的过程，可以为用户提供价值。 这些方法要求开发团队和运营团队经常沟通，并以同情他人的态度对待他们的工作。 可伸缩性和灵活的配置也是必要的。 使用 DevOps，那些最需要电源的人可以通过自助服务和自动化来获得电源。 通常在标准开发环境中进行编码的开发人员会与 IT 运营紧密合作，以在不牺牲可靠性的情况下加快软件的构建，测试和发布的速度。"

</b></details>

<details>
<summary>DevOps的好处是什么? DevOps能让我们获得什么?</summary><br><b>

可以提到以下几点：

- 合作
- 改善交付
- 安全
- 速度
- 规模
- 可靠性

</b></details>

<details>
<summary>DevOps的反例是什么?</summary><br><b>

- 不允许在周五推进生产
- 一个特定的人负责不同的任务。例如，只有一个人被允许合并其他人的代码
- 对待生产环境的方式与开发环境不同。例如，没有在开发环境中实现安全性

</b></details>

<details>
<summary>持续集成是什么?</summary><br><b>

在软件开发过程中，频繁地将代码集成到主干上，然后进行自动化测试。
持续集成的目的，就是让产品可以快速迭代，同时还能保持高质量。它的核心措施是，代码集成到主干之前，必须通过自动化测试。只要有一个测试用例失败，就不能集成。

</b></details>

<details>
<summary>什么是持续部署?</summary><br><b>

持续部署（Continuous Deployment）：代码通过评审以后，自动部署到生产环境，是持续交付的下一步。持续部署的目标是，代码在任何时刻都是可部署的，可以进入生产阶段。持续部署的前提是能自动化完成测试、构建、部署等步骤。

</b></details>

<details>
<summary>什么是持续交付?</summary><br><b>

持续交付（Continuous Delivery）：频繁地将软件的新版本，交付给质量团队或者用户，以供评审。如果评审通过，代码就进入生产阶段。持续交付可以看作持续集成的下一步。它强调的是，不管怎么更新，软件是随时随地可以交付的。
持续交付的目标是拥有一个可随时部署到生产环境的代码库。
在持续交付中，每个阶段（从代码更改的合并，到生产就绪型构建版本的交付）都涉及测试自动化和代码发布自动化。在流程结束时，运维团队可以快速、轻松地将应用部署到生产环境中。

</b></details>

<details>
<summary>您熟悉哪些CI / CD最佳实践？ 或您认为什么是CI / CD最佳实践？</summary><br><b>

</b></details>

<details>
<summary>你用什么工具或系统来做以下工作?</summary><br><b>

- CI/CD：Jenkins, Circle CI, Travis
- 配置架构：Terraform, CloudFormation
- 配置管理：Ansible, Puppet, Chef
- 监控告警：Prometheus, Nagios
- 日志：Logstash, Graylog, Fluentd
- 代码审查：Gerrit, Review Board
- 代码覆盖：Cobertura, Clover, JaCoCo
- 测试：Robot, Serenity, Gauge

</b></details>

<details>
<summary>当选择工具或技术的时候，你会怎么考虑?</summary><br><b>

回答时提到以下几点：

- 成熟的或尖端的
- 社区大小
- 架构方面，如有无 agent、中心化或去中心化

</b></details>

<details>
<summary>解释可变和不可变的基础架构</summary><br><b>

可变架构（mutable infrastructure）：可变架构是 IT 服务器基础架构，能够定期直接进行修改和更新。传统上，由于可变方法提供更大的短期灵活性，服务器体系结构是可变的。 但是，可变的基础结构会以不可变的基础结构为可能，但要以不同服务器部署之间的可预测性和一致性为代价。

在可变的架构中，将更改应用到现有架构之上，并且随着时间的推移，架构会建立更改历史记录。遵循可变架构范例的工具如 Ansible，Puppet 和 Chef 。

在不可变的架构范例中，每项更改实际上都是一个新的架构。因此，对服务器的更改将导致变为新服务器而不是对其进行更新。遵循不变基础架构范例的技术如 Terraform 。

</b></details>

<details>
<summary>你熟悉哪些交付软件的方法? 这些方法的优势和劣势是什么?</summary><br><b>

- 构建 - 将所有文件收集到一个构建文件中（如 tar），然后交付给用户
- 打包 - 取决于操作系统，你可以用操作系统的包管理工具（如 rpm），通过包管理命令来安装、卸载、更新软件
- 镜像 - 只要能包含所有能让这个软件跑起来所需的东西就行，不管是 VM 或者容器镜像

</b></details>

<details>
<summary>什么是缓存? 缓存如何工作的? 为什么缓存这么重要?</summary><br><b>

</b></details>

<details>
<summary>解释无状态和有状态</summary><br><b>

无状态应用不会在主机中存储任何数据，因此非常适合水平扩展和微服务。
有状态应用依赖于存储来保存状态和数据，通常数据库是有状态应用。

</b></details>

<details>
<summary>描述设置服务器的工作流(Apache, IIS, Tomcat等)</summary><br><b>

</b></details>

<details>
<summary>解释”开源“</summary><br><b>

</b></details>

<details>
<summary>描述一下你设计或实施的服务、应用、项目的架构</summary><br><b>

</b></details>

<details>
<summary>你熟悉的测试类型?</summary><br><b>

Styling, unit, functional, API, integration, smoke, scenario, ...

You should be able to explain those that you mention.
</b></details>

<details>
<summary>若你需要周期性地在操作系统上安装不同的软件包，你会怎么做?</summary><br><b>

It can be as simple as one Ansible (or other CM tool) task that runs periodically with Cron. In more advanced cases, perhaps a CI system.
</b></details>

<details>
<summary>SRE与DevOps的对比</summary><br><b>

</b></details>

<details>
<summary>什么是依赖性? 它是如何适应DevOps的?</summary><br><b>

Reliability, when used in DevOps context, is the ability of a system to recover from infrastructure failure or disruption. Part of it is also being able to scale based on your organization or team demands.
</b></details>

<details>
<summary>SRE团队的责任是什么?</summary><br><b>

One can argue whether it's per company definition or a global one but at least according to a large companies, like Google for example, the SRE team is responsible for availability, latency, performance, efficiency, change management, monitoring, emergency response, and capacity planning of their services
</b></details>

<details>
<summary>什么是错误预算?</summary><br><b>

</b></details>

<details>
<summary>什么是MTTF（平均故障时间）和MTTR（平均维修时间）？这些指标可帮助我们评估什么?</summary><br><b>

</b></details>

<details>
<summary>什么是尸检（post-mortem）会议？ 它为什么如此重要?</summary><br><b>

</b></details>

<details>
<summary>什么是“架构即代码”？ 你熟悉IAC的什么实现？</summary><br><b>

</b></details>

<details>
<summary>你如何管理构建工件？</summary><br><b>

</b></details>

<details>
<summary>你正在使用/首选哪种持续集成解决方案，为什么？</summary><br><b>

</b></details>

<details>
<summary>熟悉或使用了哪些部署策略？</summary><br><b>

</b></details>

<details>
<summary>如何为CI/CD资源（如服务器，存储设备等）施行计划容量</summary><br><b>

</b></details>

<details>
<summary>如何为依赖于其他应用的应用构建或实现CD？</summary><br><b>

</b></details>

<details>
<summary>如何衡量CI/CD的质量？是否使用任何度量标准或KPI来衡量质量？</summary><br><b>

</b></details>

<details>
<summary>什么是配置漂移？它会引起什么问题？</summary><br><b>

简单来说：就是配置不同步，多个服务器有着相似或相同的配置，但在配置更新时，只有部分服务器更新了配置，造成了各个服务器之间配置相对不同步。会造成很多问题，且不易排查。

</b></details>

<details>
<summary>如何应对配置漂移？</summary><br><b>

</b></details>

<details>
<summary>是否有测试跨项目变更（又称交叉依赖）的经验？</summary><br><b>

交叉依赖：当有多个独立项目，而你想相互构建而不是单独构建

</b></details>

<details>
<summary>你是否为开源项目做出了贡献？</summary><br><b>

</b></details>
