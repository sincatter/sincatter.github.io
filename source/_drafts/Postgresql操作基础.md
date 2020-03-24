---
title: Postgresql操作基础
tags: []
originContent: ''
categories: []
toc: false
---

# psql
psql 参数
* 通用参数
-c, --command=COMMAND：执行一条命令（或内置SQL）然后退出
-d, --dbname=DBNAME：默认连接的数据库
-f, --file=FILENAME：执行指定文件中的命令，然后退出
-l, --list：显示所有可用数据库名，然后退出
-v, --set=, --variable=NAME=VALUE：设置psql变量
-V, --version：显示版本信息，然后退出
-X, --no-psqlrc：不读取启动文件（系统内置的psqlrc及自定义的~/.psqlrc都不启动）
-1 ("one"), --single-transaction：执行单条存储过程
-?, --help：显示帮助信息，然后退出
* 连接选项
-h, --host=HOSTNAM：连接数据库服务器的主机IP或套接字目录（默认为“local socket”）
-p, --port=PORT：连接数据库服务器的端口号（默认为“5432”）
-U, --username=USERNAME：要连接数据库服务器的用户名
-w, --no-password：不提示密码。如果服务器需要密码验证而密码不可通过其他方式 （比如.pgpass文件）获得，则连接尝试将失败
-W, --password：强制使用密码
* 输入输出选项
-a, --echo-all：在读取行时向标准输出打印所有内容
-e, --echo-queries：打印发送到服务器的内容
-E, --echo-hidden：显示内部命令生成的查询
-L, --log-file=FILENAME：将查询记录到指定的文件中
-n, --no-readline：命令行编辑中不使用readline
-o, --output=FILENAM：将查询输出定向到指定的文件中
-q, --quiet：静默处理（除查询输出外无其它输出）
-s, --single-step：单步模式运行。即：每个命令在发往服务器之前都要提示用户确认，用这个选项也可以取消执行。此选项主要用于调试脚本
-S, --single-line：单行运行模式，这时每个命令都将由换行符结束
* 输出格式选项
-A, --no-align：切换为非对齐输出模式（默认为对齐模式）
-F, --field-separator=STRING：指定输出字段的分隔符（默认为“|”）
-H, --html：HTML表格输出模式
-P, --pset=VAR[=ARG]：切换打印风格
-R, --record-separator=STRING：设置非对齐输出的记录分隔符
-t, --tuples-only：仅输出数据行（关闭列名称和结果行计数脚本等）
-T, --table-attr=TEXT：设置HTML表格输出模式时的HTML属性（width、border等）
-x, --expanded：打开扩展表格式模式
-z, --field-separator-zero：为未对齐的输出设置字段分隔符为零字节
-0, --record-separator-zero：为未对齐的输出设置记录分隔符为零字
## 数据库操