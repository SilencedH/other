## Linux下安装nginx

### 一、下载nginx

我们到[官网](https://nginx.org/download/)找到需要的版本，使用下面命令下载。

```
wget https://nginx.org/download/nginx-1.9.9.tar.gz
```

解压

```
tar -zxvf nginx-1.9.9.tar.gz 
```


### 二、 编译安装

#### 2.1 编译前工作

检查是否安装gcc

```
gcc -v
```

如果没有，安装

```
yum install gcc-c++
```

安装pcre库
```
yum install pcre pcre-devel
```

安装zlib库
```
yum install zlib zlib-devel
```
安装openssl
```
yum install openssl openssl-devel
```

#### 2.2 编译安装

```
cd nginx-1.9.9

./configure

make && make install
```

### 三、启动服务

```
cd /usr/local/nginx/sbin/

./nginx 启动

./nginx -s stop 停止

./nginx -s quit 退出

./nginx -s reload 重新加载

./nginx -s quit:此方式停止步骤是待nginx进程处理任务完毕进行停止。

./nginx -s stop:此方式相当于先查出nginx进程id再使用kill命令强制杀掉进程。
```

直接访问服务ip就可以了。

**说明**

* nginx配置、项目文件都在 **/usr/local/nginx** 目录下面
* 阿里云访问时需要配置安全组开放80端口

---

--完--
