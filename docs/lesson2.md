# 安装WSL Ubuntu-22.04

## 什么是WSL

> Windows Subsystem for Linux - 适用于Linux的Windows子系统
它

## 安装Containerlab

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


