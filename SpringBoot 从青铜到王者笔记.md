### 课程导读

Spring Boot 知识结构图

前端层面

FreeMarker集成	Thymeleaf集成	jsp 集成	webJar 使用

开发层面

常用注解	常用插件	配置文件	Mock测试	RESTful 接口	拦截器、监听器、过滤器、启动监听器	服务器推送技术 SSE	websocket	新一代web 技术栈webflux 简介

架构服务层面

日志框架集成、log4j2、logback		邮件发送、1基于模板、2html邮件、3内联附件与带附件	定时任务与异步任务实现（quartz等）	内置容器与外置打包、tomcat、jetty、Undertow	消息队列、ActiveMQ集成与基本使用RocketMQ集成与基本使用

持久层与Docker搭建数据库

Spring Session分布式	Spring Cache缓存	设计封装	多库多数据源、分布式事务	spring Data REST	基于Docker 快速安装学习环境数据库

数据库工具类库集成

NOSQL数据库、Spring Data Redis、Spring Data MongoDB

关系型数据库、JPA、Mybatis

文件对象存储

FastDFS



### springboot诞生的背景及其优势

springMVC 配置复杂，工作重复

使配置变简单

使监控变简单

使部署变简单

使开发变简单

遵循“约定优于配置”的原则，简化配置

可以完全脱离XML配置文件,采用注解配置和java Config

内嵌Servlet容器，应用可用jar包执行: java -jar快速完成项目搭建、整合第三方类库，方便易用

提供了starter POM，能够非常方便的进行包管理，简化包管理配置

与Spring cloud天然融合，spring boot是目前java体系内实现微服务最佳方案



### helloworld及项目结构介绍

安装好IDEA，IDEA商业版是收费软件配置好IDEA的maven环境
配置好IDEA的it环境
要求JDK的版本在8及其以上的版本

目录结构

| 目录名称       | 相对路径           | 主要用途                               | 国外称呼             |
| -------------- | ------------------ | -------------------------------------- | -------------------- |
| 源码目录       | src\main\java      | 存储源码                               | Source Folders是     |
| 资源目录       | src\main\resources | 存储静态资源、动态页面、配置文件       | Resource Folders     |
| 资源目录(传统) | src\main\webapp    | 作用同上(非必须,部署War包才需要此目录) | Web Resource Folders |
| 测试目录       | src\test\java      | 存储单元测试                           | Test Source Folders  |
| 目标输出       | $output            | 存储编译文件                           | Test Source Folders  |

### 需要先了解的核心概念

springBoot 不是要替换传统spring

自动装配

什么是 springboot start 

什么是 spring boot start parent

嵌入式容器

springData

JPA*	JDBC*	CouchDB	Cassandra	Solr	MongoDB	Neo4j	Redis

spring boot 2.x相对1.x重要的变化

·最低的JDK支持版本1.8

·内置嵌入式tomcat 8.5

.Thymeleaf3.0代替2.0

·默认数据库连接池已从 Tomcat 切换到HikariCP

.redis客户端默认使用Lettuce，替换掉Jedis

·响应式编程WebFlux,重要的变革，后续章节会详细展示

什么是 Spring Boot Starter

一组被依赖的第三方类库的集合

什么是 Spring Boot Starter Parent 

对引入的第三方依赖的版本号统一在父项目的定义中统一进行版本定义

嵌入式 Web 容器

嵌入式容器中默认引入了tomcat Web 容器

可以直接用命令执行jar ：java -jar .\boot-lanuch-1.0.jar

### 提高开发效率插件lombok

使用lombok插件的好处

如何安装lombok插件

使用lombok提高开发效率

idea-file-setting-plugins 中搜索lombok

install ，重启

使用在文件中写注解 

@Data 自动生成get\set 方法

@Slf4 自动生成日志

@Builder 链式注入初始化对象属性

@AllArgsConstructor 全参构造方法

@NoArgsConstructor 无参构造方法

### IDEA环境下代码热部署热加载

方法一∶使用Jrebel插件

安装插件，使用插件启动按钮进行部署，付费插件，兼容性不好，弃用

方法二:使用devtools

pom.xml中

```xml
<dependency>

	<groupId>org.springframework.boot</groupId>

	<artifactId>spring-boot-devtools</artifactId>

	<optional>true</optional>

</dependency>


```

ctrl+f9 自动编译

安装谷歌浏览器插件  live reload 代码改变自动刷新浏览器

### 开发常用IDEA工具插件

Codota	代码自动补全 代码片搜索

Auto filling Java call arguments	自动填充函数参数

GsonFormat	根据格式json字符串自动生成对应的java代码

Rainbow Brackets	彩虹括号

Maven Helper	依赖助理

### RESTful风格API与HTTP协议 

APl (Application Programming Interface).名思义:是一组编程接接口规范，客户端与服条端通过请求响应进行数据通信

REST(Representational State Transfer）表述性状态传递，决定了接口的形式与规范

RESTful是基于http方法的API设计风格，而不是一种新的技术.

看Url就知道要什么资源

看http method就知道针对资源干什么

看http status code就知道结果如何



RESTful是面向资源的（名词)

用HTTP方法体现对资源的操作

用HTTP状态码表述结果

Get方法和查询参数不应该改变数据
改变数据的事交给POST、PUT、 DELETE

复杂资源关系的表达

GET /cars/711/drivers/返回使用过编号711汽车的所有司机

GET/cars/711/drivers/4返回使用过编号711汽车的4号司机

资源过滤、排序、选择和分页的表述

高级用法:HATEOAS 关联api 

版本化你的API
强制性增加APl版本声明，不要发布无版本的APl。如:/api/V1/blog

### 常用注解开发RESTful接口上 