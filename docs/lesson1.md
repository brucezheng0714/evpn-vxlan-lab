# 为什么我开始从 EVE-NG 转向 Containerlab

## EVE-NG 的优点

EVE-NG 作为传统的网络虚拟化实验平台，拥有成熟的 GUI 界面和大量社区资源。

---

## EVE-NG 的问题

随着 EVPN/VXLAN 实验规模越来越大，传统 VM 实验逐渐暴露出：

- 内存占用高
- 启动速度慢
- 节点扩展困难
- 自动化能力有限

### EVE 官方镜像指导文档

<a href="https://www.eve-ng.net/index.php/documentation/howtos/howto-add-cisco-nexus-9000v-switch/"
target="_blank"
rel="noopener noreferrer">
EVE 指导文档 - Nexus9K
</a>

<br>

<a href="https://www.eve-ng.net/index.php/documentation/howtos/howto-add-arista-veos/"
target="_blank"
rel="noopener noreferrer">
EVE 指导文档 - Arista vEOS
</a>

---

## Containerlab 的优势

EVE运行的是完成的VM

Containerlab 基于 Linux Container 容器技术，可以快速部署大规模网络实验。cEOS少了
- BIOS
- 虚拟硬件
- 完整Linux OS

所以Containerlab启动速度和资源占用低很多

| 对比项 | vEOS-lab（VM） | cEOS（Container） |
|---|---|---|
| 架构类型 | 完整虚拟机（QEMU/KVM） | Docker 容器 |
| 底层依赖 | 虚拟化 | Linux Container |
| 是否需要完整 Guest OS | 是 | 否 |
| 启动方式 | BIOS → Kernel → EOS | 直接启动容器进程 |
| 空闲内存占用 | 2~4GB | 700MB~1.5GB |
| EVPN/VXLAN场景内存 | 3~5GB | 1.5~2.5GB |
| 磁盘占用 | 大（多个GB） | 小很多 |
| 10节点实验资源需求 | 很高 | 可接受 |
| 20节点实验 | 很吃力 | 仍可运行 |
| YAML自动化 | 不支持 | 原生支持 |
| Wireshark抓包 | 一般 | 非常方便 |
| 批量实验 | 麻烦 | 非常适合 |
| EVPN大规模实验 | 资源容易爆 | 更适合 |

## 什么是WSL

**Windows Subsystem for Linux - 适用于Linux的Windows子系统**

它允许用户直接在Windows里运行Linux环境，而无需：
- VMware
- VirtualBox
- 双系统

即可获得完整的Linux命令行环境\

## 什么是Containerlab
Containerlab 是一个基于 Linux 容器的网络实验平台，用于快速搭建和管理网络拓扑。

相比传统的 EVE-NG、GNS3 等虚拟机方案，Containerlab 使用容器运行网络设备，因此：

- 启动速度更快
- 内存占用更低
- 更适合大规模 EVPN/VXLAN 实验
- 更容易与自动化工具结合

用户只需要编写一个 YAML 拓扑文件，即可一键创建：

- 网络设备
- 链路连接
- 管理 IP
- 实验环境
