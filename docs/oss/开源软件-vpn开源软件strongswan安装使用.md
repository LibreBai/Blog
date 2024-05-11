# strongswan 编译使用

## 编写时间

2024-04-27 14:22:50

## 参考链接

- [strongswan github 官网](https://github.com/strongswan/strongswan) 
- [快速配置](https://docs.strongswan.org/docs/5.9/config/quickstart.html)
- [配置参考](https://rhel.pkgs.org/9/epel-x86_64/strongswan-5.9.10-1.el9.x86_64.rpm.html)


## 获取

### git 获取

1. git clone https://github.com/strongswan/strongswan.git

### 安装介绍

strongswan 官网显示，centos 每个版本支持的 strongswan 版本不同，centos7 支持 5.7.2 版本；centos8 支持 5.9.10 版本；centos9 支持 5.9.10 版本。


## 安装

### 源码编译安装（放弃）

```bash
yum install g++
yum install glib2-devel
yum install NetworkManager-libnm.x86_64
yum install NetworkManager-libnm.i686
yum install NetworkManager-libnm-devel.x86_64
yum install libnm
yum install gperf
```

**抱歉，编译不过去，各种问题，放弃。**

### rpm 安装

```bash
wget https://dl.fedoraproject.org/pub/epel/9/Everything/x86_64/Packages/s/strongswan-5.9.10-1.el9.x86_64.rpm
rpm -ivh strongswan-5.9.10-1.el9.x86_64.rpm
```

配置文件位于：/etc/strongswan/。

## 测试

**测试失败。**

**此软件说明及其不友好，使用给出的示例图及 .conf 都无法顺利配置。或者水平不够，没法理解相关配置使用**。
