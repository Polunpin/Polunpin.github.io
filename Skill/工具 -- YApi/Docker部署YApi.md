# 启动mongodb

- `docker run -d --name yapi-mongo -v yapi-mongo:/data/db mongo`

为什么要先启动`mongodb`,因为`yapi`初始化的时候依赖`mongodb`,比如创建用户表这些

这条命令是什么意思呢?

```
-d : 是启动的时候输出容器的id
--name : 是给容器设置一个名字,方便我们控制,比如start,stop
-v : 指定关联的卷 => 本地卷:容器内储存位置 , 就是映射数据保存的地方
```

若是需要外部管理这个数据库的话,最好也暴露出来端口, `mongodb`容器默认也暴露了27017端口

- `docker run -d --name yapi-mongo -v yapi-mongo:/data/db -p 27017:27017 mongo`

------

# 初始化Yapi和启动Yapi

- `docker run -d --name yapi -p 3000:3000 --link yapi-mongo crper/yapi`

这里比上面多的一个参数就是`--link`,用来使连个容器通讯的,过时命令,官方已经不推荐

**过程均可用**`docker logs details 容器ID或者name`来看到内部的情况

就是`shell`执行过程,比如这个项目就可以在初始化的时候,看到初始化的账号密码(成功)

不管是`mongo`还是`crper/yapi` ,当你请求一个容器不存在的时候,

会尝试往`dockhub`上面找,默认拉取镜像`latest`版本,找不到才会报错

以下就是基本的初始化信息

```
访问链接: 127.0.0.1:3000
默认的账户名: config.json =>  adminAccount 这个字段的值
密码: ymfe.org
```



参考文献:https://github.com/crper/yapi-docker