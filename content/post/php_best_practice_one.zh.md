+++
date = "2013-07-01"
draft = false
tags = []
title = "macOS PHP best practice (one)"
math = true
+++


This article show us how to use mac own local web sever apache to build our own static website. ​:smile:​.<!--more-->


#### macOS PHP best practice (one)

最简单直接的方式还是使用 Mac 上自带的 Apache 和 PHP。

##### 启动 Apache

1. 启动:

   ````
   apache $sudo apachectl start
   ````

2. 启动后，在浏览器中输入` localhost` ，可以看到页面上显示` It works！`。(`/Library/WebServer/Documents/ `下的` index.html.en `文件)

3. `Apache` 的默认根目录是 `/Library/WebServer/Documents/`。

##### 添加apache对php的支持

1. 打开 `http.conf` 配置文件:

   ```
    sudo vim /etc/apache2/httpd.conf
   ```

2. 找到以下代码 `LoadModule php5_module libexec/apache2/ libphp5.so` 并去掉注释（去掉前面的==#==号）, `wq ` 保存退出。

#####  重启 Apache,进行php类型文件的调试

1. 重启:

   ```
   sudo apachectl restart
   ```

2. 在 `Apache` 的根目录 `/Library/WebServer/Documents/` 下新建`project`文件夹并写一个`php`文件输出`hello world`。此时，在浏览器打开 http://localhost/project/test.php 就可以正常看到`hello world `了~

3. 如果有权限问题,使用下列命令：

   ```
   sudo chown yourname:staff project
   ```

   其中 `yourname` 是你自己的名字。

##### 使用homebrew安装mysql

1. 安装homebrew

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

2. 安装mysql

```
brew install mysql
```

3. 启动mysql

```
mysql.server start
```


##### Apache 常用命令

1. 启动 Apache 服务

```
sudo apachectl start
```

2. 重新启动 Apache 服务

```
sudo apachectl restart
```

3. 关闭 Apache 服务

```
sudo apachectl stop
```

4. 查看 Apache 版本

```
httpd -v
```
