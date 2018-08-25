## Linux搭建git仓库

本篇文章我们来学习怎么在Linux上面，搭建一个远程的仓库。

### 一、初始化仓库

#### 1.1 新建一个git用户

```
useradd git
passwd git

chown -R git /home/git

```

#### 1.2 初始化仓库

新建一个要连接的仓库目录。

```
cd git/
mkdir demo
cd demo
git init
```

#### 1.3 第一次提交

1、新建一个README.md文件

```
vim README.md
```

2、提交之前需要配置一下用户，有两种配置方式

* **全局配置**
```
   git config --global user.email "you@example.com"  
   git config --global user.name "Your Name"
```


* **单独配置**
  ```
  cd .git 
  vim config
  ```
  添加
  ```
    [user]
         name=XXX(自己的名称)
         email=XXXX(邮箱)
  ```

3、提交
```
git add .
git commit -m "init"
```

### 二、拉取项目

#### 2.1 克隆项目

在自己的电脑端下载git，使用下面的命令拉取项目

```
git clone git@xx.xx.xx.xx:/home/git/demo
```

输入git用户的密码进行克隆。

**提示**
>如果报错  WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!  那么进入自己电脑端找到.ssh目录下 **known_hosts**文件，清空里面的内容。

#### 2.2 ssh克隆项目

如果每次都输入密码会比较麻烦，我们通过ssh生成密钥配置来实现免密码提交和拉取。

**生成密钥**

```
ssh-keygen -t rsa -C “xxx.mail@xxx.com”
```

**将密钥上传到.ssh目录**

```
cd /home/git/.ssh   //进入.ssh目录，并上传id_rsa.pub文件，记得是git账户的.ssh目录
cat id_rsa.pub >> authorized_keys  
```

**克隆**

```
git clone ssh://git@xx.xx.xx.xx:/home/git/demo
```

---

--完--