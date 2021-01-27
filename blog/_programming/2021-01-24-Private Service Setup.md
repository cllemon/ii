---
title: 私有服务器搭建
summary: 记录搭建私有服务器的流程，以 CentOS 7 为操作系统，主要用于存放个人网站、系统、代码仓库、CI/CD、Private NPM、等等...
date: 2021-01-24
author: Wooden Kite
location: huainan.AnHui
# tags:
#   - Linux
  # - 服务器
---

<span style="font-size:100px;"> 🚧 </span><span style="color: gray;">建设者...</span>

## 机器配置

| 机器 | 配置 | 购买时间 |
| -- | --| -- |
| 闲置笔记本 |  双核 Inter Core i5；<br> 2G 独立显卡；<br> 500G 机械硬盘；<br> 原系统 Windows 7  | 2013年|

## CentOS 7 系统安装

1. 下载 `CentOS 7` 镜像 [CentOS-7-x86_64-DVD-1810.iso](https://www.centos.org/download/)

2. 将镜像写入 `U盘` （使用 [UltraISO](https://cn.ultraiso.net/xiazai.html) 工具）

3. 插入 `U盘` 开机启动

4. 在启动界面 `选择第一项` -> `按下 Tab 键` -> `修改屏幕底部命令为：vmlinuz initrd=initrd.img inst.stage2=hd:LABEL="U 盘标签" quiet`

5. 安装

## 配置网络通道

## 实现外网访问（公网 IP）

## 结果
