---
title: edge驱动问题
date: 2019-05-12 11:24:22
tags:
---

这是硬盘坏的第几天来着？资料恢复行动已经告一段落，能回收的资料已经回收，电脑上之前的软件在陆续安装。

因为硬盘的关系，系统也恢复了一下，结果升级后，在用selenium3写脚本时出现了新的问题，关于驱动

之前发现的问题，虽然系统是64位的，但使用IE11的64位驱动，selenium3的键盘输入简直慢到令人发指。换32位驱动正常。至于驱动选择，与selenium版本号一致即可。

IE获取当前网址，获取到的是*localhost:端口号*

为什么？？？？？？？

edge浏览器之前是17版本的，17134，官网可以下到对应驱动

https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/， selenium3会出现ResourceWarning，但是脚本可以正常执行。然而此次系统恢复到原来的老版本，又更新直接更到最新版本，edge版本也更到18版本Microsoft EdgeHTML 18.17763，

于是按照官网给的命令输入然后悲剧，浏览器打开网页变的很慢。于是放弃这个驱动，难道是我打开的方式不对？？？？

（又试了一次，当时正用百度网盘上传文件，虽然速度只有200k,但打开网页的速度明显变慢，看来是百度网盘上传文件导致的，18版本的MicrosoftWebdriver*表示这锅我不背，是百度网盘和网速的问题，跟我没关系*）下载18版本驱动：打开命令行窗口，输入 *DISM.exe /Online /Add-Capability /CapabilityName:Microsoft.WebDriver~~~~0.0.1.0*

chrome打开某些网站也会很慢，目前的水平来说，使用Firefox似乎是最好选择。

以上.....

待解决......

<video width="320" height="240" controls="controls">
  <source src="panda.mp4" type="video/mp4" />
</video>