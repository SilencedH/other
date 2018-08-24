## Linux安装RabbitMQ

RabbitMQ是erlang语言开发的，所以我们先安装erlang语言，再安装RabbitMQ。

### 一、安装erlang

到此[网站](https://bintray.com/rabbitmq/rpm/erlang)下载RabbitMQ的erlang

```
wget https://bintray.com/rabbitmq/rpm/download_file?file_path=erlang%2F20%2Fel%2F7%2Fx86_64%2Ferlang-20.3.8.7-1.el7.centos.x86_64.rpm
```

安装

```
yum install download_file\?file_path\=erlang%2F20%2Fel%2F7%2Fx86_64%2Ferlang-20.3.8.7-1.el7.centos.x86_64.rpm 
```


### 二、安装RabbitMQ

#### 2.1 下载安装

到[官网](http://www.rabbitmq.com/install-rpm.html#downloads)下载合适版本rpm包。

```
wget https://dl.bintray.com/rabbitmq/all/rabbitmq-server/3.7.7/rabbitmq-server-3.7.7-1.el7.noarch.rpm
```

安装
```
yum install rabbitmq-server-3.7.7-1.el7.noarch.rpm 
```

启动服务

```
service rabbitmq-server start
```

查看服务状态

```
service rabbitmq-server status
```

#### 2.2 配置

增加用户,并授权

```
rabbitmqctl add_user admin password
rabbitmqctl set_user_tags admin administrator
```

重启

```
service rabbitmq-server stop
service rabbitmq-server start
```

#### 2.3 安装插件

```
cd /usr/sbin
./rabbitmq-plugins enable rabbitmq_management
```

这时我们访问服务器15672端口，使用上面配置的用户和密码就可以登陆控制台了。

---

--完--