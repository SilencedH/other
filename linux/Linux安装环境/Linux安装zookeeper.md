### Linux安装zookeeper

#### 一、下载

```
wget http://archive.apache.org/dist/zookeeper/zookeeper-3.4.9/zookeeper-3.4.9.tar.gz
```

#### 二、解压

```
tar zxvf zookeeper-3.4.9.tar.gz
```

#### 三、修改配置

```
cd zookeeper-3.4.9
cp conf/zoo_sample.cfg conf/zoo.cfg
vim conf/zoo.cfg
```

#### 四、启动

```
cd bin/
./zkServer.sh start
```
