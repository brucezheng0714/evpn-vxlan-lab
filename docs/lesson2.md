# 安装WSL Ubuntu-22.04

## 什么是WSL

**Windows Subsystem for Linux - 适用于Linux的Windows子系统**

它允许用户直接在Windows里运行Linux环境，而无需：
- VMware
- VirtualBox
- 双系统

即可获得完整的Linux命令行环境

## 安装WSL
1. 开启Windows功能
![开启wsl](images/wsl需开启Windows功能.png)

### 更新Ubuntu软件：
```bash
sudo apt update && sudo apt upgrade -y
```

[Containerlab使用说明传送门](https://containerlab.dev/install/)

### 安装Containerlab：
```bash
curl -sL https://containerlab.dev/setup | sudo -E bash -s "all"
```
### 下载Arista公司的cEOS镜像


### 导入cEOS镜像
```bash
 sudo docker import cEOS64-lab-4.35.3.1F.tar ceos:4.35.3.1F
```


