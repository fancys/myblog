# Nacos基础spring cloud实现配置中心

## Nacos入门

### 添加maven依赖
pom添加maven管理
```maven
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-alibaba-dependencies</artifactId>
            <version>2.1.0.RELEASE</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```
然后添加`nacos-config`maven依赖。
或者直接添加`nacos-config`依赖
```maven
<dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-starter-alibaba-nacos-config</artifactId>
            <version>0.2.1.RELEASE</version>
        </dependency>
```
### 配置文件中管理

***注意***：配置文件应为：`bootstrap`,而不能为`application`。因为spring boot(spring cloud)首先加载的配置文件为`bootstrap`。

```yaml
spring:
  cloud:
    nacos:
      config:
        server-addr: 127.0.0.1:8848
        file-extension: your configuration format
        group: yourgourpname
        prefix: yourdataidname
```

## Nacos基本概念

### 命名空间、分组、dataid

### 版本管理

## 配置管理

### 配置动态刷新


### 自定义扩展dataId


### 配置文件优先级

