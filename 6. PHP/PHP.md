#### 一、Apache服务器安装与配置

1.安装httpd

```
brew install httpd
```

2.启动

```
sudo brew services start httpd
```

3.启动／停止 Apache命令

```
sudo apachectl start
$ sudo apachectl stop
$ sudo apachectl -k restart
```

4.配置Apache

```java
//配置文件目录
/usr/local/etc/httpd/httpd.conf

//配置端口
Listen 8080 修改为 Listen 80

//配置文档根目录
DocumentRoot "/usr/local/var/www" 修改为 自己定义的目录
<Directory 自己定义的目录>
AllowOverride 修改为 AllowOverride All

//启用mod_rewrite
#LoadModule rewrite_module lib/httpd/modules/mod_rewrite.so 去掉#

//配置User Group
User 用户名
Group staff

//替换ServerName
#ServerName www.example.com:8080 替换为 ServerName localhost

//添加PHP
LoadModule php7_module /usr/local/Cellar/php/7.2.7/lib/httpd/modules/libphp7.so
//配置支持PHP解析
AddType application/x-httpd-php .php

//默认文件修改
<IfModule dir_module>
    DirectoryIndex index.html
</IfModule>

替换为
<IfModule dir_module>
    DirectoryIndex index.php index.html
</IfModule>
<FilesMatch \.php$>
    SetHandler application/x-httpd-php
</FilesMatch>

// 启用虚拟主机
#Include /usr/local/etc/httpd/extra/httpd-vhosts.conf 去掉#
```

5.安装php

```
brew install php72 --with-httpd
```

#### 二、添加虚拟主机

```java
// 虚拟主机配置文件目录
/usr/local/etc/httpd/extra/httpd-vhosts.conf

// 配置虚拟主机
<VirtualHost *:80>
	// 1.文档目录
    DocumentRoot "/Users/macbookair/Desktop/java资料/JavaWeb练习/JD"
    // 2.主机名称 需要在host中添加 127.0.0.1 boundlessocean
    ServerName boundlessocean
    // 3.日志
    ErrorLog "/usr/local/var/log/httpd/dummy-host.example.com-error_log"
    CustomLog "/usr/local/var/log/httpd/dummy-host.example.com-access_log" common
    // 4.配置目录访问权限
<Directory "/Users/macbookair/Desktop/java资料/JavaWeb练习/JD">
    AllowOverride All
    Require all granted
</Directory>
</VirtualHost>
```



