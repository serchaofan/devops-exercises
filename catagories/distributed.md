# Distributed

<details>
<summary>解释分布式计算和分布式系统</summary><br><b>

"在很多机器上运行大量进程，只是消息传递是通过不可靠的网络，并伴随可变的延迟，而且系统可能遭遇部分错误、不可靠的时钟和进程暂停。"

"在物理层面分离但在逻辑层面连接的系统"
</b></details>

<details>
<summary>什么会导致系统错误</summary><br><b>

- 网络
- CPU
- 内存
- 磁盘
  </b></details>

<details>
<summary>什么是CAP定理？</summary><br><b>

CAP 定理也称布鲁尔定理

根据 CAP 定理, 对于一个分布式计算系统来说，不可能同时满足以下三点：

- 一致性（Consistency） （等同于所有节点访问同一份最新的数据副本）
- 可用性（Availability）（每次请求都能获取到非错的响应——但是不保证获取的数据为最新数据）
- 分区容错性（Partition tolerance）（以实际效果而言，分区相当于对通信的时限要求。系统如果不能在时限内达成数据一致性，就意味着发生了分区的情况，必须就当前操作在 C 和 A 之间做出选择。）
  </b></details>

<details>
<summary>以下设计有什么问题，如何改善?<br>
<img src="images/distributed/distributed_design_standby.png" width="500x;" height="350px;"/>
</summary><br><b>
1. 切换很花时间
2. 主节点在运行而从节点不运行，浪费资源
</b></details>

<details>
<summary>以下设计有什么问题，如何改善?<br>
<img src="images/distributed/distributed_design_lb.png" width="700x;" height="350px;"/>
</summary><br><b>
如果负载均衡器挂了，那么就不能访问后端应用了

改进：

- 添加另一台负载均衡器
- 两台负载均衡器都添加 DNS 的 A 解析
- 使用消息队列
  </b></details>

<details>
<summary>什么是无共享架构（Shared-Nothing Architecture）？</summary><br><b>

数据通常是从单个非共享源中获取并检索的，该源通常专门连接到一个节点，而该体系结构中，请求可以到达多个节点之一，并且数据将从一个共享节点中获取（存储、内存等）。

</b></details>

<details>
<summary>Explain the Sidecar Pattern</summary><br><b>
</b></details>
