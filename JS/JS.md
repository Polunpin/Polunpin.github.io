# JS



## [window.localtion多种用法](https://www.cnblogs.com/lmxHome/p/10749911.html)

1. `设置或获取对象指定的文件名或路径:` window.location.pathname
2. `设置或获取整个 URL 为字符串:`window.location.href
3. `设置或获取与 URL 关联的端口号码:`window.location.port
4. `设置或获取 href 属性中在井号“#”后面的分段:`window.location.hash
5. `设置或获取 href 属性中跟在问号后面的部分:`window.location.search
6. `设置或获取 URL 的协议部分:`window.location.protocol

【举例】

```url
http://www.x2y2.com:80/fisker/post/0703/window.location.html?ver=1.0&id=6#imhere
```

```js
1.window.location.href
	整个URl字符串(在浏览器中就是完整的地址栏)
本例返回值: http://www.x2y2.com:80/fisker/post/0703/window.location.html?ver=1.0&id=6#imhere

2.window.location.protocol
URL 的协议部分
本例返回值:http:

3.window.location.host
URL 的主机部分
本例返回值:www.x2y2.com

4.window.location.port
URL 的端口部分
如果采用默认的80端口(update:即使添加了:80)，那么返回值并不是默认的80而是空字符
本例返回值:""

5.window.location.pathname
URL 的路径部分(就是文件地址)
本例返回值:/fisker/post/0703/window.location.html

6.window.location.search
查询(参数)部分
除了给动态语言赋值以外，我们同样可以给静态页面,并使用javascript来获得相信应的参数值
本例返回值:?ver=1.0&id=6

7.window.location.hash
锚点
本例返回值:#imhere
```