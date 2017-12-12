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
6.查看进程运行状态
```
ps -ef | grep tomcat //查看所有tomcat的运行状态
```
7.压缩命令：

　　命令格式：`tar  -zcvf   压缩文件名.tar.gz   被压缩文件名`

 可先切换到当前目录下。压缩文件名和被压缩文件名都可加入路径。

 

8.解压缩命令：
	
1.解压.tar.gz包
　　命令格式：tar  -zxvf   压缩文件名.tar.gz
2.解压 zip包
	命令格式 unzip 压缩文件名.zip

　　解压缩后的文件只能放在当前的目录。
  
 当运行startup.sh时 如果报错为 
 
 ```
 Neither the java_home nor the jre_home environment variable is defined
 ```
 
 linux配置java环境
 
 1.下载linux下的jdk包。放到/usr/local下
 
 2.解压jdk包
 
 3.编辑 /etc/profile文件`sudo vim etc/profile` 在文件最后加上如下代码
 ```
 JAVA_HOME=/usr/java/jdk1.8.0_151 //修改为自己相应的目录

 PATH=$JAVA_HOME/bin:$PATH

 CLASSPATH=$JAVA_HOME/jre/lib/ext:$JAVA_HOME/lib/tools.jar

 export PATH JAVA_HOME CLASSPATH
 ```
 
 编辑文件 /usr/local/tomcat/bin/catalina.sh (根据你自己的jdk路径进行修改) 在文件的正文开头，即正式代码前，大概在99行添加如下代码
 
 ```
export JAVA_HOME=/usr/local/jdk
export JRE_HOME=/usr/local/jdk/jre
 ```
 
 