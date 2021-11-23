---
title: vscode的配置方法
---
## VScode配置c语言
---
推荐插件
Bracket Pair Colorizer   括号指明(建议安装)
c/c++              必须安装的插件
Chinese            中文插件
code runner     运行run插件
error  lens        报错提示(建议安装)
visual  studio  Intellicode   提示代码(建议安装)

配置环境,需要mingw以及配置c语言的环境变量
Code  runner 扩展设置(必须安装的插件)
Code-runner:Run In Terminal(打开)
Code-runner:Saver File Befor Run(打开)

C/C++扩展设置
C_CPP>Default:Compiler Path
点击settings.json在最后一行的双引号中填上mingw的bin目录的路径,并且在bin目录后面加上\\g++.exe(注意:反斜杠会报错,需要把路径的单个反斜杠写成双反斜杠)
C_CPP>Dafault Cpp standard  :  设置成c++14
C_CPP>Dafault C standard :  设置成c11
C_CPP>Default:  Include  Path
:  点击settings.json在最后一行中的  [ ]  输入mingw中的lib路径,   把单个反斜杠改写成双斜杠 ,并且在路径的两边加上双引号
C_CPP>Default: Intelli Sense  Mode 设置成gcc-x64
---

