---
title: MySQL配置方法和环境搭建
---

### MySQL配置方法

---
推荐使用zip的版本
下载进入官网下载就行官网下载链接https://dev.mysql.com/downloads/mysql/
在开头选择Windows还是其他的系统 下载第一个就行了不用下载带有debug的版本
下载过会解压到你所要安装的位置就行(解压的路径中不能有中文)
在MySQL根目录创建一个叫做my.ini的文件,然后在里面写上下面的代码,需要有一定的修改文件路径需要修改一下其他的也没有什么了
在解压之后如果有data就不用管了,但是如果没有data就需要自己创建一个data文件夹
到此处其实就已经安装完了
```
  [mysqld]
  # 设置3306端口
  port=3306
  # 设置mysql的安装目录   ----------是你的文件路径-------------
  basedir=E:\mysql\mysql
  # 设置mysql数据库的数据的存放目录  ---------是你的文件路径data文件夹自行创建
  datadir=E:\mysql\mysql\data
  # 允许最大连接数
  max_connections=200
  # 允许连接失败的次数。
  max_connect_errors=10
  # 服务端使用的字符集默认为utf8mb4
  character-set-server=utf8mb4
  # 创建新表时将使用的默认存储引擎
  default-storage-engine=INNODB
  # 默认使用“mysql_native_password”插件认证
  #mysql_native_password
  default_authentication_plugin=mysql_native_password
  [mysql]
  # 设置mysql客户端默认字符集
  default-character-set=utf8mb4
  [client]
  # 设置mysql客户端连接服务端时默认使用的端口
  port=3306
  default-character-set=utf8mb4
```
### MySQL的初始化

需要用管理员身份打开cmd,否则会出错,然后用指令进入之前解压的MySQL文件的bin目录中(cd+文件名是进入目标文件夹 cd ..是倒退到上一个文件夹)
进入bin目录之后输入mysql --initialize --console进行初始化
之后会出现几行很长的代码,复制root@localhost后面的密码(:之后会有一个空格就不用复制了)这个是你的初始密码别删除了,先保存起来过会有用
-------------------------------------------------------平平无奇的分割线-------------------------------------------------
然后就需要安装mysql的服务,在之前打开的cmd上输入mysql --install mysql进行安装MySQL服务,安装成功之后会出现service successfully installed的提示
启动mysql的服务net start mysql之后会提示启动成功
关闭mysql的服务net stop mysql
然后连接到MySQL
在cmd中输入mysql -u root -p 输入完成之后会提示然你输入密码,输入之前复制保存的密码就行
成功的话文件路径会变成mysql而不是bin目录的路径
接下来输入`ALTER USER 'root'@'localhost' IDENTIFIED BY '新的密码' ` 然后回车就行了

### MySQL配置环境变量

找到之前解压的MySQL文件位置,然后找到bin目录,复制路径(路径不能有中文)
然后右键点击此电脑  点击属性  点击高级系统设置 点击环境变量会出现两个不一样的,一个是用户变量一个是系统变量,配置系统变量就行
在系统变量里面找到Path双击进去  点击新建把刚刚复制的bin目录的路径粘贴上去就行然后点击确定退出即可
---