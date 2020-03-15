---
title: hexo更换电脑部署
tags:
  - 工具
  - 备忘
categories:
  - 备忘
toc: false
date: 2020-03-14 03:06:43
---

## 软件准备（node && npm）
官网下载nodejs(版本为:Linux 二进制文件 (x64))
![](https://gitee.com/sincatter/open_resources/raw/picture/static/nodejs_download.png)
```shell
sudo tar -xJf node-v12.16.1-linux-x64.tar.xz -C /opt/
sudo mv /opt/node-v12.16.1-linux-x64 /opt/nodejs
sudo ln -s /opt/nodejs/bin/node /usr/local/bin/node
sudo ln -s /opt/nodejs/bin/npm /usr/local/bin/npm
# 更换淘宝软件源
sudo npm config set registry https://registry.npm.taobao.org 
source ~/.bashrc 
```
检查安装完毕
```shell
npm -v
node -v
```
## 配置hexo
下载配置好的代码仓库，仓库存在两个分支hexo(文章分支)和master(静态文件分支)
```shell
git clone -b hexo  git@e.coding.net:sincatter/blog.git
```
安装hexo
```
sudo npm install -g hexo-cli
cd blog
npm install hexo --save
```