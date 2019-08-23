---
title: Jmeter分布式执行机命令行启动报错处理
date: 2019-05-31 17:24:53
tags:
---

好长的标题，哈哈......

回顾Jmeter，这两天有点东一榔头，西一棒子的赶脚.....

之前学习Jmeter,到分布式这块，是现成的执行机，控制机，于是当我的资料丢失后，虽重新找回一部分，然后遇到这块，一脸懵逼，咩，执行机哪去了？

不过是回顾，不像初学时囫囵吞枣，还是有点明白一些了。执行机，控制机都是执行jmeter脚本，所以都是Jmeter安装目录，然而配置不同。安装目录配置环境变量就不说了

本人关于Jmeter的学习还很浮于表面，所以配置只涉及基本功能实现。控制机界面启动，执行机命令行启动。

控制机配置

打开安装目录bin下的**jmeter.properties**

查找**remote_hosts=**

把值修改为执行机的**IP：端口**

执行机配置

1. 执行机命令行启动，所以需要配置环境变量，将下面三个文件配置到Path中

* Jmeter安装目录\lib\ext\ApacheJMeter_core.jar

* Jmeter安装目录\lib\jorphan.jar

* Jmeter安装目录\lib\logkit-2.0.jar

2. 修改端口
   在Jmeter.properties中查找server_port，去掉前面注释符，值改为执行机端口号
   
3. 打开执行机（jmeter-server.bat），出现如下报警

   {% asset_img error.png %}

   在Jmeter.properties中查找server.rmi.ssl.disable,改为

   server.rmi.ssl.disable=true,保存，重新运行

   参考于：http://www.bubuko.com/infodetail-2616706.html

   <video src="lovebaby.mp4" controls="controls" autoplay="autoplay" ></video>


