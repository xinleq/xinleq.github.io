---
title: pytest零用例运行
date: 2020-03-15 14:17:51
tags:
---

好久没用pytest，最近要熟悉一下，控制台输入pytest命令执行，发现一直是零执行。一堆的error信息，百度也没发现啥有用的，pytest之前装的版本丢了，后来补装的，看着一堆报警，前面的明显自己能力有限，折腾不出来，不过看到最后一条，关于插件allure的，心想试试吧，就把allure卸载了，然后运行，果断正常。行吧，当初安装allure的时候就因为兼容问题，花了不少时间搞定，结果pytest升级，又出问题。自己现今是金鱼脑子，今天用今天记得，明天不用，就忘得一干二净，没办法只能记基本原理，原理太高深，就靠当年学校培训来的解决问题的思路本能，虽然问题根源是啥还不知道，但pytest可以跑起来了，插件再慢慢看吧，总要一步步来的。

> E:\pycharm\newproject>pytest
> =========================================== test session starts ===========================================
> platform win32 -- Python 3.6.8, pytest-5.4.1, py-1.8.0, pluggy-0.13.1
> rootdir: E:\pycharm\newproject, inifile: pytest.ini, testpaths: ./src
> plugins: allure-adaptor-1.7.10, html-2.0.1, metadata-1.8.0, ordering-0.6, rerunfailures-4.1
> collected 2 items                                                                                          
> INTERNALERROR> Traceback (most recent call last):
> INTERNALERROR>   File "e:\python\lib\site-packages\_pytest\main.py", line 191, in wrap_session
> INTERNALERROR>     session.exitstatus = doit(config, session) or 0
> INTERNALERROR>   File "e:\python\lib\site-packages\_pytest\main.py", line 246, in _main
> INTERNALERROR>     config.hook.pytest_collection(session=session)
> INTERNALERROR>   File "e:\python\lib\site-packages\pluggy\hooks.py", line 286, in __call__
> INTERNALERROR>     return self._hookexec(self, self.get_hookimpls(), kwargs)
> INTERNALERROR>   File "e:\python\lib\site-packages\pluggy\manager.py", line 93, in _hookexec
> INTERNALERROR>     return self._inner_hookexec(hook, methods, kwargs)
> INTERNALERROR>   File "e:\python\lib\site-packages\pluggy\manager.py", line 87, in <lambda>
> INTERNALERROR>     firstresult=hook.spec.opts.get("firstresult") if hook.spec else False,
> INTERNALERROR>   File "e:\python\lib\site-packages\pluggy\callers.py", line 208, in _multicall
> INTERNALERROR>     return outcome.get_result()
> INTERNALERROR>   File "e:\python\lib\site-packages\pluggy\callers.py", line 80, in get_result
> INTERNALERROR>     raise ex[1].with_traceback(ex[2])
> INTERNALERROR>   File "e:\python\lib\site-packages\pluggy\callers.py", line 187, in _multicall
> INTERNALERROR>     res = hook_impl.function(*args)
> INTERNALERROR>   File "e:\python\lib\site-packages\_pytest\main.py", line 257, in pytest_collection
> INTERNALERROR>     return session.perform_collect()
> INTERNALERROR>   File "e:\python\lib\site-packages\_pytest\main.py", line 453, in perform_collect
> INTERNALERROR>     self.config.pluginmanager.check_pending()
> INTERNALERROR>   File "e:\python\lib\site-packages\pluggy\manager.py", line 277, in check_pending
> INTERNALERROR>     % (name, hookimpl.plugin),
> INTERNALERROR> pluggy.manager.PluginValidationError: unknown hook 'pytest_namespace' in plugin <module 'allu
> re.pytest_plugin' from 'e:\\python\\lib\\site-packages\\allure\\pytest_plugin.py'>