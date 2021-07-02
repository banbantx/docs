# HTTP 协议头
## Expires
> http1.0 绝对时间，客户端时间和缓存时间做对比，存在时区不同或单方时间不准确造成缓存失效。
## Cache-Control

> http1.1 该指令控制对request和response缓存，request header 中的设置并不意味着 response也具备

### 语法

+ 不区分大小写，推荐小写
+ 多个指令之间用逗号分隔
+ 一些指令有一些可选参数（标记或者带引号的字符串）

#### request directives

+ Cache-Control: max-age=\<seconds>
+ Cache-Control: max-stale[=\<seconds>]
+ Cache-Control: min-fresh=\<seconds>
+ Cache-Control: no-cache
+ Cache-Control: no-store
+ Cache-Control: no-transform
+ Cache-Control: only-if-cached

#### response directives

+ Cache-Control: no-store
+ Cache-Control: must-revalidate
+ Cache-Control: no-cache
+ Cache-Control: no-transform
+ Cache-Control: public
+ Cache-Control: private
+ Cache-Control: proxy-revalidate
+ Cache-Control: max-age=\<seconds>
+ Cache-Control: s-maxage=\<seconds>

### 指令分类

#### 可缓存性
> 定义是否可缓存、缓存位置、是否在缓存前和源服务器进行验证

+ pubic 响应能够任何缓存存储(即使响应是不可缓存)
+ private 只能被浏览器缓存(即使响应是不可缓存),如果你不想要缓存任何影响，使用no-store。这是指令在禁止缓存响应是无效的。
+ no-cache 响应可以被任何缓存存储(即使响应是不可缓存),但是存储的响应必须在使用前首先经过和服务器的验证。因此no-cache不能和immutable一起使用。如果你不想要缓存任何影响，使用no-store。这是指令在禁止缓存响应是无效的。
+ no-store 响应不会被任何缓存存储。注意，这不会阻止预先存在的有效返回响应，客户端可以设置max-age=0清除响应。当no-store被使用时，其他指令无效。

#### 过期时间
+ max-age=\<seconds> 资源刷新的最大时间。与Expires不同，该指令和请求的时间有关。
+ smax-age=\<seconds> 覆盖max-age或Expires,但是仅共享缓存有效（代理服务器缓存），被私有缓存忽略。
+