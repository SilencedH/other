## Linux安装ftp

Linux最常用的是vsftp服务，下面我们来搭建一下。

### 一、安装

通过yarm源进行安装安装vsftpd服务

```
yum install -y vsftpd
```

### 二、配置

#### 2.1 进入vsftpd的根目录

```
cd /etc/vsftpd/
```

**配置文件说明**

* /etc/vsftpd/vsftpd.conf:vsftpd 的核心配置文件

* /etc/vsftpd/ftpusers:用于指定哪些用户不能访问FTP 服务器  黑名单

* /etc/vsftpd/user_list:指定允许使用vsftpd 的用户列表文件  白名单

* /etc/vsftpd/chroot_list：指定允许使用vsftpd的用户列表文件。控制名单下的目录能不能离开ftp根目录


添加ftp用户组

```
groupadd ftpusers
```

添加ftp用户

```
useradd -g ftpusers -s /sbin/nologin ftp_sean
passwd ftp_sean
```

授权ftp_sean目录给ftp_sean

```
chown -R ftp_sean /home/ftp_sean
```

新建**chroot_list**文件

```
ftp_sean
```

修改配置文件

```
anonymous_enable=NO
local_enable=YES
write_enable=YES
local_umask=022
dirmessage_enable=YES
xferlog_enable=YES
connect_from_port_20=YES
xferlog_std_format=YES
chroot_local_user=NO
allow_writeable_chroot=YES
chroot_list_enable=YES
chroot_list_file=/etc/vsftpd/chroot_list
listen=NO
listen_ipv6=YES
pam_service_name=vsftpd
userlist_enable=YES
tcp_wrappers=YES
```

授权

```
chmod -R 777 /home/ftp_sean/
```


启动服务

```
service vsftpd start
```

然后就可以连接啦!

---

--完--
