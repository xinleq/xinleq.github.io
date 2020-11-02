---
title: problem
date: 2020-08-07 01:00:49
tags:
---

今天发现selenium的官网无法打开，表现跟上次自己的博客一样，先提示不安全，然后拒绝连接，ping找不到主机，显示证书是过期的VMware证书

网上的解决方法：1、关闭VMware远程服务 2、Chrome安全策略改变，将网址从中去掉 3、清dns缓存。 4、将dns自动获取改为手动设置为114.114.114.114 备选8.8.8.8 

然而，没有一条有用的，手机可以访问。所以我依旧是懵逼的。先放着吧。

发现selenium的官网目前来说我的电脑访问不了，是由于edge升级为基于chromium开源项目的版本，自动化脚本出问题了。想去官网看看的。

edge升级为chromium内核版本后，直接下载了对应的webdriver驱动，然而脚本走到打开浏览器就走不动了。webdriver在启动浏览器后似乎丢失了自动到环境变量设定的路径中寻找此驱动文件的能力，估计是驱动文件改名的缘故吧。

于是脚本创建驱动对象的时候由

```pythpn
self.driver=webdriver.Edge()
```

改为

```python
driver_url="e:\python\msedgedriver.exe"
driver=webdriver.Edge(executable_path=driver_url)
```

通过

```
excutable_path
```

指明驱动文件，于是edge又可以正常跑脚本了，挺好......

但是套用unittest框架后，用例正常通过，可是结果红通通的，一堆resourceWarning，后面还要研究下是什么原因......