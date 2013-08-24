---
layout: post
title: "给debian添加中文支持"
description: ""
category: dev
tags: [git dev]
---
{% include JB/setup %}

## 中文支持 ##

http://wiki.debian.org.hk/w/Make_Debian_support_Chinese

查看区域设置：

    locale -a

改变/添加区域设置：

    dpkg-reconfigure locales

勾上 `zh_CN.GBK` 等，确定

安装字体及输入法：

    apt-get install scim

    apt-get install scim-tables-zh

