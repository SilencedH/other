## Linux安装redis

### 一、安装

```
yum install redis
```


### 二、配置

```
vim /etc/redis.conf
```

修改配置为后台启动

```
daemonize yes
```

设置密码

```
requirepass nihao456
```

允许远程连接

```
#bind 127.0.0.1
protected-mode no
```

### 三、启动服务

```
cd /usr/bin/

./redis-server /etc/redis.conf
```

