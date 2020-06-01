#  GeoServer Notes

组件名称：GeoServer 
安装文档：https://docs.geoserver.org/latest/en/user/installation/linux.html  
配置文档:  
支持平台：Debian家族 | RHEL家族 | Windows |macOS   

责任人：zxc

## 概要
GeoServer是 OpenGIS Web 服务器规范的 J2EE 实现，利用 GeoServer 可以方便的发布地图数据，允许用户对特征数据进行更新、删除、插入操作，通过 GeoServer 可以比较容易的在用户之间迅速共享空间地理信息。

## 环境要求

* 程序语言：  java
* 应用服务器：
* 数据库：
* 依赖组件：Jre 8或Jre 11
* 其他：

## 安装说明

本项目采用源码安装方式,直接从官网下载二进制文件,解压缩包。

下面基于不同的安装平台，分别进行安装说明。

### CentOS  

```shell
# 配置java环境(安装jre8或者jre11)


#下载二进制文件
mkdir /usr/share/geoserver 

cd /usr/share/geoserver(官网建议位置)

wget https://nchc.dl.sourceforge.net/project/geoserver/GeoServer/2.17.0/geoserver-2.17.0-bin.zip

#解压缩包
unzip geoserver-2.17.0-bin.zip

#用户授权
sudo chown -R USER_NAME /usr/share/geoserver/

#启动geoserver
systemctl start geoserver
systemctl enable geoserver

```
### Ubuntu (与centos相同)

```shell




```

## 路径

* 程序路径：/usr/share/geoserver
* 日志路径： /usr/share/geoserver/etc/.xml 
* 配置文件路径：/usr/share/geoserver/logs/keepme.txt
* 其他...

##配置

无

## 账号密码


### 数据库密码

如果有数据库  
无

* 数据库安装方式：
* 账号密码：

### 后台账号

如果有后台账号
* 登录地址  http://Your ip:8080/geoserver
* 账号密码  admin   geoserver
* 密码修改方案：密码存放在 /root/temp/etc/realm.properties


## 服务

本项目安装后自动生成：

备注：本项目安装后无服务,需自行编写服务

服务文件位置：/etc/systemd/system/geoserver.service

```
[Unit]
Description=geoserver
After=network.target

[Service]
Type=simple

Environment="GEOSERVER_HOME=/usr/share/geoserver"
ExecStart=/usr/share/geoserver/bin/startup.sh
ExecStop=/usr/share/geoserver/bin/shutdown.sh

[Install]
WantedBy=multi-user.target
                        

```

## 环境变量
echo  "export GEOSERVER_HOME=/usr/share/geoserver"   >>  ~/.profile
.  ~/.profile

## 版本号

通过如下的命令获取主要组件的版本号: 

```
# Check geoserver version
 cat  /usr/share/geoserver/VERSION.txt
```

## 常见问题

#### 有没有管理控制台？

*http://Your ip:8080/geoserver*即可访问控制台

#### 本项目需要开启哪些端口？
| item | port |
| ---- | ---- |
| java | 8080 |
| java | 8079 |
#### 有没有CLI工具？
无
## 日志

* 2020-05-15完成CentOS安装研究