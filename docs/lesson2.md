# 安装Containerlab

## 安装Ubuntu server 22.04.4

CPU: 1 Provessor 6 Cores，勾选虚拟化; 内存：20G；硬盘：100G；网络：桥接；

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


