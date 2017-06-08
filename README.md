# java 在线实验环境

## 软件简介

Java是一门面向对象编程语言，不仅吸收了C++语言的各种优点，还摒弃了C++里难以理解的多继承、指针等概念，因此Java语言具有功能强大和简单易用两个特征。Java语言作为静态面向对象编程语言的代表，极好地实现了面向对象理论，允许程序员以优雅的思维方式进行复杂的编程[1]  。
Java具有简单性、面向对象、分布式、健壮性、安全性、平台独立与可移植性、多线程、动态性等特点[2]  。Java可以编写桌面应用程序、Web应用程序、分布式系统和嵌入式系统应用程序等

所属类别是编程语言

特点：

1.简单性

2.面向对象

3.分布性

4.编译和解释性

5.稳健性

6.安全性

7.可移植性

8.高性能

9.多线索性

10.动态性


## 软件官网

https://www.java.com/zh_CN/

## Dockerfile 使用方法

在您的应用程序中启动Java实例

使用此映像的最简单的方法是将Java容器用作构建和运行时环境。在你的Dockerfile写作中，按照以下的方式编写和运行你的项目：
```
FROM java:7
COPY . /usr/src/myapp
WORKDIR /usr/src/myapp
RUN javac Main.java
CMD ["java", "Main"]
```
然后，您可以运行并构建Docker映像：
```
$ docker build -t my-java-app .
$ docker run -it --rm --name my-running-app my-java-app
```
在Docker容器中编译你的应用程序

有可能在容器内运行应用程序是不合适的。要编译，而不是在Docker实例中运行您的应用程序，您可以编写以下内容：
```
$ docker run --rm -v "$PWD":/usr/src/myapp -w /usr/src/myapp java:7 javac Main.java
```
这会将当前目录作为卷添加到容器中，将工作目录设置为卷，并运行该命令javac Main.java，该命令将使Java编译代码Main.java并输出Java类文件Main.class。

## 资源链接

- https://www.java.com/zh_CN/
- http://www.runoob.com/java/java-tutorial.html
