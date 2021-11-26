



# 01_Gateway：网关_API网关介绍



## 什么是网关

> API网关的作用就是吧各个服务对外提供的API汇集起来,让外界看起来是一个统一的接口

同时也可以在网关中 提供额外的功能

总结: 网关就是所有项目的一个统一的入口




## 网关组成

> 网关 =  路由转发 + 过滤器(编写额外功能)

### 2.1 路由转发

接收外界请求,通过网关的路由转发,转发到后端的服务器上

如果只有这一个功能看来和之前的学的nginx反向代理服务器很像,外界访问nginx,由nginx做负载均衡,后把请求转发到对应服务器上.

### 2.2 过滤器

网关非常重要的功能就是过滤器

过滤器中默认提供了25内置功能还自持额外的自定义功能.

> 傻瓜式攻击: 中国的一个帖子里这么写的: 中国的网民 咱们定好时间,一起访问一下日本的一个网站,内个网站直接就无了,因为中国的网民太多了,绝!

对于我们来说,比较常用的功能有网关的容错,限流以及请求相应的额外处理.



# 02_Gateway：网关_SpringCloud中的网关解决方案


## 3.1 Spring Cloud Netflix Zuul
属于Spring Cloud Netflix下一个组件，具有灵活、简单的特点。在早期Spring Cloud 中
使用的比较多。

其版本更新都依赖于Netflix Zuul

> 升级的版本不好合并,等问题

## 3.2 Spring Cloud Gateway

由Spring自己推出的网关产品，完全依赖Spring自家产品。符合Spring 战略意义，其
更新版本等都由Spring自己把控。

目前很多项目中都是使用Gateway替代Zuul.




# 03_Gateway：网关_Gateway简介

1. 简介

   1. SpringCloud Gateway是SpringCloud的二级子项目,提供了微服务网关功能

   2. 包含: 权限安全,监控/指标 等功能.

      > 让我们在开发中,不用考虑额外的反复重复流量,只需要考虑用户数量对应的流量级别

2. 名词解释

   1. 在学习Gateway时里面有一些名词需要提前了解,这对于或后面的学习是很有帮助的.

      Route

      Route中文车称为路由,Gateway里面的Route是主要学习内容,一个Gateway项目可以包含多个Route

      > 路由规则 校验 过滤 容错,
      >
      > 其中路由规则和校验 可以通过 **谓词** 来实现
      >
      > 校验 过滤 容错 可以通过 **过滤器**来实现

      一个路由 包含ID,URI,Predicate集合 , Filter集合

      在Route中ID是自定义的,URI就是一个地址.剩下的[Predicate](https://blog.colemak.cn/springcloud/SpringCloud.html#pridicate%E6%96%AD%E8%A8%80)和[Filter](https://blog.colemak.cn/springcloud/SpringCloud.html#filter%E8%BF%87%E6%BB%A4%E5%99%A8)学习明白了,Route就明白了

      2.2 Predicate

      中文: 谓词.

      谓词 时学习Gateway比较重要的一点,简单点理解谓词 就是一些附加条件和内容.

      2.3 Filter

      所有生效的Filter都是GatewayFilter的实例. 在Gateway运行过程中Filter负责在代理服务之前或之后去做一些事情

      


# 04_Gateway：网关_Gateway入门案例_自动路由映射

后面不写了,这个这个

ref: https://cloud.tencent.com/developer/article/1403887


# 05_Gateway：网关_Gateway_手工配置路由映射




# 06_Gateway：网关_Gateway_谓词




# 07_Gateway：网关_Gateway_过滤器




# 08_Gateway：网关_Gateway_限流算法介绍




# 09_Gateway：网关_Gateway_基于Redis实现令牌桶限流




# 10_Gateway：网关_Gateway_Hystrix容错处理




# 11_Gateway：网关_Gateway_自定义全局过滤器




# 12_Gateway：网关_Gateway_自定义路由过滤器