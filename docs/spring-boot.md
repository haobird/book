# Spring Boot 学习教程

## Java 环境准备

基本命令
```
/usr/libexec/java_home -V   查看java安装目录
java -v   查看版本
brew install maven   安装Maven
mvn -v      查看maven版本
```

## 项目结构介绍

+ src/main/java 程序开发以及主程序入口
+ src/main/resources 配置文件
+ src/test/java 测试程序

Spring Boot 建议的目录结果如下：
root package 结构：com.example.myproject

```
com
  +- example
    +- myproject
      +- Application.java
      |
      +- model
      |  +- Customer.java
      |  +- CustomerRepository.java
      |
      +- service
      |  +- CustomerService.java
      |
      +- controller
      |  +- CustomerController.java
      |
```

1、Application.java 建议放到根目录下面,主要用于做一些框架配置
2、model 目录主要用于实体与数据访问层（Repository）
3、service 层主要是业务类代码
4、controller 负责页面访问控制