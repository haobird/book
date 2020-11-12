# 部署步骤

### 目标

* 自动下载视频
* 自动寻找热门影视
* 备份照片、划分用户
* 磁盘阵列设置
* 远程访问

### 系统比对

一、unraid

缺点：
* 重启配置丢失 
* docker-compose

优点：
* 系统从 U 盘启动，启动后系统在内存中
* 集成插件支持，集成 Docker 支持，支持虚拟机
* 支持硬盘无访问自动休眠

二、OpenMediaVault

优点：
* 一个稳定的系统，Debian 上的扩展也非常多
* Docker 也支持
* 配合 mergerfs 可以实现多物理盘组合，实现 UnRaid 中随时添加磁盘的特性
* 配合 SnapRAID 可以实现冗余备份
* 配合 Prometheus 和 Grafana 可以对 NAS 进行全面的监控，弥补起管理后台监控的不足
* 最重要的就是 OpenMediaVault 是开放源代码的

三、Ubuntu
优点：
* 所有设置都可以自定义
* 

### 前期步骤

1. 格式化优盘
2. 移动已经解压的文件到根目录
3. 执行.bat 文件


#### 激活系统




### 系统设置



#### 配置磁盘

5盘位 ：① 缓存盘 ② 校验盘 ③ 用户盘 ④ 共享盘 ⑤ 共享盘

#### 设置时区和时间

Use NTP: Yes

推荐NTP：

ntp1.aliyun.com 阿里云NTP

time.apple.com 苹果NTP

hk.pool.ntp.org
jp.pool.ntp.org
kr.pool.ntp.org


#### 安装应用商店

[参考链接](https://forums.unraid.net/topic/38582-plug-in-community-applications/)

plugins -> Install Plugin

```
https://raw.githubusercontent.com/Squidly271/community.applications/master/plugins/community.applications.plg
```

#### 安装 CLI tools (iftop, iotop, screen, kbd, etc.)

[参考链接](https://www.xxb.me/unraid/yuque-unraid02/)

可以直接在应用商店搜索  `NerdPack` 或者 安装插件

```
https://raw.githubusercontent.com/dmacias72/unRAID-NerdPack/master/plugin/NerdPack.plg
```

#### 安装插件

* CA Application Auto Update
* CA Cleanup Appdata
* CA Config Editor
* Community Applications
* Dynamix System Buttons
* Dynamix System Information
* Dynamix System Statistics
* Dynamix System Temperature
* Fix Common Problems
* Recycle Bin
* Unassigned Devices
* Unassigned Devices Plus
* User Scripts

#### 配置安装应用

* NextCloud
* transmission
* aria2
* flexget
* frp
* Jellyfin

#### 配置自定义应用


#### 个性化配置

#### 功能准备

1. 创建docker网络连接
2. 启用docker 


#### 旁路路由OpenWrt

实现：
* 去广告
* V2ray
* 

#### 自动按照脚本

* 增加hosts
* 安装docker-compose 
```
curl -L "https://github.com/docker/compose/releases/download/1.26.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
 chmod +x /usr/local/bin/docker-compose
```
* 
