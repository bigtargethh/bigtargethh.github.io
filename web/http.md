http头认识
---
```

HTTP/1.1 200 OK
Server: bfe/1.0.8.18
Date: Sun, 24 Mar 2019 15:39:08 GMT
Content-Type: text/html
Content-Length: 277
Last-Modified: Mon, 13 Jun 2016 02:50:08 GMT
Connection: Keep-Alive
ETag: "575e1f60-115"
Cache-Control: private, no-cache, no-store, proxy-revalidate, no-transform
Pragma: no-cache
Accept-Ranges: bytes
```
200            响应状态码
Server         服务器名
Date           日期/时间
Content-Type   文档所属MIME类型
Content-Length 请求内容长度
Last-Modified  文档最后修改时间
Connection     是否需要持续连接
ETag           验证令牌，类似于token，类似于服务端与客户端进行匹配的值,缓存验证
Cache-Control  缓存控制，控制网页的缓存  private仅允许私有缓存(客户端缓存)，比如说换个浏览器你当前的缓存就没用了，no-cache响应不会被缓存，实时向服务端请求资源，no-store在任何条件下，所有内容都不会被缓存(缓存或者internet临时文件)，并且不会被写入到客户端,proxy-revalidate响应在特定条件会被重用，但是必须到服务端验证，no-transform禁止转码方式(当手机访问时不进行转码，百度会帮助用户进入mobile页面)
Pragma         缓存设置，no-cache 响应不会被缓存，实时向服务端请求资源
Accept-Ranges  请求实体的范围

例外
host           请求资源的地址
Referer        设置后仅允许请求URL的原资源地址，也可以是相对地址
User-Agent     用户信息：OS，浏览器信息
lcoation       重定向接收者到一个新的URL地址

```
建议使用http Header Live 火狐插件进行学习理解
```
响应状态码
1**   表示信息接收响应，并进行处理
2**   表示处理成功响应，表示执行操作被成功接收，执行          200响应成功
3**   表示重定向响应，为了完成请求操作，必须进行进一步处理     302重定向
4**   表示客户端错误，请求操作含语法错误或者不能被执行         404 请求资源不存在  400 客户端请求语法错误 401 请求未经允许 403 收到请求，但拒绝提供服务 
5**   表示服务端错误，服务器不能正确处理客户端正确的请求以及请求资源   500 服务器内部错误  503 服务器当前不能正确处理客户端请求，过段时间可能恢复正常。例如ST-052利用时，服务器响应该状态

```
http请求方式
```
1. GET       请求指定页面，返回请求实体内容
2. POST      请求服务器，POST方式将请求内容放入请求消息体内，GET是放入URL地址中(最大1024字节)
3. HEAD      与GET请求一致的响应，仅请求页面首部，相应中包含的元信息与GET响应相同，大部分软件做目录扫描时，使用该请求方式，例如御剑
4. PUT       从客户端向服务器传送的数据，可上传内容，比如IISput老兵(上传文件，小马)
5. DELETE    请求服务器删除指定资源
6. TRACE     请求服务器在响应中的实体主体部分并返回
7. CONNET    回显服务器收到的请求
8. OPTIONS   使用该方式进行测试服务器针对特定资源所支持的http请求方式，常用于不安全的http请求

```
http url
```
定义：统一资源符，包含查找某资源的足够的信息，http://host[':'port][path]（域名接管端口）,例如：http://www.cnblogs.com/dadawang/p/10426425.html

```
网站目录结构
```
按照功能或作用划分，更好的管理网站，也便于开发者结构化地开发

```
静态网站
```
全部由html页面组成，一般后缀htm,html,shtml等

```
动态网站
```
一般动态网站使用数据库进行架构，例如数据库内存着访问地址等，一般后缀jsp，asp,aspx,php等