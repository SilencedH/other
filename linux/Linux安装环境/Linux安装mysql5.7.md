## Linux安装MySQL5.7 

### 一、安装

#### 1.1 下载安装

进入要安装的目录

```
wget http://repo.mysql.com/mysql57-community-release-el7-10.noarch.rpm
```

```
rpm -Uvh mysql57-community-release-el7-10.noarch.rpm
```

安装服务端

```
yum install -y mysql-community-server
```

### 二、启动服务

**启动**
```
service mysqld start
```

**查看服务状态**

```
service mysqld status
```

**设置开机启动**

```
systemctl enable mysqld
```

**取消开机启动**

```
systemctl disable mysqld
```

### 三、配置

#### 3.1 设置密码

安装好后，首次启动服务时MySQL会自动给我们生成一个密码，我们找到后登录，并修改。

**查看生成密码**

```
grep 'temporary password' /var/log/mysqld.log
```

**登录MySQL**

```
mysql -u root -p 
```

**修改密码规则**

由于默认密码规则要求我们不能设置太简单的密码，所以我们修改一下规则。
```
set global validate_password_policy=0;
set global validate_password_length=6;
```

**修改密码**

```
ALTER USER 'root'@'localhost' IDENTIFIED BY '123456';
```

#### 3.2 授权远程连接

```
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY '123456' WITH GRANT OPTION;

FLUSH PRIVILEGES;
```

ok了。

---

--完--