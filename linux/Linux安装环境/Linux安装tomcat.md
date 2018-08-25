## Linux安装tomcat

### 一、下载
我们到[官网](https://tomcat.apache.org/download-80.cgi)找到8.5的版本，运行下面命令下载。

```
wget http://mirrors.hust.edu.cn/apache/tomcat/tomcat-8/v8.5.33/bin/apache-tomcat-8.5.33.tar.gz
```

解压

```
tar zxvf apache-tomcat-8.5.33.tar.gz
```

启动

```
cd apache-tomcat-8.5.33/bin

./startup.sh
```

访问8080端口号即可。