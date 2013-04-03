---
layout: post
title: "从git仓库彻底删除文件"
tagline: "彻底删除误提交的文件"
description: ""
category: [ dev ]
tags: [git dev]
---
从local repo的所有commit里删除指定文件Rakefile

    $ git filter-branch --index-filter 'git rm --cached --ignore-unmatch Rakefile' --prune-empty --tag-name-filter cat -- --all

提交到远端：

    $ git push origin master --force
    
切换到远端

    $ rm -rf .git/refs/original/
    $ git reflog expire --expire=now --all
    $ git gc --prune=now
    $ git gc --aggressive --prune=now