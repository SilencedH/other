## Linux安装erlang


#### 1.1 下载解压
到 **[官网](http://erlang.org/download/)** 去找到合适的版本来下载。

```
wget http://erlang.org/download/otp_src_21.0.tar.gz

tar -zxvf otp_src_21.0.tar.gz
```

#### 1.2 安装依赖库

```
yum install gcc glibc-devel make ncurses-devel openssl-devel autoconf
yum install unixODBC unixODBC-devel
```

#### 1.3 编译安装

```
./configure --prefix=/usr/local/erlang --enable-hipe --enable-threads --enable-smp-support --enable-kernel-poll --without-javac

make && make install
```

#### 1.4 配置环境变量

```
vim /etc/profile

export PATH=$PATH:/usr/local/erlang/bin/ 
```

#### 1.5 安装成功

```
erl 
```
如果出现版本号就说明安装成功了。

(ctrl + G 再按 a 退出)
