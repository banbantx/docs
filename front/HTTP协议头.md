# HTTP 协议头

## Cache-Control

> 该指令控制对request和response缓存，request header 中的设置并不意味着 response也具备

### 语法

+ 不区分大小写，推荐小写
+ 多个指令之间用逗号分隔
+ 一些指令有一些可选参数（标记或者带引号的字符串）

#### request directives

+ Cache-Control: max-age=\<seconds>
+ Cache-Control: max-stale[=\<seconds>]
+ Cache-Control: min-fresh=<seconds>
+ Cache-Control: no-cache
+ Cache-Control: no-store
+ Cache-Control: no-transform
+ Cache-Control: only-if-cached

#### response directives

+ Cache-Control: must-revalidate
+ Cache-Control: no-cache
+ Cache-Control: no-store
+ Cache-Control: no-transform
+ Cache-Control: public
+ Cache-Control: private
+ Cache-Control: proxy-revalidate
+ Cache-Control: max-age=<seconds>
+ Cache-Control: s-maxage=<seconds>

### 指令分类

#### 可缓存性
> 定义是否可缓存、缓存位置、是否在缓存前和源服务器进行验证

+ public