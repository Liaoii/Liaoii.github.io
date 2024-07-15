title: '''使用Vagrant与VirtualBox创建虚拟机'''
catalog: true
date: 2024-07-15 16:46:33
subtitle:
header-img:
tags:



## 使用Vagrant与VirtualBox创建虚拟机

### 1. 安装Vagrant

- 下载[Vagrant](https://developer.hashicorp.com/vagrant/downloads)
- 安装Vagrant，安装地址为 E:\Applications\Vagrant
- 配置用户级别的环境变量 VAGRANT_HOME : E:\Applications\Vagrant\.vagrant.d

### 2. 安装VirtualBox

- 下载[VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- 安装VirtualBox，安装在 E:\Applications\VirtualBox
- 启动VirtualBox，在全局设定中设置虚拟机的默认安装位置，设置为 D:\VirtualBox VMs

### 3. 使用离线镜像安装Centos7系统

- 下载[Centos7镜像](https://app.vagrantup.com/boxes/search)，并将下载的镜像命名为 CentOS-7.box
- 在CMD中将镜像添加到Vagrant的管理列表中

```sh
vagrant box add centos7 E:\Applications\VirtualBox\CentOS-7.box
```

- 查看添加状态

```sh
vagrant box list
```

- 新建存放Vagrantfile信息的文件夹 D:\Vagrantfile\Centos7-1
- 在Vagrantfile文件中初始化虚拟机

```sh
vagrant init centos7
```

- 修改目录下的Vagrantfile文件来修改配置信息
- 启动虚拟机

```sh
vagrant up
```

### 4. 在线安装Centos7系统

- 新建文件夹：D:\Vagrantfile\Docker
- 使用管理员权限运行CMD
- 初始化 Vagrantfile

```
vagrant init centos/7 #该镜像名称与官方镜像仓库中的镜像名称一致
```

- 官方镜像仓库地址：https://app.vagrantup.com/boxes/search
- 修改目录下的Vagrantfile文件来修改配置信息
- 启动虚拟机

```
vagrant up
```

### 5. Vargant命令

- 启动虚拟机

```sh
vagrant up
```

- 关闭命令

```sh
vagrant halt
```

- 连接到服务器

```sh
vagrant ssh
```

### 6. 常见问题

**(1). 怎么将服务的登录方式从Public Key修改成Password**

在CMD连接到服务器并切换到root用户；修改/etc/ssh/sshd_config文件：PasswordAuthentication yes，PermitRootLogin yes；

### 7. 常用安装

```shell
yum install net-tools
yum install wget
```

