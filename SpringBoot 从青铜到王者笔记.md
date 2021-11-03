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

### springboot2 需要先了解的核心概念 



















