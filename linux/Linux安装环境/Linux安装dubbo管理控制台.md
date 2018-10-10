### Linux安装dubbo管理控制台

#### 一、克隆代码

```
git clone https://github.com/apache/incubator-dubbo-ops.git
```

#### 二、修改配置

```
cd incubator-dubbo-ops/dubbo-admin/src/main/resources
vim application.properties
```

```
server.port=7001
spring.velocity.cache=false
spring.velocity.charset=UTF-8
spring.velocity.layout-url=/templates/default.vm
spring.messages.fallback-to-system-locale=false
spring.messages.basename=i18n/message
spring.root.password=root
spring.guest.password=guest

dubbo.registry.address=zookeeper://127.0.0.1:2181 #zookeeper地址
```


#### 三、打包

```
cd incubator-dubbo-ops/dubbo-admin
mvn clean package -Dmaven.test.skip=true
```

#### 四、启动

修改文件名
```
mv dubbo-admin-0.0.1-SNAPSHOT.jar dubbo-admin.jar
```

启动

```
nohup java -jar dubbo-admin.jar >>dubbo-admin.out 2>&1&
```

#### 五、访问

通过ip:7001访问，root默认密码root,guest默认密码guest
