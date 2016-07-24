---
title: 'git: Filename too long'
date: 2016-07-24 16:13:03
tags:
---
在git bash中，运行下列命令：

	git config --global core.longpaths true

--global是该参数的使用范围，如果只想对本版本库设置该参数，只要在上述命令中去掉--global即可。