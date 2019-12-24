# Nacos安装

## 环境预备

+ 64 bit OS
+ 64 JDK
+ maven 3.2.x+

## 下载安装

### git下载打包
```shell
git clone https://github.com/alibaba/nacos.git
cd nacos/
mvn -Prelease-nacos clean install -U
ls -al distribution/target/

// change the $version to your actual path
cd distribution/target/nacos-server-$version/nacos/bin
```

### 下载安装包

也可直接从github上下载[最新安装包](https://github.com/alibaba/nacos/releases)。


### 持久化部署

Nacos自带`嵌入式数据库`，但在线上环境，我们一般将数据持久化到`高可用数据库`中。

#### 初始化`mysql`数据库

1、初始化数据脚本
[sql语句](https://github.com/alibaba/nacos/blob/master/distribution/conf/nacos-mysql.sql)

2、修改conf/application.properties数据库连接配置
```
spring.datasource.platform=mysql

db.num=1
db.url.0=jdbc:mysql://localhost:3306/nacos-config?characterEncoding=utf8&connectTimeout=1000&socketTimeout=3000&autoReconnect=true
db.user=root
db.password=youdontknow
```


## 启动与停止

如果git下载maven编译后，可在`distribution`文件夹中进入target目录，选择`nacos-server-${version}`并进入bin目录下找到脚本文件：
![](../img/nacos-bin.jpg)

运行startup脚本命令后，浏览器打开`http://localhost:8848/nacos`进入管理界面。
用户名密码默认为`nacos`。

## 引用
[官网](https://nacos.io/zh-cn/)

