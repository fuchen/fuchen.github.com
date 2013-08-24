---
layout: post
title: "Install LuaRocks with Lua 5.2 on Windows 7"
description: ""
category: dev
tags: [git dev]
---
{% include JB/setup %}

Below are steps to install LuaRocks 2.1.0 with Lua 5.2 on Windows, using Visual Studio(Express):

1. Download [Lua 5.2 source code](http://www.lua.org/download.html)
2. Build lua52.dll, and lua5.2.exe. **Note**:
  * Add `LUA_COMPAT_ALL` to *C/C++ Preprocessor Definition*
  * *lua5.2.exe* has to depends on *lua52.dll*, otherwise you will see errors like "multiple VMs" when using a C module
3. Copy executable files, libraries, and source code to a folder. The folder structure looks like:
```
    LuaFolder/
      |-bin/
      | |-lua5.2.exe
      | |-lua52.dll
      | `-luac5.2.exe(Optional?)
      |-lib/
      | `-lua52.lib
      |-include/
        ` Header files from Lua source code
```
4. Download and unpack [LuaRocks](http://luarocks.org/releases/). I am using version 2.1.0.
5. Install: `install.bat /P InstallDir /LV 5.2 /LUA LuaFolder`
6. Goto install dir, and edit *config.lua*. Change value of `variables.LUALIB` from `lua52.dll` to `lua52.lib`.
7. Add *PATH*, *LUA_PATH* and *LUA_CPATH* to system env, according to the output of *install.bat*
8. Additional paths:
```
    PATH      : %LuaRocksDir%/bin
    LUA_CPATH : %LuaRocksDir%/lib\lua\5.2
```

Done!

To install a Lua module using LuaRocks, you have to open a command line window with Visual Studio environment, then enjoy `luarocks install xxx`!
