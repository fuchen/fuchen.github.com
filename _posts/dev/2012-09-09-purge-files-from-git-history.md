---
layout: post
title: "ssss"
tagline: "ffffffffff"
description: ""
category: dev
tags: [git, dev]
---
{% include JB/setup %}

    $ rm -rf .git/refs/original/
    $ git reflog expire --expire=now --all
    $ git gc --prune=now
    $ git gc --aggressive --prune=now