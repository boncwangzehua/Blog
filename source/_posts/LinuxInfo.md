title: Linux中在tomcat部署项目的一些命令
author: 王泽华
date: 2017-12-11 19:42:09
tags:
---
###### Linux中在tomcat中部署项目的命令
1.将tomcat包导入linux系统中
```
cd /usr/local/相应目录
rz 会打开资源管理器，选择要上传的文件即可
unzip 解压zip包
```
2.将要部署的项目（war包）放到tomcat的webapps目录下
```
mv 目标文件 目标目录
```
3.进入tomcat的bin目录，启动tomcat 

`./startup.sh` 有可能会报 permisstion defined 授予权限即可`chmod 755 startup.sh`


4.查看日志，进入tomcat的logs目录
```
tail -f catalina.out
```
5.停止tomcat 进入tomcat的bin目录
```
./shutdown.sh
```
