#redis 安装部署

> 1.源码下载安装编译[redis](https://redis.io/download)

```shell script
$ wget http://download.redis.io/releases/redis-6.0.7.tar.gz
$ tar xzf redis-6.0.7.tar.gz
$ cd redis-6.0.7
$ make
$ make install
```
> 2.修改配置文件：当前目录下redis.conf文件
```
bind 127.0.0.1
daemonize yes
port 6379
...
```


> 3.自启动
```
$ vim /utils/redis_init_script 
# 根据自己的需要修改其中的启动选项,修改运行级别
# chkconfig:   2345 90 10
# description:  Redis is a persistent key-value database
# 将脚本复制到etc/init.d
$ cp redis_init_script /etc/init.d/redis
# 设置开机自启动

```

> 4.最后
```shell script
#设置为开机自启动服务器
chkconfig redisd on
#打开服务
service redisd start
#关闭服务
service redisd stop
```