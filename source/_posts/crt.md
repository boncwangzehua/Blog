title: CRT链接不上Linux可能原因
author: 王泽华
date: 2017-12-09 17:14:54
tags:
---
1、有可能Linux系统中没有安装ssh服务
```
sudo apt-get install openssh-server
```
2、安装好了ssh服务，如果CRT连接Linux报密码错误提示，需要修改ssh配置文件
```
sudo vi /etc/ssh/sshd_config
```
找到#PermitRootLogin XXX 这一行，修改XXX为yes，就能使用root用户登录了		

3、Linux中开启root用户命令
```
sudo passwd root
```
然后设置root用户密码。

4、Linux切换用户命令
```
su 用户名
```