# JSP

## jsp注释

不同情况下使用注释的语法规则：

| **语法**       | 描述                                                 |
| :------------- | :--------------------------------------------------- |
| <%-- 注释 --%> | JSP注释，注释内容不会被发送至浏览器甚至不会被编译    |
| <!-- 注释 -->  | HTML注释，通过浏览器查看网页源代码时可以看见注释内容 |
| <\%            | 代表静态 <%常量                                      |
| %\>            | 代表静态 %> 常量                                     |
| \'             | 在属性中使用的单引号                                 |
| \"             | 在属性中使用的双引号                                 |

## JSP HTTP 状态码

| **状态码** | **消息**                      | **描述**                                                     |
| :--------- | :---------------------------- | :----------------------------------------------------------- |
| 100        | Continue                      | 只有一部分请求被服务器接收，但只要没被服务器拒绝，客户端就会延续这个请求 |
| 101        | Switching Protocols           | 服务器交换机协议                                             |
| 200        | OK                            | 请求被确认                                                   |
| 201        | Created                       | 请求时完整的，新的资源被创建                                 |
| 202        | Accepted                      | 请求被接受，但未处理完                                       |
| 203        | Non-authoritative Information |                                                              |
| 204        | No Content                    |                                                              |
| 205        | Reset Content                 |                                                              |
| 206        | Partial Content               |                                                              |
| 300        | Multiple Choices              | 一个超链接表，用户可以选择一个超链接并访问，最大支持5个超链接 |
| 301        | Moved Permanently             | 被请求的页面已经移动到了新的URL下                            |
| 302        | Found                         | 被请求的页面暂时性地移动到了新的URL下                        |
| 303        | See Other                     | 被请求的页面可以在一个不同的URL下找到                        |
| 304        | Not Modified                  |                                                              |
| 305        | Use Proxy                     |                                                              |
| 306        | *Unused*                      | 已经不再使用此状态码，但状态码被保留                         |
| 307        | Temporary Redirect            | 被请求的页面暂时性地移动到了新的URL下                        |
| 400        | Bad Request                   | 服务器无法识别请求                                           |
| 401        | Unauthorized                  | 被请求的页面需要用户名和密码                                 |
| 402        | Payment Required              | *目前还不能使用此状态码*                                     |
| 403        | Forbidden                     | 禁止访问所请求的页面                                         |
| 404        | Not Found                     | 服务器无法找到所请求的页面                                   |
| 405        | Method Not Allowed            | 请求中所指定的方法不被允许                                   |
| 406        | Not Acceptable                | 服务器只能创建一个客户端无法接受的响应                       |
| 407        | Proxy Authentication Required | 在请求被服务前必须认证一个代理服务器                         |
| 408        | Request Timeout               | 请求时间超过了服务器所能等待的时间，连接被断开               |
| 409        | Conflict                      | 请求有矛盾的地方                                             |
| 410        | Gone                          | 被请求的页面不再可用                                         |
| 411        | Length Required               | "Content-Length"没有被定义，服务器拒绝接受请求               |
| 412        | Precondition Failed           | 请求的前提条件被服务器评估为false                            |
| 413        | Request Entity Too Large      | 因为请求的实体太大，服务器拒绝接受请求                       |
| 414        | Request-url Too Long          | 服务器拒绝接受请求，因为URL太长。多出现在把"POST"请求转换为"GET"请求时所附带的大量查询信息 |
| 415        | Unsupported Media Type        | 服务器拒绝接受请求，因为媒体类型不被支持                     |
| 417        | Expectation Failed            |                                                              |
| 500        | Internal Server Error         | 请求不完整，服务器遇见了出乎意料的状况                       |
| 501        | Not Implemented               | 请求不完整，服务器不提供所需要的功能                         |
| 502        | Bad Gateway                   | 请求不完整，服务器从上游服务器接受了一个无效的响应           |
| 503        | Service Unavailable           | 请求不完整，服务器暂时重启或关闭                             |
| 504        | Gateway Timeout               | 网关超时                                                     |
| 505        | HTTP Version Not Supported    | 服务器不支持所指定的HTTP版本                                 |

## JSP 标准标签库（JSTL）

JSP标准标签库（JSTL）是一个JSP标签集合，它封装了JSP应用的通用核心功能。

JSTL支持通用的、结构化的任务，比如迭代，条件判断，XML文档操作，国际化标签，SQL标签。 除了这些，它还提供了一个框架来使用集成JSTL的自定义标签。

根据JSTL标签所提供的功能，可以将其分为5个类别。

- **核心标签**
- **格式化标签**
- **SQL 标签**
- **XML 标签**
- **JSTL 函数**



### 核心标签

> 核心标签是最常用的 JSTL标签。引用核心标签库的语法如下：

```
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
```

| 标签                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [<c:out>](https://www.runoob.com/jsp/jstl-core-out-tag.html) | 用于在JSP中显示数据，就像<%= ... >                           |
| [<c:set>](https://www.runoob.com/jsp/jstl-core-set-tag.html) | 用于保存数据                                                 |
| [<c:remove>](https://www.runoob.com/jsp/jstl-core-remove-tag.html) | 用于删除数据                                                 |
| [<c:catch>](https://www.runoob.com/jsp/jstl-core-catch-tag.html) | 用来处理产生错误的异常状况，并且将错误信息储存起来           |
| [<c:if>](https://www.runoob.com/jsp/jstl-core-if-tag.html)   | 与我们在一般程序中用的if一样                                 |
| [<c:choose>](https://www.runoob.com/jsp/jstl-core-choose-tag.html) | 本身只当做<c:when>和<c:otherwise>的父标签                    |
| [<c:when>](https://www.runoob.com/jsp/jstl-core-choose-tag.html) | <c:choose>的子标签，用来判断条件是否成立                     |
| [<c:otherwise>](https://www.runoob.com/jsp/jstl-core-choose-tag.html) | <c:choose>的子标签，接在<c:when>标签后，当<c:when>标签判断为false时被执行 |
| [<c:import>](https://www.runoob.com/jsp/jstl-core-import-tag.html) | 检索一个绝对或相对 URL，然后将其内容暴露给页面<br />打印指定页面的源代码 |
| [<c:forEach>](https://www.runoob.com/jsp/jstl-core-foreach-tag.html) | 基础迭代标签，接受多种集合类型                               |
| [<c:forTokens>](https://www.runoob.com/jsp/jstl-core-foreach-tag.html) | 根据指定的分隔符来分隔内容并迭代输出                         |
| [<c:param>](https://www.runoob.com/jsp/jstl-core-param-tag.html) | 用来给包含或重定向的页面传递参数                             |
| [<c:redirect>](https://www.runoob.com/jsp/jstl-core-redirect-tag.html) | 重定向至一个新的URL.                                         |
| [<c:url>](https://www.runoob.com/jsp/jstl-core-url-tag.html) | 使用可选的查询参数来创造一个URL                              |

### 格式化标签

> JSTL格式化标签用来格式化并输出文本、日期、时间、数字。引用格式化标签库的语法如下：

```
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>
```

| 标签                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [<fmt:formatNumber>](https://www.runoob.com/jsp/jstl-format-formatnumber-tag.html) | 使用指定的格式或精度格式化数字                               |
| [<fmt:parseNumber>](https://www.runoob.com/jsp/jstl-format-parsenumber-tag.html) | 解析一个代表着数字，货币或百分比的字符串                     |
| [<fmt:formatDate>](https://www.runoob.com/jsp/jstl-format-formatdate-tag.html) | 使用指定的风格或模式格式化日期和时间                         |
| [<fmt:parseDate>](https://www.runoob.com/jsp/jstl-format-parsedate-tag.html) | 解析一个代表着日期或时间的字符串                             |
| [<fmt:bundle>](https://www.runoob.com/jsp/jstl-format-bundle-tag.html) | 绑定资源                                                     |
| [<fmt:setLocale>](https://www.runoob.com/jsp/jstl-format-setlocale-tag.html) | 指定地区                                                     |
| [<fmt:setBundle>](https://www.runoob.com/jsp/jstl-format-setbundle-tag.html) | 绑定资源                                                     |
| [<fmt:timeZone>](https://www.runoob.com/jsp/jstl-format-timezone-tag.html) | 指定时区                                                     |
| [<fmt:setTimeZone>](https://www.runoob.com/jsp/jstl-format-settimezone-tag.html) | 指定时区                                                     |
| [<fmt:message>](https://www.runoob.com/jsp/jstl-format-message-tag.html) | 显示资源配置文件信息                                         |
| [<fmt:requestEncoding>](https://www.runoob.com/jsp/jstl-format-requestencoding-tag.html) | 设置request的字符编码<br />**指定返回给Web应用程序的表单编码类型** |

## JSTL函数

> JSTL包含一系列标准函数，大部分是通用的字符串处理函数。引用JSTL函数库的语法如下：

```
<%@ taglib prefix="fn"  uri="http://java.sun.com/jsp/jstl/functions" %>
```

| 函数                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [fn:contains()](https://www.runoob.com/jsp/jstl-function-contains.html) | 测试输入的字符串是否包含指定的子串(**大小写敏感**)           |
| [fn:containsIgnoreCase()](https://www.runoob.com/jsp/jstl-function-containsignoreCase.html) | 测试输入的字符串是否包含指定的子串(**大小写不敏感**)         |
| [fn:endsWith()](https://www.runoob.com/jsp/jstl-function-endswith.html) | 测试输入的字符串是否以指定的后缀结尾                         |
| [fn:escapeXml()](https://www.runoob.com/jsp/jstl-function-escapexml.html) | 跳过可以作为XML标记的字符                                    |
| [fn:indexOf()](https://www.runoob.com/jsp/jstl-function-indexof.html) | 返回指定字符串在输入字符串中出现的位置                       |
| [fn:join()](https://www.runoob.com/jsp/jstl-function-join.html) | 将数组中的元素合成一个字符串然后输出                         |
| [fn:length()](https://www.runoob.com/jsp/jstl-function-length.html) | 返回字符串长度<br />**返回字符串中指定开始和结束索引的子串** |
| [fn:replace()](https://www.runoob.com/jsp/jstl-function-replace.html) | 将输入字符串中指定的位置替换为指定的字符串然后返回           |
| [fn:split()](https://www.runoob.com/jsp/jstl-function-split.html) | 将字符串用指定的分隔符分隔然后组成一个子字符串数组并返回     |
| [fn:startsWith()](https://www.runoob.com/jsp/jstl-function-startswith.html) | 测试输入字符串是否以指定的前缀开始                           |
| [fn:substring()](https://www.runoob.com/jsp/jstl-function-substring.html) | 返回字符串的子集                                             |
| [fn:substringAfter()](https://www.runoob.com/jsp/jstl-function-substringafter.html) | 返回字符串在指定子串之后的子集                               |
| [fn:substringBefore()](https://www.runoob.com/jsp/jstl-function-substringbefore.html) | 返回字符串在指定子串之前的子集                               |
| [fn:toLowerCase()](https://www.runoob.com/jsp/jstl-function-tolowercase.html) | 将字符串中的字符转为小写                                     |
| [fn:toUpperCase()](https://www.runoob.com/jsp/jstl-function-touppercase.html) | 将字符串中的字符转为大写                                     |
| [fn:trim()](https://www.runoob.com/jsp/jstl-function-trim.html) | 移除首尾的空白符                                             |

## JSP 自定义标签

详情见runoob:[JSP 自定义标签](https://www.runoob.com/jsp/jsp-custom-tags.html)

