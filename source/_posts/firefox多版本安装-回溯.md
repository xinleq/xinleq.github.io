---
title: firefox多版本安装(回溯)
date: 2019-05-10 22:12:52
tags:
---

<p>因为要用selenium3，所以Firefox升级到最新版，然后发现新版不支持firebug，httpwatch插件，于是百度如何安装两个版本。方法如下：</p>
<p>鉴于本人有个毛病，爱把所有软件升级到最新版，所以，把新下载的firefox66作为主浏览器，设置为自动更新的。</p>
<ol>
<li><p>安装firefox66.0版本后，快捷方式重命名防止重复</p>
</li>
<li><p>打开浏览器，输入<em>about:profiles</em>,出现配置文件，点击<strong>创建新配置文件</strong>，按配置向导<strong>下一步</strong>，配置文件命名为firefox35（此名依据个人喜好随便）。</p>
</li>
<li><p>安装低版本Firefox，本人放在另一个盘符下，当然两个版本都没有走默认安装，全都改了安装路径，这也是根据个人习惯，只要两次安装不是同一路径就好。设置不更新。</p>
</li>
<li><p><strong>鼠标右键</strong>点击低版本<strong>快捷方式</strong>-<strong>属性</strong>，在弹出框<strong>目标</strong>里添加<em>–no-remote -P firefox35</em>,点击<strong>确定</strong>，完成。</p>
<p>–no-remote据百度，是允许多个Firefox共存</p>
<p>-P firefox35 据百度，指定使用的配置文件，firefox35就是之前在第一个浏览器里新建的配置文件名。</p>
</li>
<li><p>确认低版本浏览器配置文件是否是新建的那个，本人的低版本Firefox是35.0版本，无法使用<em>about:profiles</em>打开配置文件，故打开浏览器，点击<strong>帮助</strong>-<strong>故障排除信息</strong>，找<strong>配置文件夹</strong>后的<strong>显示文件夹</strong>，点击，跳出的文件夹名称正是之前新建那个配置文件里显示的，故成功</p>
</li>
</ol>
{% asset_img smile2.png 依旧我美丽的大国宝 %}

