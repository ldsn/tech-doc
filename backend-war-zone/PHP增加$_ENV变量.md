---
title: PHP增加$_ENV变量
time: 2015-01-29 00:29:00
category: PHP
---
[前言]：

    在日常开发过程中，我们常常会将一些系统或模块配写在配置文件里。这样便于程序维护与修改。通常的配置文件有.ini , .xml等。配置文件的好处在于：
    1，便于管理。
    2，可读性高。
    但是，使用配置文件也会有坏外，即：
    1，安全性差。如果采用加密方法，会带来解密性能上的开销。
    2，多服务器布署时，容易造成文件内容差异，从而影响程序正常运行。
    为了解决以上安全问题，通常的做法是将内容设置在系统中，使用环境变量方式进行配置。下面我们来讲一下如何在LNMP(Linux + Nginx + Mysql + PHP-FPM + PHP )中进行环境变量的配置。

[操作]：
    环境：debian linux os
    1，设置系统环境变量：
    #vi /etc/profile
    如增加一个环境变量：
    export MY_REDIS_HOST="localhost"

2，修改php-fpm.conf，设置PHP环境变量：

    #vi /etc/php5/fpm/php-fpm.conf
    增加：
    env[MY_REDIS_HOST]=$MY_REDIS_HOST

3，修改php-fpm启动脚本。
    
    因为每次要使系统变量生效，都必须source /etc/profile，而php-fpm启动时，也需要作此操作。因此，需要修改php-fpm启动脚本。
    如使用apt-get安装的，则：
    
    #vi /etc/init.d/php-fpm
    
    在PATH等环境变量定义之后，加入一行：
    
    . /etc/profile
    
    注意，点号与路径之间有空格。实际上.与source是一样的，但是这里用source会报错
    
    还要修改/etc/profile的权限，因为php-fpm启动用户是www-data , 而/etc/profile的权限用户为root，这里为了简章，将/etc/profile的权限设为“777”，即：
    
    #chmod 777 /etc/profile

4,修改php.ini配置。
    
    因为php.ini默认不载入$_ENV变量定义，如果此时查看phpinfo()，会发现我们设置的环境变量为"no value"。
    
    #vi /etc/php5/fpm/php.ini
    
    修改：variables_order为：
    
    variables_order="EGPCS"


5，重启php-fpm

    #service php5-fpm restart

6，测试设置结果。

    查看phpinfo()，在"Enviroment variables" 一节与“PHP variables”一节内可能看到我们刚才设置的变量名及变量值。

[补充]：

    1，php web可以正常得到$_ENV的变量， php-cli模式取不到$_ENV。即：
    
    php -r 'print_r($_ENV);'
    
    得到结果：array()
    
    这是因为php cli用的是另外一个php.ini，其variables_order没有打开ENV变量。其使用的是：/etc/php5/cli/php.ini，按[4]说明打开即可。
    
    碰到这个问题，可以使用指定加载配置文件（.ini）来测试是否是php.ini引起的。即：
    
    php -c '/etc/php5/fpm/php.ini' -r 'print_r($_ENV)'

<http://blog.163.com/sujoe_2006/blog/static/335315120137160515350/>
