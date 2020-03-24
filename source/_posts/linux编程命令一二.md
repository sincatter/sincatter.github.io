---
title: linux编程命令一二
tags:
  - 备忘
  - 命令
categories:
  - 备忘
toc: false
date: 2020-03-14 23:08:44
---

系统
## fdisk:磁盘分区挂载

* fdisk -l 查看磁盘挂载情况

* fdisk /dev/sdx 修改/dev/sdx分区操作，以下为用过的一些命令
	* m 帮助
	* d 删除已存在的分区
	* p 查看已存在的分区
	* n 新增分区，并可指定分区大小
	* t 改变文件系统格式对应的id，只是修改id，后续还要利用mkfs命令进行格式化
	* l 列出所有文件系统格式对应id
	* w 保存所作的分区修改

* mkfs 格式化分区为指定类型的文件系统
	* -V 显示详细信息
	* -t 指定目的文件系统
	* -c 执行格式化之前检查磁盘坏道情况
	* 示例: mkfs -V -t ext3 -c /dev/sda1
	* mkfs.ext3/mkfs.fat32之类更形象的命令，实质上也是在调用mkfs命令

* dd 拷贝文件块
	参考[pp命令详解](https://www.cnblogs.com/misswangxing/p/10911969.html)

## 操作
### 修改软件源
以清华Ubuntu 18.04 LTS软件源为例
```shell
# 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse

# 预发布软件源，不建议启用
# deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
```
小工具：在线获取源配置[TIP](https://mirror.tuna.tsinghua.edu.cn/help/ubuntu/)