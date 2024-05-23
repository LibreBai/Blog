# GDB 调试工具使用

## 编写时间

1. 2024-05-23 09:21:41

## 参考链接

- [https://www.cnblogs.com/me115/p/3837960.html](GDB 初级使用)
- [https://blog.csdn.net/smallnat/article/details/42458697](GDB 长字符串无法全部输出问题)

## 功能简介

## 获取及安装

1. yum -y install gdb
2. 其他版本 linux 可以直接安装 gdb。

## 功能使用

### 启动

- gdb 程序名 # 针对程序不需要执行参数
- gdb --args # 针对程序有运行参数

### 打断点

- `break <function>`: 在函数开始处设置断点。
- `break <line_number>`: 在指定行设置断点，这个没用过，不太懂效果。
- `break <file>:<line_number>`:在指定文件的指定行设置断点。

- `info b`：显示当前已经设定的断点情况。
- `delete 断点号`：去掉某个断点。

- `enable/disable`：开启/暂停某个断点。


注：推荐在跟读代码时，使用第三种方式。

### 执行程序

- `run 简写 r`: 启动程序。
- `run <arguments>`: 启动程序并传递命令行参数。
- `continue 简写 c`：继续执行程序，直到下一个断点。
- `next 简写 n`：单步跟踪程序，遇到函数调用，直接调用，不进入函数。
- `step 简写 s`：单步调试如果有函数调用，进入函数。

以下是用的少的：
- `finish`：运行程序，直到当前函数完成返回，并打印函数返回时的堆栈地址和返回值及参数值等信息。

## 其他

- `list`：列出源代码。
- `list 函数名`：查看指定函数的函数内容。
- `bt`：当前运行的堆栈信息。

## 其他使用问题

### 打印内容长度很长的字符串

gdb 默认输出字符串长度有限制，默认只有200个字符。可以通过以下命令解除限制：

```bash
查看当前输出长度限制
(gdb) show print elements

解除限制
(gdb) set print elements 0
(gdb) show print elements 
Limit on string chars or array elements to print is unlimited.
```

