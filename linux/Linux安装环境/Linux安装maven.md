## Linux安装maven

### 一、下载

我们到[官网](http://maven.apache.org/download.cgi#)找到指定的版本下载。

运行下面命令下载

```
wget http://ftp.wayne.edu/apache/maven/maven-3/3.5.4/binaries/apache-maven-3.5.4-bin.tar.gz
```

解压

```
tar -zxvf apache-maven-3.5.4-bin.tar.gz
```

### 二、配置环境变量

```
vim /etc/profile
```

添加以下内容

```
#set maven environment
export M2_HOME=/usr/src/maven/apache-maven-3.5.4
export M2_HOME
export PATH=$PATH:$M2_HOME/bin
```

使配置文件生效

```
source /etc/profile
```

### 三、安装成功

```
mvn -version
```

---

--完--