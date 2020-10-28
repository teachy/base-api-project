# bzzn-base-api-project

项目模板
克隆项目
对test包内的代码生成器CodeGenerator进行配置，主要是JDBC，因为要根据表名来生成代码
如果只是想根据上面的演示来亲自试试的话可以使用test resources目录下的demo-user.sql，否则忽略该步
输入表名，运行CodeGenerator.main()方法，生成基础代码（可能需要刷新项目目录才会出来）
根据业务在基础代码上进行扩展
对开发环境配置文件application-dev.properties进行配置，启动项目，Have Fun！  
开发建议

表名，建议使用小写，多个单词使用下划线拼接
Model内成员变量建议与表字段数量对应，如需扩展成员变量（比如连表查询）建议创建DTO，否则需在扩展的成员变量上加@Transient注解，详情见通用Mapper插件文档说明
建议业务失败直接使用ServiceException("message")抛出，由统一异常处理器来封装业务失败的响应结果，比如throw new ServiceException("该手机号已被注册")，会直接被封装为{"code":400,"message":"该手机号已被注册"}返回，无需自己处理，尽情抛出
需要工具类的话建议先从apache-commons-*和guava中找，实在没有再造轮子或引入类库，尽量精简项目
开发规范建议遵循阿里巴巴Java开发手册（最新版下载)
建议在公司内部使用[ShowDoc](https://github.com/star7th/showdoc)、[SpringFox-Swagger2](https://github.com/springfox/springfox) 、[RAP](https://github.com/thx/RAP)等开源项目来编写、管理API文档  
技术选型&文档

Spring Boot（[查看Spring Boot学习&使用指南](http://www.jianshu.com/p/1a9fd8936bd8)）
MyBatis（[查看官方中文文档](http://www.mybatis.org/mybatis-3/zh/index.html)）
MyBatisb通用Mapper插件（[查看官方中文文档](https://mapperhelper.github.io/docs/)）
MyBatis PageHelper分页插件（[查看官方中文文档](https://pagehelper.github.io/)）
Druid Spring Boot Starter（[查看官方中文文档](https://github.com/alibaba/druid/tree/master/druid-spring-boot-starter/)）
Fastjson（[查看官方中文文档](https://github.com/Alibaba/fastjson/wiki/%E9%A6%96%E9%A1%B5)）
其他略
