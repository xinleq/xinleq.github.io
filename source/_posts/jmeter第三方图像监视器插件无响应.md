---
title: jmeter第三方图像监视器插件无响应
date: 2019-08-23 21:34:28
tags:		
---

今天看了会jmeter,没想到又遇到了问题。因为电脑硬盘坏的突然，很多资料都没来得急保存。后来找回一些，电脑上曾经安装的环境重装了一遍，但还是有缺漏。

今天突然想用一下第三方图形监视器，于是重新下载安装：

1.在<https://jmeter-plugins.org/downloads/old/>页下载了JMeterPlugins-Standard-1.4.0.zip,解压缩，复制JMeterPlugins-Standard.jar文件到jmeter安装目录下lib/ext/里

2.服务器端，在<https://jmeter-plugins.org/wiki/PerfMonAgent/>页下载Server Agent，最新版本2.2.3，解压缩。windows平台执行startAgent.bat文件，Linux平台执行startAgent.sh文件。

结果就出了问题。

监听器选了jp@gc - PerfMon Metrics Collector后，脚本无法运行，整个Jmeter关也关不上，jp@gc - PerfMon Metrics Collector图表界面没有图表，只有*waiting for samples*字样，本人Jmeter安装在Windows里，所以只好用任务管理器关闭Jmeter进程。

后来看到下图红框里的文字

{% asset_img old.jpg  %}

于是删除了JMeterPlugins-Standard.jar，下载了jmeter-plugins-manager-1.3.jar放在jmeter安装目录下lib/ext/里，重新启动Jmeter.

果然发现菜单栏 -选项里多了一项Plugins Manager

{% asset_img option.jpg  %}

点击选项(option)--Plugins Manager，跳出下图

{% asset_img add.jpg  %}

再点击Available Plugins,出现下图

{% asset_img add2.jpg  %}

下拉找到jpgc-Standard Set,前面空格打勾，再点击右下方Apply Changes and Restart JMeter，等Jmeter重新启动后我们需要的更新版本的jp@gc - PerfMon Metrics Collector就出现在监听器里了。

果然Jmeter不再无响应，也没有报错，脚本运行正常，结果树显示正常，然而jp@gc - PerfMon Metrics Collector图表界面依旧只有*waiting for samples*字样，停止脚本重新运行就报错

{% asset_img error.jpg  %}

发现脚本只要点击运行，Server Agent就秒停，且出现报错日志。以本人不怎么地的英语连蒙带猜可能是环境报错，本机java版本12.0.1，跟Server Agent不兼容，没能百度出解决方法。

在虚拟机上Java1.8.0版本，则完美运行。

java12依旧不知道该更改哪些设置可以使用，又不想卸载，在文档说明里看到下面一段话，{% asset_img ex.jpg  %}

大概知道可以自己复制一个现成的jre包就可以，不一定要安装java。又看到下面的博文，https://blog.csdn.net/GHY2016/article/details/83422627

综合了一下，于是复制了一个jre包放在severAgent文件夹里，本人使用windows系统，所以修改startAgent.bat文件里**java -jar %0\..\CMDRunner.jar --tool PerfMonAgent %***

Java改为复制的jre的Java路径**E:\apache-jmeter-5.1.1\ServerAgent-2.2.3\jre\bin\java -jar %0\..\CMDRunner.jar --tool PerfMonAgent %***

监控的线图终于出来了，可是有点怪怪的

{% asset_img chart.jpg  %}

但是，暂时先这样吧

