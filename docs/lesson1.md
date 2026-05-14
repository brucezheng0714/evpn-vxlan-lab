# 第一课：为什么我开始从 EVE-NG 转向 Containerlab

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



### Ubuntu Server 24.04.4 LTS 下载

<a href="https://ubuntu.com/download/alternative-downloads"
target="_blank"
rel="noopener noreferrer">
Ubuntu 官方下载地址
</a>

<br>

<a href="https://mirrors.tuna.tsinghua.edu.cn/ubuntu-releases/24.04.4/"
target="_blank"
rel="noopener noreferrer">
清华大学 Ubuntu 镜像站
</a>
