## Linux安装git

### 一、下载

我们到[官网](https://mirrors.edge.kernel.org/pub/software/scm/git/)找到指定版本的源码，下载。

```
wget https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.9.5.tar.gz
```

解压

```
tar -zxvf git-2.9.5.tar.gz
```

进入目录

```
cd git-2.9.5
```

### 二、编译安装

#### 2.1 编译前

安装依赖库

```
yum install curl-devel expat-devel gettext-devel openssl-devel zlib-devel gcc perl-ExtUtils-MakeMaker
```

#### 2.2 编译 

```
./configure prefix=/usr/local/git/

make && make install
```


#### 2.3 安装成功

```
git --version
```

---

--完--