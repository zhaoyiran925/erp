**项目说明** 
- 本项目为价格追踪系统里面的后台，采用基于spring-boot的renren-fast快速开发平台进行二次开发而成，负责与大数据端和前台交互以及存储数据
- 数据库采用mysql5.6
- 实现前后端分离，通过token进行数据交互，前端再也不用关注后端技术
- 引入quartz定时任务，可动态完成任务的添加、修改、删除、暂停、恢复及日志查看等功能
- 引入API模板，根据token作为登录令牌

<br>
 
**项目文件结构** 
```
renren-fast
├─db  项目SQL语句
│
├─common 公共模块
│  ├─aspect 系统日志
│  ├─exception 异常处理
│  ├─validator 后台校验
│  └─xss XSS过滤
│ 
├─config 配置信息
│ 
├─modules 功能模块,也是本项目二次开发的主要开发模块
│  ├─app API接口模块(APP端以及大数据端调用)
      ├─controller 实现通信接口的控制类
          ├─AppController 实现与App通信的功能
          ├─BigDataController 实现与大数据端通信的功能
          ├─ParentController AppController与ParentController的父类
          ├─AppTestController 测试类，用来测试接口通信以及一些方法
      ├─utils 工具类集合
          ├─JSONUtils JSON工具类，实现与JSON字符串有关的方法
          ├─JwtUtils token工具类，实现与token有关的方法
          ├─SetterUtils 工具类
      ...    
   ├─generator mybatis的数据类模块 
│  ├─job 定时任务模块
│  ├─oss 文件服务模块
│  └─sys 权限模块
│ 
├─RenrenApplication 项目启动类
│  
├──resources 
│  ├─mapper SQL对应的XML文件
|  ├─application.yml profile文件，保存系统运行总的的环境配置
...
│  └─static 静态资源

```
<br> 




**技术选型：** 
- 核心框架：Spring Boot 2.1
- 安全框架：Apache Shiro 1.4
- 视图框架：Spring MVC 5.0
- 持久层框架：MyBatis 3.3
- 定时器：Quartz 2.3
- 数据库连接池：Druid 1.0
- 日志管理：SLF4J 1.7、Log4j
<br> 


 **后端部署**
- 通过git下载源码
- idea、eclipse需安装lombok插件，不然会提示找不到entity的get set方法
- 创建数据库renren_fast，数据库编码为UTF-8
- 执行db/mysql.sql文件，初始化数据
- 修改application-dev.yml，更新MySQL账号和密码
- Eclipse、IDEA运行RenrenApplication.java，则可启动项目
- Swagger文档路径：http://localhost:8080/renren-fast/swagger/index.html
- Swagger注解路径：http://localhost:8080/renren-fast/swagger-ui.html

<br> 



