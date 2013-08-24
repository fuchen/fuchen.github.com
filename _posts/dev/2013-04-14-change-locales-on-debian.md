---
layout: post
title: "Display Chinese on Debian"
description: ""
category: dev
tags: [git dev]
---
{% include JB/setup %}

http://wiki.debian.org.hk/w/Make_Debian_support_Chinese

Check locale settings:

    locale -a

Change/add locale settings:

    dpkg-reconfigure locales

Check on `zh_CN.GBK`, and other related items, and confirm

Install font and Chinese input app:

    apt-get install scim

    apt-get install scim-tables-zh

