## Web论坛 Demo

> 该项目完整实现了 Web 论坛的基础功能，核心功能包括基于 MD5 盐值的注册、基于验证码的登录及登录状态检查、发表与评论帖子并定时计算权重；支持用户踩赞和热贴排行；支持通过关键词搜索及结果高亮显示；支持异步系统通知。

### 项目难点
* 对于点赞、关注等用户高频访问操作，使用 Redis 缓解 IO 压力
* 使用 Redis 存储登录凭证及验证码，解决分布式 session 问题；通过注册拦截器及自定义注解实现权限控制，保护特定资源
* 通过 Elasticsearch 实现全局搜索，提供关键词高亮显示功能
* 使用 Kafka 作为消息队列推送系统通知，通过事件驱动型的异步队列实现系统的解耦、削峰
* 利用 Redis + Caffeine 实现两级缓存，优化热贴访问；并使用 Quartz 实现任务调度，定时更新热帖权重 

### 项目收获：
* 对基于 Spring Boot 及 SSM 框架的开发流程有了更为清晰的理解
* 掌握了 Redis 的多种使用场景及基于 Kafka 等中间件的性能提升方案
* 实践了基于 Logback 的日志记录、基于 JUnit 的单元测试及基于 JMeter 的压力测试，拓展了个人技术边界